# Everhour (everhour)

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

Everhour is a time tracking and budgeting platform for teams that embeds timers and timesheets directly inside the project management tools teams already use - Asana, Trello, ClickUp, Jira, GitHub, Basecamp, Notion, Monday, Linear, and more. The Everhour REST API (`https://api.everhour.com`) gives programmatic access to time records, running timers, weekly timesheets and approvals, clock-in/clock-out timecards, projects and tasks, clients, invoices, expenses, resource scheduling, time off, and reporting dashboards, plus webhooks for time, timer, task, and project change events.

**Access model:** The API is included with every Everhour account, including the Free plan (up to 5 seats) - there is no separate developer signup or API fee. Authentication is a personal API key passed in the `X-Api-Key` header; each user finds their key at the bottom of their profile page in the Everhour app. There is no OAuth flow, so integrations act as the user whose key they hold, and admin-only data (like billing fields via `opts_include_billing=1`) requires an admin's key. An optional `X-Accept-Version` header pins an API version (current 1.2). Everhour labels the API BETA - some calls can be slightly adjusted, with breaking changes pushed in separate versions. Rate limiting is around 20 requests per 10 seconds per API key (429 + `Retry-After` when exceeded), and the docs are hosted on Apiary.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/everhour/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/everhour/refs/heads/main/apis.yml)

## Tags

- Time Tracking
- Timesheets
- Productivity
- Project Management
- Budgeting
- Invoicing

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Everhour Time Records API

Read and write reported time - list time records across the whole team, per user, per task, or per project with date-range filters and pagination, add time to a task, and update or delete existing time records. Time is expressed in seconds; billing data can be included with the `opts_include_billing` flag.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/time-records](https://everhour.docs.apiary.io/#reference/time-records)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Time Tracking
- Time Records
- Timesheets

#### Properties

- [Documentation](https://everhour.docs.apiary.io/)
- [API Reference](https://everhour.docs.apiary.io/#reference/time-records)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Timers API

Control live time tracking - start a timer on a task with an optional comment, fetch the current user's running timer, list every running timer across the team, and stop the current timer to record the tracked time.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/timers](https://everhour.docs.apiary.io/#reference/timers)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Timers
- Time Tracking
- Real Time

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/timers)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Timesheets and Timecards API

Weekly timesheets and attendance timecards - fetch user or team timesheets by week ID, submit a week for approval, approve or reject approval requests (optionally per day), discard requests, and manage clock-in/clock-out timecards with breaks and full change history.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/timesheets](https://everhour.docs.apiary.io/#reference/timesheets)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Timesheets
- Timecards
- Approvals
- Attendance

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/timesheets)
- [Documentation](https://everhour.docs.apiary.io/#reference/timecards)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Projects API

Manage projects and their sections - create, list, search, update, archive, and delete projects, configure billing (hourly, fixed fee, non-billable) with project or per-user rates, set money/time/cost budgets with periods and thresholds, and instantly sync projects from connected integrations like Asana, Trello, ClickUp, and GitHub.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/projects](https://everhour.docs.apiary.io/#reference/projects)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Projects
- Sections
- Budgets
- Billing

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/projects)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Tasks API

Work with tasks - list and search tasks globally or within a project, create tasks in sections with assignees and due dates, update task details and custom field values, and set or remove time estimates (overall or per user).

- **Human URL:** [https://everhour.docs.apiary.io/#reference/tasks](https://everhour.docs.apiary.io/#reference/tasks)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Tasks
- Estimates
- Custom Fields

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/tasks)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Schedule and Time Off API

Resource planner and time off management - list, create, update, and delete schedule assignments, create time off requests with approval workflow, and manage time off types and accrual allocations with carried days and over-allocation restrictions.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/schedule](https://everhour.docs.apiary.io/#reference/schedule)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Resource Planning
- Scheduling
- Time Off

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/schedule)
- [Documentation](https://everhour.docs.apiary.io/#reference/time-off)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Clients and Invoices API

Manage clients with money, time, or cost budgets, then bill them - create invoices from uninvoiced time and expenses in a date range, refresh line items, apply tax and discounts, move invoices through draft/sent/paid statuses, and export them to Xero, QuickBooks, or FreshBooks.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/clients](https://everhour.docs.apiary.io/#reference/clients)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Clients
- Invoices
- Budgets

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/clients)
- [Documentation](https://everhour.docs.apiary.io/#reference/invoices)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Expenses API

Track billable and non-billable expenses against projects and users - create, update, and delete expenses, manage expense categories (including unit-based categories like mileage), and attach jpg, png, or pdf receipts.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/expenses](https://everhour.docs.apiary.io/#reference/expenses)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Expenses
- Attachments
- Budgeting

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/expenses)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Reports API

Dashboard reports aggregated by project, client, or team member - time, billable and non-billable time, time off, billable amounts, labor and expense costs, profit, and uninvoiced amounts, filterable by date range, project, client, and user. Time is in seconds and amounts in cents.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/reports](https://everhour.docs.apiary.io/#reference/reports)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Reports
- Dashboards
- Analytics

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/reports)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Users API

Identity and team roster - fetch the profile that owns the API key (`GET /users/me`) and list all team members with their roles (admin, supervisor, member) and statuses.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/users](https://everhour.docs.apiary.io/#reference/users)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Users
- Team

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/users)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

### Everhour Webhooks API

Subscribe to change notifications - create, get, update, and delete webhook subscriptions for project, task, section, client, estimate, timer started/stopped, and time updated events, optionally scoped to a single project, with `X-Hook-Secret` target URL verification.

- **Human URL:** [https://everhour.docs.apiary.io/#reference/webhooks](https://everhour.docs.apiary.io/#reference/webhooks)
- **Base URL:** `https://api.everhour.com`

#### Tags

- Webhooks
- Events
- Automation

#### Properties

- [API Reference](https://everhour.docs.apiary.io/#reference/webhooks)
- [OpenAPI](openapi/everhour-openapi.yml)
- [Postman Collection](collections/everhour.postman_collection.json)
- [Open Collection](collections/everhour.opencollection.json)

## Common Properties

- [Website](https://everhour.com)
- [Documentation](https://everhour.docs.apiary.io/)
- [LinkedIn](https://www.linkedin.com/company/everhour)
- [Pricing](https://everhour.com/pricing)
- [Blog](https://everhour.com/blog/)
- [Plans](plans/everhour-plans-pricing.yml)
- [Rate Limits](rate-limits/everhour-rate-limits.yml)
- [Fin Ops](finops/everhour-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
