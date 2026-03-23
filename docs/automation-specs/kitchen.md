# Kitchen Automation Spec

## Intent

Provide fast task lighting from a Pico remote while preserving an easy path to accent or evening scenes.

## Inputs

- `On` button: turn on kitchen lights to bright task level.
- `Raise` button: increase brightness.
- `Lower` button: decrease brightness.
- `Off` button: turn off kitchen lights.

## Outputs

- Main task lights at 100% when the room is actively used.
- Optional evening scene at a warmer, dimmer level.

## Notes

- Replace placeholder device IDs and entity IDs in matching Home Assistant YAML.
- Decide whether accent lights should always mirror the main kitchen zone or be controlled separately.
