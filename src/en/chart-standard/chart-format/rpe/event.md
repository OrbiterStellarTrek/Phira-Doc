# Event

This page describes **normal** judge line events. For special events see [Extended events](./extendEvent.md).

- RPE has five normal event types: `moveXEvents`, `moveYEvents`, `rotateEvents`, `alphaEvents`, `speedEvents`. Each is a `JsonArray`; missing event types have no field (not an empty array).

Each normal event (except speed) has these fields:

| Field | Type | Description | Default | Version |
|:------------:|:-----------------:|:----------------------------------------------------------------------------------------------------------------------:|:----------------------:|:----:|
| bezier | int | 0 = no bezier, 1 = bezier | 0 | - |
| bezierPoints | float[4] | Bezier control points when bezier=1 | [0,0,0,0] | - |
| easingLeft | float | Easing left bound, 0–1 | 0.0 | - |
| easingRight | float | Easing right bound, 0–1 | 1.0 | - |
| easingType | int | Easing type; see [extend](./extend.md#easingType) | 1 | - |
| linkgroup | int | - | - | - |
| start | float | Value at start | - | - |
| startTime | [beat](./beat.md) | Start time | - | - |
| end | float | Value at end | - | - |
| endTime | [beat](./beat.md) | End time | - | - |

- Origin at screen center; X range -675–675, Y -450–450.
- Alpha: 0 = transparent, 255 = opaque. Negative alpha hides the line and all its notes (deprecated but still works).

::: danger
Speed events support all easing fields from version 162 but not bezier. RPE 1.7.0 reverted speed event easing to easing the speed value itself; behavior may vary.
:::

- Negative speed makes notes move upward; for Hold, the whole note can appear when the tail appears. This may differ from official behavior.

## Python example (no bezier)

Define `rpe_easing.py`, `Beat`, `LineEvent`, and `easing_interpolation` as in the source. Then `GetEventValue(t, es, default)` returns the interpolated value for time `t` from the event list `es`.
