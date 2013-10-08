# glslify-import #

A transform stream for [glslify](http://github.com/chrisdickinson/glslify)
that adds an `import` directive to your shaders.

Pull request to make this work is pending.

## Usage ##

Given a basic shader:

``` glsl
// main.frag
#pragma import: ./common.glsl

void main() {
  gl_FragColor = vec4(color, 1.0);
}
```

You can import `./common.glsl`:

``` glsl
// common.glsl
varying vec3 color;
```

And have the contents inlined into your shader:

``` glsl
varying vec3 color;

void main() {
  gl_FragColor = vec4(color, 1.0);
}
```

You can also use glslify pragmas and the like from your imported files as well.
Useful for the cases when you want to include a common "base" set of
definitions in your shaders without losing the niceties of glslify.