# beat

`beat` is the time unit for all RPE events. It is an `int[3]`, displayed in RPE as `[0]:[1]/[2]`. For a single BPM:

```csharp
double beat = RPEBeat[1] / RPEBeat[2] + RPEBeat[0];
double seconds = 60 / BPM * beat;
```

For multiple BPMs see the Python example.

## Python example

- Let `self.BPMList` be a `list[BPMEvent]` with `BPMEvent` having `startTime: Beat` and `bpm: float`.
- In `sec2beat`, `t` is time in seconds, `bpmfactor` is the judge line’s `bpmfactor`.
- In `beat2sec`, `t` is in beats, `bpmfactor` as above.
- Then `beat2sec(sec2beat(x)) == x` and `sec2beat(beat2sec(x)) == x` should both be True. Implementation as in the source doc.
