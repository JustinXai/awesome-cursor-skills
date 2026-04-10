---
name: suggesting-cursor-rules
description: Analyze a codebase and suggest Cursor rules (.cursor/rules/) that encode the project's conventions, patterns, and best practices for the AI agent.
user-invocable: true
---

# Suggesting Cursor Rules

Analyze a project and generate tailored `.cursor/rules/` files that teach the agent the project's conventions.

## What Are Cursor Rules?

Rules live in `.cursor/rules/*.mdc` and are always-on instructions the agent follows. Unlike skills (on-demand), rules are applied every time the agent works in the project.

## Workflow

### 1. Analyze the Project

Investigate these areas:

**Stack & Framework**
- What framework? (Next.js, Express, Django, Rails, etc.)
- What language? (TypeScript, Python, Go, etc.)
- What styling? (Tailwind, CSS Modules, styled-components)
- What state management? (Redux, Zustand, Context, etc.)
- What ORM/database? (Prisma, Drizzle, SQLAlchemy, etc.)

**Code Patterns**
- File naming conventions (kebab-case, PascalCase, etc.)
- Component patterns (functional, class-based, server components)
- Import style (relative, alias, barrel files)
- Error handling patterns (try/catch, Result types, error boundaries)
- Test conventions (co-located, `__tests__` dir, `.test.ts` vs `.spec.ts`)

**Project Structure**
- Directory organization (feature-based, layer-based)
- Where do new components go?
- Where do new API routes go?
- Monorepo structure (apps, packages, shared)

### 2. Generate Rules

Create `.cursor/rules/` files for each concern:

**`project-conventions.mdc`** — General coding standards
```
---
description: Project coding conventions
globs: **/*.{ts,tsx}
---

- Use functional components with TypeScript
- Import with @ alias, not relative paths
- Prefer named exports over default exports
- Error boundaries wrap every page component
```

**`component-patterns.mdc`** — How to write components
```
---
description: React component patterns
globs: **/components/**/*.tsx
---

- Server components by default, add "use client" only when needed
- Props interface named <Component>Props
- Co-locate styles, tests, and stories with components
```

**`api-patterns.mdc`** — API route conventions
```
---
description: API route patterns
globs: **/api/**/*.ts
---

- Validate request body with zod
- Return consistent error shapes: { error: string, code: number }
- Wrap handlers in try/catch with proper status codes
```

### 3. Suggest, Don't Force

Present the suggested rules to the user with explanations:

```
Suggested Cursor Rules:

1. project-conventions.mdc
   Based on: Your use of TypeScript, @ import aliases, named exports
   
2. component-patterns.mdc
   Based on: Server components in app/, "use client" in interactive components
   
3. api-patterns.mdc
   Based on: Zod validation in existing routes, consistent error shapes

Want me to create these files?
```

## Tips

- Read existing `.cursorrules` or `.cursor/rules/` files first — don't duplicate
- Look at recent git history to understand evolving conventions
- The `globs` field in frontmatter scopes the rule to specific files
- Keep each rule file focused — one concern per file
- Rules should encode what the project already does, not impose new standards
