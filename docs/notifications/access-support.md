<!-- auto-generated, do not hand-edit -->
# ACCESS Support Notifications

This page catalogs all automated notifications for the ACCESS Support portal.

## Summary Table

| Name | Trigger | Method | Subject | Recipient | Needs Review |
|------|---------|--------|---------|-----------|:------------:|
| Needs Adjustment | content moderation transition (request_adjustment) | email | Your [...] needs adjustment | content author | — |
| Published | content moderation transition (publish) | email | Your [...] was published | content author | — |
| Review Requested | content moderation transition (send_for_review) | email | [...] needs review | match_pm role | — |
| Event Registration Confirmation | user registers for event | email | `{{ email_title }}` | registering user | — |
| Registration Approved | event registration approved | email | `{{ email_title }}` | registered user | — |
| Waitlist Notification | registration waitlisted | email | Waitlist Status for `{{ title }}` | waitlisted user | — |
| Registrant Digest | new event registrations (digest) | email | `{{ registration_count }}` new registration(s) for `{{ event_title }}` | event author | — |
| Post-Event Survey | post-event action | email | Please participate in our survey for `{{ title }}` | registered user | — |
| Post-Event Survey Reminder | post-event reminder | email | Reminder: please participate in our survey for `{{ title }}` | registered user | — |
| Announcement Review | announcement content created | email | An announcement is ready for review | reviewer role | — |
| Ticketing Form Email | webform submission (ticketing form) | email | Derived from form data | ticketing system queue | ⚠️ |
| Account Support Request | webform submission (account support form) | email | account support request from [name] | 0-Help@tickets.access-ci.org | ⚠️ |
| Request to Add Org | webform submission (orgs list form) | email | Request to add an organization from [name] | support@access-ci.atlassian.net | ⚠️ |

## Notification Details

### Needs Adjustment

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Content moderation transition: `request_adjustment` in `editorial` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Content author |
| **Recipient Role** | any (author flag) |
| **Subject** | `Your {% if entity.bundle|title == 'Access_News' %}ACCESS News{% else %}ACCESS Event{% endif %} needs adjustment` |
| **Body Summary** | Notifies the author that their ACCESS News article or ACCESS Event needs adjustment, and provides a direct edit link. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.needs_adjustment.yml` |

---

### Published

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Content moderation transition: `publish` in `editorial` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Content author |
| **Recipient Role** | any (author flag) |
| **Subject** | `Your {% if entity.bundle|title == 'Access_News' %}Announcement{% else %}Event{% endif %} was published` |
| **Body Summary** | Notifies the author that their ACCESS News announcement or event has been published, with a link to the published content. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.published.yml` |

---

### Review Requested

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Content moderation transition: `send_for_review` in `editorial` workflow |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Content moderators |
| **Recipient Role** | match_pm |
| **Subject** | `{% if entity.bundle == 'access_news' %}Community News{% else %}A Community Event{% endif %} from {{ entity.uid.entity.getDisplayName() }} needs review` |
| **Body Summary** | Notifies the `match_pm` role that a community news article or event has been submitted for review, with a link to the edit form. |
| **Edit Location** | `web/sites/default/config/default/content_moderation_notifications.content_moderation_notification.review_requested.yml` |

---

### Event Registration Confirmation

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | User registers for an event |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Registering user |
| **Recipient Role** | any |
| **Subject** | `{{ email_title }}` (configured per event) |
| **Body Summary** | Sends a confirmation email to a user who registers for an event; body content is customized per event via `{{ custom_body }}`. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.register.yml` |

---

### Registration Approved

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Event registration is approved by organizer |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Registered user |
| **Recipient Role** | any |
| **Subject** | `{{ email_title }}` (configured per event) |
| **Body Summary** | Notifies a user that their event registration has been approved; body content is customized per event via `{{ custom_body }}`. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.registration_approved.yml` |

---

