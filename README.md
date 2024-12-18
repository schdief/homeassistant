# homeassistant

## home assistant base
https://www.home-assistant.io/installation/macos/

## heatpump
### Wolf Link
https://www.home-assistant.io/integrations/wolflink
#### Energy Dashboard Individual Device
To make this work, first create a new `integral` helper under `settings -> devices -> helpers`.

<img width="557" alt="image" src="https://github.com/user-attachments/assets/80334a2c-3cc6-45ee-9fa1-a6a9e8885a5c" />

> don't set it to kilo, as the data is not W but kW already

Then overwrite the helpers data, so it appears in the device list.
For this install the https://www.home-assistant.io/common-tasks/os/#installing-and-using-the-file-editor-add-on[File Editor addon]
Then open `/homeassistant/configuration.yaml` and write:

```
homeassistant:
  customize:
    sensor.wp_verbauch_kwh_ohnekilo:
      device_class: energy
      state_class: total_increasing
      unit_of_measurement: kWh
```

### ISM7MQTT
(not tried): https://github.com/b3nn0/hassio-addon-ism7mqtt?tab=readme-ov-file

## pv
https://www.photovoltaikforum.com/wissen/entry/88-quick-and-dirty-einbindung-solax-qcells-wr-via-wifi-stick-in-homeassistant-einri/

## wallbox
https://github.com/PatrikTrestik/homeassistant-solax-http?tab=readme-ov-file
