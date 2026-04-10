---
name: suggesting-skills
description: Analyze a project and suggest Cursor skills (.cursor/skills/) that would be most useful based on the stack, workflow, and common tasks.
user-invocable: true
---

# Suggesting Skills

Analyze a project and recommend skills that would help the agent work more effectively in it.

## Workflow

### 1. Analyze the Project

Investigate the stack and workflows:

**Framework & Stack**
- Frontend: React, Vue, Svelte, Angular?
- Backend: Node, Python, Go, Ruby?
- Database: Postgres, MySQL, MongoDB?
- Hosting: Vercel, AWS, GCP, Docker?

**Existing Configuration**
- Check `.cursor/skills/` — what's already installed?
- Check `.cursor/rules/` — what conventions exist?
- Check `package.json` scripts — what tasks are common?
- Check CI/CD config — what runs on every PR?

**Common Workflows**
- How are components created? (manual, generator, CLI)
- How is the database managed? (migrations, seeds)
- How are tests written and run?
- How is deployment triggered?
- Are there repetitive tasks the developer does frequently?

### 2. Match Skills to Needs

Map the project's characteristics to useful skills:

| If the project has... | Suggest... |
|----------------------|------------|
| React + Tailwind | `using-ui-stack`, `converting-css-to-tailwind` |
| Next.js | `vercel-react-best-practices`, `vercel-composition-patterns` |
| TypeScript | `auto-type-checking` |
| API routes | `api-smoke-testing`, `adding-api-docs` |
| Forms | `form-testing` |
| Auth | `adding-auth` |
| Payments | `adding-stripe` |
| No tests | `writing-tests`, `adding-e2e-tests` |
| No CI | `setting-up-ci` |
| No analytics | `adding-analytics` |
| No error tracking | `adding-error-tracking` |
| Docker | `adding-docker` |
| Multiple services | `finding-dev-server-url`, `detecting-port-conflicts` |
| Large codebase | `codebase-onboarding`, `parallel-exploring` |
| Active PRs | `babysitting-pr`, `screenshotting-changelog` |
| CSS Modules | `converting-css-modules-to-tailwind` |
| Python + uv | `python-tdd-with-uv` |

### 3. Prioritize

Rank suggestions by impact:

1. **Critical gaps** — no tests, no CI, no error tracking
2. **Workflow improvements** — skills that automate daily tasks
3. **Quality improvements** — code review, accessibility, performance
4. **Nice-to-haves** — visual testing, onboarding docs

### 4. Present

```
Recommended Skills for this project:

High Priority:
  1. writing-tests — No test files found. Start with unit tests for utils/
  2. setting-up-ci — No GitHub Actions config. Add lint + test + build pipeline
  3. adding-error-tracking — No error tracking. Add Sentry for crash reporting

Medium Priority:
  4. api-smoke-testing — 12 API routes found, no integration tests
  5. auto-type-checking — TypeScript project, add post-edit type checking
  6. responsive-testing — Tailwind project, verify mobile breakpoints

Optional:
  7. codebase-onboarding — Large codebase (200+ files), generate onboarding doc
  8. adding-analytics — No analytics detected

Install a skill:
  Copy the SKILL.md file to .cursor/skills/<name>/SKILL.md
```

## Tips

- Don't suggest skills that duplicate existing tooling (e.g. don't suggest `adding-e2e-tests` if Playwright is already configured)
- Check `package.json` devDependencies to understand what's already set up
- Consider the team size — solo devs benefit from automation skills, teams benefit from review/convention skills
- Mention the `npx skills add` CLI as an alternative installation method
