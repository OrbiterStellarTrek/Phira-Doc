# `glitch`

Glitch / corruption effect. Produces random flicker over time.

![Example](image/glitch.png)

## Parameters

- `power` (float, default `0.3`): Glitch strength.
- `rate` (float, default `0.6`, range 0–1): Flicker rate; 0 = never, 1 = always.
- `speed` (float, default `5.0`): Speed of the glitch animation.
- `blockCount` (float, default `30.5`): Approximate number of offset bands (see image).
- `colorRate` (float, default `0.01`, range 0–1): Chromatic offset distance.
