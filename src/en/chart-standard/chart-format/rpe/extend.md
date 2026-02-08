# Extended Parameters

## attachUI

RPE-only. Binds UI elements to the judge line so you can control position, opacity, size, etc.

| Value | UI element | RPE setting number | Anchor |
|:-----------:|:----------------:|:----------:|:----------:|
| pause | Pause button | 1 | top-left |
| combonumber | Combo number | 2 | center (opacity follows Alpha when bound; shown when combo ≥ 3) |
| combo | "combo" text | 3 | center (same) |
| score | Score | 4 | top-right |
| bar | Progress bar | 5 | left center (before 1.4.0 this was the white bar left of title) |
| name | Chart name | 6 | bottom-left |
| level | Chart level | 7 | bottom-right |

When UI is bound, the judge line is hidden; UI can be animated like a child line (including angle and opacity). The line’s actual position is unchanged.

## anchor

RPE-only. Judge line texture anchor (for text events). In RPE: top toolbar, second page; two numbers separated by space. It is `float[2]` for texture x,y. x default 0.5 (center); 1 = texture left, 0 = right. y default 0.5; 1 = down, 0 = up. Also affects custom texture position.

## Texture

RPE can set the judge line `Texture` to change its texture. Custom texture is not tinted by AP/FC colors. Without scaleX/scaleY events, texture scale defaults to 1. GIF textures are controlled by [gifEvents](./extendEvent.md#gifevents) (from version 150).

## easingType

RPE easing type codes:

| Value | Easing |
|:--:|:--------------:|
| 1 | Linear |
| 2 | Out Sine |
| 3 | In Sine |
| 4 | Out Quad |
| 5 | In Quad |
| 6 | In Out Sine |
| 7 | In Out Quad |
| 8 | Out Cubic |
| 9 | In Cubic |
| 10 | Out Quart |
| 11 | In Quart |
| 12 | In Out Cubic |
| 13 | In Out Quart |
| 14 | Out Quint |
| 15 | In Quint |
| 16 | Out Expo |
| 17 | In Expo |
| 18 | Out Circ |
| 19 | In Circ |
| 20 | Out Back |
| 21 | In Back |
| 22 | In Out Circ |
| 23 | In Out Back |
| 24 | Out Elastic |
| 25 | In Elastic |
| 26 | Out Bounce |
| 27 | In Bounce |
| 28 | In Out Bounce |
| 29 | In Out Elastic (not usable in speed events in some versions; restored in 1.7.0) |

See e.g. [easings.net](https://easings.net/) for curves. Python easing implementations are in the source doc.
