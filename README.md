# yamaha-HTR-6295-RX-V2065
Homeassistant files for controlling Yamaha Receivers using YNC (aka YNC1?). This is not the same as YNCA; and it's not the same as the more modern true REST interfaces on later recievers. It may work on other recievers of this era, but YNC seems to be largely an outlier for Yamaha.

## Useful? Info
- Your XML tree is hopefully at http://[IP]/YamahaRemoteControl/UnitDesc.xml
- http://[IP]/XD/MrConnMgr.xml
- http://[IP]/XD/DeviceDescription.xml

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
5. In secrets.yaml, define your reciever ip:
```
yamahaIP: "http://192.168.10.15"
```
I think that's all, although I haven't bothered testing on a fresh install; I wrote this all in the production env.
