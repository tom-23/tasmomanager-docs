# Installation
Thanks for downloading TasmoManager! Since one of the main goals of this project was to make it beginner-friendly, I've created a windows installer and macOS .dmg for easy installation. 

## macOS
On macOS, simply download the .dmg release file, open it up and click and drag the app package into the Applications directory. When opening the app from the launchpad, you may encounter a pop-up, preventing you from opening TasmoManager. To work around this, right-click and open the app from the Applications directory.

You can also download the .pkg file and follow the on-screen instructions when installing. Be sure to right-click and open the pkg otherwise you won't get an option allowing you to open the file

## Windows
Download the installer executable and run. Windows might pop up a smart screen message (in the process of getting that removed), if so click on More Info > Allow. Then, follow the on-screen instructions.

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

# Building
**Only attempt if you have some knowledge when working with CMake / C++ projects! I'll try to go in-depth in this tutorial but it's not 100% foolproof.**

Optionally, you can build TasmoManager from source. You'll need the following prerequisites:

- Git SCM
- Perl
- CMake build system
- A Windows, macOS or Linux computer
- A C++ 17 compatible compiler (clang, MSVC, GCC)
- Qt 5.12.0 or newer (**Qt 6 is currently not supported**)
- Qt `bin` directory in your system PATH
- OpenSSL

The following prerequisites are optional:

- InnoSetup (to create a Windows installer package)
- create-dmg (to create a macOS DMG disk image. Install: `npm install --global create-dmg`)
- CPack (to create Linux Packages)

Firstly take note of you're Qt install path. On Windows, Qt installs to the `C:\Qt` directory followed by the Qt version installed. On macOS and Linux, Qt should be installed in you're home area. On macOS, Qt would be installed at: `/Users/username/Qt` and on Linux: `/home/username/Qt`.

Next, clone the TasmoManager repo and clone the submodules recursively:

```bash
git clone https://github.com/tom-23/TasmoManager.git
git submodule update --init --recursive
``` 

First we need to build and install qmqtt. Enter the qmqtt directory and create an empty build folder:

```bash
cd lib/qmqtt
mkdir build && cd build
```

Assuming you have qmake in your path, configure the project and build:

```bash
qmake ..
make -j4
```

Once the project has successfully built, install via the following command:

```bash
sudo make install
```

**You'll only need to compile and install QMQTT once**

Inside the TasmoManager repo directory, create a new folder named `build` and enter it:

```bash
mkdir build && cd build/
```

Make sure you have set the OPENSSL_ROOT_DIR system variable to your OpenSSL installation directory. On macOS, the command would look something like this:

```bash
export OPENSSL_ROOT_DIR="/usr/local/opt/openssl@1.1"
```

Run `CMake` passing the following parameters substituting `path_to_qt` with the path to your qt installation:

```bash
cmake .. -DCMAKE_PREFIX_PATH="path_to_qt"
```

Next, build using the make command:

```bash
make -j4
```