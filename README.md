tmng-setup-tools
================

A small library of utility functions designed to setup necessary development
tools for the TMNG team at T-Mobile. This package should be installed in the
node modules folder located in the root of the project folder (where the .git folder is located).
It determines the packages to install from the "globals" field in the package.json in the project root.

It was designed to be largely idempotent. That is, after the the system is properly configured,
no new modifications will be made. However, it was also developed to keep user dependencies up to
date. For this reason, it should be run regularly. When newer packages become available and the user
has an older compatible version of a package, the user can choose to ignore an update.

It was also developed to work on Windows, OSX, and Linux. It has been tested on Windows 7, Windows 10,
OSX 10.11 (El Capitan), and Ubunto 16.04 and 17.04.

## Installation

  npm install tmng-setup-tools --save

## Usage
  install ruby, required gems, java, maven, and all aem dependencies
  ```sh
  node -e "require('tmng-setup-tools').installEverything()"
  ```

  install maven and configure environment variables
  ```sh
  node -e "require('tmng-setup-tools').installMaven()"
  ```

  *download and install all required aem dependencies
  ```sh
  node -e "require('tmng-setup-tools').installAem()"
  ```

  install ruby and configure environment variables
  ```sh
  node -e "require('tmng-setup-tools').installRuby()"
  ```


### Important Notes

**Note:** In order to install most packages, users will need to have admin access on their computer.

**Note:** Users running Windows must have powershell script execution enabled. Powershell script execution
is disabled by default as a security feature on many windows distributions. Script execution policy
must either be set to "remotesigned" or "unrestricted", although it is recommended to set the
policy to "remotesigned" to maintain the highest level of security.

**Note:**  To view the current powershell execution policy for windows, copy and paste the following command in
a command prompt:  powershell.exe -command "get-executionpolicy"

**Note:**  To view the set the powershell execution policy for windows, copy and paste the following command in
a command prompt: powershell.exe -command "set-executionpolicy remotesigned"

**Note:** Users running Windows 7 must upgrade to powershell 3.0 (Windows Management Framework 3.0 package).
By default, Windows 7 comes installed with powershell 2.0. This can be downloaded at the following link:
https://www.microsoft.com/en-us/download/details.aspx?id=34595. It typically requires a system restart after install.
Users running windows 8 and above have all required powershell tools installed by default.

**Note:** the .net framework version 4.5 or above is required for script execution for Windows.
This is a prerequisite for most modern text editors, but does not come installed by default on Windows 7.


## Release History

* 0.1.0 Initial release