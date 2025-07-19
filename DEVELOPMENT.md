# BCMC Dawn Theme - Development Guide

## 🚀 Local Development Setup

This guide will help you set up your local development environment for the BCMC Dawn Theme.

## Prerequisites

- ✅ Shopify CLI (installed via Homebrew)
- ✅ Node.js (comes with Shopify CLI)
- ✅ Git (comes with Shopify CLI)
- 🔄 Shopify Partner Account (needed for development store)

## Setup Steps

### 1. Connect to Your Shopify Store

First, you need to authenticate with Shopify and connect to your development store:

```bash
# Login to Shopify
shopify auth login

# List your stores
shopify store list

# Connect to your development store
shopify store use your-store.myshopify.com
```

### 2. Create a Development Theme

```bash
# Create a development theme from your current theme
shopify theme push --development

# Or create a new development theme
shopify theme dev
```

### 3. Start Local Development

```bash
# Start the development server with live reload
shopify theme dev

# This will:
# - Start a local development server
# - Watch for file changes
# - Automatically sync changes to your development theme
# - Provide a local preview URL
```

## Development Commands

### Theme Management

```bash
# List all themes in your store
shopify theme list

# Push changes to development theme
shopify theme push

# Pull changes from development theme
shopify theme pull

# Deploy to production theme
shopify theme push --live

# Check theme for issues
shopify theme check
```

### Development Server

```bash
# Start development server
shopify theme dev

# Start with specific theme
shopify theme dev --theme=THEME_ID

# Start with custom port
shopify theme dev --port=9292
```

### Theme Information

```bash
# Get theme info
shopify theme info

# Get theme URL
shopify theme open

# Get theme preview URL
shopify theme serve
```

## File Structure

```
bcmc-dawn-theme/
├── assets/              # CSS, JS, images, fonts
├── config/              # Theme settings
├── layout/              # Layout templates
├── locales/             # Translation files
├── sections/            # Reusable sections
├── snippets/            # Reusable code snippets
├── templates/           # Page templates
├── shopify.theme.toml   # Theme configuration
└── .gitignore          # Git ignore rules
```

## Development Workflow

1. **Start Development Server**

   ```bash
   shopify theme dev
   ```

2. **Make Changes**

   - Edit files in your code editor
   - Changes are automatically synced to your development theme
   - Preview changes in real-time

3. **Test Changes**

   - Use the local preview URL
   - Test on different devices/screen sizes
   - Check for any console errors

4. **Deploy to Production**
   ```bash
   shopify theme push --live
   ```

## Common Development Tasks

### Adding New Sections

1. Create a new `.liquid` file in `sections/`
2. Add the section to your template in `templates/`
3. The section will appear in the theme editor

### Modifying Styles

1. Edit CSS files in `assets/`
2. Changes are automatically synced
3. Use browser dev tools for debugging

### Adding JavaScript

1. Edit JS files in `assets/`
2. Include them in your layout file
3. Test functionality in the browser

## Troubleshooting

### Common Issues

**Theme not syncing:**

```bash
# Check connection
shopify store list

# Re-authenticate if needed
shopify auth logout
shopify auth login
```

**Development server not starting:**

```bash
# Check if port is in use
lsof -i :9292

# Use different port
shopify theme dev --port=9293
```

**File changes not detected:**

- Ensure you're editing files in the correct directory
- Check file permissions
- Restart the development server

### Getting Help

- [Shopify CLI Documentation](https://shopify.dev/docs/themes/tools/cli)
- [Shopify Theme Development](https://shopify.dev/docs/themes)
- [Dawn Theme Documentation](https://shopify.dev/docs/themes/tools/dawn)

## Environment Variables

Create a `.env` file for any sensitive information:

```env
SHOPIFY_STORE_URL=your-store.myshopify.com
SHOPIFY_API_KEY=your-api-key
SHOPIFY_API_SECRET=your-api-secret
```

## Best Practices

1. **Always work on a development theme** - never edit the live theme directly
2. **Test thoroughly** before pushing to production
3. **Use version control** - commit your changes regularly
4. **Follow Shopify's coding standards** - use proper Liquid syntax
5. **Optimize for performance** - minimize CSS/JS, optimize images
6. **Test on multiple devices** - ensure responsive design works

## Next Steps

1. Set up your Shopify Partner account
2. Create a development store
3. Connect your local environment
4. Start developing!

---

**Need help?** Check the [Shopify Dev Documentation](https://shopify.dev/docs/themes) or contact the development team.
