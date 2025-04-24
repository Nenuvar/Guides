Guide: [[Sync Across Devices]]

Create and open your script file. Naming conventions should be `sync-[Obsidian Vault]-[OS].sh`

```bash
nano .sync-guides-windows.sh
```

Within your script file paste this:

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
