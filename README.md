# Homeassistant integration for Yamaha HTR-6295 and RX-V2065
Homeassistant files for controlling Yamaha Receivers using YNC (aka YNC1?). This is not the same as YNCA; and it's not the same as the more modern true REST interfaces on later recievers. It may work on other recievers of this era, but YNC seems to be largely an outlier for Yamaha. Not tested on RX-V2065 but should work. Tested on HTR-6295 running latest firmware.

## Useful? Info
- Your XML tree is hopefully at http://[IP]/YamahaRemoteControl/UnitDesc.xml
- http://[IP]/XD/MrConnMgr.xml
- http://[IP]/XD/DeviceDescription.xml may be helpful for future development as it contains serial number so HA can see it as a unique device? 

## Dependencies
- https://github.com/thomasloven/lovelace-layout-card OR HACS "layout-card"

## Installation
1. Add a helper to your HA install
  - Name "Yamaha Volume Slider"
  - Minimum -80.5
  - Max 16.5
  - Step Size 0.5
  - Units: "dB"
2. Append the configuration.yaml contents to your configuration.yaml
3. Append the automations.yaml contents to your automations.yaml
4. Append the scrips.yaml contents to your scripts.yaml
5. Copy the dashboard.yaml to a new custom dashboard
6. In secrets.yaml, define your reciever ip:
```
yamahaIP: "http://192.168.10.15"
```
7. Restart HomeAssistant
8. **IMPORTANT**: Your input list will start empty. You need to physically change the source selector on the reciever to EACH input and leave it there for 2-3 seconds. After cycling through all the inputs, dashboard will have a list of them all; AS you've named them using your reciever (ie; you may have renamed "AUDIO 1" to "CD Player". This custom name will appear in the list (once you've cycled to it)

I think that's all, although I haven't bothered testing on a fresh install; I wrote this all in the production env.

If anyone wants to pack this as a custom integration for homeassistant, please do.
