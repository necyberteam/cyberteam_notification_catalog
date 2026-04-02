<!-- auto-generated, do not hand-edit -->
# PA Science Notifications

This page catalogs all automated notifications for the PA Science (pascience) portal.

## Summary Table

| Name | Trigger | Method | Subject | Recipient | Needs Review |
|------|---------|--------|---------|-----------|:------------:|
| New Project Submission (Manager) | project node created | email | New Project Submission: `{{ project_title }}` | PA Science program manager | — |
| Project Submission Received (Author) | project node created | email | Project Submission Received: `{{ project_title }}` | Submitting user | — |
| Project Updated (Manager) | project node updated with notification flag | email | Project Updated: `{{ project_title }}` | PA Science program manager | — |
| Project Approved (Author) | project approved and published | email | Project Approved and Published: `{{ project_title }}` | Submitting user | — |
| Project Interest Flagged | user flags interest in project | email | `{{ title }}` - interest shown on project | Project author/role | — |

## Notification Details

### New Project Submission (Manager)

| Field | Value |
|-------|-------|
| **Portal(s)** | pascience |
| **Trigger** | New project node created/submitted to PA Science DMZ |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | PA Science program manager |
| **Recipient Role** | PA Science DMZ manager role |
| **Subject** | `New Project Submission: {{ project_title }}` |
| **Body Summary** | Notifies the PA Science DMZ manager of a new project submission with full project details (title, leader, contact email, submitter, description) and a link to review it. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc_project.project_created_pascience.yml` |

---

### Project Submission Received (Author)

| Field | Value |
|-------|-------|
| **Portal(s)** | pascience |
| **Trigger** | New project node created/submitted |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Submitting user (project author) |
| **Recipient Role** | any (submitting user) |
| **Subject** | `Project Submission Received: {{ project_title }}` |
| **Body Summary** | Confirms receipt of the project submission to the author, explains next steps (complete additional fields and notify PA Science managers when ready), and provides a link to edit the submission. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc_project.project_received_pascience.yml` |

---

### Project Updated (Manager)

| Field | Value |
|-------|-------|
| **Portal(s)** | pascience |
| **Trigger** | Project node updated (with "notify managers" flag checked) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | PA Science program manager |
| **Recipient Role** | PA Science DMZ manager role |
| **Subject** | `Project Updated: {{ project_title }}` |
| **Body Summary** | Alerts the PA Science DMZ manager that a project has been updated, includes current status, received/approved flags, and a link to review the updated submission. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc_project.project_updated_pascience.yml` |

---

### Project Approved (Author)

| Field | Value |
|-------|-------|
| **Portal(s)** | pascience |
| **Trigger** | Project approved and published on PA Science DMZ portal |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Submitting user (project author) |
| **Recipient Role** | any (submitting user) |
| **Subject** | `Project Approved and Published: {{ project_title }}` |
| **Body Summary** | Congratulates the author that their project is now published on the PA Science DMZ portal, summarizes project details, provides public and management URLs, and outlines next steps (update milestones, change status). |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc_project.project_approved_pascience.yml` |

---

### Project Interest Flagged

| Field | Value |
|-------|-------|
| **Portal(s)** | pascience |
| **Trigger** | A user flags interest in a project |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Project author or configured role |
| **Recipient Role** | project author / configured role |
| **Subject** | `{{ title }} - interest shown on project` |
| **Body Summary** | Notifies the project owner/author that a specific user (`{{ flagged_name }}`) has shown interest in their project, with a link to the project node. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc_project.project_flagged.yml` |
