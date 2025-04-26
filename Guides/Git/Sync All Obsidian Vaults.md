## Create the script file

In you `/script`folder add your script file
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
### Example

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
Replace the name of the script if it is different 

4. **Create an alias** (add this to your `~/.bashrc` or `~/.bash_aliases`):
    

bash

CopyEdit

`alias syncobsidian="bash ~/sync-all.sh"`

5. **Apply changes**:
    

bash

CopyEdit

`source ~/.bashrc`