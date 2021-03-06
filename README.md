# IvantiAVInstall-2017
This repository contains an AutoIT script which, when properly configured, will enable the installation of BitDefender Antivirus for Ivanti's LANDesk Management Suite.

> Current Version: 1.1.0

## Instructions for use

> This guide assumes that you are operating through a CSA, and as such will rely on an intermediate workstation. If you are managing LANDesk from a LANDesk client, then you may use "workstation" and "client" interchangeably.

Before continuing, download and install [AutoIT and the SciTE editor](https://www.autoitscript.com/site/autoit/downloads/) on your workstation.

1. On your LANDesk core, Go to Agent Settings under Security>Ivanti Antivirus 2017 create and configure a new agent setting for Antivirus 2017.
2. Download the Ivanti AV package: Under Tools>Security and Compliance>Patch and Compliance, choose the Download Updates option, and after ensuring `BitDefender Antivirus Updates` is checked, click Download Now.
3. Fork this project into a working directory on your workstation.
4. Once the BitDefender AV Updates have finished downloading, navigate to `\\Your2017Core\ldlogon\avclientbd` and zip the contents of this folder into a self-extracting archive called `avclientbd.exe`. Place this archive in the same directory as the AutoIT script.
5. Open the AutoIT script in SciTE and configure the following two values:
```AutoIT
dim $architecture = "x86" ; Arch of the target device. Values: x86, x64
dim $silent = true ; Use true for unattended installs
```  
6. Build the AutoIT package and name the resulting .exe a name appropriate for the architecture version it is built for.
7. Upload this file to a web server or to the Core to allow clients to download the package.

## Changes and Bugs
Please feel free to submit Issues and PRs! AutoIT is not my primary language so I'm sure there are many improvements that can be made.
