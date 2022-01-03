# 🎒Roady
Roady is an app which adds features to Drummer to make it easier to work with GitHub.

The key feature is continuous, automatic backup of your Drummer files to GitHub. 
This gives you the equivalent of a time machine for your outlines, complete with diffs.

You can also upload individual Drummer tabs to GitHub, which can be useful for sharing your code with others.

## To install the 🎒Roady menu
Follow these steps to copy the latest version of the  🎒Roady menu from GitHub into your Scripts menu file
1. <b>File </b>→<b> Open URL… </b>
1.  https://raw.githubusercontent.com/PostMonsterG/Roady/main/Roady.opml 
1. The OPML outline containing Roady's menu will open in a new tab.
1. Select the entire outline, i.e., the 🎒node that contains everything
1. Copy (⌘C)
1. <b>File </b>→<b> Special Files… </b>→<b> Scripts menu... </b>
1. Paste (⌘V) 

You should now have a new 🎒 menu. The backpack is just an emoji, you can name the menu anything you like, including "Roady".
You can uninstall Roady by deleting this entry in your scripts menu, or temporarily disable it by commenting it out. 

## To back up your files
Roady lets you use a GitHub repository to store a backup copy of your Drummer files. 
Each file is saved as a separate file, there is no zip archive. 
These are incremental backups, only those files modified or created since the last backup will be uploaded. 

#### Have these things ready before you continue
- GitHub account
- Private repository to save your backups into, e.g., <i>drummer-private-backups</i>
- Path to a folder in the repository, e.g., <i>mybackups</i>

#### To configure Roady and connect Drummer to GitHub
1. <b>🎒 </b>→<b> Preferences </b>→<b> Configure GitHub User Name… </b>
1. <b>🎒 </b>→<b> Preferences </b>→<b> Configure Backups Repository… </b>
1. <b>🎒 </b>→<b> Preferences </b>→<b> Configure Backups Path… </b>
1. <b>🎒 </b>→<b> Status </b>→<b> Connect to GitHub… </b>

#### To back up your files
1. <b>🎒 </b>→<b> Back Up Now </b>

Roady logs information to the console about the files it has uploaded. Look for the backpack emoji.


## To enable automatic backups
Roady will back up your files to GitHub each time you select the 🎒 → <b>Back Up Now</b> command. You can enable continuous, automatic, backups by copying this command into Drummer's scheduler under the <i>everyMinute</i> heading. 
1. <b>File </b>→<b> Special Files... </b>→<b> Scripts menu… </b>
1. Select the <b>Back Up Now</b> node 
1.  Copy (⌘C)
1.  <b>File </b>→<b> Special Files... </b>→<b> Scheduler… </b>
1.  Ensure there is a top-level, uncommented, node named <i>everyMinute</i>
1.  Paste (⌘V) the <b>Back Up Now</b> item under that heading

Roady logs information to the console about the files it has uploaded. Look for the backpack emoji.

## To upload a Drummer tab to GitHub
Roady lets you upload individual Drummer tabs to GitHub. This is separate from backups—it is for sharing your code with others. 
1.  <b>🎒 </b>→<b> Upload Current Tab… </b>

Roady  looks for header elements in the OPML to determine where to save the file and how it is processed. 
- <b>rd-repository</b>
Set this to the name of the GitHub repository you want to save the file into.
For example, "hello-world"

- <b>rd-path</b>
Set this to the path to the file, including the filename.  
For example, "directory/sub/file.opml"

- <b>rd-type</b>
Controls how the file is processed before uploading.

    - <b>opml</b>
The OPML file will be uploaded without processing

    - <b>text</b>
Suitable for Markdown, the text from the nodes of the outline will be included, but none of the indentation or OPML attributes

    - <b>indented</b>
Suitable for JavaScript, the text from the nodes of the outline will be included, with indentation per OPML indentation level

## What Roady does with your data 
- <i>Important: </i>Roady saves your files to GitHub. Roady cannot tell, and will not warn you, if you upload private files to a public repository.
- You install Roady by copying an outline of menu items into Drummer's scripts menu, and optionally, by copying the Back Up Now command into Drummer's scheduler. You can uninstall or disable Roady by removing or commenting-out these items.
- Roady stores settings and status information in your web browser's local storage. This remains after you remove Roady from your scripts menu and scheduler. Your web browser will have controls for managing this data.
- Roady treats GitHub as a write-only file system. It commits everything to the main branch, and does not understand revisions, history, or the difference between public and private repositories. Roady is not appropriate for use as a general-purpose client for GitHub. For details on what Roady can and cannot do, see Drummer's documentation.

## Notes
- Drummer is a scriptable outliner, created by Dave Winer, and hosted at `drummer.scripting.com`
- Roady is written in Drumkit, the scripting language for Drummer, which is based on JavaScript. The native file format for Drumkit is OPML.
- Roady was created by Gary Teter, who has a blog at `oldschool.scripting.com/PostMonsterG`, and is on Twitter `@PostMonsterG`
