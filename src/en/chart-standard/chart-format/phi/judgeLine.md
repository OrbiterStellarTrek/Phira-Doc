# judgeLine

Each judge line has these fields:

| Field name | Type | Description |
|:------------------------:|:---------:|:---------:|
| bpm | float | BPM for this line |
| notesAbove | JsonArray | Notes falling from front |
| notesBelow | JsonArray | Notes falling from back |
| speedEvents | JsonArray | Speed events |
| judgeLineMoveEvents | JsonArray | Move events |
| judgeLineRotateEvents | JsonArray | Rotate events |
| judgeLineDisappearEvents | JsonArray | Opacity events |

- **All event and note time fields use units `1.875 / bpm` seconds.**
- **Definitions:** "width unit" = `0.05625 * chart render width`; "height unit" = `0.6 * chart render height`.
- [Events](./event.md)
- [Note](./note.md)
