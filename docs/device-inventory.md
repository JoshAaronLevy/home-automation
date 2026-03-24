# Device Inventory

This file is the operational inventory for the first-floor lighting rollout. Placeholder entity IDs, device IDs, and bulb models are intentional until the real Home Assistant and Lutron details are confirmed.

## Controllers And Core Devices

| Device | Status | Function | Integration | Notes |
| --- | --- | --- | --- | --- |
| Home Assistant Green | Current | Central automation brain | Home Assistant OS | Makes the lighting decisions |
| Lutron Hub | Current | Pico event bridge | Lutron Caseta | Sends Pico button events to Home Assistant |

## First-Floor Zone Inventory

| Room | Zone | Status | Floorplan Label | Fixture Or Bulb Count | Bulb Model Placeholder | Control Class | Suggested Entity Placeholder | Intended Control Input(s) | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kitchen | `kitchen_cans` | Current | `#3` | 4 can lights | `govee_local_api_a19_tbd` x4 | Local API | `light.kitchen_cans` | `pico_kitchen_cans_a`, `pico_kitchen_cans_b` | Main kitchen task-lighting zone |
| Kitchen | `kitchen_nook` | Current | `#4` | 3 fixture bulbs | `govee_cloud_bulb_tbd` x3 | Cloud-only | `light.kitchen_nook` | `pico_kitchen_nook_main` | Separate decorative or ambient zone |
| Kitchen | `kitchen_sink` | Current | `#5` | 1 can light above sink | `govee_local_api_a19_tbd` x1 | Local API | `light.kitchen_sink` | `pico_kitchen_sink_main` | Separate task-lighting zone |
| Foyer | `foyer_main` | Current | `TBD` | TBD | `govee_local_api_bulb_tbd` | Preferred local API | `light.foyer_main` | `pico_foyer_main` | Simple entry lighting |
| Hallway | `hallway_main` | Current | `TBD` | TBD | `govee_local_api_bulb_tbd` | Preferred local API | `light.hallway_main` | `baseline_input_tbd` | Motion behavior is draft only, not baseline |
| Living Room | `living_room_torchiere_future` | Planned | `TBD` | 1 future lamp | `govee_floor_lamp_tbd` | TBD | `light.living_room_torchiere_future` | `pico_living_room_future` | Planned smart-lighting path only |

## Control Input Inventory

| Control Input | Status | Intended Zone | Control Type | Suggested Device ID Placeholder | Notes |
| --- | --- | --- | --- | --- | --- |
| Kitchen Cans Pico A | Current | `kitchen_cans` | Pico | `pico_kitchen_cans_a` | First of 2 controllers for the same zone |
| Kitchen Cans Pico B | Current | `kitchen_cans` | Pico | `pico_kitchen_cans_b` | Second of 2 controllers for the same zone |
| Kitchen Nook Main Control | Current baseline placeholder | `kitchen_nook` | Pico or switch-equivalent input | `pico_kitchen_nook_main` | Replace if the final control input is not a Pico |
| Kitchen Sink Main Control | Current baseline placeholder | `kitchen_sink` | Pico or switch-equivalent input | `pico_kitchen_sink_main` | Replace if the final control input is not a Pico |
| Foyer Pico | Current | `foyer_main` | Pico | `pico_foyer_main` | Replace with actual Lutron device ID |
| Living Room Pico | Planned | `living_room_torchiere_future` | Pico | `pico_living_room_future` | Not active yet |
| Playroom Pico | Future | Future playroom zone | Pico | `pico_playroom_future` | Not active yet |

## Operational Notes

- `kitchen_cans` is the multi-controller kitchen zone and must not use state-based toggle logic.
- `kitchen_nook` is separate on purpose and should not be merged into a generic accent abstraction.
- `kitchen_sink` is separate on purpose and should not be silently bundled into `kitchen_cans`.
- The living room overhead fan light is not part of this smart lighting system.

## Follow-Up Checklist

- Replace placeholder entity IDs with confirmed Home Assistant entity names.
- Replace placeholder Pico or control-input IDs with actual Lutron or Home Assistant identifiers.
- Replace bulb model placeholders with the actual installed bulb models.
- Add real wall locations for the kitchen control inputs to the floorplan.
