Navigate to your Obsidian vault directory. 

Run the commands
````bash 
# Reset all local changes
git reset --hard

# Clean untracked files and folders (optional but safe for a full reset)
git clean -fd

# Pull the latest version from your remote (main branch assumed)
git fetch origin
git reset --hard origin/main
````
