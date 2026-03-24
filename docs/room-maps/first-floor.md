# First Floor Room Map

Use this document with the floorplan image to map each first-floor zone to its control path. This file describes the actual intended relationships between rooms, zones, and Pico remotes.

## Current First-Floor Scope

- Kitchen
- Foyer
- Hallway

## Kitchen

The kitchen is not a single lighting zone. It is modeled as 3 distinct zones:

- `kitchen_cans`
  Main task-lighting zone
  4 can lights
  Local API bulbs
  Controlled from 2 Pico locations
- `kitchen_nook`
  Decorative or ambient zone
  3 fixture bulbs
  Cloud-only bulbs
- `kitchen_sink`
  Separate task-lighting zone
  1 can light above the sink
  Local API bulb

Control relationship:

- The 2 kitchen Pico locations are both for `kitchen_cans`.
- Those Pico presses should behave like familiar wall-switch actions, but they do not cut power to the bulbs.
- `kitchen_nook` remains a separate zone and should not be collapsed into a generic accent bucket.
- `kitchen_sink` remains a separate single-light zone and should not be bundled into `kitchen_cans` just for convenience.

## Foyer

- `foyer_main` is a current implementation area.
- Behavior should stay simple and explicit.
- Foyer is a good candidate for reliable on or off behavior rather than clever scene cycling.

## Hallway

- `hallway_main` is in current implementation scope.
- Any hallway motion logic should be treated as draft until it proves necessary and reliable.
- The repo should document hallway as current scope without pretending motion automation is already deployed.

## Living Room

- The living room overhead fan light is not part of the smart lighting system.
- A future Govee torchiere is likely, but it is planned and not active.
- A future Pico is likely for that future smart-lighting path.
- Living room smart-lighting items should be documented as planned or future, not current.

## Playroom

- A playroom Pico is future-state only.

## Asset Reference

- Floorplan image: `docs/floorplans/first-floor-lighting.png`
- Recommended next annotation pass: label both kitchen Pico locations and outline the 3 kitchen lighting zones
