# Valor Services & Contact MCP

Official connection guide for Valor’s hosted company, services, and contact MCP.
Valor is an independent mineral management firm that never buys minerals.

- **Endpoint:** https://www.onevalor.com/mcp/services/v1
- **Transport:** Streamable HTTP (JSON-RPC 2.0)
- **Authentication:** No account or API key required
- **Registry name:** `io.github.valor-mineral-management/services-contact`
- **Website and contact:** https://www.onevalor.com/contact/

This repository contains public connection documentation and registry metadata. The service runs on Valor’s website; there is no local server to install.

## Connect

In an MCP client that supports remote Streamable HTTP servers, add a custom server named **Valor Services & Contact** with this URL:

```text
https://www.onevalor.com/mcp/services/v1
```

Choose Streamable HTTP and no authentication if prompted. A browser GET may return HTTP 405 because MCP requests use POST.

## Tools

| Tool | What it does |
| --- | --- |
| `about_valor` | Company information, independence, mineral.tech® technology, credentials, and complete company and leadership awards. |
| `get_valor_services` | Mineral management and operator services, with audience filters. |
| `find_relevant_service` | Match a selected need to relevant service information. |
| `get_engagement_information` | Explain contact steps and required fields. |
| `prepare_contact_request` | Prepare a temporary inquiry draft and return a private Valor review link. |
| `get_contact_receipt` | Check whether that inquiry is pending or submitted, using its private token. |

## Example requests

- “Tell me about Valor and its mineral management services.”
- “Which Valor services help with inherited minerals?”
- “Explain Valor’s operator services.”
- “Help me prepare an inquiry for Valor.”

Preparing an inquiry does not send it. The person opens the private review link, enters their contact details on Valor, reviews the inquiry, and explicitly sends it. A receipt confirms that Valor saved the inquiry; it does not guarantee a response or downstream delivery.

Keep the review link and receipt token private. Enter names, email addresses, phone numbers, and other contact details on the Valor review page, rather than in MCP tool arguments. Use a direct connection to Valor.

## Scope

This endpoint provides company and service information plus inquiry preparation and receipt checks. It exposes no CRM search, customer records, internal financial information, or public-data research tools. It does not provide mineral valuations, purchase offers, formal appraisals, or personalized tax guidance.

For full company information and protected award details, use `about_valor`. Service descriptions link to the relevant pages on [Valor’s website](https://www.onevalor.com/).

## Registry

[Official MCP Registry record](https://registry.modelcontextprotocol.io/v0.1/servers/io.github.valor-mineral-management%2Fservices-contact/versions/latest)

The published manifest is [server.json](server.json). Directory listings should use only the endpoint above and the name **Valor Services & Contact**.

## Verification

On September 24, 2026, the public endpoint successfully answered `initialize`, `tools/list`, and `about_valor`. Its tool list contained exactly the six tools above. Verification did not submit an inquiry.
