#### Name

Elodie - Base Windows 10 Pro Windows Setup

#### commandType

windows

#### Command

```
## Commands below within the @' '@
$64BitCommand = @'
## Install Hamachi
Import-Module BitsTransfer
Start-BitsTransfer -Source https://secure.logmein.com/hamachi.msi -Destination C:\temp\hamachi.msi
Start-Process msiexec.exe -Wait -ArgumentList '/I C:\temp\hamachi.msi /q'
'@

#------ Do not modify below this line ---------------
& (Join-Path ($PSHOME -replace 'syswow64', 'sysnative') powershell.exe) -Command "& {$64BitCommand}"
```

#### Description

This is a big script that does a bunch of stuff. Early development.

#### *Import This Command*

To import this command into your JumpCloud tenant run the below command using the [JumpCloud PowerShell Module](https://github.com/TheJumpCloud/support/wiki/Installing-the-JumpCloud-PowerShell-Module)

```
Import-JCCommand -URL 'https://github.com/ElodieGames/elodie-pc-provisioning/blob/main/JumpCloudCommands/BaseWindowsSetup.md'
```