# home-assistant-dewpoint
Home Assistant custom component to calculate dew point using temperature and humidity sensors.
Calculated using [psychrolib](https://github.com/psychrometrics/psychrolib).

Forked from component by miguelangel-nubla. 

## Installation

Use [hacs](https://custom-components.github.io/hacs/) with this repo URL https://github.com/ajthom90/home-assistant-dewpoint or copy `custom_components/` to your HA configuration.

## Example configuration.yaml

```yaml
sensor:
  - platform: dewpoint
    sensors:
      dewpoint_outside:
        unique_id: sensor.unique_id_1
        temperature: sensor.temperature_outside
        rel_hum: sensor.humidity_outside
      dewpoint_office:
        unique_id: sensor.unique_id_2
        temperature: sensor.temperature_office
        rel_hum: sensor.humidity_office
      ...
```

## Configuration options

| Key       | Type   | Required | Description                           |
|-----------|--------|----------|---------------------------------------|
 | `sensors` | `list` | `True`   | List of dewpoint sensors to generate. | 

### Configuration options for `sensors` list

| Key             | Type        | Required | Default       | Description                                    |
|-----------------|-------------|----------|---------------|------------------------------------------------|
| `friendly_name` | `string`    | `False`  | `sensor name` | Custom name for the new sensor entity.         |
| `temperature`   | `entity_id` | `True`   | `none`        | Entity ID to read temperature from. (dry-bulb) |
| `rel_hum`       | `entity_id` | `True`   | `none`        | Entity ID to read relative humidity from.      |
| `unique_id`     | `entity_id` | `False`  | `none`        | Unique ID to customize this from the GUI.      |


***

[dewpoint]: https://github.com/custom-components/dewpoint