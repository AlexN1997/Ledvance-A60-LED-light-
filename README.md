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

> esphome: <br>
  name: Insert name <br>
  friendly_name: Insert name <br>
bk72xx: <br>
  board: generic-bk7231t-qfn32-tuya <br>
logger: <br>
web_server: <br>
captive_portal: <br>
mdns: <br>
api: <br>
ota: <br>
wifi: <br>
  ssid: !secret wifi_ssid <br>
  password: !secret wifi_password <br>
  ap: <br>
text_sensor: <br>
  platform: libretiny <br>
    version: <br>
      name: LibreTiny Version <br>
 output: <br>
  platform: ledc <br>
    id: output_cold <br>
    pin: P26 <br>
 light: <br>
  platform: monochromatic <br>
    id: light_monochromatic <br>
    name: Light <br>
    output: output_cold <br>
     restore_mode: RESTORE_DEFAULT_OFF
