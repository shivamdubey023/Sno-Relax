# Theme Architecture

SNO-RELAX implements a single global theme system to ensure consistent visuals and accessibility across the application.

## Design
- A `ThemeContext` (React Context) is mounted at the root of the client app and manages three canonical modes: `brand` (application default), `dark`, and `light`.
- On theme change, a single source of truth applies CSS variables (tokens) to `document.documentElement` (root), ensuring all CSS and components that reference variables update immediately.
- The chosen theme is persisted to `localStorage` with key `sno_theme` and is respected across app reloads. If the user has no saved preference, the server-configured theme (admin setting) is fetched and applied as fallback.

## Tokens & Aliases
- Tokens are named variables like `--bg-primary`, `--text-primary`, `--accent-primary`, `--divider`, `--mood-mid`, etc.
- Backwards-compatible aliases (e.g., `--app-background`, `--chat-paper-bg`) are also applied to ease migration.

## Best Practices for Contributors
- Prefer theme tokens over hard-coded color values in both CSS and inline styles. When inline colors are unavoidable, read variables from `getComputedStyle(document.documentElement)` so theme changes propagate.
- Avoid page-local theme states. Use `useTheme()` or theme tokens to ensure a single global source.
- Document new tokens in this file and add a small unit/integration test that verifies root variables change when theme is set.

This architecture was put in place to satisfy the project requirement that theme changes in Settings update the entire application instantly and predictably.