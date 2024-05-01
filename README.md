# Ledvance-A60-LED-light-
Ledvance Classic Filament A60 LED light (AC32956) uses there own (closed) software. Now it has become possible to use LibreTiny ESPHome to control it.
(First time using GitHub)

### About the light fillament

- Manufacturer: Ledvance GmbH
- Filament Classic A60 E27 Dimmable
- Fitting: E27
- Power when on: 6W
- Power stand-by: 0.5W
- lm: 806lm
- Connectivity: Wi-Fi
- Light temperature: 2700K
- Ra: 80
- Voltage: 220-240VAC
- Frequency: 50-60Hz
- Board: bk7231t



**This code works (ON/OFF and adjusting brightness), but need some tweaks:**

> esphome:
  name: ledvance-test1
  friendly_name: Ledvance Test#1
bk72xx:
  board: generic-bk7231t-qfn32-tuya
logger:
web_server:
captive_portal:
mdns:
api:
ota:
wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
  ap:
text_sensor:
>  - platform: libretiny
    version:
      name: LibreTiny Version
output:
>  - platform: ledc
    id: output_cold
    pin: P26
light:
>  - platform: monochromatic
    id: light_monochromatic
    name: Light
    output: output_cold
    restore_mode: RESTORE_DEFAULT_OFF
