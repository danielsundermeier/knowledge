# Architecture

This is a plan for a home automation architecture and i would like to get your feedback.

## Hardware

I like the idea of shields and reusable parts.
One ESP Unit contains two parts:

- Base
- "Shield"

like an [Arduino](https://www.arduino.cc)

### Base

- ESP8266 / ESP32
- power supply (230V)
- programming header [SuperHouse](https://www.superhouse.tv/vlog-66-lets-define-a-standard-esp8266-esp32-programming-header/)
- header for the shield
- status LED

it should fit inside the wall behind a standard wall switch.

Examples

- [espurna-board](https://github.com/xoseperez/espurna-board)
- [ESP8266 230V I/O Modul](https://luani.de/projekte/esp8266-hvio/)
- [SmartSwitch](https://github.com/Necromancer1982/SmartSwitch)

without the relais and with headers for shields

### Shields

#### Sensor

- DHT 22 (temperature & humidity)
- TSL2561 or TEMT6000 (lux / brightness)
- AM312 Mini PIR Sensor (motion) better alternatives?
- reed switch (door & window sensors)

#### Switch

Something like this: 

- [WallMote](https://aeotec.com/z-wave-wireless-switch/)
- [Loxone](https://www.loxone.com/dede/smart-home/einfach-bedienen/)

but normal switches would work to

#### Relais

- i do not want to use relais boards. Instead i am going to use something like this: "Finder Relais 40.61 12V DC"
- The Base needs an enclosure to mount it on a DIN rail with an I2C out connector 
- the shield should be expandable so that one esp kann switch multiple relais shields.
- the boards should be placed inside the switchboard on a DIN rail

Parts:

- MCP23017 I2C Port Expander
- dip switch for I2C address
- ULN2803 Darlington Array (or optocoppler?)
- 8x switch to trigger relais manual (testing)
- 8x led for status of the relais
- 8x output to relais (preferebly connectors; which type?)
- connector I2C in (which type?)
- connector I2C out )which type?)

## Hardware Room

### Switchboard

- All cables are individually routed to this place.
- Every light, plug, etc has its own cable 
- ESP Relais to switch relais

### Network

- Ethernet cabels to all rooms from here


## Rooms

### ESP Switches Shield

Every room should have at least one switch connected to an ESP. 
Normaly all things should be triggered by automations but it is good to have options.
Preferebly the switches have multiple Buttons to trigger many things and scene.

### ESP Sensors Shiels

Every room should have multiple sensors.
It should be mounted in the wall or ceiling.

How to make it "pretty"?

[BRUH Multisensor](https://github.com/bruhautomation/ESP-MQTT-JSON-Multisensor)

## Software

- [Home Assistant](https://www.home-assistant.io)
- [ESPHome](https://esphome.io) for the ESPs

### ESPHome

- Wifi with access point mode
- OTA
- Native API

