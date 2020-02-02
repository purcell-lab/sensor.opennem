<h1>sensor.opennem</h1>

<h2>Home Assistant sensor for OpenNEM Data</h2>

This component will set up a sensor platform to retrieve data from [OpenNEM](http://www.opennem.org.au), an open platform to access National Electricity Market Data (Australia)

[![HitCount](http://hits.dwyl.io/bacco007/sensoropennem.svg)](http://hits.dwyl.io/bacco007/sensoropennem)
![LastCommit](https://img.shields.io/github/last-commit/bacco007/sensor.opennem)
![Licence](https://img.shields.io/github/license/bacco007/sensor.opennem)
![Downloads](https://img.shields.io/github/downloads/bacco007/sensor.opennem/total)

---

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Installation](#installation)
  - [Manual Installation](#manual-installation)
  - [Installation via Home Assistant Community Store (HACS)](#installation-via-home-assistant-community-store-hacs)
- [Regions](#regions)
- [Configuration Options](#configuration-options)
  - [Monitored Conditions](#monitored-conditions)
- [Example Configuration](#example-configuration)
- [Contributions](#contributions)

---

## Installation

### Manual Installation

1. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`).
2. If you do not have a `custom_components` directory (folder) there, you need to create it.
3. In the `custom_components` directory (folder) create a new folder called `waternsw`.
4. Download _all_ the files from the `custom_components/opennem/` directory (folder) in this repository.
5. Place the files you downloaded in the new directory (folder) you created.
6. Create Configuration (see below)
7. Restart Home Assistant

### Installation via Home Assistant Community Store (HACS)

1. Ensure [HACS](http://hacs.xyz/) is installed.
2. Search for and install the "OpenNEM (AU) Data" integration
3. Configure the sensor
4. Restart Home Assistant

---

## Regions

The National Energy Market operates in the following states:

| State           | Region for Config |
| --------------- | ----------------- |
| Queensland      | qld1              |
| New South Wales | nsw1              |
| Victoria        | vic1              |
| South Australia | sa1               |
| Tasmania        | tas1              |

---

## Configuration Options

| Key                    | Type     | Required | Description                            |
| ---------------------- | -------- | -------- | -------------------------------------- |
| `region`               | `string` | `True`   | Region of Interest (See Table Sbove)   |
| `monitored_conditions` | `list`   | `True`   | Monitored Conditions (See Table Below) |

### Monitored Conditions

| Type                  | Monitored Condition   |
| --------------------- | --------------------- |
| Battery - Charging    | `battery_charging`    |
| Battery - Discharging | `battery_discharging` |
| Biomass               | `biomass`             |
| Black Coal            | `black_coal`          |
| Brown Coal            | `brown_coal`          |
| Exported Electricity  | `exports`             |

      - demand
      - distillate
      - fossilfuel
      - renewables
      - gas_ccgt
      - gas_ocgt
      - gas_recip
      - gas_steam
      - generation
      - hydro
      - imports
      - price
      - pumps
      - rooftop_solar
      - solar
      - temperature
      - wind

---

## Example Configuration

```yaml
sensor:
  - platform: opennem
    region: nsw1
    monitored_conditions:
      - battery_charging
      - battery_discharging
      - biomass.githu
      - black_coal
      - brown_coal
      - exports
      - demand
      - distillate
      - fossilfuel
      - renewables
      - gas_ccgt
      - gas_ocgt
      - gas_recip
      - gas_steam
      - generation
      - hydro
      - imports
      - price
      - pumps
      - rooftop_solar
      - solar
      - temperature
      - wind
```

---

## Contributions

Please feel free to contribute, be it with Issues or Pull Requests!