# Extended Features

Besides the official Phigros chart format, `pec`, and `rpe`, prpr supports additional chart features. These are available only in prpr and clients built on it:

- [Effects](./effect/index.md)
- [Video background](./video/index.md)

All such configuration must live in `extra.json` at the root of the chart package. To use these features, edit the JSON by hand. If you are not familiar with JSON, see e.g. [JSON tutorial](https://www.json.org/).

## BPM configuration

**Before using these features, you must set the chart BPM in `extra.json`.** Example:

```json
{
   "bpm": [
      { "time": [0, 0, 1], "bpm" : 200.0 },
      { "time": [10, 1, 2], "bpm" : 250.0 }
   ],
   ...
}
```

This means the chart starts at BPM `200`, then at 10.5 beats it changes to `250`.

## Animation variables

Configs often use animation variables. For example, in RPE, the X position event is just the X coordinate as an animation variable.

prpr supports two forms. The first is a single value (constant over time). The second is the same as in RPE: a list of `Event` objects. A single event looks like:

```json
{
	"startTime": [0, 0, 1],
	"endTime": [0, 0, 1],
	"easingType": 2,
	"easingLeft": 0.0,
	"easingRight": 1.0,
	"start": ...,
	"end": ...
}
```

`startTime` and `endTime` are the event start and end; `easingType` is the easing type; `easingLeft` and `easingRight` optionally clip the easing.

`start` and `end` are the variable values at start and end. The value type depends on the variable; it can be:

- `float`: single number
- `vec2`: 2D vector as a two-element array
- `color`: color as four integers 0–255, format `[R, G, B, A]`

Example: an animation variable that goes from `0` to `0.1` linearly between two times:

```json
[
	{
		"startTime": [2, 0, 1],
		"endTime": [4, 0, 1],
		"easingType": 2,
		"start": 0.0,
		"end": 0.1
	}
]
```