### Waitlist Notification

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | User registration placed on waitlist (event full) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Waitlisted user |
| **Recipient Role** | any |
| **Subject** | `Waitlist Status for {{ title }}` |
| **Body Summary** | Informs the user that the event is full and they have been placed on the waitlist; promises notification if a spot opens up. Signed "ACCESS Support". |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.waitlist.yml` |

---

### Registrant Digest

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | New event registrations received (digest) |
| **Send Method** | email |
| **Timing** | digest |
| **Recipient** | Event author |
| **Recipient Role** | any (event author) |
| **Subject** | `{% if registration_count == 1 %}{{ registration_count }} new registration{% else %}{{ registration_count }} new registrations{% endif %} for {{ event_title }}` |
| **Body Summary** | Sends the event author a summary of new registrations, including a count and a link to review registrants. Optionally includes the timestamp of the first registration. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.registrant_digest.yml` |

---

### Post-Event Survey

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Post-event trigger (cron or manual) |
| **Send Method** | email |
| **Timing** | immediate / cron |
| **Recipient** | Registered event attendees |
| **Recipient Role** | any |
| **Subject** | `Please participate in our survey for {{ title }}` |
| **Body Summary** | Invites event attendees to complete a post-event survey; body is customized per event via `{{ custom_body }}`. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.post_survey.yml` |

---

### Post-Event Survey Reminder

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Reminder cron/follow-up for non-responding survey recipients |
| **Send Method** | email |
| **Timing** | cron / scheduled |
| **Recipient** | Registered event attendees (non-responders) |
| **Recipient Role** | any |
| **Subject** | `Reminder: please participate in our survey for {{ title }}` |
| **Body Summary** | Reminds event attendees who have not yet completed the post-event survey to participate; body is customized per event via `{{ custom_body }}`. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_misc.post_survey_reminder.yml` |

---

### Announcement Review

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Announcement content submitted for review |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Announcement reviewer |
| **Recipient Role** | configured in mailer policy |
| **Subject** | `An announcement is ready for review` |
| **Body Summary** | Notifies the reviewer that a new announcement has been added and is ready to be reviewed, with a link to the announcement. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.access_news.announcement_review.yml` |

---

### Ticketing Form Email

> ⚠️ **Needs manual verification** — extracted via regex scan.

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Webform submission (support ticketing form) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Ticketing system queue (routing based on resource/category selection) |
| **Recipient Role** | any |
| **Subject** | Derived from form data |
| **Body Summary** | Routes support request to the appropriate ticketing queue based on resource, allocation category, or other form selections; sends formatted email via `$mailManager->mail('ticketing', 'ticketing', ...)`. |
| **Edit Location** | `web/modules/custom/access/modules/ticketing/src/Plugin/WebformHandler/TicketingSendEmailHandler.php` |

---

### Account Support Request

> ⚠️ **Needs manual verification** — extracted via regex scan.

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Webform submission (account support form) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | 0-Help@tickets.access-ci.org |
| **Recipient Role** | any |
| **Subject** | `account support request from [submitter name]` |
| **Body Summary** | Sends the account support form data to the ACCESS help ticket queue; body is rendered from a Twig template with submitter name, email, ACCESS ID, and comment fields. |
| **Edit Location** | `web/modules/custom/access/modules/ticketing/src/Plugin/WebformHandler/AccountSupportHandler.php` |

---

### Request to Add Org

> ⚠️ **Needs manual verification** — extracted via regex scan.

| Field | Value |
|-------|-------|
| **Portal(s)** | access-support |
| **Trigger** | Webform submission (add organization to ACCESS list form) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | support@access-ci.atlassian.net |
| **Recipient Role** | any |
| **Subject** | `Request to add an organization from [submitter name]` |
| **Body Summary** | Forwards the organization addition request (submitter name, email, organization details) to the ACCESS support Jira project via email, rendered from a Twig template. |
| **Edit Location** | `web/modules/custom/access/modules/ticketing/src/Plugin/WebformHandler/RequestOrgsListAddHandler.php` |
