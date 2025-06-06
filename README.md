# Pactly API Documentation

This repository contains the documentation for the Pactly public API, built with Redocly.

## Overview

The documentation consists of:
- **Introduction page** (`index.md`) - Overview of the Pactly API and getting started guide
- **API Reference** (`api-reference.html`) - Interactive API documentation generated from the OpenAPI specification
- **OpenAPI Specification** (`pactly-public-api-v.0.2.1.json`) - The API specification in OpenAPI 3.0 format

## Local Development

### Prerequisites
- Node.js and npm installed
- Redocly CLI (optional, for preview and validation)

### Installing Redocly CLI

```bash
npm install -g @redocly/cli
```

### Running Locally

1. Clone this repository
2. Navigate to the project directory
3. Run the preview server:

```bash
# Using Redocly CLI
redocly preview-docs pactly-public-api-v.0.2.1.json

# Or using Python (if you don't have Redocly CLI)
python3 -m http.server 8000
# Then open http://localhost:8000/api-reference.html
```

## File Structure

```
pactly-api-docs/
├── index.md                           # Introduction page
├── api-reference.html                 # API reference page (uses Redoc)
├── pactly-public-api-v.0.2.1.json    # OpenAPI specification
├── redocly.yaml                      # Redocly configuration
└── README.md                         # This file
```

## Updating the API Documentation

1. **To update API endpoints**: Edit the `pactly-public-api-v.0.2.1.json` file
2. **To update the introduction**: Edit the `index.md` file
3. **To change the theme or configuration**: Edit the `redocly.yaml` file

## API Specification

The current API version is **v0.2.0** and includes the following endpoints:

- `GET /v1/test` - Test endpoint for connectivity
- `GET /v1/contracts` - List all contracts
- `GET /v1/contracts/{id}` - Get a specific contract
- `GET /v1/contracts/{id}/text` - Get contract text content
- `GET /v1/contracts/{id}/download` - Download contract file
- `GET /v1/templates` - List all templates
- `POST /v1/contracts/generate` - Generate contract from template (coming soon)
- `POST /v1/contract-set-from-values` - Create contract set (coming soon)

## Authentication

All API endpoints require Bearer token authentication:

```
Authorization: Bearer YOUR_API_KEY
```

## Deployment

This documentation is automatically deployed via Redocly when changes are pushed to the main branch.

## Contributing

When making changes:
1. Update the OpenAPI specification for any API changes
2. Ensure the specification is valid: `redocly lint pactly-public-api-v.0.2.1.json`
3. Preview changes locally before committing
4. Create a pull request with your changes

## Support

For questions about the API documentation:
- Email: developers@pactly.com
- Internal: Contact the Platform team

## Future Enhancements

Based on the roadmap (JIRA tickets PAC-3266, PAC-3400, PAC-3401), upcoming features include:
- Webhook notifications for contract events
- Contract generation endpoints
- Expanded filtering and search capabilities
- Write operations for contract updates