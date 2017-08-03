# CAPolicySQLDump
Takes PolicyID and PolicyName from every file in the PasswordManager_info safe and INSERT INTO capolicies table in mssql to cols caPolicyID and caPlatformName.

## Pre-Requisites
* This PowerShell script is unsigned and may throw warnings from PowerShell.
    * To prevent this, run `Set-ExecutionPolicy Unrestricted` in an elevated PowerShell console window.
* `git clone https://github.com/psPete/PoShPACLI.git` into `C:\Windows\system32\WindowsPowerShell\v1.0\Modules`
    * This will add the [PoShPACLI](https://github.com/psPete/PoShPACLI) PowerShell Module for PACLI into the proper directory. 
* Install CyberArk PACLI into `C:\PACLI` on the local machine this script is run from.
    * If you install to a different location, please update the variable in the .ps1 file.
* Create a user.ini credential file to be used for authentication to prevent passing plaintext passwords. (See [Troubleshooting](#troubleshooting) section for help.)
    * Browse into CreateCredFile directory.
    * Shift+Right Click in whitespace in the directory, select `Open command window here`. (May need to run in escalated cmd prompt.)
    * `CreateCredFile.exe user.ini Password` (If user.ini already exists in the directory, add a number to the end. i.e. `user2.ini`)
    * Enter username and password and all default values and user.ini will be created in the directory CreateCredFile.exe ran from.

## Usage
* Edit `Settings.xml` and set the parameters to your specifications.
* Open PowerShell Console, browse to directory the .ps1 is at and `.\CAPolicySQLDump.ps1`

## Troubleshooting
* If CreateCredFile included with this repository does not work, use the CreateCredFile located on your CPM Server at `{Drive}:\Program Files (x86)\CyberArk\Password Manager\Vault`.

## Support
Please update the [Issues](https://github.com/infamousjoeg/CAPolicySQLDump/issues) on this repo for support.

## License
[MIT](https://github.com/infamousjoeg/CAPolicySQLDump/blob/master/LICENSE)
