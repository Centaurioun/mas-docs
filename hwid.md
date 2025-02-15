---
pagetitle: HWID Activation
---

# **HWID Activation**

------------------------------------------------------------------------

## Overview

-   How to use it? Please find the instructions [here](index.html#Download__How_to_use_it).

-   This activation is supported for Windows 10/11 only.

-   This activation does not store or modify/patch any files in your system.

-   This activation is a permanent activation for your system Hardware.

-   On a system, this activation can be created for all the supported editions, and all can be linked to Microsoft account without any issues.

-   Once a system is activated, this activation cannot be removed because the license is stored in the Microsoft servers and not in the user's system. MS checks the hardware ID (HWID) and if a license is found in their database, the system will automatically activate. This is how official digital license works.

-   Any significant changes in the Hardware (such as a motherboard) may deactivate the system. It is possible to reactivate a system that was deactivated because of significant hardware changes, IF your activation, was linked to an online Microsoft account.

-   For activation to succeed, internet connectivity must be enabled. If you are trying to activate without these conditions being met, then the system will auto-activate later when the conditions are met.

-   Auto activation scenario after the Windows re-install:

    -   The Internet is required. (Only at the time of activation)

    -   The system will auto-activate if Retail (Consumer) media was used for the installation.

    -   The system will NOT auto-activate if VL (Business) media was used for the installation. In this case, the user will have to insert that windows edition Retail/OEM key (find keys below on this page) to activate, if the user doesn't wish to activate again using this script.

------------------------------------------------------------------------

## How does it work?

-   In the official upgrade process from Windows 7 to Windows 10, Microsoft provides an HWID (digital license) activation for Windows 10 without any cost.

-   In the background, the upgrade process runs a file named gatherosstate.exe (available in Windows 10/11 ISO) and it checks the license of current Windows if found activated, it generates a valid GenuineTicket.xml **ticket** which is sent to Microsoft and in return, MS authorizes a license.

-   So if we just convince the gatherosstate.exe file that the conditions are met for ticket generation by fooling it, it will generate a valid ticket, which can be used to get the valid HWID (Digital license).

-   How to convince the gatherosstate.exe?\
    There are two methods for it.\
    \
    **1-** Place a [custom slc.dll](https://github.com/Gamers-Against-Weed/Integrated_Patcher_3) file beside gatherosstate.exe:\
    gatherosstate.exe uses the system's `C:\Windows\System32\slc.dll` file to gather the system's info. If we place a custom slc.dll file beside gatherosstate.exe which can send the rubbish data to it, then it will simply accept it and generate a valid ticket.\
    \
    **2-** [Modify](https://github.com/Gamers-Against-Weed/GamersOsState) the gatherosstate.exe file itself so that it doesn't check the system's activation status and can directly create a valid ticket.

-   **Notes:**

    -   To be clear, we are **not modifying/patching any on-board system file** to get digital license. Gatherosstate.exe is a part of ISO file and not available in C drive system files. System's slc.dll file is not touched, instead we use custom slc.dll only for a brief moment of ticket generation.
    -   If you want to understand more about how these above mentioned both methods then check this repo [MAS-Legacy-Methods](https://github.com/massgravel/MAS-Legacy-Methods)
    -   Latest MAS doesn't use any of these methods, instead it uses ready to use Universal tickets (check below for info).

------------------------------------------------------------------------

## Types of Tickets

There are many methods for ticket generation, majorly we can classify the ticket types in 3 categories.

1.  **Downlevel Ticket** - This is the simplest ticket generation process. In this method, ticket is signed by downlevel key by the system and the ticket's OSVersion is =\<10. If it's generated on Windows 10/11 then MS ideally aren't supposed to grant activation, however they do and method is continuously working from last 4-5 years. Almost every HWID activator (at the time of writing this) is based on this method.

2.  **Lockbox Ticket** - This is slightly a trickier method. The ticket is signed by Lockbox key by the system and the ticket's OSVersion is 10. This ticket generation process involves cleaning Clipsvc licenses and IdentityCRL registry key in the system. Due to some hiccups in the process, this method is not primarily used in MAS, however these are the types of tickets that are identical to the genuine ticket generated by system on activated Windows 10/11.

3.  **Universal Ticket** - In this method, we set the OSVersion =\<5 in the ticket and when we apply the ticket, system ignores the HWID in the ticket due to lower OSVersion and grant the activation anyway. This ticket can be applied on any system. These tickets can either be Downlevel or Lockbox type. MS ideally aren't supposed to grant activation, however they do.

Latest version of MAS is using Universal ticket method. Other ticket method scripts can be found in this repo [MAS-Legacy-Methods](https://github.com/massgravel/MAS-Legacy-Methods)

Now a question, can Microsoft block the new requests or revoke already established HWID license?

-   Revoking the license would be too extreme and will face many complications and risk of voiding valid licenses. However maybe they can block the new activation requests coming from Downlevel and Universal tickets. But the tools are working from 4-5 years and they don't seem to care much for consumer piracy; That's not where they get the most money from.

------------------------------------------------------------------------

## Supported Products

| Windows 10/11                    | Generic Retail/OEM/MAK Key      |
|:---------------------------------|:--------------------------------|
| Education                        | `YNMGQ-8RYV3-4PGQ3-C8XTP-7CFBY` |
| Education N                      | `84NGF-MHBT6-FXBX8-QWJK7-DRR8H` |
| Enterprise                       | `XGVPP-NMH47-7TTHJ-W3FW7-8HV2C` |
| Enterprise N                     | `3V6Q6-NQXCX-V8YXR-9QCYV-QPFCT` |
| Enterprise LTSB 2015             | `FWN7H-PF93Q-4GGP8-M8RF3-MDWWW` |
| Enterprise LTSB 2016             | `NK96Y-D9CD8-W44CQ-R8YTK-DYJWX` |
| Enterprise LTSC 2019             | `43TBQ-NH92J-XKTM7-KT3KK-P39PB` |
| Enterprise N LTSB 2015           | `NTX6B-BRYC2-K6786-F6MVQ-M7V2X` |
| Enterprise N LTSB 2016           | `2DBW3-N2PJG-MVHW3-G7TDK-9HKR4` |
| Home                             | `YTMG3-N6DKC-DKB77-7M9GH-8HVX7` |
| Home N                           | `4CPRK-NM3K3-X6XXQ-RXX86-WXCHW` |
| Home China                       | `N2434-X9D7W-8PF6X-8DV9T-8TYMD` |
| Home Single Language             | `BT79Q-G7N6G-PGBYW-4YWX6-6F4BT` |
| IoT Enterprise                   | `XQQYW-NFFMW-XJPBH-K8732-CKFFD` |
| IoT Enterprise LTSC 2021         | `QPM6N-7J2WJ-P88HH-P3YRH-YY74H` |
| IoT Enterprise LTSC Subscription | `J7NJW-V6KBM-CC8RW-Y29Y4-HQ2MJ` |
| Pro                              | `VK7JG-NPHTM-C97JM-9MPGT-3V66T` |
| Pro N                            | `2B87N-8KFHP-DKV6R-Y2C8J-PKCKT` |
| Pro Education                    | `8PTT6-RNW4C-6V7J2-C2D3X-MHBPB` |
| Pro Education N                  | `GJTYN-HDMQY-FRR76-HVGC7-QPF8P` |
| Pro for Workstations             | `DXG7C-N36C4-C4HTG-X4T3X-2YV77` |
| Pro N for Workstations           | `WYPNQ-8C467-V2W6J-TX4WX-WT2RQ` |
| S                                | `V3WVW-N2PV2-CGWC3-34QGF-VMJ2C` |
| S N                              | `NH9J3-68WK7-6FB93-4K3DF-DJ4F6` |
| SE                               | `K9VKN-3BGWV-Y624W-MCRMQ-BHDCD` |
| SE N                             | `KY7PN-VR6RX-83W6Y-6DDYQ-T6R4W` |
| Team                             | `XKCNC-J26Q9-KFHD2-FKTHY-KD72Y` |

**Notes:**

-   X86-X64 and ARM64 architecture systems are supported.

-   Any Evaluation version of Windows (i.e. 'EVAL' LTSB/C) cannot be activated.

-   IoTEnterpriseS (LTSC) 2021 key will be used to activate the unsupported EnterpriseS (LTSC) 2021 edition.

-   Windows Server does not support HWID activation.

-   ServerRdsh edition does not [officially](https://learn.microsoft.com/en-us/azure/virtual-desktop/windows-10-multisession-faq) support activation on non-azure systems.

------------------------------------------------------------------------

## How to remove HWID?

-   You can not remove it, same as you can not remove official Windows digital (HWID) license. Once a system is activated, this activation cannot be removed because the license is stored in the Microsoft servers and not in the user's system. MS checks the hardware ID (HWID) and if a license is found in their database, the system will automatically activate.

------------------------------------------------------------------------

## Command line Switches

-   Check [here](command_line_switches.html).

------------------------------------------------------------------------

## Manual Activation

This is for those who wants to perform manual activation. If you want a tool to do this for you then check [here](index.html).

We can divide the manual activation process into two parts.

### 1- From Ready-Made Ticket

-   Make sure the Internet is enabled.

-   Open Windows Powershell as administrator, and enter the following listed commands in the sequence in which they are given.

-   Enter the Key, (Replace `<key>` with the key from the above list) with the following command

`slmgr /ipk <key>`

-   Download Universal tickets from [here](https://www.box.com/index.php?rm=box_download_shared_file&shared_name=p9zvmu4tnogv4nkn01kpyvkndfzhhiv4&file_id=f_1171245497490) and extract the downloaded file.

-   Now enter below code in Powershell

`(Get-ItemProperty HKLM:\SYSTEM\CurrentControlSet\Control\ProductOptions).OSProductPfn`

-   This command will you show you some text like `Microsoft.Windows.48.X19-98841_8wekyb3d8bbwe`

-   You need to find the exact same name ticket file in the folder which you have extracted earlier.

-   Copy that ticket file and paste it in the below folder

    `C:\ProgramData\Microsoft\Windows\ClipSVC\GenuineTicket`

-   Now run below command in Powershell to apply the ticket

`clipup -v -o`

-   Activate Windows with the following command

`slmgr /ato`

-   Check Activation Status with the following command

`slmgr /xpr`

-   Done.

------------------------------------------------------------------------

### 2- From Scratch

In this process we will perform activation from scratch. This is based on Universal ticket method. Here we will create identical tickets which are used in MAS HWID script and activate the system with it.

-   Download file from the below official MS link and extract this .cab file.\
    <https://download.microsoft.com/download/9/A/E/9AE69DD5-BA93-44E0-864E-180F5E700AB4/adk/Installers/14f4df8a2a7fc82a4f415cf6a341415d.cab>

-   Find the file named `filf8377e82b29deadca67bc4858ed3fba9` and rename it as `gatherosstate.exe`

-   Make a folder named `Files` in C drive, `C:\Files` and copy the `gatherosstate.exe` file in that folder.

-   Make sure the Internet is enabled.

-   Open Windows Powershell as administrator, and enter the following listed commands in the sequence in which they are given.

-   Enter the Key, (Replace `<key>` with the key from the above list) with the following command

`slmgr /ipk <key>`

-   Copy the below code all at once and enter it in PowerShell to modify the `gatherosstate.exe` file. This code to modify the file is based on [GamersOsState](https://github.com/Gamers-Against-Weed/GamersOsState).

<!-- -->

    $bytes  = [System.IO.File]::ReadAllBytes("C:\Files\gatherosstate.exe")
    $bytes[320] = 0xf8
    $bytes[321] = 0xfb
    $bytes[322] = 0x05
    $bytes[324] = 0x03
    $bytes[13672] = 0x25
    $bytes[13674] = 0x73
    $bytes[13676] = 0x3b
    $bytes[13678] = 0x00
    $bytes[13680] = 0x00
    $bytes[13682] = 0x00
    $bytes[13684] = 0x00
    $bytes[32748] = 0xe9
    $bytes[32749] = 0x9e
    $bytes[32750] = 0x00
    $bytes[32751] = 0x00
    $bytes[32752] = 0x00
    $bytes[32894] = 0x8b
    $bytes[32895] = 0x44
    $bytes[32897] = 0x64
    $bytes[32898] = 0x85
    $bytes[32899] = 0xc0
    $bytes[32900] = 0x0f
    $bytes[32901] = 0x85
    $bytes[32902] = 0x1c
    $bytes[32903] = 0x02
    $bytes[32904] = 0x00
    $bytes[32906] = 0xe9
    $bytes[32907] = 0x3c
    $bytes[32908] = 0x01
    $bytes[32909] = 0x00
    $bytes[32910] = 0x00
    $bytes[32911] = 0x85
    $bytes[32912] = 0xdb
    $bytes[32913] = 0x75
    $bytes[32914] = 0xeb
    $bytes[32915] = 0xe9
    $bytes[32916] = 0x69
    $bytes[32917] = 0xff
    $bytes[32918] = 0xff
    $bytes[32919] = 0xff
    $bytes[33094] = 0xe9
    $bytes[33095] = 0x80
    $bytes[33096] = 0x00
    $bytes[33097] = 0x00
    $bytes[33098] = 0x00
    $bytes[33449] = 0x64
    $bytes[33576] = 0x8d
    $bytes[33577] = 0x54
    $bytes[33579] = 0x24
    $bytes[33580] = 0xe9
    $bytes[33581] = 0x55
    $bytes[33582] = 0x01
    $bytes[33583] = 0x00
    $bytes[33584] = 0x00
    $bytes[33978] = 0xc3
    $bytes[34189] = 0x59
    $bytes[34190] = 0xeb
    $bytes[34191] = 0x28
    $bytes[34238] = 0xe9
    $bytes[34239] = 0x4f
    $bytes[34240] = 0x00
    $bytes[34241] = 0x00
    $bytes[34242] = 0x00
    $bytes[34346] = 0x24
    $bytes[34376] = 0xeb
    $bytes[34377] = 0x63
    [System.IO.File]::WriteAllBytes("C:\Files\gatherosstatemodified.exe", $bytes)

-   Now right click on the file `gatherosstatemodified.exe` and goto properties and set the compatibility to Windows XP SP3.\
-   Now we need to generate the ticket, to do that, enter the below command.

<!-- -->

    $value = (Get-ItemProperty HKLM:\SYSTEM\CurrentControlSet\Control\ProductOptions).OSProductPfn

    C:\Files\gatherosstatemodified.exe /c Pfn=$value`;DownlevelGenuineState=1

-   A GenuineTicket.xml file should be created in the folder `C:\Files\` now let's apply it.

`clipup -v -o -altto C:\Files\`

-   Activate Windows with the following command

`slmgr /ato`

-   Check Activation Status with the following command

`slmgr /xpr`

-   Done.

**Notes:**

-   If the system is already activated then created ticket will be a Lockbox ticket and if not then it will be a Downlevel ticket.

-   To make the exact ticket used in MAS HWID script, make sure system is already activated and fix the time with below Powershell command and then initiate the ticket generation process as per above mentioned steps.\
    `$date=[datetime]"2022/10/11 12:00";while($true){set-date $date; start-sleep -milliseconds 10}`

------------------------------------------------------------------------

## Setup Preactivate

-   Check the Extract OEM option in the MAS `Extras` section if you want pre-activated Windows installation.

-   Further, read [here](oem-folder.html).

------------------------------------------------------------------------

## Troubleshooting

-   Check [here](troubleshoot.html).
