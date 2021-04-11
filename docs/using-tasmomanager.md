# General Usage

Once connected to a server, click on a device to view its basic properies and controls (to the right of the window). You can edit the name and friendly name of a device by editing the text in fields on the right and save by clicking on the green check mark. To revert, click on the orange undo button beside it.

## Firmware Upgrade
TasmoManager has the ability to update firmware on multiple devices at once. To do this, connect to an MQTT server and click on the Firmware Update button. Click next next on the dialog and selct the devics you would like to upgrade. Pressing `cmd + a` or `ctrl + a` will select / deselect all devices in the list. Then, click on next and select the OTA server you would like to use. Be sure you select the type of binary you want to upgrade to if you're using the `ota.tasmota.com` server. Then click on next, read the message and click on Begin Update to start updating the selected devices.