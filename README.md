# Resume Site

This is a personal resume site built with [Eleventy](https://www.11ty.dev/). It is designed to be a single-page portfolio/resume.

## Features
- Single-page resume layout
- PDF generation friendly
- Responsive design
- SEO optimized

## Local Development

1. Install dependencies:
   ```bash
   pnpm install
   ```

2. Run local server:
   ```bash
   pnpm start
   ```

3. Build for production:
   ```bash
   pnpm build
   ```

## Customization

### Color Theme
The site uses a **Light High Contrast Sunset** theme designed for accessibility (WCAG AA/AAA).

- **Background**: `#fffef0` (Very Light Cream)
- **Text**: `#540b0e` (Dark Red/Brown)
- **Headings**: `#335c67` (Deep Teal)
- **Links**: `#9e2a2b` (Rust Red)
- **Accents**: `#e09f3e` (Golden Orange)

To change these colors, edit `_includes/css/index.css`.

## Future: How to Add a Blog

If you want to add a blog to this site in the future, follow these steps:

1.  **Create Blog Posts**:
    Create markdown files in `content/blog/`. For example `content/blog/my-first-post.md`:

    ```markdown
    ---
    title: My First Post
    date: 2024-01-01
    tags: posts
    ---
    This is my first post content.
    ```

    *Note: The `tags: posts` frontmatter is crucial for the post to appear in collections.*

2.  **Restore Blog Index**:
    Create a file `content/blog.njk` to list your posts:

    ```html
    ---js
    const eleventyNavigation = {
    	key: "Archive",
    	order: 2
    };
    ---
    <h1>Blog Archive</h1>

    {% set postslist = collections.posts %}
    {% include "postslist.njk" %}
    ```

3.  **Update Navigation**:
    The `eleventyNavigation` key in the frontmatter will automatically add the link to the header navigation.

## Deployment

This site is configured to automatically deploy to GitHub Pages via GitHub Actions when you push to the `main` branch.
