# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Commands

This repo is a Hugo site configured via `hugo.yaml` and using the `PaperMod` theme. All commands below are run from the repository root.

### Local development

```bash path=null start=null
hugo server -D
```

- Serves the site at the default Hugo dev URL (usually `http://localhost:1313/`).
- `-D` includes content marked as `draft: true` (for example, anything created from `archetypes/default.md` that you haven’t published yet).

### Build for deployment

```bash path=null start=null
hugo
```

- Builds the static site into the `public/` directory.
- Treat `public/` as build output: edit content in `content/`, layouts in `layouts/`, and styles in `assets/`, then rebuild with `hugo` rather than editing `public/` by hand.

### Content authoring

Hugo will use `archetypes/default.md` when creating new content files.

Create a new project entry:

```bash path=null start=null
hugo new projects/<slug>.md
```

Create a new research entry:

```bash path=null start=null
hugo new research/<slug>.md
```

Then edit the generated file under `content/` to fill in front matter (`title`, `date`, `summary`, `tags`, `cover`, etc.) and the body.

### Tests / linting

There is no dedicated automated test or lint command defined in this repository (no `package.json`, `Makefile`, or similar). Site verification is currently manual via the Hugo build/dev server.

## Architecture and structure

### High-level layout

- **Static site engine**: Hugo, configured via `hugo.yaml`.
  - `baseURL`, `languageCode`, `title`, and `theme` (`PaperMod`) are defined here.
  - The main navigation menu is defined under `menu.main`.
  - `params` configures PaperMod behavior and custom sections (home hero, featured pages, social icons, metadata, etc.).
- **Content** lives under `content/`:
  - `content/projects/` – individual project case studies with rich front matter (`title`, `summary`, `tags`, `cover.image`, `weight`, etc.).
  - `content/research/` – research index and entries.
  - `content/about.md`, `content/resume.md`, `content/contact/_index.md` – single pages for About, Resume, and Contact.
  - `content/_index.md` – homepage body content (e.g., testimonial quotes) that is injected into the custom home layout.
- **Templates / layouts** live under `layouts/` and extend/override PaperMod:
  - `layouts/index.html` – custom home page composition.
  - `layouts/_default/list.html` – default list (section) page layout, customized with a card grid.
  - `layouts/projects/list.html` – specialized list layout for the Projects section.
  - `layouts/contact/single.html` – custom single-page layout for the Contact page.
  - `layouts/partials/*.html` – custom partials and extensions (home hero, featured cards, background shader, head tweaks, etc.).
- **Styling**:
  - Primary custom CSS is in `assets/css/extended/custom.css` and is referenced via `params.customCSS` in `hugo.yaml`.
  - Hugo’s asset pipeline compiles this into the hashed CSS files under `public/assets/css/` (generated output).

### Home page and featured content

The home page combines configuration from `hugo.yaml`, content from `content/_index.md`, and custom layouts:

- `hugo.yaml`:
  - `params.homeInfoParams` controls the primary hero on the homepage (title, blurb, portrait, bullets under `extraContent`, and the set of hero links).
  - `params.featuredPages` lists the canonical URLs of key projects/research pages to feature on the home page.
- `layouts/index.html`:
  - Defines the `main` block for the home page.
  - Renders `home_info.html` for the hero section.
  - Renders `home-featured.html` for the featured work rail.
  - Renders the markdown from `content/_index.md` into a "Testimonials" article.
- `layouts/partials/home_info.html`:
  - Implements the hero section layout, including the portrait image, headline, blurb, and a grid of primary navigation buttons.
  - Proxies the hero’s theme toggle button to PaperMod’s core `#theme-toggle` button in the header to reuse the same logic for switching themes.
  - Uses `homeInfoParams.links` (if present) to drive the hero link buttons; otherwise it falls back to a hard-coded list of section links.
- `layouts/partials/home-featured.html`:
  - Uses `params.featuredPages` to build a horizontally constrained featured work rail.
  - For each configured page, calls `partials/custom-card.html` (from the PaperMod theme) with an additional `custom-card` class to apply card-specific styling.

When adding a new high-visibility project or research entry you want on the homepage:

1. Create or update the content file under `content/projects/` or `content/research/` with appropriate front matter and a `cover.image`.
2. Add the page’s canonical URL (e.g., `/projects/echoes/`) to `params.featuredPages` in `hugo.yaml`.

### List pages and card grid layout

Section listing pages (e.g., Projects, Research) are built around a shared card-grid pattern:

