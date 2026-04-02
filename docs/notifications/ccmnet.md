<!-- auto-generated, do not hand-edit -->
# CCMNet Notifications

This page catalogs all automated notifications for the CCMNet portal.

## Summary Table

| Name | Trigger | Method | Subject | Recipient | Needs Review |
|------|---------|--------|---------|-----------|:------------:|
| New CCMNet User (Admin) | new user registration | email | A new CCMNet participant has joined! | CCMNet PM | — |
| CCMNet Welcome | new user registration | email | Welcome to CCMNet... | New CCMNet user | — |
| Mentorship Interest (Author) | daily cron | email | Interest in your Mentorship | Mentorship author | — |
| Mentorship Interest Digest (Role) | daily cron | email | Daily mentorship interest summary | CCMNet role members | — |
| Liaison/Mentor/Mentee Match | mentor match made | email | A new mentorship match | Liaison | — |
| Mentee Selected | mentor/mentee pairing saved | email | You have been selected as a mentee | Mentee user | — |
| Mentor Selected | mentor/mentee pairing saved | email | You have been selected as a mentor | Mentor user | — |
| Mentorship Approved (PM) | mentorship approved | email | Mentorship Engagement approved | CCMNet PM | — |
| New Mentorship (Admin) | mentorship created | email | New Mentorship Created | CCMNet admin | — |
| Mentorship Created (Requestor) | mentorship created | email | Mentorship Engagement received | Mentorship requestor | — |
| Mentorship In Progress | mentorship status changed to in-progress | email | Mentorship in progress | Liaison and CCMNet PM | — |

## Notification Details

### New CCMNet User (Admin)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | A new user registers or is added to CCMNet |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | CCMNet PM (project manager) |
| **Recipient Role** | ccmnet_pm (BCC: andrew+ccmnet@elytra.net) |
| **Subject** | `A new CCMNet participant has joined!` |
| **Body Summary** | Notifies the CCMNet PM that a new participant has joined the network, with a link to their profile. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.ccmnet_new_user.yml` |

---

### CCMNet Welcome

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | New user added to CCMNet |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | New CCMNet user |
| **Recipient Role** | any (new user) |
| **Subject** | `Welcome to CCMNet (Cyberinfrastructure Community-Wide Mentorship Network)` |
| **Body Summary** | Welcomes the new user to CCMNet, explains the program's purpose, prompts them to update their persona (bio, skills, photo), and links to the CCMNet Affinity Group. Signed by the CCMNet Project team. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.ccmnet_welcome.yml` |

---

### Mentorship Interest (Author)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Daily cron — someone expresses interest in a mentorship request |
| **Send Method** | email |
| **Timing** | cron (daily) |
| **Recipient** | Author of the mentorship request |
| **Recipient Role** | any (mentorship author) |
| **Subject** | `Interest in your Mentorship` |
| **Body Summary** | Notifies the mentorship author that someone is interested in their request; instructs them to review interested parties and update the mentorship when ready. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.cron_author_update.yml` |

---

### Mentorship Interest Digest (Role)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Daily cron — mentorships with new interest requests |
| **Send Method** | email |
| **Timing** | cron (daily) |
| **Recipient** | CCMNet role members |
| **Recipient Role** | ccmnet role |
| **Subject** | `Daily mentorship interest summary` |
| **Body Summary** | Sends a daily digest to CCMNet role members listing all mentorship nodes that received new interest requests recently. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.cron_role_update.yml` |

---

### Liaison/Mentor/Mentee Match

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Mentor match confirmed (mentor and mentee assigned) |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | CCMNet liaison |
| **Recipient Role** | ccmnet liaison (BCC: andrew+ccmnet@elytra.net) |
| **Subject** | `A new mentorship match` |
| **Body Summary** | Notifies the liaison that a CCMNet mentor match has been made, with a link to the mentorship node. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.liaison_mentor_mentee_changed.yml` |

---

### Mentee Selected

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Mentee field updated on mentorship node |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | The selected mentee |
| **Recipient Role** | any (mentee user) |
| **Subject** | `You have been selected as a mentee` |
| **Body Summary** | Congratulates the user on being selected as a mentee for a specific mentorship engagement, with a link to the mentorship. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentee_changed.yml` |

---

### Mentor Selected

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Mentor field updated on mentorship node |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | The selected mentor |
| **Recipient Role** | any (mentor user) |
| **Subject** | `You have been selected as a mentor` |
| **Body Summary** | Congratulates the user on being selected as a mentor for a specific mentorship engagement, with a link to the mentorship. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentor_changed.yml` |

---

### Mentorship Approved (PM)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Mentorship node approved |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | CCMNet PM |
| **Recipient Role** | ccmnet_pm (BCC: andrew+ccmnet@elytra.net) |
| **Subject** | `Mentorship Engagement approved` |
| **Body Summary** | Notifies the CCMNet PM that a mentorship has been approved and is ready for review, with a link to the node. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentorship_approved_ccmnet_pm.yml` |

---

### New Mentorship (Admin)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | New mentorship node created |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | CCMNet admin |
| **Recipient Role** | ccmnet admin (BCC: andrew+ccmnet@elytra.net) |
| **Subject** | `New Mentorship Created` |
| **Body Summary** | Notifies the admin that a new CCMNet mentorship has been requested and needs approval, with a link to approve it. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentorship_created_admin.yml` |

---

### Mentorship Created (Requestor)

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | New mentorship node created |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | Mentorship requestor |
| **Recipient Role** | any (submitting user) |
| **Subject** | `Mentorship Engagement received` |
| **Body Summary** | Confirms to the requestor that their CCMNet mentorship engagement has been created, with a link to view the submission. Thanks them for their participation. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentorship_created.yml` |

---

### Mentorship In Progress

| Field | Value |
|-------|-------|
| **Portal(s)** | ccmnet |
| **Trigger** | Mentorship status changed to "In Progress" |
| **Send Method** | email |
| **Timing** | immediate |
| **Recipient** | CCMNet liaison and PM (watchers) |
| **Recipient Role** | ccmnet liaison / ccmnet_pm (BCC: andrew+ccmnet@elytra.net) |
| **Subject** | `Mentorship in progress` |
| **Body Summary** | Notifies the liaison and CCMNet PM that a mentorship they are watching has been updated to "In Progress" status, with a link to the mentorship. |
| **Edit Location** | `web/sites/default/config/default/symfony_mailer.mailer_policy.ccmnet.mentorship_in_progress.yml` |
