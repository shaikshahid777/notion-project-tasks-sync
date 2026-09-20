# 📸 Evidence Gallery

This page maps every captured screenshot to the exact workflow/assessment component it proves.

> **Evaluator shortcut:** Start with the evidence below in order. Each item tells you **what to inspect, why it matters, and which assessment requirement it supports**.

---

## 01 — Extract Task Data

**Evidence file:** `Screenshot 2026-09-20 093903.png`

### What this proves
The n8n **Extract Task Data** node receives a Project Tasks record and maps the source fields into normalized values:

- `taskId`
- `taskName`
- `priority`
- `status`
- `dueDate`

### Assessment mapping
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 11 — Mini Project**

---

## 02 — Find in Knowledge Base

**Evidence file:** `Screenshot 2026-09-20 093917.png`

### What this proves
The workflow queries the **Knowledge Base** database and searches using the **Original Task relation**.

The screenshot also shows the configured Knowledge Base data source and filter.

### Assessment mapping
**Exercise 6 — Query Database Records**  
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 11 — Mini Project**

---

## 03 — KB Page Exists?

**Evidence file:** `Screenshot 2026-09-20 093932.png`

### What this proves
The IF node checks whether the Knowledge Base lookup returned a page ID.

This is the workflow's **create-vs-update decision point**.

### Assessment mapping
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 9 — End-to-End Workflow**

---

## 04 — Update Knowledge Base Page

**Evidence file:** `Screenshot 2026-09-20 093947.png`

### What this proves
When a matching Knowledge Base page already exists, the workflow updates it using:

- Title
- Priority
- Status
- Due Date
- Original Task relation

### Assessment mapping
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 9 — End-to-End Workflow**

---

## 05 — Create Knowledge Base Page

**Evidence file:** `Screenshot 2026-09-20 094002.png`

### What this proves
When no matching Knowledge Base page exists, n8n creates one in the target database and maps the source task relation.

### Assessment mapping
**Exercise 4 — Create a Database Page**  
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 11 — Mini Project**

---

## 06 — Task Created Trigger

**Evidence file:** `Screenshot 2026-09-20 094015.png`

### What this proves
The workflow monitors the **Project Tasks** database for newly created pages.

### Assessment mapping
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 11 — Mini Project**

---

## 07 — Task Updated Trigger

**Evidence file:** `Screenshot 2026-09-20 094032.png`

### What this proves
The workflow also detects updates to existing Project Tasks records.

This is required for keeping the Knowledge Base synchronized after task changes.

### Assessment mapping
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 9 — End-to-End Workflow**

---

## 08 — Knowledge Base Database

**Evidence file:** `Screenshot 2026-09-20 111754.png`

### What this proves
The target **Knowledge Base** database contains synchronized task information.

Visible target properties include:

- Title
- Due Date
- Original Task
- Priority
- Status

### Assessment mapping
**Exercise 3 — Create and Share a Database**  
**Exercise 8 — Synchronize Content Between Databases**  
**Exercise 9 — End-to-End Workflow**

---

## 09 — Project Tasks Database

**Evidence file:** `Screenshot 2026-09-20 111819.png`

### What this proves
The source **Project Tasks** database contains the task records being monitored by the n8n workflow.

Visible properties include:

- Task Name
- Due Date
- Priority
- Status
- Phone

### Assessment mapping
**Exercise 3 — Create and Share a Database**  
**Exercise 4 — Create a Database Page**  
**Exercise 8 — Synchronize Content Between Databases**

---

# 🔎 Evaluator Quick Path

If you only have a few minutes, inspect these in order:

| Step | Evidence | Why |
|---|---|---|
| 1 | Project Tasks | Source database |
| 2 | Task Created / Updated | Automation trigger |
| 3 | Extract Task Data | Data transformation |
| 4 | Find in Knowledge Base | Relation lookup |
| 5 | KB Page Exists? | Upsert decision |
| 6 | Create / Update | Synchronization action |
| 7 | Knowledge Base | Final synchronized result |

---

# 🔗 Related Project Artifacts

- [← Main README](../../README.md)
- [Assessment Matrix](../assessment/assessment-mapping.md)
- [Architecture Diagram](../diagrams/architecture.svg)
- [Data Model](../diagrams/data-model.svg)
- [Troubleshooting Runbook](../troubleshooting.md)
- [n8n Workflow JSON](../../workflow/notion-project-tasks-to-knowledge-base-sync.json)

---

## Screenshot source mapping

The screenshots listed above correspond to the nine workspace captures supplied with this assessment submission. The original captures are preserved in the conversation submission package; the filenames above are used as stable evidence IDs for the evaluator.
