# Install
## Use JBang to run the tool
[Tutorial](https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/alternateRun.md#use-jbang)

Install JBang using this command:
```Bash
curl -Ls https://sh.jbang.dev | bash -s - app setup
```

Try running `j! version` to verify the install. This should get you the version number

## Install the pre-built release of ttrpg-convert-cli

Use the command
```bash
jbang app install --name ttrpg-convert --force --fresh https://github.com/ebullient/ttrpg-convert-cli/releases/download/3.0.3/ttrpg-convert-cli-3.0.3-runner.jar
```
Copy the command from [the Github](https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/alternateRun.md#use-jbang), this way you will always have the right version number
	🔹 Feel free to use an alternate alias by replacing the value specified as the name. For example, for the snapshot, you can use `--name ttrpg-convert-ss`, allowing you to keep both versions available. You will need to adjust commands accordingly.

Verify the install by running the command:
```bash
ttrpg-convert --help
```

## Setup before conversion

### Download the Latest Release of TTRPG-Convert-CLI
You can find the latest release here:
	[https://github.com/ebullient/ttrpg-convert-cli/releases](https://github.com/ebullient/ttrpg-convert-cli/releases)  
Find the latest release and scroll down to the section titled Assets. This is a list of files included in this release.

This will get you a .zip file

### Create A Home for TTRPG-Convert-CLI 

Create a folder where the CLI is going to live.  
I have put mine in `/home/nenuvar/Documents/D&D/TTRPG CLI/`

Inside this folder you need to extract the contents of the *.zip we downloaded in the step above. The result should look like this:

![[Pasted image 20250418133946.png]]
### Install Git (if you havent already)

Git is an application that allows you to control Github using Command Prompts. It's a pre-requisite for the next steps in the process.

Download Git from this site and complete the install. [https://git-scm.com/downloads](https://git-scm.com/downloads)

### Download The Content You Intend To Use 

#### D&D 5e Tools

Open the folder you made above and navigate to the `bin` folder. Right-click within the folder and click `Open Terminal here`. This is important because the next process must be run from the folder where you want to download the site with the 5etools you want to use. 

Paste this into the Terminal:

```
git clone --depth 1 https://github.com/5etools-mirror-3/5etools-src
```

Press Enter to commence the process.

![explorer_mk6sSKsefH.gif](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/explorer_mk6sSKsefH.gif)

Wait for the process to complete. Basically the process is downloading a copy of the 5eTools site onto your machine.
##### Folder for Template Examples
If you cannot see a folder in your bin directory called `examples`, you'll need to download this for the config file to run correctly.
Go to [Ebullient's main github](https://github.com/ebullient/ttrpg-convert-cli/tree/main) and download the entire code. Within the `.zip` find the folder called `examples` and copy this to your `/bin` folder. Your `bin` folder should now look like this (maybe except the `dm` folder)
![[Pasted image 20250419200104.png]]
#### D&D 5e Images
Repeat the same process as above. But this time paste this command. 

```
git clone --depth 1 https://github.com/5etools-mirror-3/5etools-img
```
This command will download a copy of the images to your machine. This is a much larger download and may take quite a bit of time if you have a slow internet connection.

### Create Your Config File 

==Configuration Files are now a requirement for using the CLI tool.==

Create a new Text Document in your BIN folder and rename it to 

`config.5e.json`

Paste the following into that file and save it.

```
{
    "sources": {
        "adventure": [
            "WBtW",
            "LoX"
        ],
        "book": [
            "PHB",
            "DMG",
            "MM"
        ],
        "reference": [
            "SCREEN",
            "LMoP"
        ]
    },
    "paths": {
        "rules": "/CLI/",
        "compendium": "/CLI/"
    },
    "images": {
    "copyInternal": true,
    "copyExternal": true,
    "internalRoot": "5etools-img"
    },
    "reprintBehavior": "newest",
    "useDiceRoller": false,
    "tagPrefix": "ttrpg-cli",
    "template": {
        "background": "examples/templates/tools5e/images-background2md.txt",
        "monster": "examples/templates/tools5e/monster2md-yamlStatblock-body.txt",
        "item" : "examples/templates/tools5e/images-item2md.txt",
        "race" : "examples/templates/tools5e/images-race2md.txt",
        "spell" : "examples/templates/tools5e/images-spell2md.txt"
    }
}
```

#### Common Issue - File Type
Make sure you actually change the file type to a json file! Lots of people have common file extensions hidden in Windows and many people have incorrectly renamed the file to `config.5e.easy.json.txt` which causes the process to fail. 

It should look like this:
![Pasted image 20250127185945.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127185945.png)

#### Understanding the Config File 
You can find excellent documentation on the config file here: [https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/configuration.md](https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/configuration.md)  
The documentation covers a lot more than I do and is recommended reading for all users of the CLI tool.

##### Adding The Content You Own 
The content available through this process is documented in the [Source Map](https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/sourceMap.md)  
To add content you own, lookup the content in the [Source Map](https://github.com/ebullient/ttrpg-convert-cli/blob/main/docs/sourceMap.md) and take note of the Type field.  
Copy the Abbreviation for the content into the correct Type section in the config file.

Take note of the structure of this information. The commas are important. You need a comma at the end of every line except the last one in each grouping.

![Pasted image 20250127192339.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127192339.png)

Here's an example where I have added additional content. Note there is no comma on the end of each section but all content codes above the end; do have a comma. The tool will fail if you have incorrect syntax.

![Pasted image 20250127192650.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127192650.png)

##### Set The Home Vault Location 
This is where you can define the folder where the CLI will go in your vault. You set the location in your config file, and then copy the notes into this location in your vault.  
This is very important. **DO NOT MOVE THE CLI CONTENT FROM THIS LOCATION**  
If you want to change the location where the notes go, you need to update your config and re-run the process. This will recreate all of the notes and update the links accordingly.

![Pasted image 20250127193015.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127193015.png)
##### How Will Images Be Handled? 
This section defines how images are handled.

- if copyInternal is set to true, it will use images from the internalRoot setting. The setting in the internalRoot needs to match the name of the folder we created above that contains the images.
- If copyExternal is set to true, it will download any images that are not available locally. Homebrew content commonly stores images in lots of different places so you will need to set this to true if you are using Homebrew content.

![Pasted image 20250127193359.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127193359.png)

##### Dice Roller? 
My personal preference is to not use Dice Roller in my statblocks. I've found it to be buggy and I don't like that it changes the HP of my monsters everytime I access the note.
##### Templates 

Out of the box, the CLI tool comes with a variety of templates that can be used to change the way the notes look when created.  
By default, monsters are created as standard Markdown notes. This means they do not use the [Fantasy Statblocks](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/Fantasy+Statblocks) plugin. Most people I encounter though, wish to use [Fantasy Statblocks](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/Fantasy+Statblocks) and as such they need to change the default template that is used to create monsters.

We do this in the config file by selecting the template that has `yamlStatblock-body` in the name. In the Template section you need to define the name of the templates you wish to use for each category you wish to control. The path in the config file needs to match what you have in your bin folder exactly.

![Pasted image 20250127193739.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127193739.png)

![explorer_yQHZOxKrtB.gif](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/explorer_yQHZOxKrtB.gif)

The example config provided above will create monsters that use the [Fantasy Statblocks](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/Fantasy+Statblocks) plugin.

|Format|Template Name|Pros|Cons|
|---|---|---|---|
|Markdown|object2md-yamlStatblock-body.txt|Very usable  <br>Less system intensive  <br>Can be published||
|Fantasy Statblocks|monster2md-yamlStatblock-body.txt|Very pretty  <br>Cannot be published  <br>Includes buttons to trigger comat in Initiative Tracker|More system intensive|
|||||

There are options to store the monster content in the header or body of the note. I personally find the header takes up too much space in the Properties of the note and thus recommend the body version.

There are templates for different item types. For now, just know that they are there. It is possible to change them, but that's a tutorial for a later time.
## Convert 5eTools JSON data

By now, your `bin` folder should look like this. If it doesn't; go back up and repeat the process to see what you are missing.

![Pasted image 20250127200029.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127200029.png)
### Run The CLI 

Navigate to the `bin` folder and open your terminal here. 

Now you need to run this command and hit `Enter`
```bash
ttrpg-convert   --index   -o dm   "/home/nenuvar/Documents/D&D/TTRPG CLI/bin/5etools-src/data"
```
What the command does
	`--index` tells it to create an index of all the converted content.
	`-o dm` is the directory where the converted files will end up. 
	`"/home/nenuvar/Documents/D&D/TTRPG CLI/bin/5etools-src/data"` the input directory with 5etools JSON files.
Replace the path in " " with the path to your `5etools-src/data` folder. 
	**TIP**
		You can easily find that path by navigating to the folder in your file explorer, right-clickin within the folder and open the terminal from there. 
		In the terminal, write `pwd` and copy that path. 


Wait for the process to complete.

#### Run with the Config file
After the initial run of the tool, the json files have been generated. Now you can run it again with your config file
```bash
ttrpg-convert  --index  -o dm  -c config.5e.json "/home/nenuvar/Documents/D&D/TTRPG CLI/bin/5etools-src/data/"
```
Replace the `config.5e.json` with whatever name your config file has.
	TIP
		You can have several config files, you just need to call the right one when running the CLI
#### What's Happening?
The CLI process is now running. It is converting the site you downloaded above into Markdown format and putting the notes in a new folder called `dm`.

You can tell the process is complete when the command link prompt displays the folder path again. It should provide a summary of the notes that have been created. The created notes will be in the folder called `dm`.

![explorer_TKCo3WSMM0.gif](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/explorer_TKCo3WSMM0.gif)

## Common Errors 

**Error parsing configuration file (config.5e.easy.json): Unexpected character ('"' (code 34)): was expecting comma to separate Object entries**

- There is an error in your config file. Go back through and make sure the Syntax is correct. Are you missing a comma or perhaps have an extra one?

![Pasted image 20250127214151.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127214151.png)

- This is a rare error but indicates that your PC is not compatible with the Windows CLI process. If you see this you will need to try a different process such as the Java JAR process. You can find instructions for other methods [HERE](https://github.com/ebullient/ttrpg-convert-cli). The screenshot above shows the error. The JAR file has then been downloaded per the JAR process and the command is then run using the variation shown in the screenshot.
## Extras

### Install the Templates 

Templates can be used to change the output of the CLI tool. I don't recommend changing these until you get more comfortable with the process. However if you want to use the [Fantasy Statblocks](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/Fantasy+Statblocks) plugin; you will need to change the default template to the one that supports Fantasy Statblocks.

Navigate to the ttrpg-convert-cli release page: [https://github.com/ebullient/ttrpg-convert-cli/releases/](https://github.com/ebullient/ttrpg-convert-cli/releases/)  
Download the examples file.

![Pasted image 20250127191445.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127191445.png)

Export the *.zip file into your BIN folder. It should look like this.
![Pasted image 20250127191649.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020250127191649.png)


### Homebrew Content 

The CLI process also supports a bunch of homebrew content. This is content developed by 3rd party providers.

See [TTRPG-Convert-CLI Homebrew Content](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/TTRPG-Convert-CLI/TTRPG-Convert-CLI+Homebrew+Content) for instructions.


# Add to Obsidian
## Copy The Files Into Your Vault 

Once the process is complete you can find the files inside the `dm` folder.  
You can now Copy and Paste these into your Obsidian vault.

**IMPORTANT:** The folder and files MUST be pasted into your Parent Vault Folder. 

`Do not put them into a sub-folder. Do not rename them. Do not move them.`

If you do not like the location of the notes within your vault you will need to modify the directory you want them in; in the config file. You should consider the CLI notes as **Read Only**. You will more than likely want to refresh these notes as some point, like when you purchase a new book; and therefore any manual changes you make, would be lost in the refresh process.

![explorer_Fhscj150b5.gif](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/explorer_Fhscj150b5.gif)

You can now restart your Obsidian Vault. Obsidian will likely need some time to `Index` the new files.

![Pasted image 20230820101035.png](https://publish-01.obsidian.md/access/36b98e212e9d73fe1bd4813f96b0fd71/z_Assets/Pasted%20image%2020230820101035.png)

## Setup Your Vault 
The notes are designed to use some additional elements such as plugins and `.css` files. Work through the steps below to ensure your vault is setup to use the new notes.

### ITS Theme
Download the ITS Theme and Style Settings
### Admonitions 
Install the [Admonitions Plugin](obsidian://show-plugin?id=obsidian-admonition). This plugin will enable some of the notes to display as intended.  
Now download the Admonition json files that you would like to use.

[admonitions-5e.json](https://github.com/ebullient/ttrpg-convert-cli/tree/main/examples/admonitions) for 5e tools  
[other-admonitions.json](https://github.com/ebullient/ttrpg-convert-cli/tree/main/examples/admonitions) some additional css files that may be of interest.

Save these files to your computer and then install them into the Admonitions plugin.  
`Obsidian > Settings > Community Plugins > Admonition > Options > Import Admonition(s) > Select Downloaded JSON file`
### Fantasy Statblocks 
Some of the CLI templates use the [Fantasy Statblocks](obsidian://show-plugin?id=obsidian-5e-statblocks) plugin so install that and then configure it.

Obsidian > Settings > Fantasy Statblocks > Note Parsing > Automatically Parse Frontmatter for Creatures = Enabled  
Obsidian > Settings > Fantasy Statblocks > Note Parsing > Bestiary Folder = Your CLI Folder

**Note:** We define the CLI folder here so that it limits where the plugin will search for new monsters. This will speed up the time it takes to start Obsidian. If you leave it with just `/` it will scan your whole vault everytime Obsidian starts.
### Initiative Tracker (Optional) 
Some of the CLI templates use the [Initiative Tracker](obsidian://show-plugin?id=initiative-tracker) plugin so install that.

Obsidian > Settings > Initiative Tracker > Plugin Integrations > Sync Monsters from TTRPG Statblocks = Enabled
### Install CSS Snippets 
These snippets are optional but can improve the way the notes look.

Check inside this folder:  
`bin\examples\css-snippets`

And you should find a number of *.css files. Copy the ones you would like to use into your vault and then enable them ([How To - Install Custom CSS](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Tutorials/Basic+Tool+Usage/How+To+-+Install+Custom+CSS)) from `Obsidian > Settings > Appearance > CSS Snippets > Enable`

`Vault\.obsidian\snippets\<copy here>`
# Update
## Updating the CLI Data
You will likely want to re-run the CLI tool at some point. The instructions below can be used to update the data so you can re-run the process.
#### Update The 5eT Data 
Navigate to your `bin/5etools-src` folder. Open the folder location in the Terminal
Type: `git pull` and press `enter`. 
This will update to the latest release. 

#### Update The 5eT Images 
Navigate to your `bin/5etools-img` folder. Open the folder location in the Terminal
Type: `git pull` and press enter. 
This will update to the latest release.

#### Update the CLI Executable 
Navigate to the [ttrpg-convert-cli/releases](https://github.com/ebullient/ttrpg-convert-cli/releases) page and check for the latest release (do not use the Pre-release unless you know what you are doing). Download the latest release (ttrpg-convert-cli-X.X.X-linux-x86_64.zip).  
Export the downloaded zip file and copy the `ttrpg-convert` into your `bin` folder. This will override the old version.

#### Make Changes To Your Config File 
Assuming the reason you want to re-run the process is there's a new book you would like to add to your vault; don't forget to add the book to your config file.
#### Rerun the CLI 
Go back to Run the CLI above (or [TTRPG-Convert-CLI 5e > Are You Ready?](https://obsidianttrpgtutorials.com/Obsidian+TTRPG+Tutorials/Plugin+Tutorials/TTRPG-Convert-CLI/TTRPG-Convert-CLI+5e#Are%20You%20Ready?)) and re-run the CLI command.