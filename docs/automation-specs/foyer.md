# Foyer Automation Spec

## Status

Current first-floor implementation area.

## Intent

Keep foyer behavior boring and reliable. The foyer should respond to Pico presses with explicit lighting actions and should not depend on toggle logic or speculative scene behavior.

## Current Control Model

- A foyer Pico triggers explicit `on` and `off` actions for `foyer_main`.
- Smart bulbs remain continuously powered.
- Home Assistant translates the Pico button press into the desired light action.

## Initial Rollout

- `foyer_main` on
- `foyer_main` off
- optional simple foyer scenes for later reference, but not required for day one

## Scope Notes

- Foyer is current scope.
- Hallway is also current scope, but hallway motion logic should remain draft until deliberately enabled.
- If foyer and hallway are eventually coordinated, that behavior should be documented as an explicit rule, not inferred from a toggle.
