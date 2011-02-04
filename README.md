SYNOPSIS 
========
Automates the logic of sorting downloaded movie and tv torrents.

DESCRIPTION
===========
###Type:
	POWERSHELL 2.0									
###What:
	uTORRENT onComplete run program 	
###Author:
	ulf@flashback				

USAGE
======

###ADD THIS in uTorrent	

	> powershell.exe C:\PathToThisSCRIPT.ps1 -TORRENT_NAME '%N' -TORRENT_DIR '%D'	

###OR THIS if you want to read the output

	> powershell.exe C:\PathToThisSCRIPT.ps1 -noexit -TORRENT_NAME '%N' -TORRENT_DIR '%D'	

###IF you want to specify the Paths directly you can do

	> powershell.exe C:\PathToThisSCRIPT.ps1 -TORRENT_NAME '%N' -TORRENT_DIR '%D'-BASE_MOVIE_DIR "C:\PATH"

###IF you want to disable/enable loggin

	> powershell.exe C:\PathToThisSCRIPT.ps1 -TORRENT_NAME '%N' -TORRENT_DIR '%D'-LOGG "NO/YES"

###IF you want to alter the winRAR path

	> powershell.exe C:\PathToThisSCRIPT.ps1 -TORRENT_NAME '%N' -TORRENT_DIR '%D'-WINRAR "D:\PATH_TO_WINRAR"
	
###IF you want to turn off Unpacking

	> powershell.exe C:\PathToThisSCRIPT.ps1 -TORRENT_NAME '%N' -TORRENT_DIR '%D' -UNRAR "NO"
	
###To get more information about the PARAMS

	> powershell get-help .\PathTOScript.ps1 -detailed

TODO
=====
Tv Episodes that are DVDrips probebly has an IMDB link and not a TvRage link, wich means that the TV Show DVDrip is treated as a Movie. 
This should be fixed later somehow.

DEPENDENCIES
============
	bin\mklnk.exe (included)
	
	bin\taglib-sharp.dll(included)
	
	winRAR (not included)
	
	uTorrent (not included) 	
	
###Authors:
mklnk is Copyright (c) 2005-2006 Ross Smith II (http://smithii.com) All Rights Reserved
taglib-sharp.dll is Copyright (c) http://code.google.com/p/thelastripper/source/browse/trunk/taglib-sharp/taglib-sharp.dll?r=176


INFORMATION
===========
### Implementation
So, almost everybody run Windows 7 or Vista these days. If you do, Powershell is inlcuded and to test that
you have it installed, open a command promt run -> cmd) and type 

	powershell $psversiontable

####Output:

	C:\Windows\System32>powershell $psversiontable

	Name                           Value
	----                           -----
	PSVersion                      2.0


So, if this works, and PSVersion = 2.0 we are good to go.

###Then:

	Type> Get-ExecutionPolicy
	Output> Restricted

If the output says Restricted, it means that the default value is still set. Change this by doing

	Type> Set-ExecutionPolicy RemoteSigned
Read more here: http://technet.microsoft.com/en-us/library/ee176949.aspx

###Else:

####Goto 
	http://support.microsoft.com/kb/968929
####scroll to
	Windows Management Framework Core (WinRM 2.0 and Windows PowerShell 2.0)
Download for your windows version
####Install
###OR: 
Do a system update. It should be included.

LINKS
====
###Github:
	https://github.com/mline/uTorrentSorter
###Screencasts:
####How it operates
	http://www.swfcabin.com/open/1296763224
	http://www.swfcabin.com/open/1296814280
####How to set Execution Policy
	http://www.swfcabin.com/open/1296731645	
