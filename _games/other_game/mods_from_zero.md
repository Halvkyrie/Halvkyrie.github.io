---
layout: categoryindex
title:  "Other - Game 2 Electric Boogaloo"
categories: other
---
> I say from zero, but it does assume that you have the game installed, have *some* very basic understanding of operating windows, have an internet connection and a web browser, so on.

This was done using Windows 11, using the Steam version of the game, and using Visual Studio Code as text editor.

[7-Zip](https://www.7-zip.org/) is used for .zip, .rar, .7z archive viewing and extraction

[Visual Studio Code](<https://code.visualstudio.com/>) and [Notepad++](<https://notepad-plus-plus.org/>) are both great text editors with lots of nifty features like syntax highlighting for different file types, which can especially be relevant beyond this short guide, if you want to edit things like .xml and .json files for mods

The install process will vary a bit depending on the mod. This short guide is for the standard .ba2 archive mods, which is how most mods work. Some mods will have accompanying configuration files or additional install instructions, but those will usually build on top of the knowledge in this guide.

## 1: Locating your game install
This process can be done with more or less any program running on a windows computer.
For Steam, locating the game install can be done in a shorter process, but for the purpose of this guide, I will be using this method as it is mostly failproof.

* Open Task Manager
    * Such as by running `taskmgr`, searching for and opening "Task Manager" from the [Windows Start Menu](<https://support.microsoft.com/en-us/windows/open-the-start-menu-4ed57ad7-ed1f-3cc9-c9e4-f329822f5aeb#WindowsVersion=Windows_11>) or by pressing \[CTRL\]+\[SHIFT\]+\[ESC\]
* Launch the game and wait for it to get to the main menu
    * If you already have the game running, that is fine, just leave it running. no need to go to the main menu specifically
* Switch over to Task Manager with the game still running.
   * Such as by using the \[Alt\]+\[Tab\] Shortcut
* Search for the program name
    * Using the Search function at the top of the Task Manager window (In the Processes Tab, which you should be at by default), search for the program name, in this case "Fallout 76".
* Select and right click the game process, then select `Open file location` as shown in the screenshot below

## 2: Locating your game's .ini files and configuration folder
.ini files are commonly used for configuration of game settings and similar things. For mods with a .ba2 files, it is necessary to instruct the game to load them via the game's .ini files
Both Steam and Microsoft Store versions use the same folders for configuration, but they use different file names for the .ini files

* Open up the File Explorer, such as by running `explorer`, searching for an opening "File Explorer" from the Windows Start Menu, or by pressing \[Windows\]+\[E\]
* Navigate to your Windows User's Documents folder, then into the `My Games` folder, and finally into the `Fallout 76` Folders.
    * This can be done by entering `%USERPROFILE%\Documents\My Games\Fallout 76\` into the address bar of the File Explorer, or by pasting/writing it directly into the Windows Start Menu
* For Steam, confirm that the files `Fallout76.ini` and `Fallout76Prefs.ini` are present. For Microsoft Store, confirm that the files `Project76.ini` and `Project76Prefs.ini` are present. This means you're likely in the right place

## 3: Create the "Custom ini" file in your game's configuration folder
This refers specifically to a file named either `Fallout76Custom.ini` for Steam or `Project76Custom.ini` for Microsoft Store.
The Custom.ini file can provide additional parameters to the game that you otherwise cannot simply change in the game's settings, including loading .ba2 archives, which is necessary for most mods.
If this file is already present, you do not need to replace it or create a new one.

* Open your text editor, like VSCode, and create a new file.
    * In the bar at the top of VSCode, press File, then New **Text** File for simplicity. The "New File" option prompts you to select language. This isn't important for now.
* Save the file as either `Fallout76Custom.ini` or `Project76Custom.ini` into your game .ini folder, depending on game version
    * In the bar at the top of VSCode, press File, then Save As... 
    * Navigate to the folder as you did in step 2
    * Select "Save as type" and chose "ini"
    * Input `Fallout76Custom.ini` or `Project76Custom.ini` as file name
    * Select Save

## 4: Extract your mod .ba2 into the game's Data folder

* Open the game install folder that you located in step 1 in the File Explorer
* Navigate to the `Data` folder
* Copy/Extract the mod .ba2 file into the data folder
    * If the mod came in a .7z, .zip, .rar or similar file type, you can open this with 7-Zip, and Drag the file(s) from 7-Zip into the File Explorer window to extract it to the Data folder.
    * If the mod .7z etc archive came with additional files such as a .json file, this likely should also go in the Data folder alongside the .ba2 file. Read the mod install instructions to be sure!

## 5: Add the .ba2 archive to be loaded in your Custom.ini
This assumes the file is blank/empty. If the file is not empty and you wish to keep what is in it already, simply add the text to the bottom of the file
* Open whichever of `Fallout76Custom.ini` or `Project76Custom.ini` you created in step 3
    * If for whatever reason this file was already present and you did not create it following the guide, ensure that `[Archive]` and/or `sResourceArchive2List` is not present in the file.
    * If they are, delete them and their accompanying lines. If you don't do this you will have to instead add the archive name to the `sResourceArchive2List`.
* Add the following two lines (Can be Copy/Pasted):
```ini
[Archive]
sResourceArchive2List = 
```
> This is only necessary to do once
* Add the Mod's FULL .ba2 file name to `sResourceArchive2List`
    * This is only necessary for the .ba2 file. Any other file format, like .json or .xml should NOT be here
* To add additional mods, separate the file names by a comma and a space

Your `Fallout76Custom.ini` should look something like the below code box if you then have multiple mods to load
```ini
[Archive]
sResourceArchive2List = HUDEditor.ba2, perkloadoutmanager.ba2, cool_mod_name.ba2, another_cool_mod_filename.ba2
```

## 6: Disable or Uninstall a mod
* Remove the File name from your Custom.ini's `sResourceArchive2List`, to disable, and delete the file from your Data folder to remove it completely
