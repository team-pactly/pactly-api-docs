# Deployment Guide for Pactly API Documentation

This guide explains how to deploy and manage the Pactly API documentation using Redocly.

## Prerequisites

- Node.js and npm installed (for local development)
- Git repository access
- Redocly account (for hosting)

## Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/pactly/pactly-api-docs.git
   cd pactly-api-docs
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run local preview**
   ```bash
   npm run preview
   ```
   This will start a local server at `http://localhost:8080`

## File Structure Overview

- `index.html` - Landing page
- `index.md` - Introduction content (Markdown)
- `introduction.html` - Introduction page (HTML version)
- `api-reference.html` - API reference page using Redoc
- `pactly-public-api-v.0.2.1.json` - OpenAPI specification
- `redocly.yaml` - Redocly configuration
- `package.json` - NPM scripts and dependencies
- `CNAME` - Custom domain configuration

## Updating Documentation

### Updating API Endpoints

1. Edit `pactly-public-api-v.0.2.1.json`
2. Validate the OpenAPI spec:
   ```bash
   npm run lint
   ```
3. Preview changes locally:
   ```bash
   npm run preview
   ```

### Updating Introduction Content

- For Markdown version: Edit `index.md`
- For HTML version: Edit `introduction.html`

### Updating Theme/Styling

1. Edit `redocly.yaml` for Redocly-specific theme options
2. Edit the inline styles in HTML files for custom styling

## Deployment Options

### Option 1: Redocly Hosting (Recommended)

1. **Connect GitHub repository to Redocly**
   - Log in to Redocly
   - Create a new project
   - Connect your GitHub repository
   - Select the main branch

2. **Configure deployment settings**
   - Set the OpenAPI file: `pactly-public-api-v.0.2.1.json`
   - Configure custom domain if needed

3. **Automatic deployment**
   - Push changes to the main branch
   - Redocly will automatically rebuild and deploy

### Option 2: GitHub Pages

1. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Select source: Deploy from a branch
   - Select branch: main (or gh-pages)
   - Select folder: / (root)

2. **Configure custom domain**
   - The `CNAME` file is already configured for `api-docs.pactly.com`
   - Add DNS records pointing to GitHub Pages

3. **Deploy**
   - Push changes to the configured branch
   - GitHub Pages will serve the static files

### Option 3: Static Hosting (Netlify, Vercel, etc.)

1. **Build static files**
   ```bash
   npm run build
   ```
   This creates a static HTML file in the `dist` directory

2. **Deploy to your hosting provider**
   - Upload the built files
   - Configure custom domain
   - Set up automatic deployments from Git

## Environment-Specific Deployments

The API documentation supports multiple environments:

- **Production**: `https://api.pactly.ai/`
- **Staging**: `https://api-staging.pactly.com/`
- **UAT**: `https://api-uat.pactly.com/`

To create environment-specific documentation:

1. Create environment-specific OpenAPI files:
   - `pactly-api-production.json`
   - `pactly-api-staging.json`
   - `pactly-api-uat.json`

2. Update the server URLs in each file

3. Create corresponding HTML files that reference the appropriate spec

## Maintenance Tasks

### Regular Updates

1. **Update API version**
   - Update version in `pactly-public-api-v.0.2.1.json`
   - Update version in `package.json`
   - Update version references in documentation

2. **Validate OpenAPI specification**
   ```bash
   npm run validate
   ```

3. **Test all links and examples**
   - Verify all endpoint URLs
   - Test authentication examples
   - Validate response schemas

### Monitoring

- Set up uptime monitoring for the documentation site
- Monitor 404 errors for broken links
- Track API documentation usage analytics

## Troubleshooting

### Common Issues

1. **Redoc not rendering**
   - Check browser console for errors
   - Verify OpenAPI spec is valid JSON
   - Ensure CORS is properly configured if loading spec from different domain

2. **Theme not applying**
   - Clear browser cache
   - Check `redocly.yaml` syntax
   - Verify theme configuration in Redoc.init()

3. **Build failures**
   - Run `npm run lint` to check for spec errors
   - Check for syntax errors in configuration files
   - Ensure all required files are present

### Support

For deployment issues:
- Redocly documentation: https://redocly.com/docs
- GitHub Pages: https://docs.github.com/pages
- Internal support: Contact the Platform team

## Future Enhancements

- Implement versioning strategy for API documentation
- Add automated API testing from documentation
- Integrate with CI/CD pipeline for automatic validation
- Add search functionality across all documentation
- Implement multi-language support