# Spaceflux Design System

A comprehensive design system for the Spaceflux project, featuring dark mode aesthetics, standardized typography, color palettes, and reusable UI components.

## Overview

This project serves as the single source of truth for the Spaceflux UI. It provides:
- **CSS Variables:** Centralized definition of colors, typography, and spacing.
- **Typography:** Utility classes for headings, body text, and labels.
- **Components:** Core UI elements like buttons, inputs, date pickers, and data tables.

## File Structure

- **`styles/variables.css`**: Defines all design tokens (colors, font families, spacing).
- **`styles/typography.css`**: Defines font faces and typography utility classes.
- **`styles/components.css`**: Contains styling for core components.
- **`reference_components.html`**: Canonical HTML markup for all supported components.
- **`DESIGN_SYSTEM_RULES.md`**: Guidelines for generating and extending UI code.

## Usage

To use the design system in your pages, include the CSS files in the following order:

```html
<link rel="stylesheet" href="styles/variables.css">
<link rel="stylesheet" href="styles/typography.css">
<link rel="stylesheet" href="styles/components.css">
```

## Guidelines

Please refer to `DESIGN_SYSTEM_RULES.md` for detailed instructions on:
- Naming conventions
- Extension rules
- Correct usage of utility classes and variables

## Development

Open `index.html` in a browser to view the visual showcase of the design system, including color palettes, typography examples, and interactive components.
