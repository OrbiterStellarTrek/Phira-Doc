# Custom Shaders

Effect shaders are fragment shaders. You can write your own and ship them in the chart package. In the `shader` field use `/path/to/shader`; the leading `/` is required to distinguish custom from built-in shaders.

Use GLSL 1.00 for compatibility.

## Built-in variables

prpr provides:

```glsl
varying vec2 uv; // texture UV
uniform vec2 screenSize; // screen size (full screen, not just chart area)
uniform sampler2D screenTexture; // screen texture (full screen)
uniform float time; // chart time in seconds
```

These exist but are not meaningful in the fragment shader; avoid reusing their names:

```glsl
uniform mat4 Model;
uniform mat4 Projection;
uniform vec2 UVScale;
```

## Shader parameters

To expose parameters from the chart, define uniforms like:

```glsl
uniform type name; // %def%
```

`type` is the type (`float`, `vec2`, `vec4` supported); `name` is the name; `def` is the default. All three are required.

## Example

This example tints the screen red according to `factor`:

```glsl
#version 100
precision mediump float;

varying lowp vec2 uv;
uniform sampler2D screenTexture;

uniform float factor; // %0.5% 0..1

void main() {
  gl_FragColor = mix(texture2D(screenTexture, uv), vec4(1.0, 0.0, 0.0, 1.0), factor);
}
```
