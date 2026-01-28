# READ THIS FIRST

This is a Xymon client for Windows written in PowerShell.

For more information about the Xymon Monitoring project, see:  
https://github.com/xymon-monitoring

## Source History

This code was originally hosted on SourceForge:  
https://sourceforge.net/p/xymon/code/HEAD/tree/sandbox/WinPSClient/

On **2026-01-27**, the code was copied to this repository.

This repository started with **version v2.42** of the Xymon client.

## Documentation

See https://github.com/xymon-monitoring/xymon-wiki/wiki#windows-powershell-client

## Roadmap

* ~~Convert XymonPSClient.doc to wiki pages~~
* Remove dependency for nssm.exe
* Remove file xymonsend.ps1: this is a standalone function with old code
* Remove xymon.ps1
    * Data can be send to the xymon server by creating a file in the tmp directory
    * This can also be used to download a file: is someone using this feature?
* Integrate multiple changes from Stef Coene
    * Download configuration files from Xymon Server
    * Allow overriding the user xml config file via environment variable
    * Make slowscanrate an option in the configuration file
    * Allow sendng of usermsg and trends messages
    * Allow multiple servers in serverUrl
    * Adding xymonlogarchive to config file to allow for keeping and rotating the logfles
    * Add a more flexiple scan option beside slowscan and everyscan
    * Test connection to xymon before upgrade
    * Allow multiple clientversion lines in configuration file
    * Add xymon: (like bb:) for location in configuration file

# Original README from sourceforge

## READ THIS FIRST

This is the original code copied for archival purposes from
https://sourceforge.net/p/xymon/code/HEAD/tree/sandbox/WinPSClient/

## What is this?

This is a Xymon monitoring client for Windows systems that have
the "Windows Powershell" scripting tool installed. This is
available for Windows 7, Windows Server 2008, Windows Server 2003
and Windows XP. If it is not installed on your system, it can 
be downloaded from the Microsoft website.

The client utility is completely written in Powershell, so no
additional programs need be installed to run it.

## Installation guide

Please see the installation instructions in XymonPSClient.doc.

## Client configuration

Please see the configuration instructions in XymonPSClient.doc.

## Talking to the Xymon Server

The "xymonsend.ps1" script contains a Powershell function "XymonSend"
that lets you communicate with the Xymon server in the same way that
the "bb" utility does on the Unix platforms. To use it, you must 
"source" this into your Powershell commandline window: At the "PS"
prompt, enter

	PS C:\xymon> . .\xymonsend.ps1

Note the initial "dot-space" on this line. This defines the function
"XymonSend" in your Powershell instance. You can now use it to talk to
the Xymon server - e.g. ping it (substitute your server name for "xymonhost")

	PS C:\xymon> xymonsend "ping" "xymonhost"
	hobbitd 4.3.0-1.3

You can use all of the normal commands when talking to the server,
e.g. to download a Xymon configuration file you can run

	PS C:\xymon> xymonsend "config bb-hosts" "xymonhost" >bb-hosts

and then you have a copy of the bb-hosts file.




