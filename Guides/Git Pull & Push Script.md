Create a new file in your home directory.
`nano git_sync.sh`

In the editor paste this code 

```bash
#!/bin/bash

# Change this to the path of your Git repo
VAULT_DIR="$HOME/git/obsidian-vault"

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
git commit -m "Safe sync from Android" || echo "✅ Nothing to commit."

echo "📤 Pushing to GitHub..."
git push

echo "✅ Sync complete!"
```


##### TIP!
Your Obsidian Vault directory on Android is:
`/data/data/com.termux/files/home/storage/shared/Documents/Obsidian/"Obsidian Vault on Android"`

