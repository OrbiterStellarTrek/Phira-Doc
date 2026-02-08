# Note

Each note has these parameters:

| Field | Type | Description | Unit |
|:-------------:|:-----:|:---------------------------------------------------------------:|:-------------:|
| type | int | Note type | - |
| time | int | Note time | `1.875 / bpm` |
| holdTime | float | Hold duration (hold only; 0.0 for others) | `1.875 / bpm` |
| positionX | float | Horizontal position | width unit |
| speed | float | For non-hold: note speed multiplier. For hold: tail speed; head speed is always 1 | - |
| floorPosition | float | Distance from judge line when judged (for computation) | height unit |
