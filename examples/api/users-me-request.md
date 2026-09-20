# Authentication Verification — GET /v1/users/me

## Headers

```http
Authorization: Bearer <NOTION_INTEGRATION_TOKEN>
Notion-Version: 2022-06-28
```

## Expected result

HTTP **200 OK** with integration-user information.

> Never commit the real integration token. Replace the placeholder only in a local/API client environment.
