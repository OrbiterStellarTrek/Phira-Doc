# judgeLine

Each judge line has these fields:

| Field | Type | Description | Default | Version |
|:----------------:|:------------------------------:|:------------------------------------------------------------:|:--------------:|:----:|
| Group | int | [Group](./root.md#judgelinegroup) | 0 | - |
| Name | string | Line name | Untitled | - |
| Texture | string | Texture path relative to chart root; see [Texture](./extend.md#texture) | line.png | - |
| anchor | float[2] | Texture anchor; see [extend](./extend.md#anchor) | [0.5, 0.5] | 142 |
| eventLayers | [EventLayer](./event.md)[]? | Event layers (1–5); see [event](./event.md) | - | - |
| extended | [JsonObject](./extendEvent.md) | Extended events; see [extendEvent](./extendEvent.md) | - | - |
| father | int | Parent line; -1 = none | -1 | - |
| isCover | int | 1 = mask (notes on back side not rendered when not hit) | 1 | - |
| notes | [Note](./note.md)[] | Notes on this line | - | - |
| numOfNotes | int | Note count (incl. FakeNote, excl. Hold) | 0 | - |
| zOrder | int | Layer (z), range ±100 | 0 | - |
| attachUI | string? | UI binding; see [extend](./extend.md#attachui) | - | - |
| isGif | bool | Texture is GIF | false | 150 |
| posControl, sizeControl, skewControl, yControl, alphaControl | JsonArray | See [Controls](./controls.md) | - | - |
| bpmfactor | float | BPM factor (not editable in RPE) | 1.0 | - |
| rotateWithFather | bool | Child inherits parent rotation if true | true | 163 |

- Empty layers: in some versions the field was `null`; from some version (e.g. 143) empty layers have no field. If a layer has no events of a type, that event field is omitted. If all layers are empty, `eventLayers` may be omitted.
- Effective BPM = current BPM / bpmfactor (not ×).
- Parent nesting is allowed. Parent rotation affects child only if `rotateWithFather` is true; if the field is missing, treat as false (pre-163).
- `isCover` 1 = mask: notes on the back side of the line (or front when note `Above` ≠ 1) are not rendered until hit.

## Event interpolation

See the source doc for the Python example (Beat, LineEvent, EventLayer, Extended, JudgeLine, Rpe_Chart, load, GetState). Call `result.JudgeLineList[i].GetState(t, defaultColor, master)` to get line position, alpha, rotation, color, scaleX, scaleY, and text at beat `t`.
