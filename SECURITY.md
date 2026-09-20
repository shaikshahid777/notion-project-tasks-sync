# Security Notes

This repository intentionally excludes secrets.

## Never commit

- Notion Internal Integration tokens
- API keys
- OAuth client secrets
- n8n credential exports containing secrets
- Webhook secrets
- Personal access tokens

## Local configuration

Configure credentials directly in n8n or your API client. Use placeholders such as `<NOTION_INTEGRATION_TOKEN>` in documentation and examples.

## Credential references

The n8n workflow export may contain credential **names/IDs** required by the n8n environment. These identifiers are not substitutes for the actual secret token.

If a secret is accidentally committed, revoke/rotate it immediately and remove it from the repository history as appropriate.
