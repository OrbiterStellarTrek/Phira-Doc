# Data types

UML has these types:

## Float

Single-precision float. Any numeric literal is a Float.

## Rect

Rectangle, defined as `[left, top, width, height]` (top-left x, top-left y, width, height).

After definition, a Rect has read-only properties:

- `Rect.l` or `Rect.x`: left (x)
- `Rect.t` or `Rect.y`: top (y)
- `Rect.w`: width
- `Rect.h`: height
- `Rect.r`: right (x)
- `Rect.b`: bottom (y)
- `Rect.cx`: center x
- `Rect.cy`: center y

## Bool

Boolean: `true` or `false`. Currently only used in element attributes.

## String

Double-quoted text. Used for button actions, colors, URLs:

- **Color**: hex RGB or ARGB (e.g. `"#ff0000"`, `"#7fffffff"`) or name: `"white"`, `"black"`, `"red"`, `"blue"`, `"yellow"`, `"green"`, `"gray"`.
- **Action**: button action. Values: `"join"` (join event), `"open:url"` (open URL).
- **URL**: web address.
