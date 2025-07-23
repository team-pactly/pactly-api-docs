# Pactly API Documentation

Welcome to the Pactly API documentation. The Pactly API provides programmatic access to contract management functionality, enabling you to integrate Pactly with your existing business systems and automate your contract workflows.

## Overview

The Pactly API is a RESTful web service that allows you to:

- **Access contract data** - Retrieve information about your contracts, including metadata, properties, and status
- **Download documents** - Get contract files in their original format or extract text content for analysis
- **List templates** - Access your contract templates for integration with external systems
- **Generate contracts** - Create new contracts from templates programmatically *(coming soon)*
- **Receive real-time updates** - Get notified about contract events via webhooks *(coming soon)*

## Current API Version

The current version of the Pactly API is **v0.2.0**. This is a read-only API that focuses on retrieving contract and template information. Write operations and webhook functionality are planned for future releases.

## Getting Started

To use the Pactly API, you'll need:

1. **API Key** - Contact your Pactly administrator to obtain an API key for your organization
2. **API Endpoint** - Use the appropriate endpoint for your environment:
   - Production: `https://api.pactly.ai/`
   - Staging: `https://staging-api.pactly.com/`
   - UAT: `https://api-uat.pactly.com/`

## Authentication

The Pactly API uses API key authentication. Include your API key in the x-api-key header of all requests:

```
x-api-key: YOUR_API_KEY
```

## Contract Types

Pactly manages three types of contracts, all accessible through the same API endpoints:

- **Template Contracts** - Generated from pre-defined templates within Pactly
- **Playbook Contracts** - Third-party contracts reviewed against your organization's playbooks
- **External Contracts** - External documents uploaded to the system for tracking

## Response Format

All API responses are in JSON format. Contract responses include a `type` field to identify the contract type:

```json
{
  "_id": "contract-id",
  "type": "template", // or "playbook" or "external"
  "name": "Contract Name",
  "reference": "2024-0001",
  "status": 5, // 1=Draft, 2=In Negotiation, 3=Pending Approval, 4=Pending Signature, 5=Executed, 6=Terminated
  // ... additional fields
}
```

## Rate Limiting

API requests are subject to rate limiting to ensure service stability. Current limits will be communicated when you receive your API key.

## Support

For API support, please contact:
- Email: developers@pactly.com
- Documentation: [API Reference](./api-reference.html)

## Roadmap

We're actively developing new API capabilities based on customer needs:

### Coming Soon (v1.0)
- Contract generation from templates
- Contract property updates
- Webhook notifications for contract events
- Expanded search and filtering capabilities

### Future Enhancements
- Playbook management
- Form submissions via API
- Bulk operations
- GraphQL endpoint

Stay tuned for updates as we expand the API functionality to better serve your integration needs.