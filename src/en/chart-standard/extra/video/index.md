# Video Background

In prpr you can play a video as the background; audio from the video is not played. Video files are often large, and prpr’s chart upload limit is 10MB, so charts with large BGAs may fail to upload. If you use video background, prefer short clips and compress the video (e.g. remove the audio track).

## Format

Add a `videos` array to `extra.json`. Each element is a `Video`:

### Video

```json
{
	"path": "bga.mp4",
	"time": [0, 0, 1],
	"scale": "cropCenter",
	"alpha": 1.0,
	"dim": 0.3
}
```

`path` is required (path to the video file). The other four fields are optional.

`time` is the start time in beats.

`scale` is how the video is scaled for different aspect ratios:

- `cropCenter` (default): scale uniformly until the video fills the screen (may crop)
- `inside`: scale uniformly so the whole video fits on screen
- `fit`: stretch to fill the screen

`alpha` and `dim` are opacity (if transparent, the illustration shows underneath) and dim amount. Both can be [animation variables](../index.md#animation-variables).
