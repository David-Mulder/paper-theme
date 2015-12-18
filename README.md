paper-theme
===
This is a fully functional proposal for a new basis for `paper-styles`. Scroll down for a demo and read on for the theory and the proposal.

The MD side
---
The current `paper-styles` is a poor reflection of the color section of the Material Design spec and lacks a lot of
 necessary variables. This proposal implements the following variables

| Base variable | MD spec | Description |
| ------------- | ------- | ----------- |
| `primary-color`, `primary-color-light`, `primary-color-dark`, `accent-color` | [Choose your palette](http://www.google.be/design/spec/style/color.html#color-ui-color-application) | Three shades of the primary color and 1 shade of the accent color should be chosen as the main colors |
| `primary-color-*`, `accent-color-*` | [Color palette](http://www.google.be/design/spec/style/color.html#color-color-palette) | The full color palettes should be available |
| `status-bar-color`, `app-bar-color`, `background-color`, `card-dialog-color` | [Themes](http://www.google.be/design/spec/style/color.html#color-themes) | These are shades of white or black (depending on the theme) used for backgrounds. |
| `inverse-card-dialog-color` | Toasts | Not specified in spec, but it's sensible that these should be black on white in a dark theme |

Next it needs to be possible to show text and components on top of these colors. The material design spec defines the colors and opacity of those components, but the base color (black or white) is dependent on the contrast<sup>1</sup>. In other words we need to define this base color for each variable. As there is no way to do this dynamically (e.g. this would be a lot simpler with CSS preprocessors) we end up defining the following set of variables for *each* of the above variables.

| Augment | MD spec | Description |
| ------- | ------- | ----------- |
| `text-on-*`, `secondary-text-on-*`, `disabled-on-*`, `divider=on-*` | [Use opacity for text, icons, and dividers](http://www.google.be/design/spec/style/color.html#color-ui-color-application) | Straight from the spec |
| `text-30-on-*` | [Track Off from Switch](http://www.google.be/design/spec/components/selection-controls.html#selection-controls-switch) | Base color with 30% in dark and 26% in light |

What do we still miss? It's still not possible this way to take 50% of a certain swatch (as is for example required by switches), and probably a lot more augments might still be necessary.

What about `<paper-theme>`?
---
We're talking about approxamatily 150 css variables and even more if new augments are added. That's far too much to define by hand, so that's where `<paper-theme>` comes in. This element defines all the variables for you and is as easy to use as the following statement:

    <paper-theme primary-palette="Indigo" accent-palette="Pink"></paper-theme>
    
Now, sometimes the official MD colors might not be good enough for you, so it's also possible to set custom hex colors which will automatically generate a palette for you (still need to add support for fully custom palettes):

    <paper-theme primary-palette="#673AB7" accent-palette="#073AB7"></paper-theme>

And lastly (as far as important features go) you can set the theme

    <paper-theme primary-palette="Indigo" accent-palette="Pink" theme="Dark"></paper-theme>

Additionally there is a `standard-styles.html` import that will set the styles of a number of elements to use the new variables, although this is mostly for demonstration purposes right now and not finished. 

Want to see it in action?
---
Well, check [this demo](http://david-mulder.github.io/paper-theme/components/paper-theme/demo/dark.html) here and explore the generated palettes [here](http://david-mulder.github.io/paper-theme/components/paper-theme/demo/custom-theme.html)

Notes
---

 1. The contrast calculation used is the http://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html spec, however this does not seem to match the MD spec and thus the
    luminance break off point has been manually aligned with the MD spec.