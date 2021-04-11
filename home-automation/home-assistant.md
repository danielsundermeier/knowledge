# Home Assistant

- [Lovelace Soft UI](https://github.com/N-l1/lovelace-soft-ui)
- [Awesome HA](https://github.com/frenck/awesome-home-assistant)
- [Demo Frontend](https://demo.home-assistant.io/#/lovelace/0)

## Plugins

- [HACS](https://community.home-assistant.io/t/custom-component-hacs/121727)
Home Assistant Community Store

## Automations

### 2 Lichtquellen, 2 Bewegungsmelder, 1 Helligkeitssensor

Ich habe in einem Raum zwei Lampen mit jeweils einem Bewegungssensor. Die Lampen werden eingeschaltet, wenn es dunkel ist und Bewegung entdeckt wird.

Wenn eine Lampe eingeschaltet war, war es nicht dunkel genug, damit die andere Lampe angeht, wenn Bewegung erkannt wurde.

Jetzt wird die zweite Lampe eingeschaltet, wenn es entweder dunkel genug ist oder die erste Lampe eingeschaltet ist.

```yaml
condition: or
conditions:
  - below: '5'
    condition: numeric_state
    entity_id: sensor.helligkeit
  - condition: state
    entity_id: switch.shelly
    state: 'on'
```

### Links

- [No more light switches](https://smarthome.university/automations/no-more-light-switches/)

