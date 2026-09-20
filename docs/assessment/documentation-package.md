# Notion Integration & Automation Documentation Package

## Cross-Database Content Synchronization Architecture using n8n and Notion API

### Submission artifacts

- GitHub: https://github.com/shaikshahid777/notion-project-tasks-sync
- Loom: https://www.loom.com/share/307f15da00f34f7687b6beb9bf913f1b
- n8n workflow: https://mohammad-shaheed.app.n8n.cloud/assistant/2a6a757f-6b4e-4c2a-9cfd-c3e2644e3a9d

## Executive summary

The solution bridges Notion databases through the Notion REST API and n8n. It monitors changes in Project Tasks, extracts task attributes, checks for an existing Knowledge Base record using the source-task relation, and creates or updates the corresponding record.

## Database schema

### Project Tasks
- Task Name — Title
- Priority — Select
- Status — Select
- Tags — Multi-select
- Due Date — Date
- Project — Relation

### Projects
- Project Name — Title
- Tasks — Relation

### Knowledge Base
- Title — Title
- Priority — Select
- Status — Select
- Due Date — Date
- Original Task — Relation

## Synchronization logic

1. Task Created / Task Updated trigger polls Project Tasks.
2. Extract Task Data normalizes the source fields.
3. Find in Knowledge Base queries by Original Task relation.
4. KB Page Exists? checks whether a matching page was returned.
5. Existing match → Update Knowledge Base Page.
6. No match → Create Knowledge Base Page.
7. Original Task relation is retained for traceability.

## Idempotency

The existence check is based on the source page relation rather than a display title. Repeated updates therefore target the existing synchronized record instead of creating another record for the same task.

## Troubleshooting

See [Troubleshooting Runbook](../troubleshooting.md).

## Evidence

See [Evidence Index](../evidence/evidence-index.md).

> The original submitted PDF remains the source documentation package; this Markdown version is the repository-friendly text edition.
