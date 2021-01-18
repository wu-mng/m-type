# m-type

is a tool to easily and quickly set-up typography for the web: provided with a few values, it will automatically generate a baseline grid and a modular scale.

The grid establish the vertical rhythm of the page, allowing for visual consistency of spacing and text, while the scale determines the proportional size of the elements, where each value is a factor of the preceding one.

## demo

**[https://wu-mng.gitlab.io/m-type](https://wu-mng.gitlab.io/m-type)**

## requirements

[Sass](https://sass-lang.com/install) should be installed in your system.

## basic usage

Open `_config.scss`, select one of the examples, or insert custom values (see below); then compile: `sass _config.scss style.css`.

## custom values

- `$brekapoints: (phablet: 576px, tablet: 768px, laptop: 992px, desktop: 1200px);`
  
  At each of these screen sizes the layout will change, adapting to the device.
  
  There's usually no need to modify this option, since these are pretty much standard sizes.

- `$containers: (phablet: 480px, tablet: 640px, laptop: 720px);`
  
  This sets the width of the paragraph at each `$breakpoint`.

- `$scale: 1.2;`
  
  This value will determine font-size and spacing of the headings, and of any text element other than body text.
  
  Pick a scale from those listed in `_config.scss`, or put any number that makes sense. Note that you can use different scales for different devices (see `$scales` below): in that case this value will be used for smaller screens (mobile phones).

- `$scales: (tablet: 1.25, laptop: 1.333); `
  
  You can set extra scales for different devices: the keys are `phablet, tablet, laptop, desktop`, same as in `$breakpoints`. Each scale will come into effect at the screen widths set in`$breakpoints`.
  
  As a general rule, values like `1.067` to `1.2` are good for mobile phones; `1.2` to `1.333` for tablets; `1.25` to `1.414` for laptops; `1.333` to `1.618` for desktop screens.

- `$stranded: false;`
  
  If set to true, 'stranded' intervals will be inserted between the scale's sizes, resulting in a more compact vertical layout (and in smaller headings).
  
  This can be practical when using 'big' scales like `1.618` (a.k.a. `$golden-ratio`).

- `$font-size: 16px;`
  
  This is the 'root' font that - together with `$line-spacing` and `$grid-points` - will determine line-height and margin of the body text, affecting the vertical spacing of the page.

- `$font-sizes: (laptop: 18px);`
  
  You might want larger fonts for larger screens.
  
  Again, the keys you can use are the ones from `$breakpoints`. The value(s) inserted must be bigger than `$font-size`.

- `$line-spacing: 1.5;`
  
  This stands for the approximate distance between the lines of the grid (a.k.a 'leading'). Note that the actual line-height in any case will be a multiple of `$grid-points`.

- `$grid-points: 8;`
  
  The height of each row in the baseline grid, expressed in points.
