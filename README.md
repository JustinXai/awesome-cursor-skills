# Awesome Cursor Skills [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome [skills](https://docs.cursor.com/agent/skills) for [Cursor](https://cursor.com), the AI code editor.

Cursor Skills are reusable `SKILL.md` instruction files that teach the AI agent how to perform specific tasks — from setting up analytics to scaffolding entire projects. They live in `.cursor/skills/` (personal) or project directories and are automatically discovered by the agent.

## Contents

- [Featured](#featured)
- [Skills](#skills)
- [Plugins](#plugins)
- [Community Skills](#community-skills)
- [Cursor Rules (Related)](#cursor-rules-related)
- [Resources](#resources)
- [Contributing](#contributing)

---

## Featured

Standout skills and collections that are especially useful across many projects.

- [PostHog Skills](https://github.com/PostHog/skills) - Official PostHog skills for adding analytics, feature flags, and event tracking to any project.
- [Vercel Agent Skills](https://github.com/vercel-labs/agent-skills) - Official Vercel skills including React best practices, web design guidelines, and deploy workflows.
- [Anthropic Skills](https://github.com/anthropics/skills) - Official Anthropic skills including skill-creator, frontend-design, webapp-testing, and MCP builder.
- [Sentry Skills](https://github.com/getsentry/skills) - Official Sentry skills for security review, code review, and development workflows.

## Skills

Ready-to-use `SKILL.md` files you can copy into your `.cursor/skills/` directory. Each one teaches the agent a specific engineering workflow.

### Analytics & Tracking

- [Add Analytics (PostHog)](resources/add-analytics/SKILL.md) - Add event tracking, page views, feature flags, and session replay to any web app.
- [Add Feature Flags](resources/add-feature-flags/SKILL.md) - Add feature flags for gradual rollouts and A/B testing using PostHog or a simple local implementation.

### Error Tracking & Monitoring

- [Add Error Tracking (Sentry)](resources/add-error-tracking/SKILL.md) - Add crash reporting, performance monitoring, and source maps.

### Authentication & Payments

- [Add Authentication (Auth.js)](resources/add-auth/SKILL.md) - Add OAuth login, session management, and protected routes with NextAuth.js.
- [Add Stripe Payments](resources/add-stripe/SKILL.md) - Integrate Stripe checkout, subscriptions, webhooks, and customer portal.

### Testing

- [Add E2E Tests (Playwright)](resources/add-e2e-tests/SKILL.md) - Set up Playwright with config, example tests, page objects, and CI integration.

### Infrastructure & DevOps

- [Add Docker](resources/add-docker/SKILL.md) - Dockerize any app with a multi-stage Dockerfile, docker-compose, and .dockerignore.
- [Setup CI (GitHub Actions)](resources/setup-ci/SKILL.md) - Set up a CI/CD pipeline with linting, testing, type-checking, and deployment.
- [Setup Terraform](resources/setup-terraform/SKILL.md) - Infrastructure-as-code with provider config, modules, remote state, and CI integration.

### Code Quality & Security

- [Code Review](resources/code-review/SKILL.md) - Thorough code review focused on correctness, maintainability, performance, and best practices.
- [Security Audit](resources/security-audit/SKILL.md) - Systematic security audit checking for OWASP Top 10 vulnerabilities, secrets exposure, and insecure patterns.
- [Performance Audit](resources/performance-audit/SKILL.md) - Audit bundle size, rendering, database queries, and Core Web Vitals.

### Documentation

- [Add API Docs (OpenAPI)](resources/add-api-docs/SKILL.md) - Generate OpenAPI/Swagger documentation with interactive docs UI.

## Plugins

Official Cursor marketplace plugins with bundled skills. Install via **Cursor Settings > Plugins**.

- [Figma](https://cursor.com/cn/marketplace/figma) - Design-to-code workflows and design system management. Skills: *Generate Design from Code*, *Code Connect Components*, *Generate Design System Library* + 4 more.
- [Linear](https://cursor.com/cn/marketplace/linear) - Manage issues, projects, documents, and sprints via MCP.
- [Slack](https://cursor.com/cn/marketplace/slack) - Search channels, send messages, and perform Slack actions via MCP.
- [Datadog](https://cursor.com/cn/marketplace/datadog) - Query logs, metrics, traces, and dashboards. Skills: *Datadog MCP Setup*.
- [Stripe](https://cursor.com/cn/marketplace/stripe) - Payment integration best practices and API guidance. Skills: *Stripe Best Practices*, *Upgrade Stripe API/SDK*.
- [Firebase](https://cursor.com/cn/marketplace/firebase) - Backend and AI infrastructure with Firebase. Skills: *Firebase AI Logic*, *Firebase Auth Basics*, *App Hosting Basics* + 8 more.
- [Shopify](https://cursor.com/cn/marketplace/shopify) - Shopify developer tools for GraphQL, Liquid, and extensions. Skills: *Admin GraphQL API*, *Admin Execution*, *Custom Data (Metafields)* + 13 more.
- [dbt Labs](https://cursor.com/cn/marketplace/dbt-labs) - Data modeling, analytics engineering, and semantic layer metrics. Skills: *Adding Unit Tests*, *Answering Natural Language Questions*, *Building Semantic Layer* + 6 more.
- [Sentry](https://cursor.com/cn/marketplace/sentry) - Error tracking and performance monitoring. Skills: *Code Review*, *Browser SDK Setup*, *Cloudflare SDK Setup* + 25 more.
- [Vercel](https://cursor.com/cn/marketplace/vercel) - Build and deploy web apps and agents. Skills: *AI Architect*, *Deployment Expert*, *Performance Optimizer* + 25 more.
- [Svelte](https://cursor.com/cn/marketplace/svelte) - Svelte development, MCP, and component skills. Skills: *Svelte File Editor*, *Svelte Code Writer*, *Core Best Practices* + 1 more.
- [Elastic](https://cursor.com/cn/marketplace/elastic) - Elasticsearch, Kibana, Observability, and ES|QL docs. Skills: *Cloud Create Project*, *Cloud Manage Project*, *Cloud Access Management* + 30 more.
- [Postman](https://cursor.com/cn/marketplace/postman) - Full API lifecycle management. Skills: *API Readiness Analyzer*, *Client Code Generation*, *Mock Server Creation* + 10 more.
- [Sanity](https://cursor.com/cn/marketplace/sanity) - CMS integration with agent skills, rules, and commands. Skills: *Content Experimentation & A/B Testing*, *Content Modeling Best Practices*, *SEO & AEO Best Practices* + 5 more.
- [Langfuse](https://cursor.com/cn/marketplace/langfuse) - LLM tracing, prompt management, and evaluation. Skills: *Langfuse CLI & Docs*.
- [CockroachDB](https://cursor.com/cn/marketplace/cockroachdb) - Schema exploration, SQL optimization, and distributed DB management. Skills: *SQL Patterns*, *App Patterns*, *Operator Patterns* + 1 more.
- [Encore](https://cursor.com/cn/marketplace/encore) - Backend services in TypeScript/Go with automatic infrastructure. Skills: *Add Infrastructure*, *Create Service*, *Code Review* + 19 more.
- [AWS Amplify](https://cursor.com/cn/marketplace/aws-amplify) - Full-stack apps with authentication, data models, and storage. Skills: *Amplify Workflow*.
- [AWS Serverless](https://cursor.com/cn/marketplace/aws-serverless) - Design, build, deploy, and debug serverless applications. Skills: *AWS Lambda*, *API Gateway*, *Lambda Durable Functions* + 1 more.
- [Pendo](https://cursor.com/cn/marketplace/pendo) - Product analytics for account health, feature adoption, and session replays. Skills: *Account Health*, *Feature Adoption*, *Feedback Analysis* + 1 more.
- [GitLab](https://cursor.com/cn/marketplace/gitlab) - Issues, merge requests, and pipeline management. Skills: *CI/CD Author*, *Backlog Health*, *Pipeline Status* + 6 more.
- [Sourcegraph](https://cursor.com/cn/marketplace/sourcegraph) - Code search and navigation. Skills: *Searching Sourcegraph*, *Deep Search*.
- [Miro](https://cursor.com/cn/marketplace/miro) - Read board context, create diagrams, and generate code from whiteboards. Skills: *Miro MCP*, *Create Diagram*, *Summarize Board* + 3 more.
- [Cloudinary](https://cursor.com/cn/marketplace/cloudinary) - Media asset management, transformations, and optimization. Skills: *Cloudinary Docs*, *Cloudinary Transformations*.
- [Appwrite](https://cursor.com/cn/marketplace/appwrite) - Backend-as-a-service with database, auth, and storage. Skills: *Appwrite CLI*, *Appwrite Web SDK*, *Appwrite Dart SDK* + 7 more.
- [ClickUp](https://cursor.com/cn/marketplace/clickup) - Task management, time tracking, and collaboration via MCP.
- [Box](https://cursor.com/cn/marketplace/box) - Content management, AI Q&A, summarization, and extraction. Skills: *Box MCP Workflows*.
- [Chargebee](https://cursor.com/cn/marketplace/chargebee) - Billing operations, API integration, and webhook handling. Skills: *Chargebee Integration*.
- [Circle](https://cursor.com/cn/marketplace/circle) - Stablecoin payments, cross-chain transfers, and smart contracts. Skills: *Bridge Stablecoin (CCTP)*, *Circle Wallets*, *Gateway* + 6 more.
- [Runlayer](https://cursor.com/cn/marketplace/runlayer) - Security policies, secret protection, and audit trails for MCPs. Skills: *MCP Builder*, *MCP Security Audit*, *Plugin Builder*.
- [Superpowers](https://cursor.com/cn/marketplace/superpowers) - Core skill library for TDD, debugging, and collaboration patterns. Skills: *Code Reviewer*, *Brainstorming*, *Dispatching Parallel Agents* + 12 more.
- [Omni](https://cursor.com/cn/marketplace/omni) - Analytics exploration, querying, model building, and dashboard creation. Skills: *Content Builder*, *AI Optimizer*, *Content Explorer* + 8 more.
- [Braintrust](https://cursor.com/cn/marketplace/braintrust) - AI evaluation, experiments, and evaluation logs via MCP.
- [Parallel](https://cursor.com/cn/marketplace/parallel) - Web search, content extraction, and deep research. Skills: *Web Search*, *Deep Research*, *Data Enrichment* + 1 more.
- [Tavily](https://cursor.com/cn/marketplace/tavily) - Web search, crawling, deep research, and URL discovery. Skills: *Web Search CLI*, *Extract Content*, *Crawl Sites* + 3 more.
- [Astronomer](https://cursor.com/cn/marketplace/astronomer) - Data engineering, warehouse exploration, and Airflow integration. Skills: *Airflow DAG Management*, *Airflow Plugins*, *Analyzing Data* + 18 more.
- [Meta Reality Labs](https://cursor.com/cn/marketplace/meta-reality-labs) - Quest and Horizon OS development. Skills: *Immersive Designer*, *New Project Creation*, *WebXR (IWSDK)* + 10 more.
- [Plain](https://cursor.com/cn/marketplace/plain) - Support threads, customer management, and help center articles.
- [Turbopuffer](https://cursor.com/cn/marketplace/turbopuffer) - Vector and full-text search database integration.

## Community Skills

Open-source skill repositories from the community and official dev teams.

### Analytics & Monitoring

- [PostHog/skills](https://github.com/PostHog/skills) - Official PostHog skills for analytics, feature flags, session replay, and LLM analytics.
- [PostHog/ai-plugin](https://github.com/PostHog/ai-plugin) - PostHog AI plugin for Cursor and other coding agents.

### Infrastructure & Deployment

- [antonbabenko/terraform-skill](https://github.com/antonbabenko/terraform-skill) - Claude Agent Skill for Terraform and OpenTofu — testing, modules, CI/CD, and production patterns.

### Frontend & UI

- [shadcn/ui Skill](https://github.com/hzm0321/real-time-fund/blob/main/.cursor/skills/shadcn/SKILL.md) - Managing shadcn components — adding, searching, debugging, styling, and composing UI.
- [Vercel React Best Practices](https://github.com/vercel-labs/agent-skills) - 40+ rules for React/Next.js performance, including eliminating request waterfalls and bundle optimization.
- [Vercel Web Design Guidelines](https://github.com/vercel-labs/agent-skills) - UI code auditing for accessibility, UX, and performance compliance.

### Code Quality

- [Anthropic Simplify](https://github.com/anthropics/skills) - Reviews code for reuse, efficiency, and quality, fixing dead code and naming issues.
- [Sentry Code Review](https://github.com/getsentry/skills) - Code review following Sentry's engineering practices.
- [Sentry Security Review](https://github.com/getsentry/skills) - Systematic security code review for injection, XSS, and authentication vulnerabilities.

## Cursor Rules (Related)

Cursor Rules (`.cursorrules` / `.cursor/rules/`) are complementary to skills — rules are always-on conventions, skills are on-demand workflows.

- [PatrickJS/awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) - The most comprehensive collection of `.cursorrules` files, categorized by framework and language.
- [sanjeed5/awesome-cursor-rules-mdc](https://github.com/sanjeed5/awesome-cursor-rules-mdc) - Curated `.mdc` format rules with a generator tool.
- [tugkanboz/awesome-cursorrules](https://github.com/tugkanboz/awesome-cursorrules) - Showcases modern Cursor Rules system with MDC format.

## Resources

### Learning

- [Cursor Skills Documentation](https://docs.cursor.com/agent/skills) - Official docs on creating and using skills.
- [Cursor Marketplace](https://cursor.com/marketplace) - Browse and install official plugins with bundled skills.
- [Agent Skills Specification](https://agentskills.io) - The open standard for defining agent capabilities.
- [Deep Dive SKILL.md](https://abvijaykumar.medium.com/deep-dive-skill-md-part-1-2-09fc9a536996) - In-depth walkthrough of the SKILL.md format.

### Directories

- [cursor-skills GitHub Topic](https://github.com/topics/cursor-skills) - Browse community repos tagged with cursor-skills.
- [skills.sh](https://skills.sh/) - Leaderboard and directory for popular skill repositories.
- [AgentDepot.dev](https://agentdepot.dev/) - Open-source explorer for agents, skills, and rules.
- [CursorDirectory](https://cursor.directory/) - Community directory for Cursor rules and configurations.

### Tools

- [npx skills](https://github.com/vercel-labs/skills) - CLI to search, install, and manage skills.
- [PostHog/context-mill](https://github.com/PostHog/context-mill) - Assemble context for AI agents into Agent Skills-compliant packages.
- [Anthropic Skill Creator](https://github.com/anthropics/skills) - Official skill for drafting, testing, and optimizing custom SKILL.md files.

---

## Contributing

Contributions welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

If you know of a great Cursor skill that isn't listed here, please open a PR. Include:
- A link to the skill or repository
- A brief description of what it does
- Which category it belongs to
