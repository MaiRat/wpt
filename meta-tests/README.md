# Meta-Tests: Consolidated Thematic Test Pages

## Overview

This directory contains **meta-tests** — larger, thematic test pages that
combine multiple related atomic tests into integrated suites. These pages
provide an additional layer of broad, cross-feature testing on top of the
existing granular tests in the repository.

> **Important:** Meta-tests are strictly additive. No existing atomic tests
> are removed, replaced, or skipped. Each meta-test page exercises multiple
> features together to reveal integration issues that individual atomic tests
> may not catch.

## Categories

| Category | Directory | Description |
|----------|-----------|-------------|
| **CSS / Acid4** | `css/` | Combined CSS feature tests inspired by Acid2 and Acid3 |
| **DOM** | `dom/` | Integrated DOM manipulation, traversal, and event tests |
| **Graphics** | `graphics/` | SVG rendering, Canvas drawing, and image format tests |
| **Media** | `media/` | Audio and video playback, codec, and API tests |
| **Forms** | `forms/` | Input types, constraint validation, form submission |
| **Web APIs** | `web-apis/` | Fetch, Web Storage, URL, Encoding, and Streams |
| **Accessibility** | `accessibility/` | ARIA roles, states, properties, keyboard focus |

### Planned Categories (future work)

- **JavaScript/ECMAScript** — High-level JS behavioral and compliance tests
- **Security** — CSP, CORS, and XSS vector tests
- **Performance** — Macro-level benchmarks (TBD)

Categories that grow too large should be subdivided (e.g., `dom/events/`,
`dom/manipulation/`; `graphics/svg/`, `graphics/canvas/`).

## Mapping to Atomic Tests

Each meta-test page documents the atomic tests it covers through HTML
comments at the top of the file and `<link rel="help">` elements pointing
to the relevant specifications. The mapping follows this convention:

```html
<!--
  Meta-test: css/acid4.html
  Covers atomic tests in:
    - css/css-flexbox/
    - css/css-grid/
    - css/css-color/
    - css/css-backgrounds/
    ...
-->
```

## Contributing

1. Identify a group of related atomic tests that would benefit from
   integrated testing.
2. Create a new meta-test page in the appropriate category directory.
3. Use standard WPT conventions (`testharness.js`, `<link rel="help">`).
4. Document which atomic test areas are covered in comments.
5. Ensure the meta-test passes in at least two major browser engines.

## Design Principles

- **Additive only** — Never remove or modify existing atomic tests.
- **Self-contained** — Each meta-test page runs independently.
- **Spec-linked** — Every test links to the specification it validates.
- **Cross-feature** — Tests should exercise interactions between features
  that atomic tests cover in isolation.
