# Installation
Thanks for downloading TasmoManager! Since one of the main goals of this project was to make it beginner-friendly, I've created a windows installer and macOS .dmg for easy installation. 

## macOS
On macOS, simply download the .dmg release file, open it up and click and drag the app package into the Applications directory. When opening the app from the launchpad, you may encounter a pop-up, preventing you from opening TasmoManager. To work around this, right-click and open the app from the Applications directory.

You can also download the .pkg file and follow the on screen instructions when installing. Be sure to right-click and open the pkg otherwise you won't get an option allowing you to open the file

## Windows
Download the installer executable and run. Windows might pop up a smart screen message (in the process of getting that removed), if so just click on More Info > Allow. Then, follow the on-screen instructions.

## Linux

There are two types of packages you can install on Linux.

### Using apt
You can install TasmoManager using the precompiled .deb package. Firstly, download the latest version of TasmoManager fr
from the [GitHub releases page](https://github.com/tom-23/TasmoManager/releases):

Example:
```bash
wget https://github.com/tom-23/TasmoManager/releases/download/v1.0.0-alpha.11/tasmomanager_20210412-v1.0.0-alpha.11_amd64.deb
```

Once downloaded, install the package using the apt command (be sure to run as super user):
```bash
sudo apt install ./tasmomanager_20210412-v1.0.0-alpha.11_amd64.deb
```

You should see a new icon appear in your app launcher.

### Using rpm
Download the rpm package from the [GitHub releases page](https://github.com/tom-23/TasmoManager/releases) and install using the following command:

```bash
sudo rpm -i tasmomanager_20210412-v1.0.0-alpha.11_amd64.rpm --no-deps
```

## Updating
You can update TasmoManager the same way in macOS or Windows. Firstly, head over to the app's preferences and click on "Software Update". Next, select the update channel you would like to receive updates from (default is "Stable"). If there is a new update to be installed, a green "Begin Software Update" button should appear. Once pressed, TasmoManager will download the update and begin installing it onto your system. Please ensure you enter your administrator password when you are presented to do so otherwise the update process will not begin. (This only applies to TasmoManager v1.0.0-alpha.5 and above).
