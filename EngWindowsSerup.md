#### Name

ElodieEngWin10ProSetup

#### commandType

windows

#### Command

```
## Commands below within the @' '@
$64BitCommand = @'
## Import Modules
Import-Module BitsTransfer

## Setup setup directory for downloads...
New-Item -ItemType Directory -Force -Path C:\temp

## Install Visual Studio 
Start-BitsTransfer -Source https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2019# -Destination C:\temp\vs_community.exe
Invoke-Expression vs_community.exe -q --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NativeDesktop --add Microsoft.VisualStudio.Workload.NativeMobile --add Microsoft.VisualStudio.Workload.NativeGame

## Install Kleopatra/gpg4win
Start-BitsTransfer -Source https://elodie-desktop-artifacts.s3-us-west-1.amazonaws.com/provisioning/gpg4win-3.1.15.exe -Destination C:\temp\gpg4win-3.1.15.exe
Invoke-Expression gpg4win-3.1.15.exe /S

## Install things with choco
choco install git -y
choco install microsoft-windows-terminal -y
choco install docker-desktop -y
choco install keybase -y
choco install github-desktop -y
choco install bloomrpc -y


## Delete setup directory cause we no longer need it...
Remove-Item 'C:\temp' -Recurse
'@

#------ Do not modify below this line ---------------
& (Join-Path ($PSHOME -replace 'syswow64', 'sysnative') powershell.exe) -Command "& {$64BitCommand}"
```

#### Description

This is a big script that does a bunch of stuff. Early development.

#### *Import This Command*

To import this command into your JumpCloud tenant run the below command using the [JumpCloud PowerShell Module](https://github.com/TheJumpCloud/support/wiki/Installing-the-JumpCloud-PowerShell-Module)

```
Import-JCCommand -URL 'https://git.io/JG31d'
```
