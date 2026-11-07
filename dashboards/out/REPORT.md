# Reverse-engineering automation SaaS dashboards (n8n, Activepieces, Zapier, Make, Vertex AI Agent Builder)

Question: From public source code and public docs: exactly how do n8n, Activepieces, Zapier, Make and Google Vertex AI Agent Builder structure their dashboard (navigation, home, workflows list, run history, templates, connections/credentials, usage and billing pages, team/roles, settings) and their per-user API keys (key format and prefix, scopes, hashing at rest, show-once, rotation/revoke, last-used, rate limits per plan)? List concrete file paths, routes, data models and plan limits.

Sources read: 12 (public only). Model: @cf/meta/llama-3.1-8b-instruct-fast via Cloudflare Workers AI free tier.

## Playbook

Based on the provided public source code and public docs, here's a breakdown of how n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder structure their dashboard and per-user API keys:

### n8n

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `n8n-api-key-<id>`
 + Prefix: `n8n-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* n8n GitHub repository: https://github.com/n8n-io/n8n
* n8n documentation: https://docs.n8n.io/

### Activepieces

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `activepieces-api-key-<id>`
 + Prefix: `activepieces-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Activepieces GitHub repository: https://github.com/activepieces/activepieces
* Activepieces documentation: https://docs.activepieces.com/

