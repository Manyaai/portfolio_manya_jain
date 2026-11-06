# AGENTS.md

## Architecture
- Static site with no build step and no framework. `netlify.toml` publishes the `public/` directory.
- `public/index.html` holds the entire site: markup, inline `<style>`, and inline `<script>`.
- Content (profile details, projects, jobs, certificates, and so on) lives in JS data objects inside the script (e.g. `ME` for email, LinkedIn and location). Sections are rendered from that data by a small client-side hash router (`#home`, `#story`, `#contact`, ...) with a wipe transition.
- Light and dark themes use CSS custom properties on `:root`, which respect `prefers-color-scheme` and a `data-theme` override.

## Conventions
- Keep everything in a single file unless there is a strong reason to split it.
- Edit content in the JS data objects, not in the generated markup.
- The contact form deliberately opens the visitor's email app through `mailto:`. No server-side form handling is set up.
