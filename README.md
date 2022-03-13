# scss-hsl-shades
Automatically generates color shades using scss

## Define colors as HSL
See HSL: https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl()

Define your colors in a list like below:
```scss
$lightColors: (
  primary: (
    h: 250,
    s: 100%,
    l: 100%,
  ),
  secondary: (
    h: 240,
    s: 20%,
    l: 79%,
  ),
  blue: (
    h: 214,
    s: 90%,
    l: 64%,
  ),
);
```

Use the `create-color-variables` function.

```scss
:root,
:root[light] {
  @include create-color-variables($lightColors);
}
```

After compiling your scss file, you'll have list.length * 5 total css variables.

for instance; above `primary` scss variable will become:

- var(--primary)
- var(--primary-light)
- var(--primary-lighter)
- var(--primary-dark)
- var(--primary-darker)

variables. All shades are relative to the main color.
