# PushPress (pushpress)

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
