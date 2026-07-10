# Warm Palette Design

## Objective

Apply the supplied warm palette to the complete website while preserving its
existing HTML structure, content, and responsive layout.

## Palette

- Coral: `#F97350`
- Yellow: `#FAD06C`
- Warm white: `#F7F2E5`
- Taupe: `#B7AC9A`

## Visual System

- Use warm white as the page background.
- Use a near-black warm neutral for primary text to preserve reading contrast.
- Render the sticky navigation on a translucent warm-white surface with a taupe
  divider.
- Use coral for links and interactive highlights. Its hover state will use a
  darker warm neutral for clear feedback.
- Render project cards on a lighter surface with taupe borders. On hover, keep
  the existing upward movement and change the border to coral.
- Use taupe for secondary text, section dividers, and footer text.
- Reserve yellow for subtle secondary emphasis only, avoiding low-contrast body
  text.

## Scope

Only `css/style.css` will change. No content, markup, JavaScript behavior, or
responsive breakpoints will be altered.

## Verification

- Confirm the stylesheet contains no remaining dark-theme colors.
- Open the site locally and verify readable text, persistent sticky navigation,
  responsive project-card stacking, and clear link/card hover feedback.