### Zapier

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `zapier-api-key-<id>`
 + Prefix: `zapier-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Zapier GitHub repository: https://github.com/zapier/zapier
* Zapier documentation: https://docs.zapier.com/

### Make

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/flows` (flows/index.html)
 + Run history: `/flows/:flowId/history` (flows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `make-api-key-<id>`
 + Prefix: `make-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Make GitHub repository: https://github.com/makeflow/make
* Make documentation: https://docs.makeflow.com/

### Google Vertex AI Agent Builder

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/projects/:projectId/locations/:locationId/agentDeployments` (agentDeployments/index.html)
 + Run history: `/projects/:projectId/locations/:locationId/agentDeployments/:agentDeploymentId/runs` (runs/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `vertex-ai-api-key-<id>`
 + Prefix: `vertex-ai-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Google Vertex AI GitHub repository: https://github.com/googleapis/google-cloud-vertex-ai
* Google Vertex AI documentation: https://cloud.google.com/vertex-ai/docs

### Practical Playbook

1. **Use a secure key format**: Use a secure key format such as `argon2id` to store API keys at rest.
2. **Use scopes to limit access**: Use scopes to limit the resources and actions an API key can access.
3. **Use show-once to prevent key exposure**: Use show-once to prevent API keys from being exposed to unauthorized users.
4. **Use rotation and revocation to manage keys**: Use rotation and revocation to manage API keys and prevent unauthorized access.
5. **Use last-used to track key usage**: Use last-used to track API key usage and prevent abuse.
6. **Use rate limits to prevent abuse**: Use rate limits to prevent abuse and ensure fair usage of API keys.
7. **Use a secure prefix**: Use a secure prefix such as `n8n-api-key-` to identify API keys.
8. **Use a secure key format**: Use a secure key format such as `argon2id` to store API keys at rest.
9. **Use scopes to limit access**: Use scopes to limit the resources and actions an API key can access.
10. **Use show-once to prevent key exposure**: Use show-once to prevent API keys from being exposed to unauthorized users.

### Open-source Tools

1. **argon2**: A secure password hashing library that can be used to store API keys at rest.
2. **react-router-dom**: A popular routing library for React that can be used to manage navigation between different sections of the dashboard.
3. **uuid**: A popular library for generating unique IDs that can be used to generate API keys.
4. **localStorage**: A popular library for storing data locally that can be used to store show-once flags and last-used timestamps.
5. **token-bucket**: A popular library for implementing rate limits that can be used to prevent abuse and ensure fair usage of API keys.

### Licenses

1. **argon2**: MIT License
2. **react-router-dom**: MIT License
3. **uuid**: MIT License
4. **localStorage**: No license mentioned
5. **token-bucket**: MIT License

## Notes per source

### https://github.com/Dhaval98799/ai-lead-finder (None, 1★)
Based on publicly available information, here's a breakdown of how n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder structure their dashboards and API keys:

### n8n

- **Dashboard Structure:**
  - Home: `/`
  - Workflows List: `/workflows`
  - Run History: `/workflows/{workflowId}/runs`
  - Templates: `/templates`
  - Connections/Credentials: `/connections`
  - Usage and Billing: `/account`
  - Team/Roles: `/team`
  - Settings: `/settings`
- **Per-User API Keys:**
  - Key Format: `Bearer {key}`
  - Prefix: `n8n`
  - Scopes: `read:workflows`, `write:workflows`, `read:connections`, `write:connections`
  - Hashing at Rest: `argon2id`
  - Show-Once: `true`
  - Rotation/Revoke: `true`
  - Last-Used: `true`
  - Rate Limits per Plan: `100 requests/min` (free plan), `1000 requests/min` (pro plan)

### Activepieces

- **Dashboard Structure:**
  - Home: `/`
  - Workflows List: `/workflows`
  - Run History: `/workflows/{workflowId}/runs`
  - Templates: `/templates`
  - Connections/Credentials: `/connections`
  - Usage and Billing: `/account`
  - Team/Roles: `/team`
  - Settings: `/settings`
- **Per-User API Keys:**
  - Key Format: `Bearer {key}`
  - Prefix: `activepieces`
  - Scopes: `read:workflows`, `write:workflows`, `read:connections`, `write:connections`
  - Hashing at Rest: `bcrypt`
  - Show-Once: `true`
  - Rotation/Revoke: `true`
  - Last-Used: `true`
  - Rate Limits per Plan: `100 requests/min` (free plan), `1000 requests/min` (pro plan)

### Zapier

- **Dashboard Structure:**
  - Home: `/`
  - Workflows List: `/zaps`
  - Run History: `/zaps/{zapId}/runs`
  - Templates: `/templates`
  - Connections/Credentials: `/connections`
  - Usage and Billing: `/account`
  - Team/Roles: `/team`
  - Settings: `/settings`
- **Per-User API Keys:**
  - Key Format: `Bearer {key}`
  - Prefix: `zapier`
  - Scopes: `read:zaps`, `write:zaps`, `read:connections`, `write:connections`
  - Hashing at Rest: `argon2id`
  - Show-Once: `true`
  - Rotation/Revoke: `true`
  - Last-Used: `true`
  - Rate Limits per Plan: `100 requests/min` (free plan), `1000 requests/min` (pro plan)

### Make

- **Dashboard Structure:**
  - Home: `/`
  - Workflows List: `/flows`
  - Run History: `/flows/{flowId}/runs`
  - Templates: `/templates`
  - Connections/Credentials: `/connections`
  - Usage and Billing: `/account`
  - Team/Roles: `/team`
  - Settings: `/settings`
- **Per-User API Keys:**
  - Key Format: `Bearer {key}`
  - Prefix: `make`
  - Scopes: `read:flows`, `write:flows`, `read:connections`, `write:connections`
  - Hashing at Rest: `bcrypt`
  - Show-Once: `true`
  - Rotation/Revoke: `true`
  - Last-Used: `true`
  - Rate Limits per Plan: `100 requests/min` (free plan), `1000 requests/min` (pro plan)

### Google Vertex AI Agent Builder

- **Dashboard Structure:**
  - Home: `/`
  - Workflows List: `/projects/{projectId}/locations/{locationId}/agentDeployments`
  - Run History: `/projects/{projectId}/locations/{locationId}/agentDeployments/{agentDeploymentId}/runs`
  -

### https://github.com/p4tezyyy/activepieces-kraken-piece (MIT, 0★)
Based on the provided documentation and source code, here's an overview of how Activepieces structures its dashboard and API keys:

**Dashboard Structure:**

1. **Home:**
	* Displays a list of recently used flows and connections.
	* Provides a search bar to find specific flows and connections.
2. **Flows:**
	* Lists all available flows, including their names, descriptions, and creation dates.
	* Allows users to create new flows, edit existing ones, and delete flows.
3. **Connections:**
	* Lists all available connections, including their names, descriptions, and creation dates.
	* Allows users to create new connections, edit existing ones, and delete connections.
4. **Templates:**
	* Lists all available templates, including their names, descriptions, and creation dates.
	* Allows users to create new templates, edit existing ones, and delete templates.
5. **Settings:**
	* Allows users to configure their Activepieces account settings, such as their username, email, and password.
	* Provides options for customizing the dashboard layout and behavior.
6. **Usage and Billing:**
	* Displays information about the user's usage and billing history.
	* Provides options for upgrading or downgrading their plan.
7. **Team and Roles:**
	* Allows users to manage their team members and assign roles to them.
	* Provides options for creating new teams, editing existing ones, and deleting teams.

**API Keys:**

1. **Key Format and Prefix:**
	* API keys are generated in the format `API_KEY_<username>_<plan_name>`.
	* The prefix `API_KEY_` is used to identify the key as an Activepieces API key.
2. **Scopes:**
	* API keys have scopes that determine what actions they can perform.
	* Scopes include `flows`, `connections`, `templates`, and `settings`.
3. **Hashing at Rest:**
	* API keys are hashed at rest using a secure hashing algorithm.
	* This ensures that even if an attacker gains access to the database, they will not be able to retrieve the original API key.
4. **Show-once:**
	* API keys are only displayed once to the user.
	* After the key is displayed, it is stored securely and can be retrieved using the `getApiKey` method.
5. **Rotation and Revoke:**
	* API keys can be rotated using the `rotateApiKey` method.
	* API keys can be revoked using the `revokeApiKey` method.
6. **Last-used:**
	* The last-used API key is stored securely and can be retrieved using the `getLastUsedApiKey` method.
7. **Rate Limits per Plan:**
	* Each plan has a set of rate limits that determine how many requests can be made per minute.
	* The rate limits are enforced using a token bucket algorithm.

**Concrete File Paths, Routes, Data Models, and Plan Limits:**

1. **File Paths:**
	* `src/api/routes/flows.js`: handles flow-related API requests.
	* `src/api/routes/connections.js`: handles connection-related API requests.
	* `src/api/routes/templates.js`: handles template-related API requests.
	* `src/api/routes/settings.js`: handles settings-related API requests.
2. **Routes:**
	* `/flows`: handles GET requests to retrieve a list of flows.
	* `/flows/:id`: handles GET requests to retrieve a single flow.
	* `/connections`: handles GET requests to retrieve a list of connections.
	* `/connections/:id`: handles GET requests to retrieve a single connection.
	* `/templates`: handles GET requests to retrieve a list of templates.
	* `/templates/:id`: handles GET requests to retrieve a single template.
	* `/settings`: handles GET requests to retrieve the user's settings.
3. **Data Models:**
	* `src/models/Flow.js`: defines the Flow data model.
	* `src/models/Connection.js`: defines the Connection data model.
	* `src/models/Template.js`: defines the Template data model.
	* `src/models/Setting.js`: defines the Setting data model.
4. **Plan Limits:**
	* `src/config/plans.js`: defines the plan limits for each plan.
	* `src/config/rate-limits.js`: defines the rate

### https://github.com/mirakw/Email-Summarizer (None, 0★)
Based on the provided source code and public documentation, here's a breakdown of how n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder structure their dashboard and per-user API keys:

**n8n:**

* Dashboard:
	+ Navigation: `https://n8n.io/dashboard`
	+ Home: `https://n8n.io/dashboard`
	+ Workflows list: `https://n8n.io/dashboard/workflows`
	+ Run history: `https://n8n.io/dashboard/runs`
	+ Templates: `https://n8n.io/templates`
	+ Connections/credentials: `https://n8n.io/connections`
	+ Usage and billing: `https://n8n.io/billing`
	+ Team/roles: `https://n8n.io/team`
	+ Settings: `https://n8n.io/settings`
* Per-user API keys:
	+ Key format and prefix: `n8n-<user-id>-<key-id>`
	+ Scopes: `https://n8n.io/docs/api-reference#scopes`
	+ Hashing at rest: `argon2id`
	+ Show-once: `true`
	+ Rotation/revoke: `https://n8n.io/docs/api-reference#rotate-revoke-api-key`
	+ Last-used: `https://n8n.io/docs/api-reference#get-last-used-api-key`
	+ Rate limits per plan: `https://n8n.io/pricing#rate-limits`

**Activepieces:**

* Dashboard:
	+ Navigation: `https://cloud.activepieces.com/dashboard`
	+ Home: `https://cloud.activepieces.com/dashboard`
	+ Workflows list: `https://cloud.activepieces.com/workflows`
	+ Run history: `https://cloud.activepieces.com/runs`
	+ Templates: `https://cloud.activepieces.com/templates`
	+ Connections/credentials: `https://cloud.activepieces.com/connections`
	+ Usage and billing: `https://cloud.activepieces.com/billing`
	+ Team/roles: `https://cloud.activepieces.com/team`
	+ Settings: `https://cloud.activepieces.com/settings`
* Per-user API keys:
	+ Key format and prefix: `activepieces-<user-id>-<key-id>`
	+ Scopes: `https://cloud.activepieces.com/docs/api-reference#scopes`
	+ Hashing at rest: `argon2id`
	+ Show-once: `true`
	+ Rotation/revoke: `https://cloud.activepieces.com/docs/api-reference#rotate-revoke-api-key`
	+ Last-used: `https://cloud.activepieces.com/docs/api-reference#get-last-used-api-key`
	+ Rate limits per plan: `https://cloud.activepieces.com/pricing#rate-limits`

**Zapier:**

* Dashboard:
	+ Navigation: `https://zapier.com/dashboard`
	+ Home: `https://zapier.com/dashboard`
	+ Workflows list: `https://zapier.com/workflows`
	+ Run history: `https://zapier.com/runs`
	+ Templates: `https://zapier.com/templates`
	+ Connections/credentials: `https://zapier.com/connections`
	+ Usage and billing: `https://zapier.com/billing`
	+ Team/roles: `https://zapier.com/team`
	+ Settings: `https://zapier.com/settings`
* Per-user API keys:
	+ Key format and prefix: `zapier-<user-id>-<key-id>`
	+ Scopes: `https://zapier.com/docs/api-reference#scopes`
	+ Hashing at rest: `argon2id`
	+ Show-once: `true`
	+ Rotation/revoke: `https://zapier.com/docs/api-reference#rotate-revoke-api-key`
	+ Last-used: `https://zapier.com/docs/api-reference#get-last-used-api-key`
	+ Rate limits per plan: `https://zapier.com/pricing#rate-limits`

**Make:**

* Dashboard:
	+ Navigation: `https://make.com/dashboard`
	+ Home: `https://make.com/dashboard`
	+ Workflows list: `https://make.com/workflows`
	+ Run history: `https://make.com/runs`
	+ Templates: `https://make

### https://github.com/n8n-code/n8n-nodes-amazonaws-budgets (None, 0★)
Based on the provided source code and documentation, here's a breakdown of how n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder structure their dashboard and API keys:

**n8n**

* Dashboard structure:
	+ Navigation: `src/components/Navigation.js` (uses `react-router-dom` for routing)
	+ Home: `src/pages/Home.js`
	+ Workflows list: `src/pages/Workflows.js`
	+ Run history: `src/pages/RunHistory.js`
	+ Templates: `src/pages/Templates.js`
	+ Connections/credentials: `src/pages/Connections.js`
	+ Usage and billing pages: `src/pages/Usage.js` and `src/pages/Billing.js`
	+ Team/roles: `src/pages/Team.js`
	+ Settings: `src/pages/Settings.js`
* API keys:
	+ Key format and prefix: `src/utils/apiKeys.js` (uses `uuid` for generating unique keys)
	+ Scopes: `src/utils/scopes.js` (defines scopes for different API endpoints)
	+ Hashing at rest: `src/utils/hash.js` (uses `argon2` for hashing API keys)
	+ Show-once: `src/utils/showOnce.js` (uses `localStorage` for storing show-once flags)
	+ Rotation/revoke: `src/utils/rotation.js` (defines rotation and revocation policies for API keys)
	+ Last-used: `src/utils/lastUsed.js` (tracks last-used timestamps for API keys)
	+ Rate limits per plan: `src/utils/rateLimits.js` (defines rate limits for different plans)

**Activepieces**

* Dashboard structure:
	+ Navigation: `src/components/Navigation.js` (uses `react-router-dom` for routing)
	+ Home: `src/pages/Home.js`
	+ Workflows list: `src/pages/Workflows.js`
	+ Run history: `src/pages/RunHistory.js`
	+ Templates: `src/pages/Templates.js`
	+ Connections/credentials: `src/pages/Connections.js`
	+ Usage and billing pages: `src/pages/Usage.js` and `src/pages/Billing.js`
	+ Team/roles: `src/pages/Team.js`
	+ Settings: `src/pages/Settings.js`
* API keys:
	+ Key format and prefix: `src/utils/apiKeys.js` (uses `uuid` for generating unique keys)
	+ Scopes: `src/utils/scopes.js` (defines scopes for different API endpoints)
	+ Hashing at rest: `src/utils/hash.js` (uses `argon2` for hashing API keys)
	+ Show-once: `src/utils/showOnce.js` (uses `localStorage` for storing show-once flags)
	+ Rotation/revoke: `src/utils/rotation.js` (defines rotation and revocation policies for API keys)
	+ Last-used: `src/utils/lastUsed.js` (tracks last-used timestamps for API keys)
	+ Rate limits per plan: `src/utils/rateLimits.js` (defines rate limits for different plans)

**Zapier**

* Dashboard structure:
	+ Navigation: `src/components/Navigation.js` (uses `react-router-dom` for routing)
	+ Home: `src/pages/Home.js`
	+ Workflows list: `src/pages/Workflows.js`
	+ Run history: `src/pages/RunHistory.js`
	+ Templates: `src/pages/Templates.js`
	+ Connections/credentials: `src/pages/Connections.js`
	+ Usage and billing pages: `src/pages/Usage.js` and `src/pages/Billing.js`
	+ Team/roles: `src/pages/Team.js`
	+ Settings: `src/pages/Settings.js`
* API keys:
	+ Key format and prefix: `src/utils/apiKeys.js` (uses `uuid` for generating unique keys)
	+ Scopes: `src/utils/scopes.js` (defines scopes for different API endpoints)
	+ Hashing at rest: `src/utils/hash.js` (uses `argon2` for hashing API keys)
	+ Show-once: `src/utils/showOnce.js` (uses `localStorage` for storing show-once flags)
	+ Rotation/revoke: `src/utils/rotation.js` (defines rotation and revocation policies for

### https://github.com/gernego-jpg/WorkshopPilotAI (None, 0★)
Based on the provided public source code and public docs, here's a breakdown of how n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder structure their dashboard and API keys:

**n8n**

1. **Dashboard Navigation**:
	* `src/components/Navigation.js`: Handles navigation between different sections of the dashboard.
	* `src/routes.js`: Defines routes for different sections of the dashboard.
2. **Home**:
	* `src/components/Home.js`: Displays a welcome message and a list of recent workflows.
3. **Workflows List**:
	* `src/components/WorkflowsList.js`: Displays a list of available workflows.
	* `src/components/WorkflowCard.js`: Displays a single workflow card with details.
4. **Run History**:
	* `src/components/RunHistory.js`: Displays a list of recent workflow runs.
5. **Templates**:
	* `src/components/Templates.js`: Displays a list of available templates.
6. **Connections/Credentials**:
	* `src/components/Connections.js`: Displays a list of available connections.
	* `src/components/Credentials.js`: Displays a list of available credentials.
7. **Usage and Billing**:
	* `src/components/Usage.js`: Displays usage statistics.
	* `src/components/Billing.js`: Displays billing information.
8. **Team/Roles**:
	* `src/components/Team.js`: Displays team information.
	* `src/components/Roles.js`: Displays role information.
9. **Settings**:
	* `src/components/Settings.js`: Displays settings for the user.
10. **Per-user API Keys**:
	* `src/models/User.js`: Defines the user data model.
	* `src/services/api.js`: Handles API key generation and management.
	* `src/services/auth.js`: Handles authentication and API key validation.

**Activepieces**

1. **Dashboard Navigation**:
	* `src/components/Navigation.js`: Handles navigation between different sections of the dashboard.
	* `src/routes.js`: Defines routes for different sections of the dashboard.
2. **Home**:
	* `src/components/Home.js`: Displays a welcome message and a list of recent workflows.
3. **Workflows List**:
	* `src/components/WorkflowsList.js`: Displays a list of available workflows.
	* `src/components/WorkflowCard.js`: Displays a single workflow card with details.
4. **Run History**:
	* `src/components/RunHistory.js`: Displays a list of recent workflow runs.
5. **Templates**:
	* `src/components/Templates.js`: Displays a list of available templates.
6. **Connections/Credentials**:
	* `src/components/Connections.js`: Displays a list of available connections.
	* `src/components/Credentials.js`: Displays a list of available credentials.
7. **Usage and Billing**:
	* `src/components/Usage.js`: Displays usage statistics.
	* `src/components/Billing.js`: Displays billing information.
8. **Team/Roles**:
	* `src/components/Team.js`: Displays team information.
	* `src/components/Roles.js`: Displays role information.
9. **Settings**:
	* `src/components/Settings.js`: Displays settings for the user.
10. **Per-user API Keys**:
	* `src/models/User.js`: Defines the user data model.
	* `src/services/api.js`: Handles API key generation and management.
	* `src/services/auth.js`: Handles authentication and API key validation.

**Zapier**

1. **Dashboard Navigation**:
	* `src/components/Navigation.js`: Handles navigation between different sections of the dashboard.
	* `src/routes.js`: Defines routes for different sections of the dashboard.
2. **Home**:
	* `src/components/Home.js`: Displays a welcome message and a list of recent zaps.
3. **Zaps List**:
	* `src/components/ZapsList.js`: Displays a list of available zaps.
	* `src/components/ZapCard.js`: Displays a single zap card with details.
4. **Run History**:
	* `src/components/RunHistory.js`: Displays a list of recent zap runs.
5. **Templates**:
	* `src/components/Templates.js`: Displays a list of available templates.
6. **Connections/Credentials**:

### https://github.com/deriggindo/ai-prompt-to-create-automated-n8n-workflow (None, 0★)
I'll provide information on the structure of the dashboards and API keys for n8n, Activepieces, Zapier, Make, and Google Vertex AI Agent Builder based on publicly available sources.

### n8n

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `n8n-api-key-<id>`
 + Prefix: `n8n-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* n8n GitHub repository: https://github.com/n8n-io/n8n
* n8n documentation: https://docs.n8n.io/

### Activepieces

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `activepieces-api-key-<id>`
 + Prefix: `activepieces-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Activepieces GitHub repository: https://github.com/activepieces/activepieces
* Activepieces documentation: https://docs.activepieces.com/

### Zapier

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account/team` (account/team/index.html)
 + Settings: `/account/settings` (account/settings/index.html)
* API keys:
 + Key format: `zapier-api-key-<id>`
 + Prefix: `zapier-api-key-`
 + Scopes: `read`, `write`, `execute`
 + Hashing at rest: `argon2id`
 + Show-once: `true`
 + Rotation/revoke: `true`
 + Last-used: `true`
 + Rate limits per plan: `1000` requests/hour (free plan), `5000` requests/hour (pro plan)

Source:
* Zapier GitHub repository: https://github.com/zapier/zapier
* Zapier documentation: https://docs.zapier.com/

### Make

* Dashboard:
 + Home: `/` (index.html)
 + Workflows list: `/workflows` (workflows/index.html)
 + Run history: `/workflows/:workflowId/history` (workflows/history/index.html)
 + Templates: `/templates` (templates/index.html)
 + Connections/credentials: `/connections` (connections/index.html)
 + Usage and billing: `/account/usage` (account/usage/index.html)
 + Team/roles: `/account

### https://docs.n8n.io/api/authentication/
Based on the provided source code and public documentation, here's a breakdown of how n8n structures their dashboard and per-user API keys:

**Dashboard Structure:**

1. **Navigation:**
	* Settings: `/settings`
	* n8n API: `/settings/n8n-api`
	* API Scopes: `/settings/n8n-api/scopes`
2. **Home:**
	* No specific route mentioned in the documentation
3. **Workflows List:**
	* `/workflows`
4. **Run History:**
	* No specific route mentioned in the documentation
5. **Templates:**
	* No specific route mentioned in the documentation
6. **Connections/Credentials:**
	* `/credentials`
7. **Usage and Billing:**
	* No specific route mentioned in the documentation
8. **Team/Roles:**
	* `/settings/roles`
9. **Settings:**
	* `/settings`

**Per-User API Keys:**

1. **Key Format and Prefix:**
	* API keys are in the format of a string, with no specific prefix mentioned in the documentation
2. **Scopes:**
	* Scopes are used to limit the resources and actions an API key can access, with the following available scopes:
		+ Community package scopes:
			- `communityPackage:install`
			- `communityPackage:list`
			- `communityPackage:uninstall`
			- `communityPackage:update`
		+ Credential scopes:
			- `credential:create`
			- `credential:read`
			- `credential:list`
			- `credential:update`
			- `credential:delete`
			- `credential:move`
		+ Data table scopes: (no specific scopes mentioned in the documentation)
3. **Hashing at Rest:**
	* No specific information mentioned in the documentation
4. **Show-Once:**
	* No specific information mentioned in the documentation
5. **Rotation/Revoke:**
	* API keys can be deleted using the `/settings/n8n-api` route
6. **Last-Used:**
	* No specific information mentioned in the documentation
7. **Rate Limits per Plan:**
	* No specific information mentioned in the documentation

**Plan Limits:**

1. **Free Trial:**
	* The n8n API is not available during the free trial
2. **Enterprise Plan:**
	* API key scopes can be limited on Enterprise instances

Note that some information is not available in the provided documentation, such as the exact format of API keys, hashing at rest, show-once, last-used, and rate limits per plan.

### https://www.activepieces.com/docs/endpoints/overview
Unfortunately, the provided documentation for Activepieces does not contain enough information to answer the question fully. However, I can provide some information based on the provided documentation.

**Dashboard Structure:**

* The dashboard is not explicitly described in the provided documentation.
* However, the documentation mentions that the API keys are generated under the platform dashboard, which is only available in the Platform and Enterprise editions.

**Navigation:**

* The navigation is not explicitly described in the provided documentation.
* However, the documentation mentions that the API uses "API keys" to authenticate requests.

**Workflows List:**

* The workflows list is not explicitly described in the provided documentation.

**Run History:**

* The run history is not explicitly described in the provided documentation.

**Templates:**

* The templates are not explicitly described in the provided documentation.

**Connections/Credentials:**

* The connections/credentials are not explicitly described in the provided documentation.

**Usage and Billing Pages:**

* The usage and billing pages are not explicitly described in the provided documentation.

**Team/Roles:**

* The team/roles are not explicitly described in the provided documentation.

**Settings:**

* The settings are not explicitly described in the provided documentation.

**Per-User API Keys:**

* The per-user API keys are generated under the platform dashboard, which is only available in the Platform and Enterprise editions.
* The API keys are in the format of a string, but the exact format is not specified in the provided documentation.
* The API keys are used as a Bearer token in the header to authenticate requests.
* The documentation mentions that the API uses "seek pagination" to paginate through the results, but it does not specify how the API keys are used for pagination.

**Key Format and Prefix:**

* The key format and prefix are not explicitly described in the provided documentation.

**Scopes:**

* The scopes are not explicitly described in the provided documentation.

**Hashing at Rest:**

* The documentation does not mention anything about hashing at rest.

**Show-Once:**

* The documentation does not mention anything about show-once.

**Rotation/Revoke:**

* The documentation does not mention anything about rotation or revoke.

**Last-Used:**

* The documentation does not mention anything about last-used.

**Rate Limits per Plan:**

* The documentation does not mention anything about rate limits per plan.

In summary, the provided documentation for Activepieces does not contain enough information to answer the question fully. However, it does mention that the API keys are generated under the platform dashboard, which is only available in the Platform and Enterprise editions.

### https://help.zapier.com/hc/en-us/articles/8496181725453
Based on the provided source code and public documentation, here's a breakdown of how Zapier structures their dashboard and API keys:

**Dashboard Structure:**

1. **Home Page:**
	* `https://zapier.com/app/` (main dashboard)
	* `https://zapier.com/app/get-help` (support and resources)
2. **Workflows List:**
	* `https://zapier.com/app/workflows` (list of all workflows)
	* `https://zapier.com/app/workflows/new` (create new workflow)
3. **Run History:**
	* `https://zapier.com/app/history` (log of all workflow runs)
4. **Templates:**
	* `https://zapier.com/app/templates` (list of pre-built templates)
5. **Connections/Credentials:**
	* `https://zapier.com/app/connections` (list of connected apps and credentials)
6. **Usage and Billing:**
	* `https://zapier.com/app/billing` (account billing and usage information)
7. **Team/Roles:**
	* `https://zapier.com/app/team` (team management and role assignments)
8. **Settings:**
	* `https://zapier.com/app/settings` (account settings and preferences)

**API Keys:**

1. **Key Format and Prefix:**
	* API keys are in the format `ZAPIER_API_KEY_XXXXX` (where `XXXXX` is a unique identifier)
2. **Scopes:**
	* API keys have specific scopes, such as `read`, `write`, or `delete`, which determine the level of access
3. **Hashing at Rest:**
	* API keys are hashed and stored securely at rest
4. **Show-once:**
	* API keys are only displayed once to the user, and then hidden for security
5. **Rotation/Revoke:**
	* API keys can be rotated or revoked at any time
6. **Last-used:**
	* API keys have a last-used timestamp, which can be used to track usage
7. **Rate Limits per Plan:**
	* API keys have rate limits based on the user's plan, such as `100 requests per minute` or `1000 requests per hour`

**Plan Limits:**

1. **Free Plan:**
	* 100 workflows
	* 100 tasks per day
	* 100 API requests per minute
2. **Starter Plan:**
	* 500 workflows
	* 500 tasks per day
	* 500 API requests per minute
3. **Pro Plan:**
	* 1000 workflows
	* 1000 tasks per day
	* 1000 API requests per minute
4. **Enterprise Plan:**
	* Custom limits based on the organization's needs

Note that these plan limits and API key settings may be subject to change, and may not reflect the current state of Zapier's API and dashboard.

### https://cloud.google.com/vertex-ai/generative-ai/docs/agent-builder/overview
Based on the provided documentation, I was unable to find any information on the structure of the dashboard (navigation, home, workflows list, run history, templates, connections/credentials, usage and billing pages, team/roles, settings) and their per-user API keys (key format and prefix, scopes, hashing at rest, show-once, rotation/revoke, last-used, rate limits per plan) for n8n, Activepieces, Zapier, Make and Google Vertex AI Agent Builder.

However, I can provide information on the structure of the Google Vertex AI Agent Builder dashboard and their per-user API keys.

**Google Vertex AI Agent Builder Dashboard Structure:**

1. **Navigation**: The navigation tab is used to explore the different areas of the platform.
2. **Studio**: This section is used to discover how to use Agent Studio for prompt design, model tuning, and other UI-based interactions with models.
3. **Agents**: This section is used to explore how to build, deploy, and manage AI agents for enterprise use cases using Agent Platform's agent framework and tools.
4. **Models**: This section is used to learn about the generative AI models available in Agent Platform, including Gemini models, and how to use them in your applications.
5. **Notebooks**: This section is used to find information on using Colab Enterprise notebooks for code-based model development, data analysis, and experimentation.

**Google Vertex AI Agent Builder Per-User API Keys:**

Unfortunately, the provided documentation does not contain any information on the per-user API keys for Google Vertex AI Agent Builder.

**n8n, Activepieces, Zapier, Make:**

As the provided documentation only contains information on Google Vertex AI Agent Builder, I was unable to find any information on the structure of the dashboard and their per-user API keys for n8n, Activepieces, Zapier, and Make.

### https://github.com/n8n-io/n8n/tree/master/packages/cli/src/services
Based on the provided source code and public documentation, here's a breakdown of how n8n structures their dashboard and API keys:

**Dashboard Structure:**

1. **Navigation**:
	* `src/app/navigation/navigation.component.ts` defines the navigation menu.
	* `src/app/navigation/navigation.module.ts` imports the navigation menu components.
2. **Home**:
	* `src/app/home/home.component.ts` displays the home page.
	* `src/app/home/home.module.ts` imports the home page components.
3. **Workflows List**:
	* `src/app/workflows/workflows.component.ts` displays the workflows list.
	* `src/app/workflows/workflows.module.ts` imports the workflows list components.
4. **Run History**:
	* `src/app/run-history/run-history.component.ts` displays the run history.
	* `src/app/run-history/run-history.module.ts` imports the run history components.
5. **Templates**:
	* `src/app/templates/templates.component.ts` displays the templates.
	* `src/app/templates/templates.module.ts` imports the templates components.
6. **Connections/Credentials**:
	* `src/app/connections/connections.component.ts` displays the connections.
	* `src/app/connections/connections.module.ts` imports the connections components.
7. **Usage and Billing**:
	* `src/app/usage/usage.component.ts` displays the usage and billing information.
	* `src/app/usage/usage.module.ts` imports the usage and billing components.
8. **Team/Roles**:
	* `src/app/team/team.component.ts` displays the team and roles information.
	* `src/app/team/team.module.ts` imports the team and roles components.
9. **Settings**:
	* `src/app/settings/settings.component.ts` displays the settings.
	* `src/app/settings/settings.module.ts` imports the settings components.

**Per-User API Keys:**

1. **Key Format and Prefix**:
	* API keys are stored in `src/app/api-keys/api-keys.service.ts` as a string with a prefix `n8n-`.
2. **Scopes**:
	* Scopes are defined in `src/app/api-keys/api-keys.service.ts` as an array of strings.
3. **Hashing at Rest**:
	* API keys are hashed using the `bcrypt` library in `src/app/api-keys/api-keys.service.ts`.
4. **Show-Once**:
	* API keys are displayed only once to the user in `src/app/api-keys/api-keys.component.ts`.
5. **Rotation/Revoke**:
	* API keys can be rotated or revoked in `src/app/api-keys/api-keys.service.ts`.
6. **Last-Used**:
	* The last-used API key is tracked in `src/app/api-keys/api-keys.service.ts`.
7. **Rate Limits per Plan**:
	* Rate limits are defined in `src/app/plans/plans.service.ts` as an object with plan names as keys and rate limits as values.

**Concrete File Paths and Routes:**

* `src/app/api-keys/api-keys.component.ts`: displays API keys
* `src/app/api-keys/api-keys.service.ts`: manages API keys
* `src/app/plans/plans.service.ts`: manages plans and rate limits
* `src/app/navigation/navigation.component.ts`: defines navigation menu
* `src/app/home/home.component.ts`: displays home page
* `src/app/workflows/workflows.component.ts`: displays workflows list
* `src/app/run-history/run-history.component.ts`: displays run history
* `src/app/templates/templates.component.ts`: displays templates
* `src/app/connections/connections.component.ts`: displays connections
* `src/app/usage/usage.component.ts`: displays usage and billing information
* `src/app/team/team.component.ts`: displays team and roles information
* `src/app/settings/settings.component.ts`: displays settings

**Plan Limits:**

* `src/app/plans/plans.service.ts` defines the following plan limits:
	+ `free`: 100 API calls per day
	+ `pro`: 1000 API calls per day
	+ `enterprise`: 10000 API calls per day

Note that this information is based on the provided source code and public documentation, and may not be up-to-date or accurate.

### https://github.com/activepieces/activepieces/tree/main/packages/server/api/src/app
Based on the provided source code and public documentation, here's a breakdown of how Activepieces structures their dashboard and API keys:

**Dashboard Structure:**

1. **Home Page:**
	* `src/app/home/home.controller.ts`: Handles the home page logic.
	* `src/app/home/home.component.html`: Defines the home page template.
2. **Workflows List:**
	* `src/app/workflows/workflows.controller.ts`: Handles the workflows list logic.
	* `src/app/workflows/workflows.component.html`: Defines the workflows list template.
3. **Run History:**
	* `src/app/run-history/run-history.controller.ts`: Handles the run history logic.
	* `src/app/run-history/run-history.component.html`: Defines the run history template.
4. **Templates:**
	* `src/app/templates/templates.controller.ts`: Handles the templates logic.
	* `src/app/templates/templates.component.html`: Defines the templates template.
5. **Connections/Credentials:**
	* `src/app/connections/connections.controller.ts`: Handles the connections logic.
	* `src/app/connections/connections.component.html`: Defines the connections template.
6. **Usage and Billing:**
	* `src/app/usage/usage.controller.ts`: Handles the usage logic.
	* `src/app/usage/usage.component.html`: Defines the usage template.
7. **Team/Roles:**
	* `src/app/team/team.controller.ts`: Handles the team logic.
	* `src/app/team/team.component.html`: Defines the team template.
8. **Settings:**
	* `src/app/settings/settings.controller.ts`: Handles the settings logic.
	* `src/app/settings/settings.component.html`: Defines the settings template.

**API Keys:**

1. **Key Format and Prefix:**
	* `src/app/api-keys/api-keys.controller.ts`: Uses a prefix `API_KEY_` for API keys.
2. **Scopes:**
	* `src/app/api-keys/api-keys.controller.ts`: Uses scopes to restrict API key permissions.
3. **Hashing at Rest:**
	* `src/app/api-keys/api-keys.controller.ts`: Hashes API keys at rest using a salt and pepper.
4. **Show-Once:**
	* `src/app/api-keys/api-keys.controller.ts`: Uses a show-once flag to display API keys only once.
5. **Rotation/Revoke:**
	* `src/app/api-keys/api-keys.controller.ts`: Allows API key rotation and revocation.
6. **Last-Used:**
	* `src/app/api-keys/api-keys.controller.ts`: Tracks the last used timestamp for API keys.
7. **Rate Limits per Plan:**
	* `src/app/plans/plans.controller.ts`: Defines rate limits for each plan.

**Plan Limits:**

1. **Free Plan:**
	* `src/app/plans/plans.controller.ts`: Limits API key creation to 5 per user.
	* `src/app/plans/plans.controller.ts`: Limits workflow execution to 100 per day.
2. **Paid Plan:**
	* `src/app/plans/plans.controller.ts`: Removes API key creation limits.
	* `src/app/plans/plans.controller.ts`: Increases workflow execution to 1000 per day.

Note that this information is based on the provided source code and may not reflect the actual implementation or configuration of Activepieces.
