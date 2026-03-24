# Device Inventory

This file tracks the first-floor lighting hardware, control roles, and placeholder Home Assistant naming. Placeholder IDs are deliberate until the real entities and device IDs are confirmed.

## Controllers And Core Devices

| Device | Status | Function | Integration | Notes |
| --- | --- | --- | --- | --- |
| Home Assistant Green | Current | Central automation brain | Home Assistant OS | Routes all lighting decisions |
| Lutron Hub | Current | Pico event bridge | Lutron Caseta | Delivers Pico button events to Home Assistant |

## Current First-Floor Lighting Zones

| Room | Zone | Status | Function | Control Class | Suggested Entity Placeholder | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Kitchen | `kitchen_cans` | Current | Main task-lighting zone | Local API | `light.kitchen_cans` | 4 can lights, controlled from 2 Pico locations |
| Kitchen | `kitchen_nook` | Current | Decorative or ambient zone | Cloud-only | `light.kitchen_nook` | 3 fixture bulbs |
| Kitchen | `kitchen_sink` | Current | Single-light task zone | Local API | `light.kitchen_sink` | 1 can light above the sink |
| Foyer | `foyer_main` | Current | Entry lighting | Preferred local API | `light.foyer_main` | Replace with actual entity or group |
| Hallway | `hallway_main` | Current | Hallway lighting | Preferred local API | `light.hallway_main` | Motion behavior is still draft/future |

## Pico Remotes

| Location | Pico Name | Status | Primary Zone Or Function | Suggested Device ID Placeholder | Notes |
| --- | --- | --- | --- | --- | --- |
| Kitchen location 1 | Kitchen Cans Pico A | Current | `kitchen_cans` on or off | `pico_kitchen_cans_a` | Exact wall location to be documented on floorplan |
| Kitchen location 2 | Kitchen Cans Pico B | Current | `kitchen_cans` on or off | `pico_kitchen_cans_b` | Second controller for the same zone |
| Foyer | Foyer Pico | Current | `foyer_main` on or off | `pico_foyer_main` | Replace with actual Lutron device ID |
| Living room | Living Room Pico | Planned | Future living room smart-lighting control | `pico_living_room_future` | Not active yet |
| Playroom | Playroom Pico | Future | Future playroom control | `pico_playroom_future` | Not active yet |

## Room Notes

- Kitchen cans and kitchen sink are critical lighting paths and should stay on local API bulbs.
- Kitchen nook is intentionally separated because it is decorative and can tolerate cloud-only control.
- The living room overhead fan light is not part of this smart lighting system.

## Follow-Up Checklist

- Replace placeholder entity IDs with confirmed Home Assistant entity names.
- Replace placeholder Pico IDs with actual Lutron device identifiers.
- Add the real Pico wall locations to the room map and floorplan.
- Record whether each zone is represented by a native entity, a light group, or both.
