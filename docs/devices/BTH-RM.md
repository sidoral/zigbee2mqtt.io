---
title: "Bosch BTH-RM control via MQTT"
description: "Integrate your Bosch BTH-RM via Zigbee2MQTT with whatever smart home infrastructure you are using without the vendor's bridge or gateway."
addedAt: 2023-06-27T19:44:08
pageClass: device-page
---

<!-- !!!! -->
<!-- ATTENTION: This file is auto-generated through docgen! -->
<!-- You can only edit the "Notes"-Section between the two comment lines "Notes BEGIN" and "Notes END". -->
<!-- Do not use h1 or h2 heading within "## Notes"-Section. -->
<!-- !!!! -->

# Bosch BTH-RM

|     |     |
|-----|-----|
| Model | BTH-RM  |
| Vendor  | [Bosch](/supported-devices/#v=Bosch)  |
| Description | Room thermostat II |
| Exposes | humidity, climate (local_temperature, occupied_heating_setpoint, local_temperature_calibration, system_mode), window_open, lock (state), display_ontime, display_brightness, battery_low, voltage, linkquality |
| Picture | ![Bosch BTH-RM](https://www.zigbee2mqtt.io/images/devices/BTH-RM.jpg) |


<!-- Notes BEGIN: You can edit here. Add "## Notes" headline if not already present. -->
## Notes

### Pairing
To pair this device you have to install the device via its installation code. The installation code can be obtained by scanning the QR-code on the inside of the battery cover with your smartphone. Then get the device into pairing mode. In zigbee2mqtt navigate to  "Settings" --> "Tools" and click on "Add install code". Paste the code you got from the QR-code and confirm by clicking "OK" which will get zigbee2mqtt into pairing mode automatically. Wait for your device to be joined.


### Factory resetting
To factory reset the device remove one of the batteries. While pressing and holding the device's main button on the front, insert the battery back. As soon as the device's LED is starting to blink orange while showing "RES", release the main button and press and hold it again until the device's LED is lighting up green. The device will then restart into the calibration process and look for a Zigbee network to join. In case something went wrong, the device's LED will start to blink red. The process has then to be start all over again.
<!-- Notes END: Do not edit below this line -->



## Options
*[How to use device type specific configuration](../guide/configuration/devices-groups.md#specific-device-options)*

* `thermostat_unit`: Controls the temperature unit of the thermostat (default celsius). The value must be one of `celsius`, `fahrenheit`

* `humidity_precision`: Number of digits after decimal point for humidity, takes into effect on next report of device. The value must be a number with a minimum value of `0` and with a with a maximum value of `3`

* `humidity_calibration`: Calibrates the humidity value (absolute offset), takes into effect on next report of device. The value must be a number.


## Exposes

### Humidity (numeric)
Measured relative humidity.
Value can be found in the published state on the `humidity` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The unit of this value is `%`.

### Climate 
This climate device supports the following features: `local_temperature`, `occupied_heating_setpoint`, `local_temperature_calibration`, `system_mode`.
- `occupied_heating_setpoint`: Temperature setpoint. To control publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"occupied_heating_setpoint": VALUE}` where `VALUE` is the °C between `5` and `30`. To read send a message to `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"occupied_heating_setpoint": ""}`.
- `local_temperature`: Current temperature measured on the device (in °C). To read send a message to `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"local_temperature": ""}`.
- `system_mode`: Mode of this device. To control publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"system_mode": VALUE}` where `VALUE` is one of: `off`, `heat`, `auto`. To read send a message to `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"system_mode": ""}`.
- `local_temperature_calibration`: Offset to be used in the local_temperature. To control publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"local_temperature_calibration": VALUE}.`To read send a message to `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"local_temperature": ""}`.The minimal value is `-12` and the maximum value is `12` with a step size of `0.5`.

### Window open (binary)
Window open.
Value can be found in the published state on the `window_open` property.
To read (`/get`) the value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"window_open": ""}`.
To write (`/set`) a value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"window_open": NEW_VALUE}`.
If value equals `ON` window open is ON, if `OFF` OFF.

### Child lock (lock)
The current state of this lock is in the published state under the `child_lock` property (value is `LOCK` or `UNLOCK`).
To control this lock publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"child_lock": "LOCK"}` or `{"child_lock": "UNLOCK"}`.
To read the current state of this lock publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"child_lock": ""}`.

### Display ontime (numeric)
Specifies the diplay On-time.
Value can be found in the published state on the `display_ontime` property.
To read (`/get`) the value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"display_ontime": ""}`.
To write (`/set`) a value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"display_ontime": NEW_VALUE}`.
The minimal value is `5` and the maximum value is `30`.

### Display brightness (numeric)
Specifies the brightness value of the display.
Value can be found in the published state on the `display_brightness` property.
To read (`/get`) the value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/get` with payload `{"display_brightness": ""}`.
To write (`/set`) a value publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"display_brightness": NEW_VALUE}`.
The minimal value is `0` and the maximum value is `10`.

### Battery low (binary)
Indicates if the battery of this device is almost empty.
Value can be found in the published state on the `battery_low` property.
It's not possible to read (`/get`) or write (`/set`) this value.
If value equals `true` battery low is ON, if `false` OFF.

### Voltage (numeric)
Voltage of the battery in millivolts.
Value can be found in the published state on the `voltage` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The unit of this value is `mV`.

### Linkquality (numeric)
Link quality (signal strength).
Value can be found in the published state on the `linkquality` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The minimal value is `0` and the maximum value is `255`.
The unit of this value is `lqi`.

