# ROS_on_Windows
This repository consists of all the commands that you need to install ROS on Windows 10 in 3 Simple Steps

## Step 1

### Install Visual Studio:

Download Visual Studio Community 2017 - https://bit.ly/visualstudiocommunity2017 <br>
Download Visual Studio's Latest Version - https://visualstudio.microsoft.com/vs/


## Step 2

### Set path for installation of Chocolatey
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

### Make directory for Chocolatey to install packages
```
mkdir c:\opt\chocolatey
```

### Set the directory for installation
```
set ChocolateyInstall=c:\opt\chocolatey
```

### Test Chocolatey by installing git
```
choco install git -y
```

### Give the source to install ROS for Windows to Chocolatey
```
choco source add -n=ros-win -s="https://aka.ms/ros/public" --priority=1
```

### Install full desktop version of ROS Melodic which includes Gazebo, RViz and other packages
You can replace melodic with noetic if you wish to install ROS Noetic

```
choco upgrade ros-melodic-desktop_full -y 
```

It will take some time to download based upon your Internet Connection<br><br>
If you have reached till here and found these steps helpful,<br>
please give a ⭐ to this repository by clicking on the option on top-right corner of the page 🙂<br>
This will help me make more such useful tutorials for you. Thank You! ✌🏻

## Step 3

Paste the following in the location of your shortcut<br>
```
C:\Windows\System32\cmd.exe /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\Tools\VsDevCmd.bat" -arch=amd64 -host_arch=amd64&& set ChocolateyInstall=c:\opt\chocolatey&& c:\opt\ros\melodic\x64\setup.bat
```

* If you are using different version of Visual Studio i.e. Professional or Enterprise other than Community, then replace the Community folder in the path by your respective version name.
* Also if you are using any other Year's version of Visual Studio other than 2017, then replace 2017 with your version's year
* And finally depending upon your version of ROS, you can replace Melodic with Noetic
