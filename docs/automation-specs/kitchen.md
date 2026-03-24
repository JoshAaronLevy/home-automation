# Kitchen Automation Spec

## Status

Current first-floor implementation area.

## Intent

Model the kitchen as 3 explicit lighting zones with baseline switch-equivalent behavior first. The goal is not a generic smart kitchen. The goal is to preserve familiar, boring, reliable control for the actual kitchen lighting plan while keeping smart bulbs continuously powered.

## Zones

- `kitchen_cans`
  4 can lights
  Main task-lighting zone
  Local API bulbs
  Floorplan label `#3`
  Controlled from 2 Pico locations
- `kitchen_nook`
  3 fixture bulbs
  Separate decorative or ambient zone
  Cloud-only bulbs
  Floorplan label `#4`
- `kitchen_sink`
  1 can light above the sink
  Separate task-lighting zone
  Local API bulb
  Floorplan label `#5`

## Baseline Control Model

- All kitchen zones should begin with explicit `on` and `off` behavior.
- Pico presses should behave like familiar wall-switch actions.
- Pico presses do not remove power from any smart bulbs.
- `kitchen_cans` must not use state-based toggle logic because it has 2 controllers.

### kitchen_cans

- Intended baseline inputs:
  `pico_kitchen_cans_a`
  `pico_kitchen_cans_b`
- Intended baseline behavior:
  explicit `on`
  explicit `off`
- Notes:
  This is the primary kitchen task-lighting zone and the most important kitchen control path to keep reliable.

### kitchen_nook

- Intended baseline input:
  `pico_kitchen_nook_main`
- Intended baseline behavior:
  explicit `on`
  explicit `off`
- Notes:
  This remains a separate decorative or ambient zone. Even though it is cloud-only, the control model should still be simple and switch-like.

### kitchen_sink

- Intended baseline input:
  `pico_kitchen_sink_main`
- Intended baseline behavior:
  explicit `on`
  explicit `off`
- Notes:
  This remains a separate task-lighting zone and should not be folded into `kitchen_cans` for convenience.

## Initial Rollout

Current starter implementation should focus on:

- `kitchen_cans` on
- `kitchen_cans` off
- `kitchen_nook` on
- `kitchen_nook` off
- `kitchen_sink` on
- `kitchen_sink` off
- clear script names matching real zones

This preserves familiar switch-like behavior before adding scenes or adaptive logic.

## Planned Or Future Behavior

- More scene variety for cooking, evening, and cleanup
- Optional brightness raise or lower mappings
- Optional coordinated behavior between `kitchen_cans` and `kitchen_sink`

## YAML Expectations

- Use placeholder entity and device IDs if needed, but keep them named after the real kitchen zones.
- Keep comments where the real Lutron event payloads still need to be confirmed.
- Do not reintroduce vague labels like `main` or `accent`.
