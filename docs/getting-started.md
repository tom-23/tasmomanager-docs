# Inital Setup
Once you have installed TasmoManager, firstly press on the connect button to open up the preferences window. Here, click on "MQTT Servers" and add an MQTT Server by pressing the green plus button. Fill out the required information and click on Save Changes. Then, close the preferences dialog and click on the connect button once again. Select the MQTT server you just added and click on connect. You should start to see devices appearing in the device list.

# Things to note
You MUST have either HASS Discovery enabled (`SetOption19 0`) or firmware compiled with `USE_TASMOTA_DISCOVERY`. More Info: [troubleshooting](troubleshooting.md).