- `layouts/_default/list.html`:
  - Handles generic section and taxonomy list rendering with breadcrumbs, title, optional description, and pagination.
  - Chooses pages to display via Hugo’s `.Paginate` over `.RegularPages`/`.Sections`, with special handling when `.IsHome`.
  - Wraps items in a `.custom-grid` container and uses a `custom-card` CSS class to style entries as image-first cards.
- `layouts/projects/list.html`:
  - Mirrors the default list behavior but explicitly uses `partials/custom-card.html` for each project page.
  - Ensures Projects uses the same grid-based card layout as other sections but allows project-specific tweaks.
- `assets/css/extended/custom.css`:
  - Defines `.custom-grid` (responsive CSS Grid container) and `.custom-card` (hover animations, box shadows, and card proportions).
  - Controls card image height, title overlay styling (`.card-title-overlay`), and summary text clamping so cards remain visually consistent.

To adjust how project or research cards look (layout density, image height, summary length), prefer editing the relevant rules in `assets/css/extended/custom.css` instead of per-template inline styles.

### Theming, background shader, and head extensions

The repo adds a site-wide WebGL background shader and fine-grained theme behavior on top of PaperMod:

- `layouts/partials/extend-head.html`:
  - Injects a `meta name="color-scheme"` hint and small inline script that:
    - Reads the saved theme preference (`pref-theme`) and system `prefers-color-scheme`.
    - Applies a `dark` class and background color to `document.documentElement` before paint to avoid theme flicker.
    - Adds a `no-transitions` class initially, then removes it on `DOMContentLoaded` to prevent jarring transitions on initial load.
- `layouts/partials/extend_footer.html`:
  - Declares a full-screen `<canvas id="bg-canvas">` and embeds GLSL vertex/fragment shaders that render a smooth animated noise background.
  - Sets up a `WebGL` context with a full-screen triangle, time-based animation, and uniforms for:
    - `uRes` – canvas resolution.
    - `uDark` – whether the site is in dark or light mode (driven by the `body.dark` class).
    - `uMouse` – normalized mouse/touch position to subtly accent the background under the cursor.
  - Listens for `MutationObserver` changes on `body.classList` to keep the shader’s `uDark` uniform in sync with theme changes.
  - Handles device pixel ratio, resize events, reduced motion preferences, and visibility changes to balance quality and performance.
  - Adds a `.shader-ready` class to `body` once the first frame has rendered; accompanying CSS then makes PaperMod wrappers transparent so content floats above the shader.
- `assets/css/extended/custom.css`:
  - Defines `.bg-canvas` and ensures `header`, `main`, and `footer` sit above the canvas via `z-index`.
  - Sets dark background defaults on `html`/`body` to match the shader.

If you need to change the overall visual character of the background, focus on the color and noise parameters inside the fragment shader in `extend_footer.html` rather than rewriting the entire WebGL setup.

### Contact page and form styling

The contact page combines the base content with a specialized layout and styles:

- `layouts/contact/single.html`:
  - Loads an additional CSS resource (`css/extra.css`) and passes it into `extend-head.html` for inclusion.
  - Delegates the main body rendering to the standard `content.html` partial, so the markdown/HTML in `content/contact/_index.md` controls the actual form or embed.
- `assets/css/extended/custom.css`:
  - Provides `.contact-wrapper` and related form control styles for a card-like contact form container.
  - Aligns fonts, colors, focus states, and buttons with the rest of the PaperMod theme.

When altering the contact form appearance, prefer updating the `.contact-wrapper` rules and related selectors in `assets/css/extended/custom.css`.

### Content behavior and HTML

- `hugo.yaml` sets `markup.goldmark.renderer.unsafe: true`, allowing raw HTML in markdown content.
  - This is used for components like the embedded resume iframe in `content/resume.md`.
  - When editing or adding content that includes HTML (iframes, custom figures, etc.), you can rely on Hugo rendering it as-is.
- Many content files (e.g., project pages) use fairly rich front matter and headings; keep new content consistent in tone and structure with existing entries (`content/projects/debuglibrary.md`, `content/projects/optimized_boids.md`, etc.).

### Generated assets

- The `public/` directory contains generated static output (HTML, CSS, etc.) from previous Hugo builds.
- Do **not** hand-edit files under `public/`; instead:
  - Modify source content (`content/`), layouts (`layouts/`), or styles (`assets/`).
  - Rebuild with `hugo` and redeploy the new `public/` output as appropriate.
