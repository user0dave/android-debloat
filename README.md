# How To Android Debloat Using Debian/Ubuntu

This is a quick guide on how to get rid of unwanted applications on any android device. Install an app manager or some other application to list all the packages, that are installed on the device. Then you can search for packages that you wish to remove (e.g. facebook).

On your computer you need to install adb (android debug bridge). This can be done by running the following command:
`$ sudo apt install android-tools-adb`

Now you need to enable USB-Debugging on your android device. If you have not enabled developer options on your device, go into
settings -> about phone and hit the build number a couple of times to enable it. Then go into the developer options and enable USB-Debugging. Next connect your device to the computer. Make sure your computer has access to the data on the device (you may need to unlock the device). Then open a terminal and run:
`$ adb shell`

Now you will be able to **list** all installed packages on the device by running:
`$ pm list packages`or filter out a package with a specific name e.g. `$ pm list packages wechat`

To **remove** a package type:
`$ pm uninstall -k --user 0 package.name.example`

To **disable** a package:
`$ pm disable --user 0 package.name.example`

To **enable** a package:
`$ pm enable --user 0 package.name.example`

To **reinstall** a package:
`$ cmd install-existing package.name.example`

Disclaimer: Some packages may still not be removable with this method. Do not remove packages that you do not know anything about. Doing so may lead to a malfunctioning device and may require a factory reset.
