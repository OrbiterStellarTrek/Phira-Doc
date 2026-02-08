# Note

Each note has these parameters:

| Field | Type | Description | Default | Version |
|:------------------------------------------:|:-----------------:|:----------------------------------------------------:|:---------------:|:----:|
| above | int | 1 = from front of line, other = from back | 1 | - |
| alpha | int | Opacity; 0 transparent, 255 opaque | 255 | - |
| endTime | [beat](./beat.md) | End time; for type 2 (Hold) = Hold end, else = startTime | - | - |
| startTime | [beat](./beat.md) | Start time; for Hold = Hold start, else = endTime | - | - |
| isFake | int | 1 = fake, other = real | 0 | - |
| positionX | float | X offset from line center | - | - |
| size | float | Size multiplier (in RPE this is width only) | 1.0 | - |
| speed | float | Speed multiplier | 1.0 | - |
| type | int | Note type; see table below | - | - |
| visibleTime | float | Visible time in seconds | 999999.0 | - |
| yOffset | float | Y offset (positive = up); also moves hit effect | 0 | - |
| hitsound | string? | Custom hit sound path relative to chart root | - | 142 |
| judgeArea | float | Judge area width multiplier | 1.0 | 170 |
| tint or color | int[3] | Note color [R,G,B] 0–255 | [255,255,255] | 170 |
| tintHitEffects | int[3]? | Hit effect color [R,G,B] | [255,255,255] | 170 |

- In RPE, `above`: Hold from back is 2, other notes 0; 1 = always from front.
- `hitsound` is absent when no custom sound.
- Fake notes: no judgment, no hit effect/sound, no score, no density; Hold always shows as unhit.
- Color: `noteColor = noteColor * color` (vertex color multiply).

::: danger
The color field was renamed: `color` was used in beta, then `tint`; both may appear. Definition unchanged; handle both for compatibility.
:::

- `tintHitEffects`: when present, hit effect uses this color for both Good and Perfect (vertex color on original texture).

## Note types

| Value | Description |
|:-------:|:-----:|
| 1 | Tap |
| 2 | Hold |
| 3 | Flick |
| 4 | Drag |
| Default | Tap |
