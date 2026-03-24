# First Floor Room Map

This file is the literal room, zone, and control map for the first floor. It should read like an operational reference, not a conceptual summary.

## Current First-Floor Zones

| Zone | Room | Floorplan Label | Fixture Or Bulb Count | Control Classification | Intended Pico Or Control Input(s) | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `kitchen_cans` | Kitchen | `#3` | 4 can lights | Local API | `pico_kitchen_cans_a`, `pico_kitchen_cans_b` | Current | Main kitchen task-lighting zone with 2 controllers |
| `kitchen_nook` | Kitchen | `#4` | 3 fixture bulbs | Cloud-only | `pico_kitchen_nook_main` | Current | Separate decorative or ambient zone |
| `kitchen_sink` | Kitchen | `#5` | 1 can light above sink | Local API | `pico_kitchen_sink_main` | Current | Separate task-lighting zone |
| `foyer_main` | Foyer | `TBD` | TBD | Preferred local API | `pico_foyer_main` | Current | Baseline behavior should stay explicit on or off |
| `hallway_main` | Hallway | `TBD` | TBD | Preferred local API | `baseline_input_tbd` | Current | Hallway is current scope, but motion logic is draft only |
| `living_room_torchiere_future` | Living Room | `TBD` | 1 future lamp | TBD | `pico_living_room_future` | Planned | Future smart-lighting path only |

## Kitchen Control Relationships

- `kitchen_cans` is the multi-controller kitchen zone.
- Both kitchen Pico locations are intended to provide the same baseline switch-equivalent `on` and `off` behavior for `kitchen_cans`.
- `kitchen_nook` is a separate zone with its own baseline control path.
- `kitchen_sink` is a separate zone with its own baseline control path.
- None of the kitchen control inputs should cut power to the bulbs.
- For `kitchen_cans`, do not use state-based toggle behavior because there are 2 controllers for the same zone.

## Status Boundaries

- Current: kitchen, foyer, and hallway baseline control modeling
- Planned: future living room smart-lighting path
- Future or draft: hallway motion behavior, playroom Pico, adaptive scene logic

## Explicit Exclusions

- The living room overhead fan light is not in the smart-lighting system.

## Asset Reference

- Floorplan image: `docs/floorplans/first-floor-lighting.png`
- Next annotation pass should mark `#3`, `#4`, `#5`, and the physical locations of the kitchen control inputs
