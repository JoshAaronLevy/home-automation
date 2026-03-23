# Home Automation

This repository is the source of truth for the Home Assistant, Lutron Pico, and Govee lighting setup in our home. It centralizes configuration, room-level automation specs, device inventory, and future AppDaemon apps so changes can be documented before they are deployed.

## Goals

- Keep Home Assistant configuration organized by room and function.
- Document how Pico remotes map to lighting behaviors.
- Track devices, entity names, and room assumptions in one place.
- Provide a safe staging area for automation changes before they are copied to Home Assistant Green.

## Repository Layout

```text
docs/                 Architecture notes, room maps, and automation specs
home-assistant/       YAML configuration for automations, scripts, scenes, templates, and packages
appdaemon/            Future AppDaemon apps for logic that is easier to manage in Python
```

## Getting Started

1. Review [device-inventory](./docs/device-inventory.md) and replace placeholder devices/entities with the real ones from Home Assistant.
2. Update room specs in [automation-specs](./docs/automation-specs/) before changing automations.
3. Replace placeholder entity IDs in `home-assistant/automations`, `home-assistant/scripts`, and `home-assistant/scenes`.
4. Copy validated YAML into the matching location on Home Assistant Green or sync it using your preferred deployment workflow.
5. Test one room at a time and document any behavioral changes in [CHANGELOG.md](./CHANGELOG.md).

## Naming Conventions

- Use room-first names for files: `kitchen.yaml`, `foyer.yaml`, `living-room.yaml`.
- Use descriptive entity placeholders until final entities exist, for example `light.kitchen_govee_main`.
- Keep automations thin when possible; move reusable actions into scripts and scene definitions.
- Add room-level notes to `docs/automation-specs/` before introducing non-trivial behavior.

## Deployment Notes

- `home-assistant/configuration.yaml` is set up to include directories for automations, scripts, scenes, templates, and packages.
- Empty directories use `.gitkeep` so they remain in Git until real files are added.
- The included floorplan PNG is a placeholder asset. Replace it with the actual annotated floorplan when ready.

## Next Suggested Steps

- Create the real device/entity inventory from Home Assistant.
- Decide how each Pico button should behave for single press, hold, and off actions.
- Add room-by-room lighting scenes for day, evening, and night modes.
- Add validation or sync scripts later if you want this repo to deploy directly to Home Assistant Green.
