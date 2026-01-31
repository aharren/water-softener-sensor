# water-softener-sensor.makefile

A vl53l0x-time-of-flight-based sensor for a water softener to detect the regeneration salt level, using ESPHome.

## Images

![](.readme/image-0.png)
![](.readme/image-1.png)
![](.readme/image-2.png)
![](.readme/image-3.png)

## Development Environment

Set up the environment and install ESPHome:

```
.env/init
source .env/activate
```

Create a `secrets.yaml` file based on `secrets.yaml.template` and configure the OTA password and WiFi details.

Connect the ESP device to your USB port and compile and install the software:

```
esphome run water-softener-sensor.yaml
```

Or, set up via ESPHome in Home Assistant.

## Salt Level Distance Configuration

The level of the regeneration salt is reported in percent, like a battery's charging level. Based on the installation point and water softener model, the distance measurement from the vl53l0x time-of-flight sensor needs to be mapped to the 100% and 0% levels.

Example mapping using 0.3m for 100% and 0.5m for 0%:

```
substitutions:
  distance_full_in_m: 0.3
  distance_empty_in_m: 0.5
```
