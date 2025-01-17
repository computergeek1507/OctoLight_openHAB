# OctoLight openHAB
A simple plugin that adds a button to the navigation bar for toggling a openHAB connected Light.

Code forked from [OctoLight by gigibu5](https://github.com/gigibu5/OctoLight) with HA integration based on [OctoPrint-PSUControl by kantlivelong](https://github.com/kantlivelong/OctoPrint-PSUControl)

![WebUI interface](img/screenshoot.png)

## Setup
Install via the bundled [Plugin Manager](https://docs.octoprint.org/en/master/bundledplugins/pluginmanager.html) or manually using this URL:

        https://github.com/computergeek1507/OctoLight_openHAB/archive/master.zip
Alternatively:
- Download the repository code as a .zip
- In the plugin manager of OctoPrint, go to "Get More"
- Under "... from an uploaded file" select the .zip you downloaded to install.

## Configuration
Curently, you can configure 8 settings, including 4 configuration items:
- `Address`: The IP address or hostname of your openHAB server. e.g. http://ip:port or http://hostname:port. Do not include a trailing slash /

- `Item Name`: The Itme Name of the device you'd like to control. Currently must be a light device supporting the light/toggle action.

### Operational settings [to be introduced in v0.4]
- `Turn on light on print start`: Turn on the light when OctoPrint receives a "print started" message.

- `Turn off light on print end`: Turn off the light when OctoPrint receives a "print complete" message.

- `Turn off light on print failure`: Turn off the light when OctoPrint receives a "print failure" message.

- `Turn off light on print cancellation`: Turn off the light when OctoPrint receives a "print cancellation" message.

![Settings panel](img/settings1.png)

## API
**UNTESTED in HA MOD**
Base API URL : `GET http://YOUR_OCTOPRINT_SERVER/api/plugin/octolight?action=ACTION_NAME`

This API always returns updated light state in JSON: `{state: true}`

_(if the action parameter not given, the action toggle will be used by default)_
#### Actions
- **toggle** (default action): Toggle light switch on/off.
- **turnOn**: Turn on light.
- **turnOff**: Turn off light.
- **getState**: Get current light switch state.

## TO DO
- [x] Update interface if Light is turned on or off
- [x] Turn off on finish print (thank you [Nick-Gatti](https://github.com/Nick-Gatti/OctoLight_Home-Assistant/tree/master))

Maybe in the distant future:
- [ ] Add light settings (e.g. brightness and colour) for turn on
