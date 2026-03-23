# Device Inventory

Use this file to track the real hardware, integrations, and Home Assistant entity IDs as they are created.

## Hubs and Controllers

| Device | Role | Integration | Notes |
| --- | --- | --- | --- |
| Home Assistant Green | Core automation host | Home Assistant OS | Primary runtime |
| Lutron Hub | Pico bridge | Lutron Caseta | Receives button events |

## Pico Remotes

| Room | Friendly Name | Expected Device ID | Buttons Used | Notes |
| --- | --- | --- | --- | --- |
| Kitchen | Kitchen Main Pico | `pico_kitchen_main` | On, Raise, Lower, Off | Placeholder device ID |
| Foyer | Foyer Pico | `pico_foyer_main` | On, Off | Placeholder device ID |
| Living Room | Living Room Pico | `pico_living_room_main` | On, Scene, Off | Placeholder device ID |

## Lighting Entities

| Room | Friendly Name | Home Assistant Entity | Type | Notes |
| --- | --- | --- | --- | --- |
| Kitchen | Kitchen Main Lights | `light.kitchen_govee_main` | Light | Replace with real entity |
| Kitchen | Kitchen Accent Lights | `light.kitchen_govee_accent` | Light | Optional accent zone |
| Foyer | Foyer Lights | `light.foyer_govee_main` | Light | Replace with real entity |
| Hallway | Hallway Lights | `light.hallway_govee_main` | Light | Replace with real entity |
| Living Room | Living Room Lights | `light.living_room_govee_main` | Light | Replace with real entity |

## Follow-Up Checklist

- Replace all placeholder device IDs with actual integration identifiers.
- Note which buttons support single press, double press, and hold.
- Capture firmware model details if any device behavior differs by hardware revision.
