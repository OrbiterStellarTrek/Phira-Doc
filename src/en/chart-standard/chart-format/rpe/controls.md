# Controls

Controls are an RPE feature that change note parameters by keyframes.

## Alpha Control

| Field | Type | Description | Default | Version |
|:------:|:-----:|:----------------------------------------------:|:---:|:----:|
| easing | int | Easing to next keyframe; see [table](./extend.md#easingType) | - | - |
| alpha | float | Note opacity | 1.0 | - |
| x | float | Note’s vertical distance from judge line | - | - |

- Combines with note `alpha`: `noteAlpha = noteAlpha * nowAlpha` (convert 0–255 to 0–1 first).

### Behavior

With alpha control keyframes, opacity is 0.5 before 100 y-units from the line, then eases (e.g. Out Sine) to 1.0 by the line.

## Size Control

| Field | Type | Description | Default | Version |
|:------:|:-----:|:----------------------------------------------:|:---:|:----:|
| easing | int | Easing; see [table](./extend.md#easingType) | 1 | - |
| size | float | Note size multiplier | 1.0 | - |
| x | float | Vertical distance from judge line | - | - |

- Controls actual note size (not just width). Does not affect Hold size.

### Behavior

Example: size 1.5× before 200 y-units, then eases to 1.0× at the line.

## pos Control (X Control)

| Field | Type | Description | Default | Version |
|:------:|:-----:|:----------------------------------------------:|:---:|:----:|
| easing | int | Easing; see [table](./extend.md#easingType) | 1 | - |
| pos | float | Multiplier for note `positionX` | - | - |
| x | float | Vertical distance from judge line | - | - |

- Example: positionX ×2 before 100 y-units, then eases to ×1 at the line.

## y Control

| Field | Type | Description | Default | Version |
|:------:|:-----:|:----------------------------------------------:|:---:|:----:|
| easing | int | Easing; see [table](./extend.md#easingType) | 1 | - |
| y | float | (TBD) | - | - |
| x | float | Vertical distance from judge line | - | - |

- Behavior TBD.

## Skew Control

| Field | Type | Description | Default | Version |
|:------:|:-----:|:----------------------------------------------:|:---:|:----:|
| easing | int | Easing; see [table](./extend.md#easingType) | 1 | - |
| skew | float | (TBD) | - | - |
| x | float | Vertical distance from judge line | - | - |

- No effect on Hold. Behavior TBD.
