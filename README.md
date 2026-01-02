# Devspade Blog

A personal blog built with [Zola](https://www.getzola.org/), a fast static site generator written in Rust.

## Prerequisites

Install Zola on your system. See the [official Zola installation guide](https://www.getzola.org/documentation/getting-started/installation/) for platform-specific instructions.

### macOS

```bash
brew install zola
```

## Development

To start the development server with live reload:

```bash
zola serve
```

The site will be available at `http://127.0.0.1:1111` by default. The server will automatically reload when you make changes to your content or templates.

### Custom Port

To use a different port:

```bash
zola serve --port 8080
```

## Building

To build the static site for production:

```bash
zola build
```

This generates all static files in the `public/` directory, ready to be deployed.

## Project Structure

```
.
├── config.toml          # Site configuration
├── content/             # Markdown content
│   ├── about/          # About page
│   └── posts/          # Blog posts
├── static/             # Static assets (images, etc.)
├── sass/               # Custom SASS styles
├── templates/          # Custom templates (overrides theme)
└── themes/            # Theme files
    └── hermit_zola/   # Hermit theme
```

## Theme

This site uses a modified version of the [Hermit Zola](https://github.com/VersBinarii/hermit_zola) theme, a minimal and fast theme for bloggers.
 

## Resources

- [Zola Documentation](https://www.getzola.org/documentation/)
- [Zola Getting Started Guide](https://www.getzola.org/documentation/getting-started/overview/)
- [Zola Themes](https://www.getzola.org/themes/)
- [Hermit Zola Theme](https://github.com/VersBinarii/hermit_zola)



