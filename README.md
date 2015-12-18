paper-theme
===
This is a fully functional proposal for a new basis for `paper-styles`

The MD side
---
The current `paper-styles` is a poor reflection of the color section of the Material Design spec and lacks a lot of
 necessary variables. This proposal implements the following variables

| Base variable | MD spec | Description |
| ------------- | ------- | ----------- |
| `primary-color`, `primary-color-light`, `primary-color-dark`, `accent-color` | [Choose your palette](http://www.google.be/design/spec/style/color.html#color-ui-color-application) | Three shades of the primary color and 1 shade of the accent color should be chosen as the main colors |
| `primary-color-*`, `accent-color-*` | [Color palette](http://www.google.be/design/spec/style/color.html#color-color-palette) | The full color palettes should be available |
| `status-bar-color`, `app-bar-color`, `background-color`, `card-dialog-color` | [Themes](http://www.google.be/design/spec/style/color.html#color-themes) | These are shades of white or black (depending on the theme) used for backgrounds.
