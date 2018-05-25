# SCSS foundations
This is a collection of helpful SCSS systems for starting new projects. It contains systems for:
* colors
* typography
* spacing

Update the SCSS maps to automatically generate utility classes and functions that return values for use inside of SCSS declarations.

## Getting started

## Colors
```
/* colors.scss * /

// Define your color palette in the SASS map and remove the ones you don't want
$colors: (
  brand: #178AFF,
  brand-dark: #001B37,
  grey-100: #FAFAFB,
  grey-200: #F1F5F9,
  grey-300: #DAE0E7,
  grey-400: #667881,
  grey-500: #263238,
  white: #fff,
);

// Use the colors in your SCSS code:
.some-class {
  background-color: color(brand);
}
```

## Spacing

```
/* spacing.scss * /

// Define your spacing sizes in the SASS map and remove the ones you don't want
$spacing: (
  xs: 4px,
  s: 8px,
  m: 12px,
  l: 20px,
  xl: 32px,
);

// Use the spacing sizes in your SCSS code:
.some-class {
  margin-bottom: spacing(xs);
}

// Or use utility classes in your HTML
<div class="spacing-stack-s"> This applies bottom margin of 8px </div>
<div class="spacing-inline-s"> This applies right margin of 8px </div>
<div class="spacing-inset-s"> This applies padding of 8px </div>

```

## Typography
```
// Define your tap styles in the SASS map

$font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;

// Add your weights here
$type-weights: (
  regular: 400,
  bold: 500
);
// Gets a type weight e.g. type-weight(bold);
@function type-weight($weight) {
  @return map-get($type-weights, $weight)
};

$type-colors: (
  default: color(grey-400),
  subdued: color(grey-300),
  link: color(brand)
);

// Get and set the type color e.g. type-color(link);
@function type-color($color) {
  @return map-get($type-colors, $color)
};

$type-styles: (
  body: (
    font-size: 16px,
    line-height: 24px,
    font-weight: type-weight(regular),
    color: type-color(subdued)
  ),
  link: (
    color: color(brand)
  ),
  h1: (
    font-size: 32px,
    line-height: 36px,
    font-weight: type-weight(regular),
    color: type-color(default)
  ),
  h2: (
    font-size: 24px,
    line-height: 28px,
    font-weight: type-weight(regular),
    color: type-color(default)
  ),
  h3: (
    font-size: 18px,
    line-height: 24px,
    font-weight: type-weight(regular),
    color: type-color(default)
  ),
  h4: (
    font-size: 16px,
    line-height: 20px,
    font-weight: type-weight(regular),
    color: type-color(default)
  ),
  small: (
    font-size: 14px,
    line-height: 18px,
  ),
  subdued: (
    color: type-color(subdued)
  ),
  strong: (
    font-weight: type-weight(bold)
  )
);

// Include the type mixin in your SCSS code
.some-class {
  @include type(h4);
}
```
