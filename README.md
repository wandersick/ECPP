# Enhanced Command Prompt Portable (ECPP)

Based on Command Prompt Portable, ECPP enables PC enthusiasts, who bring a lot of portable utilities with them on a flash drive, to easily execute them by names or commands from a consolidated console without the need to remember where they are deep in the folder hierarchy.

## The Need to More Easily Execute Utilities within a Portable Collection

Do you use a lot of command line tools in your USB flash drive or cloud drive?

 ![](https://1.bp.blogspot.com/_Rn_IR-WNJ-M/Srgz4br9cYI/AAAAAAAAAQ8/m-C8_WNn28I/s1600/cmd1a.png "")

So, as an PC enthusiast, you probably have got a bunch of useful command line tools with you on the go. To use them, you first insert your USB flash drive (or establish cloud drive), start the command prompt on the target computer, navigate to your drive, then find out where your program is, `cd` to it and finally start it. However, you're always using them, and as the list of executables and subfolders grows, you start to wonder whether there's an easier way. Enhanced Command Prompt Portable (ECPP) to the rescue!

## List of Features

- Easily execute utilities within a portable collection by directly entering names or commands of the executables in Enhanced Command Prompt Portable (ECPP), eliminating the need to locate them or memorize where they are deep in the folder hierarchy
- Displays a list of command line executables and folders placed inside `CommandPromptPortable\Exe\` in the USB drive (or cloud drive)
- Top-most executables are listed as file1.exe, file2.bat; folders are listed as [Folder1], [Folder2]...
- PATH variable is automatically and dynamically updated on each run to detect new executables. (Alternatively, reload Command Prompt anytime by entering `commandprompt`)
- Only folders with executables are appended to PATH to save space (configurable)
- If utilities are grouped within folders, ECPP provides two subscripts, `DirC.bat` and `ListC.bat`, for listing executables in specified [folder(s)] to easily identify the names of the executables that can be run, e.g. `listc linux windows` (or `dirc linux windows`) would show all executables inside [linux] and [windows] folders
- Display a welcome message when ECPP is run
- Doesn't depend on a static location – portable usage or not – ECPP can be placed anywhere
- Enhances upon Command Prompt Portable from PortableApps.com
- Or, if no portability is demanded,  **merely replacing the Command Prompt**  is a valid use case as well!

## Concept of ECPP – Enhanced Command Prompt Portable

Command Prompt Portable is another portable software from PortableApps.com. It provides us with a command prompt we can customize the way we want. One of the most useful customization is setting PATH to whatever locations we need. We simply edit a batch file called commandprompt.bat inside `CommandPromptPortable\Data\Batch` and set PATH to e.g. `%~d0\[folder\_hierarchy]\Exe`, ... where we put our executables. `%~d0` will become the root of the USB drive (or cloud drive) automatically. Then we can use our commands right after we have opened Command Prompt Portable, no matter at which PC! So, instead of getting frustrated with the Command Prompt of a target computer, we can actually bring our own and have our settings on the go.

To go further, here's my customized take, known as Enhanced Command Prompt Portable (ECPP), with PStart as a launcher.

 ![](https://3.bp.blogspot.com/_Rn_IR-WNJ-M/Srg01CyEDZI/AAAAAAAAARk/JszJHWvT0J8/s1600/cmd2.png "")

(The screen shot shown is non-English but the downloadable version is in English)

## Available Utilities are Listed and Executable Eliminating the Need to Memorize Where They Are

For example, executables (.exe .bat .cmd .vbs...) put inside [CommandPromptPortable\Exe] folder are shown as file1.exe file2.bat, while folders are shown as [dir1], [dir2].

For me, I prefer to group my executables within folders as there're a lot of them. ECPP makes it such that as long as I remember the name of an executable inside any subfolder, I can type and run it without going into the sub-sub-subfolder. No more the need to edit the `commandprompt.bat` for each new folder. It achieves this by dynamically setting the PATH environmental variable to all subfolders that contain executables where ECPP command prompt is run each time.

An optional feature can be turned on so that only folders with executables inside will be appended to PATH, meaning PATH will be shorter, consuming less memory and searching faster if there are a lot of subfolders. However, the disadvantage is startup time being slower due to extra processing. To enable it, see `commandprompt.bat /?`.

The following illustrates the relationship between folders and PATH. Note the green line especially, while there are many folders inside UnxUtils, only [bin] and [wbin] are appended to PATH. That's because only those 2 folders contain executables.

 ![](https://3.bp.blogspot.com/_Rn_IR-WNJ-M/SqJNi3QTblI/AAAAAAAAANE/a1hdZkh478M/s1600/cmd3.png "")

## Listing Utilities within Subfolders

OK. Utilities in subfolders are all handled by PATH now, but what if I don't remember the name of an executable at all? Then I would first need to see what's inside subfolders using `Dirc.bat` or `Listc.bat` which are a part of ECPP.

This is a sample output of what's inside [Microsoft] and [PnP] folders – `listc Microsoft Pnp` (`listc` is now deprecated; please use `dirc` below)

 ![](https://2.bp.blogspot.com/_Rn_IR-WNJ-M/SqJNjdE8KQI/AAAAAAAAANM/H0-CmbskLm4/s1600/cmd4.png "")

Alternatively, in `dir /w` style using `Dirc.bat` – `dirc Microsoft Netcat`

By default, only executables (defined as .exe .bat .cmd .vbs...) are shown.

 ![](https://1.bp.blogspot.com/_Rn_IR-WNJ-M/SqJNjhDmjgI/AAAAAAAAANU/cceePGiL-qw/s1600/cmd5.png "")

## Getting Started

1. After downloading and extracting, put your executable files and folders into a folder named [Exe] (as shown in the below folder hierarchy of ECPP)
2. Run ECPP. Observe that the executable files and folders are listed
3. To find out what applications are inside sub-folders, query folder content using `dirc folder_name`
4. Execute your applications by entering the filenames directly without the need to first `cd` into sub-folders

```
  "Command Prompt Portable" (base folder)
       |  
       |  CommandPromptPortable.exe
       |  
       ├─── Data
       |     └─── Batch
       |           └─── commandprompt.bat
       |                dirc.bat
       |                listc.bat
       ├─── Exe
       |     ├─── addswap.exe... (example)
       |     |
       |     ├─── Microsoft (example)
       |     └─── UnxUtils (example)
       |           └───...  
       |                └───...  
```

- All scripts inside [Data\Batch] are ECPP customization
- The download includes ECPP and a few third-party open-source CLI utilities for demonstration.

## Release History

| Ver | Date | Update | MD5 |
| --- | --- | --- | --- |
| TBC | 20200704 | Information update | Refer to [GitHub Releases](https://github.com/wandersick/enhanced-command-prompt-portable/releases) |
| 1.2a | 20110105 | Fixes an issue where the last character in PATH is stripped | 5b234884461157d1b595dcfc6d6e2e22 |
| 1.2 | 20100103 | Coding consolidation | 0a57d4f1efc1152ccbb3eabd61032317 |
| 1.1 | 20090921 | Original release | 38d1bde4b9137fcf70d85f6033ec241c |
