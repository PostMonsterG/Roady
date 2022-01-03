# 🎒 Roady
Roady adds features to Drummer to make it easier to work with GitHub.

The key feature is continuous, automatic backup of your Drummer files to GitHub. 
This gives you the equivalent of a time machine for your outlines, complete with diffs.

You can also upload individual Drummer files to GitHub, which can be useful for sharing your outlines with others.

Roady is currently at version 0.1.0, which means it is brand new.

## To install the 🎒 Roady menu
Follow these steps to copy the latest version of the  🎒 Roady menu from GitHub into your Scripts menu file
1. File → Open URL…  `https://raw.githubusercontent.com/PostMonsterG/Roady/main/Roady.opml`
2. Select the entire outline, i.e., the 🎒 node that contains everything
3. Copy (⌘C)
4. File → Special Files… → Scripts menu... 
5. Paste (⌘V) 

You should now have a new 🎒 menu. The backpack is just an emoji, you can name the menu anything you like, including "Roady".
You can uninstall Roady by deleting this entry in your scripts menu, or temporarily disable it by commenting it out. 

## To back up your files
Roady lets you use a GitHub repository to store a backup copy of your Drummer files. 
Each file is saved as a separate file, there is no zip archive. 
These are incremental backups, only those files modified or created since the last backup will be uploaded. 

#### Have these things ready before you continue
- GitHub account username
- Private repository to save your backups into, e.g., `drummer-private-backups`
- Path to a folder in the repository, e.g., `mybackups`

#### To configure Roady and connect Drummer to GitHub
1. 🎒→ Preferences → Configure GitHub Username… 
2. 🎒→ Preferences → Configure Backups Repository… 
3. 🎒→ Preferences → Configure Backups Path… 
4. 🎒→ Status → Connect to GitHub… 

#### To back up your files
1. 🎒→ Back Up Now 

Roady logs information to the console about the files it has uploaded. Look for the backpack emoji.

## To enable automatic backups
Roady will back up your files to GitHub each time you select the 🎒→ <b>Back Up Now</b> command. You can enable automatic backups by copying this command into Drummer's scheduler. 
1. File → Special Files... → Scripts menu… 
2. Select the <b>Back Up Now</b> node 
3.  Copy (⌘C)
4.  File → Special Files... → Scheduler… 
5.  Ensure there is a top-level, uncommented, node named `everyMinute`
6.  Paste (⌘V) the <b>Back Up Now</b> item under that heading

You can turn off automatic backups by deleting this item from Drummer's scheduler, or temporarily disable them by commenting it out.
Roady logs information to the console about the files it has uploaded. Look for the backpack emoji.

## To restore your files
Roady does not have any special features for restoring files from GitHub. For now, do this by hand.

## To upload a Drummer file to GitHub
Roady lets you upload individual Drummer files to GitHub. This is a separate thing from backups—it is for sharing your outlines with others. 
1.  🎒→ Upload Current Tab… 

Roady  looks for header elements in the OPML to determine where to save the file and how it is processed. 
- `rd-repository`
Set this to the name of the GitHub repository you want to save the file into.
For example, `hello-world`

- `rd-path`
Set this to the path to the file, including the filename.  
For example, `directory/sub/file.opml`

- `rd-type`
Controls how the file is processed before uploading.

    - `opml`
The OPML file will be uploaded without processing

    - `text`
Suitable for Markdown, the text from the nodes of the outline will be included, but none of the indentation or OPML attributes

    - `indented`
Suitable for JavaScript, the text from the nodes of the outline will be included, with indentation per OPML indentation level

## What Roady does with your data 
- <i>Important: </i>Roady uploads your files to GitHub. Roady cannot tell, and will not warn you, if you upload private files to a public repository.
- You install Roady by copying an outline of menu items into Drummer's scripts menu, and optionally, by copying the 🎒→ <b>Back Up Now</b> command into Drummer's scheduler. You can uninstall or disable Roady by removing or commenting-out these items.
- Roady stores settings and status information in your web browser's local storage. This remains after you remove Roady from your scripts menu and scheduler. Your web browser will have controls for managing this data.
- Roady treats GitHub as a write-only file system. It commits everything to the main branch, and does not understand revisions, history, or the difference between public and private repositories. Roady is not appropriate for use as a general-purpose client for GitHub.

## Notes
- Drummer is a scriptable outliner, created by Dave Winer, and hosted at http://drummer.scripting.com
- Roady is written in Drumkit, the scripting language for Drummer, which is based on JavaScript. The native file format for Drumkit is OPML.
- Roady was created by Gary Teter, who has a blog at http://oldschool.scripting.com/PostMonsterG and is on Twitter `@PostMonsterG`.
