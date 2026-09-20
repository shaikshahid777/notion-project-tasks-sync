# Notion Integration Troubleshooting Runbook

## 401 Unauthorized

**Typical cause:** invalid, expired, malformed, or incorrectly configured bearer credentials.

**Checks**
1. Verify the Notion credential selected in n8n.
2. Re-copy the Internal Integration token if necessary.
3. Confirm the request uses bearer authentication.
4. Avoid storing tokens in source control.

## 403 Forbidden / 404 Object Not Found

**Typical cause:** the integration cannot access the requested page/database, or the identifier is wrong.

**Checks**
1. Open the target Notion database/page.
2. Use **Share / Connections / Add connections** to grant the integration access.
3. Verify the database/data-source ID.
4. Confirm the n8n credential belongs to the intended integration.

## Database not shared with the integration

The API can only operate on resources available to the integration. Share each required database with the Internal Integration and then retry the n8n node.

## Block append failures

**Checks**
- Confirm the target page ID is valid.
- Verify the block payload shape.
- Confirm the integration has access to the parent page.
- Validate rich-text and block type fields.

## Invalid property mapping

**Checks**
- Match property names exactly.
- Match the Notion property type: title, select, multi-select, date, or relation.
- Validate that select option values exist.
- Validate ISO date values.

## Relation property errors

**Checks**
- Confirm the relation property points to the intended database.
- Pass the source page ID, not the page title.
- Verify the related page is accessible to the integration.
- Confirm the property key matches the Notion schema.

## 429 Too Many Requests

**Typical cause:** request rate limiting.

**Checks**
- Reduce polling frequency where practical.
- Avoid unnecessary repeated queries.
- Add pacing/retry behavior.
- Use n8n execution controls and polling intervals.

## Empty database query results

**Checks**
- Confirm the correct data source/database ID.
- Verify the filter property names and types.
- Confirm the records actually satisfy every condition when using compound filters.
- Check whether the integration has access to the records.
