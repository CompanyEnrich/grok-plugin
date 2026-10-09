# CompanyEnrich plugin

Connect CompanyEnrich's hosted MCP server to research companies and discover target accounts.

## Capabilities

- Enrich a company from its domain with available business information.
- Search for companies using criteria such as industry, location, size, and technologies.
- Find companies similar to one or more seed businesses.

These capabilities are documented in the [CompanyEnrich MCP guide](https://docs.companyenrich.com/docs/mcp-server). Returned fields and matches vary. This draft has not yet been tested in Grok Bot or approved for its marketplace.

## Account and configuration

You need a CompanyEnrich account and your own API key from the [dashboard](https://app.companyenrich.com/). API requests use your account and may consume credits under your [CompanyEnrich plan](https://companyenrich.com/pricing).

The plugin declares `COMPANYENRICH_API_KEY` as a required configuration variable. Set it through the host's supported plugin configuration interface. Enter the raw key; the configuration supplies the `Bearer` prefix. Do not commit a real API key to this repository.

Requests go directly to `https://mcp.companyenrich.com/mcp`. Company identifiers and search criteria supplied to CompanyEnrich tools are sent to that service.

## Example tasks

- “Enrich stripe.com and summarize its industry, size, location, and business description.”
- “Find up to five software companies in California with 50–200 employees.”
- “Find five companies similar to stripe.com and explain their reported business overlap.”

## Package

This draft uses the Cursor Plugin format because it documents user-supplied configuration variables for authenticated HTTP MCP servers. The manifest lives at `.cursor-plugin/plugin.json`, and `mcp.json` is discovered at the repository root. No local executable or dependency installation is required by this package.

## Validation before submission

1. Install the draft through a supported plugin development or private marketplace workflow.
2. Confirm that the host requests and securely stores the API key, expands the declared variable, and connects successfully.
3. List the live MCP tools. Confirm that enrichment, search, and similarity tools are available before advertising them as tested.
4. Run one bounded example for each advertised capability with an agreed credit budget. Check returned companies and gracefully handle missing data.
5. Test missing or invalid credentials, then verify the intended Grok Bot installation flow and authentication experience.

JSON/configuration checks alone do not establish runtime compatibility or marketplace acceptance.

## Publishing

The standalone plugin repository is [CompanyEnrich/grok-plugin](https://github.com/CompanyEnrich/grok-plugin). It contains connection configuration and documentation for the hosted service. A package license has not yet been selected.

The [Cursor plugin submission documentation](https://cursor.com/docs/reference/plugins) directs publishers to the [publisher application](https://cursor.com/marketplace/publish). Request Grok Bot availability explicitly during review; acceptance and distribution have not been confirmed for this draft.

## Links

- [CompanyEnrich](https://companyenrich.com/)
- [MCP documentation](https://docs.companyenrich.com/docs/mcp-server)
- [API documentation](https://docs.companyenrich.com/)

Prepared 10 October 2026. Not yet submitted.
