# Extended Events

This page describes RPE extended events (storyboard), the fifth layer in the event editor. Each event type is a `JsonArray`. **Except `inclineEvents`, event types that are unused have no field.**

## colorEvents

Color events for judge line or texture. Same common fields (bezier, bezierPoints, easingLeft, easingRight, easingType, linkgroup, startTime, endTime). `start` and `end` are `int[3]` RGB (0–255).

## scaleXEvents

X-scale events for judge line, texture, or text width. Common fields plus `start`/`end` (float, default 1).

## scaleYEvents

Y-scale events. Same structure as scaleX.

## textEvents

Text display. Common fields plus `start`/`end` (string) and `font` (string). From 152, `font` is omitted when using default `cmdysj`. Before 152, `font` defaulted to `cmdysj`. Easing on text may be ineffective or cause undefined behavior/crash ([issue](https://github.com/TeamFlos/phira/issues/252)). `%P%` in text lets the number update with easing. Judge lines with text events are always hidden (only text shown) and custom texture is cleared. Without color events, text is white. From 153, `\n` in text is supported.

## paintEvents

Paint events; replaced by shader editing in 143, so not editable. Had the same common fields and start/end for brush size. Behavior TBD.

## gifEvents

GIF playback progress (added with GIF judge line texture in 150). Fields: easingType, linkgroup, start, startTime, end, endTime. Without gifEvents, GIF loops. Progress 0 = first frame, 1 = last; outside that range loops. No gifEvents at current time also loops. Text events clear this texture. GIFs over 15MB can cause RPE to fail decoding on load. When texture is GIF, speed events are replaced by this event editor, so they don’t coexist. gifEvents on other layers are ignored; RPE may flag them.

## inclineEvents

Incline (Z tilt). Likely deprecated; a placeholder event may exist under `extended`. Cannot be edited in RPE. Start/end values are Z tilt angle. Behavior TBD.
