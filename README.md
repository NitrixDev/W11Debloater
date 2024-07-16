## Windows11Debloater
Script/Utility/Application to debloat Windows 10, to remove Windows pre-installed unnecessary applications, stop some telemetry functions, stop Cortana from being used as your Search Index, disable unnecessary scheduled tasks, and more...

## Disclaimer
WARNING: I do NOT take responsibility for what may happen to your system! Run scripts at your own risk! Also, other variants of this repo are not technically "new" versions of this, but they are different in their own respective ways. There are some sites saying that other projects are "new" versions of this, but that is inaccurate.

How To Run the Windows11Debloater.ps1 and the Windows11DebloaterGUI.ps1 files
There are different methods of running the PowerShell script. The methods are as follows:

## First Method
Download the .zip file on the main page of the GitHub and extract the .zip file to your desired location
Once extracted, open Requiments as Administrator
Enable PowerShell execution Set-ExecutionPolicy Unrestricted -Force
On the prompt, change to the directory where you extracted the files:   e.g. - cd c:\temp
Next, to run either script, enter in the following:   e.g. - .\Windows10DebloaterGUI.ps1

## Second Method
Download the .zip file on the main page of the GitHub and extract the .zip file to your desired location
Right-click the PowerShell file that you'd like to run and click on "Run With PowerShell"
This will allow the script to run without having to do the above steps but Powershell will ask if you're sure you want to run this script.
Remember this script NEEDS to be run as admin in order to function properly.

## How To Run the Windows11SysPrepDebloater.ps1 file
For the WindowsSysPrepDebloater.ps1 file, there are a couple of parameters that you can run so that you can specify which functions are used. The parameters are: -SysPrep, -Debloat and -Privacy.

## To run this with parameters, do the following:

Download the .zip file on the main page of the GitHub and extract the .zip file to your desired location
Once extracted, open PowerShell (or PowerShell ISE) as an Administrator
On the prompt, change to the directory where you extracted the files:   e.g. - cd c:\temp
Next, to run either script, enter in the following:
e.g. - .\Windows11SysPrepDebloater.ps1 -Sysprep -Debloat -Privacy

#Sysprep, Interactive, and GUI Application
There are now 3 versions of Windows11Debloater - There is an interactive version, a GUI app version, and a pure silent version.

Windows11SysPrepDebloater.ps1 -> The silent version now utilizes the switch parameters: -Sysprep, -Debloat -Privacy. The silent version can be useful for deploying MDT Images/sysprepping or any other way you deploy Windows 10. This will work to remove the bloatware during the deployment process.

Windows11Debloater.ps1 -> This interactive version is what it implies - a Windows11Debloater script with interactive prompts. This one should not be used for deployments that require a silent script with optional parameters. This script gives you choices with prompts as it runs so that you can make the choices of what the script does.

Windows11DebloaterGUI.ps1 -> There is now a GUI Application named Windows11DebloaterGUI.ps1 with buttons to perform all of the functions that the scripts do. This is better for the average user who does not want to work with code, or if you'd prefer to just see an application screen.

## Switch Parameters
There are 3 switch parameters in the Windows11SysPrepDebloater.ps1 script.

-SysPrep, which runs the command within a function: get-appxpackage | remove-appxpackage. This is useful since some administrators need that command to run first in order for machines to be able to properly provision the apps for removal.

-Debloat, switch parameter which does as it suggests. It runs the following functions: Start-Debloat, Remove-Keys, and Protect-Privacy. Remove-Keys removes registry keys leftover that are associated with the bloatware apps listed above, but not removed during the Start-Debloat function.

-Privacy, adds and/or changes registry keys to stop some telemetry functions, stops Cortana from being used as your Search Index, disables "unnecessary" scheduled tasks, and more.

This script will remove the bloatware from Windows 11 when using Remove-AppXPackage/Remove-AppXProvisionedPackage, and then delete specific registry keys that are were not removed beforehand. For best results, this script should be run before a user profile is configured, otherwise, you will likely see that apps that should have been removed will remain, and if they are removed you will find broken tiles on the start menu.

## These registry keys are
EclipseManager, ActiproSoftwareLLC, Microsoft.PPIProjection, Microsoft.XboxGameCallableUI

You can choose to either 'Debloat' or 'Revert'. Depending on your choice, either one will run specific code to either debloat your Windows 10 machine.

## The Debloat switch choice runs the following functions
Debloat, Remove-Keys, Protect-Privacy, Stop-EdgePDF (If chosen)

## The Revert switch choice runs the following functions
Revert-Changes, Enable-EdgePDF

The Revert option reinstalls the bloatware and changes your registry keys back to default.

## The scheduled tasks that are disabled are
XblGameSaveTaskLogon, XblGameSaveTask, Consolidator, UsbCeip, DmClient

These scheduled tasks that are disabled have absolutely no impact on the function of the OS.

## Bloatware that is removed
3DBuilder, ActiproSoftware, Alarms, Appconnector, Asphalt8, Autodesk SketchBook, MSN Money, Food And Drink, Health And Fitness, Microsoft News, MSN Sports, MSN Travel, MSN Weather, BioEnrollment, Windows Camera, CandyCrush, CandyCrushSoda, Caesars Slots Free Casino, ContactSupport, CyberLink MediaSuite Essentials, DrawboardPDF, Duolingo, EclipseManager, Facebook, FarmVille 2 Country Escape, Flipboard, Fresh Paint, Get started, iHeartRadio, King apps, Maps, March of Empires, Messaging, Microsoft Office Hub, Microsoft Solitaire Collection, Microsoft Sticky Notes, Minecraft, Netflix, Network Speed Test, NYT Crossword, Office Sway, OneNote, OneConnect, Pandora, People, Phone, Phototastic Collage, PicsArt-PhotoStudio, PowerBI, Royal Revolt 2, Shazam, Skype for Desktop, SoundRecorder, TuneInRadio, Twitter, Windows communications apps, Windows Feedback, Windows Feedback Hub, Windows Reading List, XboxApp, Xbox Game CallableUI, Xbox Identity Provider, Zune Music, Zune Video.

## Allowlist and Blocklist
There may be some confusion, but when using the Allowlist/Blocklist, the checkmark means it is on the blocklist, and that it will be removed.
