# Multi Dryer PCB Upgrade

This is an esp32-c3 based upgrade for 3dGenius, Firos, Dikal or other similar oem branded filament dryers. The upgrade is designed to replace the original controller with a more advanced one that can control the heating element, fan and display the current temperature and humidity. This hardware was designed to work with esphome and home assistant. 

The esp32 was chosen over an esp8266 mainly just to keep my designs similar. If you have used an esp8266, this is no different.

Both fans should never be used at once. The additional fan header is meant to server as a replacement for the original 12v fan. The 4 pin fan header is meant to be used with a pwm fan.

[Purchase PCB Here](https://shop.silocitylabs.com/products/3dgenius-dikale-firos-smart-pcb-esp32-conversion-preorder)

## TODO:

- [x] Schematic
- [x] PCB Design
- [x] Base Config
- [x] AHT21 Reading
- [x] Display Output
- [x] Button Controls
- [ ] Get "Made for ESPHOME" approved
- [ ] Add Images to Repo
- [ ] Work on Custom Mode
- [ ] Heating Element Control
- [ ] NTC Calibration
- [ ] NTC/AHT Toggle or substitution
- [ ] Test PWM Fan Mode, seperate header
- [ ] Test Fan Frequency Switching for Speed control of regular DC Fan
- [ ] Github Pipeline
- [ ] OSHWA Certification

## Pins

-------------------
| XIAO Pin | Pin | Function | Description |
| --- | --- | --- | --- |
| D0 | GPIO2 | Fan 1 | Original 12v Fan |
| D1 | GPIO3 | Fan 2 | 4 pin PWM fan |
| D2 | GPIO4 | 10k NTC | OEM Temp sensor |
| D3 | GPIO5 | Heat Element | Relay for heating element |
| D4 | GPIO6 | i2c SDA | Shared Bus |
| D5 | GPIO7 | i2c SCL | Shared Bus |
| D9 | GPIO9 | BTN pwr | Power Button |
| D10 | GPIO10 | BTN mode | Mode Button |
| D7 | GPIO20 | BTN up | Up Button |
| D8 | GPIO8 | BTN down | Down Button |


## i2c Devices

- 128x32 OLED Display - Address 0x3C
- AHT 21 Sensor - Address 0x38

## Modes

Chamber temps for materials

-------------------
| Mode | Temp | Humidity | Time |
| --- | --- | --- | --- |
| Idle | 0 | 0 | 0 |
| PLA | 45 | 20 | 4h |
| PETG | 60 | 20 | 4h |
| ABS | 65 | 20 | 4h |
| Custom |  |  |  |