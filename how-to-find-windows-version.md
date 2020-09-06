# How to Determine the Windows Version, Build or Edition of  Windows ISO, DVD or USB.

## Problem:
You have an .ISO file, DVD or an USB drive with booteable windows 10 image and need to know the Windows Version, Edition.

## Solution:

1. Mount the ISO file to Windows, or attach the Windows Media (USB or DVD) and notice the drive letter in Windows Explorer. (e.g. "X:")

2. Open Windows Explorer and explore the contents of "sources" directory, to see if it contains a file named "install.wim" or a file named "install.esd"

3. 

### Case A. 
If an "install.wim" file exists under the "sources" folder, then open an elevated command prompt (Command Prompt as Administrator) and give the following command to find the Windows version, Edition and Build of the ISO/DVD/USB:

```bash
dism /Get-WimInfo /WimFile:X:\sources\install.wim /index:1
```

After the execution of the above command, you should see on your screen all the information that you 're looking for.

*Notes:*  
1. Change the drive letter "X" according your case.  
2. The Windows 10 Build number, can be retrieved from the "Created" date field (e.g. If the created date is: 7/10/2015 then the build number is the "1507" = Year & Month of Windows 10 release) or by searching the version number (e.g. "10.0.1563") at Wikipedia's Windows 10 version history article.  
3. If you want to find out, if the Windows ISO, USB or DVD image contains contains multiple Windows versions of Windows, just give the above command without the "/Index:1" switch* or change the “/index:1” to “/index:2” or “/index:2”  or “/index:3” or “/index:4”  

### Case B. 
If an "install.esd" file exists under the "X:\Sources" folder, then open an elevated command prompt and give the following command to find the Windows version, Edition and Build of the ISO/DVD/USB file: *

```bash
    dism /Get-WimInfo /WimFile:D:\sources\install.esd /index:1
```
*Notes:*
1. The Windows 10 Build number, can be retrieved from the "Created" date field (e.g. If the created date is: 3/19/2017 then the build number is the "1703" = Year & Month of Windows 10 release) or by searching the version number (e.g. "10.0.1563") at Wikipedia's Windows 10 version history article.
2. If you want to find out, if the Windows ISO, DVD or USB contains contains multiple versions of Windows, just give the above command without the "/Index:1" switch or change the “/index:1” to “/index:2” or “/index:2”  or “/index:3” or “/index:4”


*Additional help:*  
If you receive the 'Error 11' or the 'Error 87', after executing the above "dism /Get-WimInfo" command, then probably you wrote wrong the command or you run the command in an older Operating System (e.g. Windows 7) for a newer Windows 'Install.WIM' or 'Install.ESD' file. (e.g. Windows 10).


Source:  
<https://www.wintips.org/how-to-find-windows-10-version-edition-build-from-windows-iso-dvd-usb/>

