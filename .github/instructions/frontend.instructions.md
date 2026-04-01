---
applyTo: "*.html,*.css,*.js"
---

## Frontend Guidelines

- Use accessibility attributes (alt text, aria labels) and color schemes.
- Use responsive design for compatibility with mobile devices.
- Validate HTML structure and semantic elements

# Frontend Guidelines

## General

- Use vanilla HTML, CSS, and JS only — no frameworks or build tools
- Frontend files live in `src/static/` and are served by FastAPI as static assets
- Use semantic HTML elements (`<header>`, `<main>`, `<aside>`, `<footer>`, `<section>`)

## JavaScript

- Wrap all initialization logic inside a `DOMContentLoaded` event listener
- Use event delegation on parent containers instead of binding listeners to each child
- Prefer `const` over `let`; avoid `var`
- Use `async`/`await` for API calls; handle errors with `try`/`catch`
- Use `encodeURIComponent` when interpolating user input into URLs
- Cache DOM element references at the top of the `DOMContentLoaded` callback
- Group related state variables together (e.g., filter state, auth state)

## CSS

- Define all colors and theme values as custom properties in `:root`
- Reference custom properties (`var(--primary)`, `var(--border)`) instead of hard-coded color values
- Use `box-sizing: border-box` globally (already set via `*` selector)
- Use relative units (`rem`, `%`) for font sizes and spacing
- Follow mobile-first layout; add desktop overrides in `@media (min-width: 768px)` blocks
- Keep hover/focus effects in CSS transitions for smooth interaction feedback

## Accessibility

- Include `aria-label` attributes on icon-only buttons
- Use the `lang` attribute on the `<html>` element
- Ensure interactive elements are keyboard-accessible
- Provide visible focus styles for all focusable elements

## API Integration

- Call backend API endpoints using relative paths (e.g., `/activities`, `/auth/login`)
- Display user-facing error messages from `response.json().detail` on failure
- Show loading states while awaiting network responses
