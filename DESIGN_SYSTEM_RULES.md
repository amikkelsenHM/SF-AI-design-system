# Design System Rules

This document serves as the instruction set for generating UI code for the Spaceflux project. All future AI sessions must adhere to these rules to ensure consistency.

## 1. Source of Truth
*   **Styles:** The design system is implemented in standard CSS variables and utility classes.
    *   `styles/variables.css`: Defines all colors, typography, and primitive tokens.
    *   `styles/typography.css`: Defines font faces and typography utility classes.
    *   `styles/components.css`: Defines the styling for core components (buttons, inputs, tables, pickers).
    *   `styles/charts.css`: Defines styling for charts and data visualization.
*   **Reference:** The file `index.html` contains the canonical HTML markup for all supported components.
    *   **RULE:** Always check `index.html` for the correct DOM structure and class names before generating new UI components.

## 2. Import Structure
When creating new HTML pages or components, always include the CSS files in the following order:

```html
<link rel="stylesheet" href="styles/variables.css">
<link rel="stylesheet" href="styles/typography.css">
<link rel="stylesheet" href="styles/components.css">
<link rel="stylesheet" href="styles/charts.css">
```

## 3. Naming Conventions & Usage

### Typography
Use the utility classes defined in `styles/typography.css` instead of raw font properties.
*   **Headings:** `.text-display-large`, `.text-heading-large`, `.text-heading-medium`
*   **Body:** `.text-body-large`, `.text-body-small`
*   **Labels/Overlines:** `.text-overline-large`, `.text-label`
*   **Links:** `.text-link-large`, `.text-link-small`

### Colors
Use CSS variables for all colors. Do not hardcode hex values.
*   **Surfaces:** `var(--color-surface-dark)`, `var(--color-surface-dark-progress)`
*   **Text:** `var(--color-on-surface-dark)`, `var(--color-on-surface-light)`
*   **Primary Brand:** `var(--color-primary-500)`
*   **Borders:** `var(--color-border-dark)`, `var(--color-border-focus)`

### Components
*   **Buttons:** Use `.btn` combined with `.btn-primary`, `.btn-secondary`, or `.btn-tertiary`.
*   **Inputs:** Use `.input-field` for text inputs. Wrap date picker inputs in `.date-picker-input-wrapper`.
*   **Data Tables (V2):**
    *   Container: `.table-container`
    *   Table: `.table-v2`
    *   Rows: Standard `thead > tr > th` and `tbody > tr > td`
    *   Badges: `.badge` with variants `.badge-success`, `.badge-warning`, `.badge-error`, `.badge-processing`.
*   **Dropdowns:**
    *   Structure: `.dropdown-container` > `.dropdown-trigger` (+ `.open`, `.error`, `.success`) > `.dropdown-menu` (+ `.open`) > `.dropdown-item` (+ `.selected`).
*   **Date Picker:** Follow the structure: `.date-picker` > `.date-picker-header` > `.date-picker-inputs` > `.date-picker-controls` > `.date-picker-grid`.
*   **Charts:**
    *   **Foundational Module:** `.chart-base` > `.chart-header` + `.chart-layout-container` > `.chart-layout` (containing `.chart-y-label-container` + `.chart-plot-area`) + `.chart-x-axis-container`.
    *   **Grid System:** `.chart-plot-area` contains `.chart-grid-line` (horizontal) and `.chart-grid-vertical`.
    *   **Bar Chart (Bi-directional):** `.bar-chart-container.bi-directional` > `.bar-group` > `.bar-value` (+ `.positive`/`.negative`, `.bar-1`/`.bar-2`/`.bar-3`).
    *   **Scatter Chart:** `.chart-plot-area` contains `.scatter-point` (+ sizes `.size-xs` to `.size-lg`, colors `.color-1` to `.color-3`).
    *   **Multi-Line Chart:** `.chart-plot-area` contains `<svg class="line-chart-svg">` with `<path class="line-path">` (+ `.color-1` to `.color-3`).

## 4. Extension Rules
*   If a new component is needed that does not exist in `reference_components.html`, try to compose it using existing primitives (CSS variables).
*   Do not introduce new hex values. Use the provided color palette variables.
*   Maintain the "Dark Mode" aesthetic as the default.

