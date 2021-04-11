# Troubleshooting
If you have any issues whilst using TasmoManager, please look at this page before submitting a github issue.
## No devices show up
Ensure that you have the following:

- Tasmota version that supports device discovery

    Make sure that the tasmota version installed on your devices, includes the new home assistant discovery protocol. If you have `tasmota-lite` installed, you will NOT have home assistant discovery compiled by default.

- `SetOption19` set to `0`

    Have `SetOption19` set to `0` to ensure the new home assistant discovery protocol is used. You can change this in the WebUI by opening up the console and entering `SetOption19 0`. The device should start to appear in the device list after a few seconds.

- MQTT Server which allows for client Read/Write access

    TasmoManager needs to read data from the `tasmota/discovery`. Make sure you are able to Read/Write data using an MQTT client such as MQTTExplorer. Make sure your MQTT server isn't sonoff-adapter (for iobroker) as it doesn't allow for client read access.

- `tasmota/discovery` topic deleted

    The tasmota discovery topic could of been deleted. This can easily by fixed by restarting the devices connected to the MQTT server.

## Old devices still exist
This is caused by the device's discovery topic still being retained on the MQTT server. You can either delete the topic from the server using an MQTT client or hide offline devices in TasmoManager (Settings > General > Show Offline Devices).