# Kitchen Automation Spec

## Status

Current first-floor implementation area.

## Intent

Model the kitchen as 3 explicit lighting zones with simple, reliable behavior. The starting goal is not scene-heavy automation. The starting goal is to make the kitchen behave clearly and predictably with smart bulbs that remain continuously powered.

## Zones

- `kitchen_cans`
  4 can lights
  Main task-lighting zone
  Local API bulbs
  Controlled from 2 Pico locations
- `kitchen_nook`
  3 fixture bulbs
  Separate decorative or ambient zone
  Cloud-only bulbs
- `kitchen_sink`
  1 can light above the sink
  Separate task-lighting zone
  Local API bulb

## Control Model

- The 2 kitchen Pico remotes both control `kitchen_cans`.
- Pico presses should behave like familiar wall-switch actions.
- Pico presses do not remove power from any smart bulbs.
- Avoid toggle logic for `kitchen_cans` because the zone has multiple controllers.
- Prefer explicit `on` and `off` actions for the initial rollout.

## Initial Rollout

Current starter implementation should focus on:

- `kitchen_cans` on
- `kitchen_cans` off
- clear script and scene names matching real zones

This keeps the main kitchen task-lighting path dependable before adding anything more clever.

## Current Questions

- Whether `kitchen_sink` gets its own dedicated Pico control path or is controlled another way
- Whether `kitchen_nook` gets a dedicated Pico, a dashboard control, voice control, or scene-based control only
- Whether raise and lower behavior is worth implementing in the first rollout

## Planned Or Future Behavior

- More scene variety for cooking, evening, and cleanup
- Optional brightness raise or lower mappings
- Optional coordinated behavior between `kitchen_cans` and `kitchen_sink`

## YAML Expectations

- Use placeholder entity and device IDs if needed, but keep them named after the real kitchen zones.
- Keep comments where the real Lutron event payloads still need to be confirmed.
- Do not reintroduce vague labels like `main` or `accent`.
