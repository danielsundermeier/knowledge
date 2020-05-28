# ESP Home

[ESPHome](https://esphome.io)

## Flashen

### .yaml

In ESPHOME Home Assistant Plugin erstellen.

### .bin erstellen

- In Node auf 3 Punkte Menu klicken
- compile
- Im PopUp auf Download Binary
- Binary auf Laptop speichern

### Flashen

- [ESPHome Flasher](https://github.com/esphome/esphome-flasher) herunterladen
- ESP an Laptop anschließen
- ESPHome Flasher starten
- Port auswählen
- Binary auswählen
- "Flash ESP"

Danach kann ich den ESP over the air flashen

## Snippets

### Skeleton

```
esphome:
  name: name
  platform: ESP8266
  board: nodemcuv2

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Fallback Hotspot"
    password: "1234"

captive_portal:

# Enable logging
logger:

# Enable Home Assistant API
api:

ota:

# Sensoren
```
