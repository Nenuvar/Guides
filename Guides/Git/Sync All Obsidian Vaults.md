## Create the script file

In you `/script`folder add your script file
```bash
nano sync-all.sh
```

Add this inside it (replace the paths with your actual script paths):
```bash

```

`#!/bin/bash  # Sync Test 1 vault bash ~/path/to/sync-test1.sh  # Sync Guides vault bash ~/path/to/sync-guides.sh`

3. **Make it executable**:
    

bash

CopyEdit

`chmod +x ~/sync-all.sh`

4. **Create an alias** (add this to your `~/.bashrc` or `~/.bash_aliases`):
    

bash

CopyEdit

`alias syncobsidian="bash ~/sync-all.sh"`

5. **Apply changes**:
    

bash

CopyEdit

`source ~/.bashrc`