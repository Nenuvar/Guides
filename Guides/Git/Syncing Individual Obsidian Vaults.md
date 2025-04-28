## The Script
Go to your home directory
### Place your Scripts in a Folder

Place your script somewhere consistent, like:
```bash
~/scripts/sync-guides-windows.sh
```

You can create this folder if it doesn’t exist:
```bash
mkdir -p ~/scripts
```

If you created the script file before the script folder, you can move it
```bash
mv /path/to/your/sync-guides-windows.sh ~/scripts/sync-guides-windows.sh
```

### Create the Script
Navigate to your `scripts` folder
Create and open your script file. Naming conventions should be `sync-[Obsidian Vault]-[OS].sh`

**Example Guides vault on Windows
```bash
nano sync-guides-windows.sh
```

Within your script file paste one of the versions below. Change these parts
- The vault directory should be the vault path on your device
	- if the vault directory contains spaces, it should just stay like that
- The commit message should reflect what OS you are pushing from
#### V1
```bash
#!/bin/bash

# Change this to the path of your Git repo
VAULT_DIR="//svgkomm.svgdrift.no/Users/sk5049835/Documents/Notater/Obsidian/Guides Windows"

echo "📁 Navigating to vault: $VAULT_DIR"
cd "$VAULT_DIR" || { echo "❌ Directory not found!"; exit 1; }

echo "🔍 Stashing any uncommitted changes..."
git stash

echo "⬇️ Pulling latest changes with rebase..."
git pull --rebase

echo "🎒 Reapplying stashed changes..."
git stash pop

echo "➕ Staging all changes..."
git add .

echo "📝 Committing changes..."
# Change the commit message to mirror the OS your are using
git commit -m "Git Sync Script from Windows" || echo "✅ Nothing to commit."

echo "📤 Pushing to GitHub..."
git push

echo "✅ Sync complete!"
```
Then save (`ctrl + o` and `enter` ) and exit (`ctrl + x` )

#### V2 (updated)

```bash
#!/bin/bash

# Set your vault directory
VAULT_DIR=~/"Documents/Obsidian/[name of Vault]"

# Set your commit message
COMMIT_MESSAGE="Sync from [OS]"

echo "📁 Navigating to vault: $VAULT_DIR"
cd "$VAULT_DIR" || { echo "❌ Failed to navigate to vault directory."; exit 1; }

# Stash any uncommitted changes (quiet if none)
echo "🔍 Stashing local changes (if any)..."
git stash push -u -q

# Pull latest changes with rebase
echo "⬇️ Pulling latest changes..."
git pull --rebase --quiet

# Apply any stashed changes
echo "🎒 Reapplying stashed changes..."
git stash pop -q || echo "ℹ️ No stash to apply."

# Stage all changes
echo "➕ Staging all changes..."
git add .

# Check if there are any staged changes
if git diff --cached --quiet; then
    echo "✅ No changes to commit!"
else
    # Commit and push
    echo "📝 Committing changes..."
    git commit -m "$COMMIT_MESSAGE" --quiet

    echo "📤 Pushing to GitHub..."
    git push --quiet
    echo "✅ Sync complete!"
fi
```


#### V3 (Pro)

```bash
#!/bin/bash

# --- Configuration ---
VAULT_DIR=~/"Documents/Obsidian/[name of Vault]"
COMMIT_MESSAGE="Sync from [OS]"

# --- Helpers ---
abort() {
    echo "❌ $1"
    exit 1
}

prompt_show() {
    read -p "👀 $1 (y/N): " response
    [[ "$response" == [yY] ]]
}

# --- Start Script ---
echo "📁 Navigating to vault: $VAULT_DIR"
cd "$VAULT_DIR" || abort "Failed to navigate to vault directory."

# Remember current HEAD before pull
BEFORE_PULL=$(git rev-parse HEAD)

# Stash uncommitted changes
echo "🔍 Stashing local changes (if any)..."
git stash push -u -q

# Pull latest changes with rebase
echo "⬇️ Pulling latest changes..."
if ! git pull --rebase --quiet; then
    abort "Git pull failed. Resolve conflicts manually!"
fi

# How many commits were pulled?
AFTER_PULL=$(git rev-parse HEAD)
PULLED_COMMITS=$(git rev-list --count "$BEFORE_PULL..$AFTER_PULL")

# Show pulled commits if wanted
if [[ "$PULLED_COMMITS" -gt 0 ]]; then
    if prompt_show "See what was pulled?"; then
        echo "🔍 Pulled commits:"
        git log "$BEFORE_PULL..$AFTER_PULL" --oneline
    fi
else
    echo "ℹ️ No new commits were pulled."
fi

# Reapply stashed changes
echo "🎒 Reapplying stashed changes..."
git stash pop -q || echo "ℹ️ No stash to apply."

# Stage changes
echo "➕ Staging all changes..."
git add .

# Commit and push if needed
if git diff --cached --quiet; then
    echo "✅ No local changes to commit!"
    PUSHED_COMMITS=0
else
    echo "📝 Committing changes..."
    git commit -m "$COMMIT_MESSAGE" --quiet

    echo "📤 Pushing to GitHub..."
    if ! git push --quiet; then
        abort "Git push failed!"
    fi
    PUSHED_COMMITS=1

    # Show pushed commit if wanted
    if prompt_show "See what was pushed?"; then
        echo "🔍 Last pushed commit:"
        git log origin/main --oneline -n 1
    fi
fi

# --- Final Summary ---
echo ""
echo "📋 Sync Summary:"
echo "   - Pulled commits: $PULLED_COMMITS"
echo "   - Pushed commits: $PUSHED_COMMITS"
echo "✅ Done!"
```

### Make the Script Executable

```bash
chmod +x ~/scripts/sync-guides-windows.sh
```

## Create the alias in `.bashrc`

Open your `.bashrc` file:
```bash
nano ~/.bashrc
```

Add the alias at the bottom of the file. The name convention should be `sync[Obsidian vault]`. This way it will be easier to remember 
```bash
alias syncguides="~/scripts/sync-guides-windows.sh"
```

Then save (`ctrl + o` and `enter` ) and exit (`ctrl + x` )

### Reload `.bashrc`

Apply the changes by reloading your terminal session (and therefore your `.bashrc` file):
```bash
source ~/.bashrc
```

### Test the alias

Now you should be able to run this command from anywhere in your terminal:
```bash
syncguides
```

This should now run your script and handle the Git sync process!