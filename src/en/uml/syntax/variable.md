# Variables

Variables hold values that can be read or written. Definition:

```js
let name = value
```

This defines `name` with value `value`. `value` can be a `Float`, a `Rect`, or an expression that evaluates to one of those.

Variables can be redefined; only the last definition is used. After definition, you can use the variable when creating elements or defining other variables.

## Built-in variables

- `t`: current time in seconds
- `top`: ratio of actual height to actual width
- `o`: scroll offset
- `joined`: 1 if the user has joined the event, 0 otherwise
- `$h`: maximum scroll height; set this to limit how far the user can scroll

> [!NOTE]
> UML has no events; use `t`, `o`, and [button](./elements/btn.md) press times to add dynamics (animations, page changes, etc.).

## Global variables

Global variables can be read or written anywhere in the UML file. Definition:

```js
global name = @type
```

Here `type` can only be `btn`. You can still assign with `let`; the last assignment wins.

> [!NOTE]
> The event UI is redrawn every frame, so all variables are recomputed each frame. Some [button](./elements/btn.md) properties must persist across frames, so they use global variables.
