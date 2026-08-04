# PushPress (pushpress)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

PushPress is a gym and fitness business management platform covering membership management, billing and payments, class and appointment scheduling, check-ins, CRM, and a member app. The **PushPress Platform API** is a REST API that lets developers read and manage customers (members), check-ins, appointments, classes, events, plan enrollments, membership plans, invitations, and transactional messaging, and subscribe to platform webhooks for real-time events.

## Access Model (Read First)

- **This is a REST API, not a WebSocket API.** Base URL `https://api.pushpress.com/v3` (staging `https://api.pushpressstage.com/v3`, dev `https://api.pushpressdev.com/v3`). All operations are request/response over HTTPS.
- **Authentication:** an API key passed in the `API-KEY` request header. Every request is also scoped to a single gym location with a `company-id` header. Keys are issued in the developer portal (developer.pushpress.com) and can be managed via the `/keys` endpoints.
- **Real-time:** delivered by **outbound platform webhooks** (PushPress POSTs signed JSON event payloads to your URL). PushPress does **not** expose a first-party WebSocket. The "send notification" endpoint publishes to an **Ably** Realtime channel over REST; the WebSocket in that flow belongs to Ably, a third party.
- **Grounding:** endpoint **paths and methods** here are confirmed against the official Speakeasy-generated SDK (`@pushpress/pushpress`) and the public API reference. Request/response **schemas** in the OpenAPI are **modeled** by API Evangelist and should be reconciled against the authoritative PushPress OpenAPI. The official SDK is described by its maintainers as early/alpha, so details can change.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/pushpress/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/pushpress/refs/heads/main/apis.yml)

## Tags

- Fitness
- Gym Management
- Membership Management
- Fitness Software
- Class Scheduling
- Billing
- CRM
- Wellness
- SaaS
- Webhooks

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### PushPress Customers API

Create, list, and retrieve gym members and leads (customers), plus their lead-source / marketing attributions. The core CRM surface of the PushPress platform.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Check-Ins API

List and retrieve check-ins across class, appointment, event, and open-facility contexts, and get filtered check-in counts.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Appointments API

Retrieve details for scheduled one-on-one and small-group appointments booked through PushPress.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Classes API

Retrieve scheduled classes and list or retrieve the class types offered by a gym.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Events API

List and retrieve gym events such as workshops, competitions, and socials.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Enrollments and Plans API

List and retrieve customer enrollments in membership plans and the membership / billing plan definitions they enroll in.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Company API

Retrieve details for the gym / business (company) that the API key is scoped to.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Invitations API

Create, list, retrieve, and delete invitations for members or staff to join a gym on PushPress.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Messaging API

Send transactional email, SMS, push, and in-app / realtime notifications to gym members. Realtime notifications are published to an Ably channel over a REST request, not a PushPress WebSocket.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress Webhooks API

Create, list, retrieve, update, delete, activate, deactivate, and rotate the signing secret of platform webhooks that deliver real-time events to your endpoints.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

### PushPress API Keys API

Create, list, retrieve, and revoke the API keys used to authenticate against the PushPress Platform API.

- **Human URL:** [https://ppe.apidocumentation.com/](https://ppe.apidocumentation.com/)
- **Base URL:** `https://api.pushpress.com/v3`

## Common Properties

- [Domain Security](security/pushpress-domain-security.yml)
- [Authentication](authentication/pushpress-authentication.yml)
- [GitHub Organization](https://github.com/PushPress)
- [LinkedIn](https://www.linkedin.com/company/pushpress)
- [Website](https://www.pushpress.com)
- [Documentation](https://ppe.apidocumentation.com/)
- [Plans](plans/pushpress-plans-pricing.yml)
- [Rate Limits](rate-limits/pushpress-rate-limits.yml)
- [Fin Ops](finops/pushpress-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
