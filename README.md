# irusb-remote-card
Example of a card that I have modified to be used with the Video Storm irusb module and Home Assistant to control Android TV devices more reliably

I managed to do a 'quick and dirty' integration with this, and while setting it up is slightly cumbersome it actually works well. Essentially gives you the instantaneous responsiveness you expect from a remote control. I was very dissatisfied with the adb control, even after setting up the /sendevent commands it was still not good. 
It is essentially a one-way local push mechanism. It is co-dependent on the androidtv (adb) integration being setup to interact with it as a media_player entity. 
 ⠀
Pre-requisites:
* androidtv integration already setup and in home assistant
* IRusb and companion app setup/installed on Nvidia Shield (should work on other ATV devices, but not tested)
* Custom Cards:
* mini-media-player
* button-card
 ⠀
Configuration:
 ⠀
> *In /config/configuration.yaml*

```
# TCP Android Control
shell_command: !include shellcmd.yaml
```
 ⠀
Grab/use the shellcmd.yaml in this repository and modify accordingly
 ⠀
Save, reboot config. 
After reboot under Developer Tools you should now be able to issue the shell commands
```
shell_command.home_shield_livingroom
```
Test and confirm working with your shield.
