# Emergency stop simplified (fork from Mechazawa pluggin, with a merge from Alexiri & Crysxd) 

This plugin reacts to a switch or button, if triggered (switch open or closed, to GND or 3V3) it issues **M112** or another command to printer.

Let's check some features:
* info pop-up when plugin hasn't been configured
* user-friendly and easy to configure
* modification from Mechazawa pluggin : 
** select if BCM or GPIO mode
** select if the stop is active if the button is activated or not
** select if the printer does stop and disconnect, or just make a "pause"
** add a test to see if the pluggin is active and can detect the button

## Setup

Install via the bundled [Plugin Manager](https://docs.octoprint.org/en/master/bundledplugins/pluginmanager.html)
or manually using this URL:

    https://github.com/DuduNord/Emergency_stop_simplified

## Configuration

Configuration couldn't be simpler, all you need is to configure listening board pin (board mode) and if the second switch terminal is connected to ground or 3.3V.

Default pin is -1 (not configured) and ground (as it is safer, read below) or 3,3V.

**WARNING! Never connect the switch input to 5V as it could fry the GPIO section of your Raspberry!**

#### Advice from Mechazawa

You might experience the same problem as I experienced - the button was randomly triggered. Turns out that if running button wires along motor wires, it was enough to interfere with button reading.

To solve this connect a shielded wire to your button and ground the shielding, ideally on both ends.

If you are unsure about your button being triggered, check [OctoPrint logs](https://community.octoprint.org/t/where-can-i-find-octoprints-and-octopis-log-files/299)
