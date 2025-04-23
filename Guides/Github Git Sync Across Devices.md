a **step-by-step guide** to set up reliable two-way syncing of your **Obsidian vault** between **Linux**, **GitHub**, and **Android**, using Git and SSH. This will make it easy to edit your vault on either device and sync the changes via GitHub.

---

## ✅ Requirements (you’ve likely done these already)

1. ✅ Git installed on both Linux and Android (e.g. via Termux or an app like MGit).
    
2. ✅ GitHub account with a repo you want to backup to. 
    
3. ✅ SSH key setup for **both** Linux and Android, with public keys added to your GitHub account.
    
4. ✅ Obsidian installed on both devices.
    

---

## 🌱 Linux - Initial Setup (One-Time)

### 1. Open Terminal and navigate to your vault

```
cd ~/Documents/Obsidian/Linux\ Sync
```
_(adjust path if needed)_
- TIP - If you go to your vault folder in your files explorer, right-click in the folder window and choose "open terminal here" in the menu
### 2. Initialize Git

If it’s not already a Git repo:
```
git init
```
### 3. Add your GitHub remote (SSH)

```
git remote add origin git@github.com:Nenuvar/L-A-Sync.git
git add .
git commit -m "Initial"
git push -u origin main
```
### 4. Create a `.gitignore` file
Use the command
```
nano .gitignore
```
In the editor paste this

```.gitignore
# ------------------------
# OS/System files
# ------------------------
.DS_Store
.trash
Thumbs.db
*.log
*.tmp
*.swp
*.bak
*~

# ------------------------
# Obsidian folders to ignore
# ------------------------
compendium/
rules/

# ------------------------
# Obsidian UI + device-specific files to ignore
# ------------------------
.obsidian/workspace.json
.obsidian/app.json
.obsidian/appearance.json
.obsidian/graph.json
.obsidian/workspace-mobile.json

# ------------------------
# Obsidian plugin-related files to track
# (Do NOT ignore these)
# .obsidian/core-plugins.json
# .obsidian/community-plugins.json
# .obsidian/hotkeys.json (optional)
# .obsidian/plugins/ (plugin configs)
# .obsidian/snippets/ (custom CSS)
# .obsidian/themes/ (if using custom themes)

# ------------------------
# Ignore plugin node_modules (if plugins are cloned manually)
# ------------------------
.obsidian/plugins/*/node_modules/
.obsidian/plugins/*/.obsidian-staging
```
`ctrl`+ `o`to write out, then `enter`. `ctrl` + `x` to save and exit

Commit and push the .gitignore file
```
git add .gitignore
git commit -m "Add .gitignore for Obsidian vault"
git push
```

#### Untrack .gitignore files
To delete the files that is already in your repo (and untrack them), do this
```
git rm -r --cached .
git add .
git commit -m "Apply .gitignore rules to existing repo"
git push
```

### Test your setup
Now you can test your setup. Create a file in Obsidian and do this:
```
git add .
git commit -m "Initial"
git push
```

In your repo there should only be one file in your .obsidian file: `core-plugins.json`
This confirms that the .gitignore file was setup correctly. 

---

## 📲 Android Setup

### Prerequisites:
	Your SSH key is already set up. 

### 1. Clone the GitHub repo

**Do not create a new Obsidian vault manually.** This you will do through the clone command:

On Android in Termux:

```
cd ~/storage/shared/Obsidian

git clone git@github.com:Nenuvar/name-of-your-github-repo.git "Obsidian-vault-on-Android"

```
Change the name of the Github repo to the one you used to connect to your Linux PC. Change the name of the Obsidian vault on Android to what you want your Android Vault to be named. 

> This creates an Obsidian vault named whatever you put inside **"Obsidian-vault-on-Android"** and links it to the same Github repo you used on your Linux PC.

### 2. Open in Obsidian app

- Open Obsidian → “Open folder as vault”
    
- Select the `Android Vault` folder
    

### 3. Give premissions
Go to your new vault directory (not the Obsidian directory). Add the premissions to push changes from here

```
git config --global --add safe.directory /storage/emulated/0/Documents/Obsidian/"name-of-your-vault"
```
The `"name of your vault"` should be in quotes. This is due to the command not recognising empty spaces or special characters like `&` in path names. 
### 4. Push your first Android change
In Obsidian add a new file or change an existing file. Run the commands: 

```
git add . 
git commit -m "Your commit message here" 
git push
```

The new changes should come up in the Github repo

---
## 🔁 Daily Workflow

### To pull the latest changes (do this first):
```
git pull
```
### To save your edits:
```
git add . 
git commit -m "Your commit message here" 
git push
```

---
## 💡 Pro Tips
- Use **consistent commit messages** like `edit from Android` or `notes from Linux`.
    
- Avoid working **simultaneously** on both devices without syncing first.
    
- If you hit a conflict, Git will let you know — you can resolve it by editing the file manually, committing again, and pushing.
    
- You CAN add folders or files to .gitignore file from gtihub. Then delete the folders or files from github before you pull again. The folders or files with then not sync anymore. 