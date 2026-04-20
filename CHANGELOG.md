# Changelog

## 0.3.0 - 2026-04-17

Rebrand from "Public Safety 2026" to "Seiler 2026", restructure into `src/`, and overhaul mobile and tablet styling.

### Changed
- **Breaking:** Rename theme identifier from `public-safety-2026` to `seiler-2026` across slugs, text-domain, function prefixes, PHP namespace, pattern categories, and block names (e367e22)
- **Breaking:** Move theme files from repository root into `src/` (e367e22)
- Genericize pattern prose so the theme is division-agnostic (e367e22)
- Restore WP fluid typography for hero slider heading sizing (e367e22)
- Switch CI and release workflows to `npm install` to avoid bun's handling of optional-dep `file:` failures (2120593, 7ee85f9)
- Make `@wordpress/env` an optional dependency so CI can skip it (7fa2081)

### Added
- WooCommerce My Account FSE template (`src/templates/page-my-account.html`) with scoped styling (e367e22)
- Mobile and tablet responsive styles for nav overlay, search overlay, slider, footer, CTA banner, features pattern, and industry cards (e367e22)
- "> " prefix on mobile nav submenu items to indicate nesting (e367e22)
- `render_block_core/post-excerpt` filter suppressing empty excerpt wrappers (gutenberg#30571 workaround) (e367e22)
- GitHub Actions CI and Release workflows via `seiler-workflow-setup` (4260ba0, 2120593)
- Release workflow auto-detects prerelease flag for `v0.x` tags and tags containing a hyphen (4260ba0)
- GitHub Packages authentication in workflows via `SEILER_CLASSIC_PAT` (d1a6767)
- `CHANGELOG.md` (4260ba0)

### Removed
- Hardcoded skip-link from header template — WP core injects its own via `the_block_template_skip_link()` (e367e22)
- Duplicate `theme.css` enqueue on the frontend (e367e22)
- `test` job from release workflow — rely on pre-push hooks + CI (fe9aae7)
- `--omit=optional` flag from install commands — was skipping `lightningcss-cli` platform-specific binaries (815214e)

### Fixed
- Webpack build output recursion (`src/build/build/build/…`) from wp-scripts auto-discovering its own output (e367e22)
- Mobile nav overlay submenus expand inline instead of floating as desktop dropdowns (e367e22)
- Mobile and tablet search overlay is full-width up to 960px (e367e22)
- Footer stacks at `<= 980px`; `.footer-since-group` hidden on mobile; `.txt-sep` separators convert to line breaks at `<= 450px` (e367e22)
- Focus outlines on mobile nav overlay use `:focus-visible` so pointer taps don't leave lingering outlines (e367e22)
- Block validation errors in `hero-slider` pattern and `home` template (missing `"arrows": false` and `"level": 1`) (e367e22)
- Slider carousel arrows disabled at block level with CSS fallback (e367e22)
