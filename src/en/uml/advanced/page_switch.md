# Page switching

To have multiple “pages” in an event, place content for other pages off-screen and move all elements to simulate page changes.

Example layout for a grid of pages (e.g. 4×3 plus extra):

```text
            |-----------|
            |   3, 2    |
            |           |
            |-----------|
            |   2, 2    |
            |           |
|-----------|-----------|-----------|-----------|
|   1, 1    |   1, 2    |   1, 3    |   1, 4    |
|           |           |           |           |
|-----------|-----------|-----------|-----------|
```

Place an anchor (e.g. `o`) at the top-left of each page to compute positions. Use variables like `page_offset_x_1`, `page_offset_y_1`, etc. for the first anchor; other pages are positioned relative to it, so when the first anchor moves, everything else moves with it.

Use `#>if` to control when elements on other pages are drawn (e.g. so content above the current page is not visible on the first screen after a vertical switch).

Define buttons for “next/previous page” and use each button’s `last` (press time) to compute the offset values with an animation (e.g. easeInOutQuad). The number in each button id can indicate which page it belongs to.

Full UML for this pattern (variables for horizontal/vertical offsets, anchors o11–o14, o22, o32, and nav buttons with `last`-based animation) is in the source doc. Set `$h` to limit scroll height (e.g. `2 * top - 0.02`).
