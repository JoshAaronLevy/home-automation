# Home Automation

This repository documents and stages the first-floor smart lighting system built around Home Assistant Green, Lutron Pico remotes, and Govee bulbs. It is not a generic Home Assistant starter project. It is the planning and source-of-truth repo for the actual lighting architecture being implemented in the house.

## Design Philosophy

- Pico remotes preserve familiar wall-switch behavior.
- Smart bulbs stay continuously powered. Pico presses do not cut power to bulbs.
- Home Assistant is the central control brain.
- Multi-controller zones should use explicit `on` and `off` behavior, not clever toggle logic.
- Local API Govee bulbs are preferred for critical lighting paths.
- Cloud-only Govee bulbs are acceptable for decorative or non-critical zones.
- The initial rollout should be boring, clear, and reliable before it becomes advanced.

## Current Scope

Current first-floor implementation focus:

- Kitchen
- Foyer
- Hallway

Current kitchen zone model:

- `kitchen_cans`: 4 can lights, critical task-lighting zone, local API bulbs, controlled from 2 Pico locations
- `kitchen_nook`: 3 fixture bulbs, decorative/ambient zone, cloud-only bulbs
- `kitchen_sink`: 1 can light above the sink, separate task zone, local API bulb

## Planned And Future Scope

- Living room smart lighting is planned, but not active yet.
- The living room overhead fan light is not part of the smart lighting system.
- A future Govee torchiere and future Pico are likely for the living room.
- A playroom Pico is future-state only.
- Hallway motion behavior is not part of the initial reliable rollout unless explicitly promoted from draft.

## How To Treat Placeholders

- Placeholder entity IDs are intentional and should be replaced with the real Home Assistant names later.
- Placeholder Pico device IDs are intentional and should be replaced after the Lutron integration is confirmed.
- Comments marked `TODO` identify places where the real Home Assistant event payloads, entity IDs, or secrets still need to be filled in.
- Draft and future-state files should not be treated as already deployed behavior.

## Repository Layout

```text
docs/                 Architecture notes, room maps, device inventory, and room specs
home-assistant/       Starter YAML reflecting the real first-floor design
appdaemon/            Reserved for future Python logic if YAML becomes awkward
```

## Working Rules

1. Update the room spec before changing room behavior.
2. Keep reusable lighting actions in scripts and scenes, not duplicated across automations.
3. Prefer explicit zone names such as `kitchen_cans` over vague names like `main` or `accent`.
4. Clearly label anything that is planned, draft, or speculative.
5. Do not treat this repo as production-complete just because the YAML parses.

## Suggested Next Steps

1. Replace placeholder entity IDs in the kitchen, foyer, and hallway YAML.
2. Confirm the actual Pico button event payloads exposed by the Lutron integration.
3. Annotate the floorplan image with real Pico locations and zone boundaries.
4. Promote draft hallway logic only after the boring baseline behavior is working reliably.
