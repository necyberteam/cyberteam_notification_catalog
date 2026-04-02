<!-- auto-generated, do not hand-edit -->
# Shared Notifications

This page catalogs all automated notifications that apply to multiple portals (MATCH Engagement workflow).

## Summary Table

| Name | Trigger | Method | Subject | Recipient | Needs Review |
|------|---------|--------|---------|-----------|:------------:|
| MATCH Engagement Draft | content moderation transition (create_new_draft) | email | MATCH Engagement draft created | MATCH PM | — |
| MATCH Engagement Received | content moderation transition (save_as_submitted) | email | Your MATCH Engagement was received | Submitting author | — |
| MATCH Engagement Accepted *(disabled)* | content moderation transition (start_recruiting_and_notify_author_) | email | Your MATCH Engagement is ready to recruit! | Submitting author | — |
| MATCH Engagement Review Requested *(disabled)* | content moderation transition (request_review) | email | MATCH Engagement submitted for review | MATCH PM | — |
| MATCH Engagement Final Review *(disabled)* | content moderation transition (finished_adding_information) | email | MATCH Engagement ready for review | MATCH SC | — |

## Notification Details

### MATCH Engagement Draft

| Field | Value |
|-------|-------|
| **Portal(s)** | shared |
| **Trigger** | Content moderation transition: `create_new_draft` in `match_engagement` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | MATCH program managers |
| **Recipient Role** | match_pm |
| **Subject** | `MATCH Engagement draft created` |
| **Body Summary** | Notifies the MATCH PM that a new engagement draft has been created; includes a link to review and edit the draft. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.engagement_draft.yml` |

---

### MATCH Engagement Received

| Field | Value |
|-------|-------|
| **Portal(s)** | shared |
| **Trigger** | Content moderation transition: `save_as_submitted` in `match_engagement` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Submitting author |
| **Recipient Role** | any (author flag) |
| **Subject** | `Your MATCH Engagement was received` |
| **Body Summary** | Confirms to the submitting user that their MATCH engagement request has been received and the team will be in touch soon. Includes a link to the canonical source domain. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.engagement_received.yml` |

---

### MATCH Engagement Accepted *(disabled)*

> **Note:** This notification is currently disabled (`status: false`).

| Field | Value |
|-------|-------|
| **Portal(s)** | shared |
| **Trigger** | Content moderation transition: `start_recruiting_and_notify_author_` in `match_engagement` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Submitting author |
| **Recipient Role** | any (author flag) |
| **Subject** | `Your MATCH Engagement is ready to recruit!` |
| **Body Summary** | Would notify the engagement author that their engagement has been accepted and is now ready to recruit participants, with an edit link. Currently disabled. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.engagement_accepted.yml` |

---

### MATCH Engagement Review Requested *(disabled)*

> **Note:** This notification is currently disabled (`status: false`).

| Field | Value |
|-------|-------|
| **Portal(s)** | shared |
| **Trigger** | Content moderation transition: `request_review` in `match_engagement` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | MATCH program managers |
| **Recipient Role** | match_pm |
| **Subject** | `MATCH Engagement submitted for review` |
| **Body Summary** | Would notify the MATCH PM to review a specific engagement submission, with a link to the edit form. Currently disabled. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.engagement_review_requested.yml` |

---

### MATCH Engagement Final Review *(disabled)*

> **Note:** This notification is currently disabled (`status: false`).

| Field | Value |
|-------|-------|
| **Portal(s)** | shared |
| **Trigger** | Content moderation transition: `finished_adding_information` in `match_engagement` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | MATCH steering committee |
| **Recipient Role** | match_sc |
| **Subject** | `MATCH Engagement ready for review` |
| **Body Summary** | Would notify the MATCH steering committee that an engagement is ready for final review, with a link to the edit form. Currently disabled. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.final_review.yml` |
