# Phigros Official Chart Root Structure

Phigros Official chart data and rendering are well established. All time units are in `128th notes`, i.e. `60 / 32 / bpm`, abbreviated below as `1.875 / bpm`.

## Chart root structure

### formatVersion

- `formatVersion` is an `int`.
- It affects how judge line move events are parsed.
- Possible values: `1`, `3`, or others.

### offset

- `offset` is a `float`.
- Chart delay in seconds.
- Positive: chart is ahead of music; negative: chart is behind.

### judgeLineList

- `judgeLineList` is a `JsonArray` of `JsonObject`s; each object is one [judge line](./judgeLine.md).
