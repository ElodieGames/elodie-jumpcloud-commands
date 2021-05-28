#### Name

ElodieWin10ProSetup

#### commandType

windows

#### Command

```
## Commands below within the @' '@
$64BitCommand = @'
## Setup setup directory for downloads...
New-Item -ItemType Directory -Force -Path C:\temp
## Install Hamachi...
Import-Module BitsTransfer
Start-BitsTransfer -Source https://secure.logmein.com/hamachi.msi -Destination C:\temp\hamachi.msi
Start-Process msiexec.exe -Wait -ArgumentList '/I C:\temp\hamachi.msi /q'
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