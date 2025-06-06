# Changelog

All notable changes to the Pactly API will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned for v1.0.0
- Contract generation from templates (`POST /v1/contracts/generate`)
- Contract set creation (`POST /v1/contract-set-from-values`)
- Webhook notifications for contract events
- Contract property updates
- Expanded search and filtering capabilities
- Write operations for contract management

## [0.2.0] - 2024-06-06

### Added
- Initial public API release
- Authentication using Bearer tokens
- Read-only contract operations:
  - `GET /v1/contracts` - List all contracts
  - `GET /v1/contracts/{id}` - Get contract details
  - `GET /v1/contracts/{id}/text` - Extract contract text
  - `GET /v1/contracts/{id}/download` - Download contract file
- Template listing:
  - `GET /v1/templates` - List all templates
- Test endpoint:
  - `GET /v1/test` - Test API connectivity
- Support for three contract types:
  - Template contracts
  - Playbook contracts
  - External contracts
- Pagination support with limit and skip parameters
- Sorting and filtering capabilities
- Comprehensive API documentation with Redocly

### Security
- Bearer token authentication required for all endpoints
- Rate limiting implemented
- HTTPS required for all API calls

## [0.1.0] - 2024-03-01 (Internal Alpha)

### Added
- Initial internal API implementation
- Basic contract retrieval endpoints
- Authentication system setup

---

## API Versioning Strategy

The Pactly API follows semantic versioning:
- **Major version (X.0.0)**: Breaking changes that require code updates
- **Minor version (0.X.0)**: New features that are backwards compatible
- **Patch version (0.0.X)**: Bug fixes and minor improvements

All API endpoints are versioned with `/v1/` prefix. When v2 is released, v1 endpoints will continue to work for at least 12 months to allow for migration.