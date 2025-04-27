## Create the script file

In you `/scripts`folder add your script file
```bash
nano sync-all.sh
```

Add this inside the script (replace the paths with your actual script paths):
```bash
#!/bin/bash

# Sync Obsidian Vault [name]
bash ~/scripts/[your-script].sh

# Sync Obsidian Vault [name]
bash ~/scripts/[your-script].sh
```
### Example - Linux

```bash
#!/bin/bash

# Sync Obsidian Vault Test 1
bash ~/scripts/sync-test1-linux.sh

# Sync Obsidian Vault Guides
bash ~/scripts/sync-guides-linux.sh
```
## Make the Script Executable
Run this command: 
```bash
chmod ~/scripts/sync-all.sh
```
Replace the name of the script if it is different.

## Create the Alias

**Create an alias.** Add this to your `~/.bashrc`:
```bash
alias syncall="bash ~/scripts/sync-all.sh"
```
The alias can be whatever you like.
Keep the script name the same as in the last step. 

## Apply the Changes

```bash
source ~/.bash
```
This restarts your terminal session, resetting the `.bashrc` file. 