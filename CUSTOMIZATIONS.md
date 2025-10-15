# Customizations for matiasilva

This is a fork of [hugo-bearblog](https://github.com/janraasch/hugo-bearblog) with customizations for matiasilva.com.

All custom code is wrapped in comments with `BEGIN CUSTOM: matiasilva` and `END CUSTOM` markers for easy identification when syncing with upstream.

## Modified Files

### Styles (`layouts/partials/style.html`)
- **Light theme only**: Override dark mode to always show light theme
- **Custom accent colors**: Deep navy (`#1a3a52`) for site title, muted beige/grey (`#8b8680`) for navigation
- **Link underlines**: All links are underlined by default
- **Header layout**: Horizontal flexbox header with name and nav on same line, baseline aligned
- **Navigation**: Lowercase links, custom colors, hover opacity effect
- **Footer**: Custom multi-column footer with thick border, floated columns
- **Blog post lists**: Monaco monospace dates, custom spacing and colors
- **Project links**: Styled metadata boxes for project pages
- **Post meta**: Date footer on blog posts with dashed border

### Partials
- **`layouts/partials/header.html`**: Custom horizontal header with site title link
- **`layouts/partials/footer.html`**: Multi-column footer with contact info

### Layouts
- **`layouts/_default/single.html`**: Show title for non-blog pages (e.g., Projects page)
- **`layouts/blog/list.html`**: Blog list with relative URLs (`.RelPermalink`)
- **`layouts/blog/single.html`**: Blog post with "Originally written on [date]" footer
- **`layouts/index.html`**: Homepage with featured posts section

## Content Structure

All content (blog posts and projects) lives in `content/blog/` with unified date-based URLs: `/:year/:month/:day/:slug/`

### Optional Front Matter for Projects
Blog posts can include these optional fields for project metadata:
```toml
blog_post = "/2021/03/16/related-post/"
github = "https://github.com/..."
demo = "https://example.com"
```

### Color Variables
- `--accent-name`: Deep navy blue for site title
- `--accent-nav`: Muted beige/grey for navigation and footer text

## Syncing with Upstream

When syncing with the upstream hugo-bearblog repository:

1. Search for `BEGIN CUSTOM: matiasilva` to find all modifications
2. Preserve these sections when merging upstream changes
3. Review conflicts carefully to maintain custom styling
4. Test build after sync: `hugo && hugo server`

## Local Overrides

The main site repository (`/layouts`) only contains:
- `shortcodes/` - Custom shortcodes (figure, notification, quote)

Everything else is in the theme to minimize local overrides.
