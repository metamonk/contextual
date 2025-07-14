### 🔄 Project Awareness & Context
- **Always read `PLANNING.md`** at the start of a new conversation to understand the project's architecture, goals, style, and constraints.
- **Check `/PRPs`** before starting a new task. If the task isn't listed, add it with a brief description and today's date.
- **Use consistent naming conventions, file structure, and architecture patterns** as described in `PLANNING.md`.
- **Understand the tech stack** - Next.js 15 with App Router, TypeScript 5, Turbopack, and Vercel AI SDK.

### 🧱 Code Structure & Modularity
- **Never create a component file longer than 300 lines**. If approaching this limit, split into smaller components or extract hooks.
- **Organize code into clearly separated modules**, grouped by feature or domain:
  - `components/` - Reusable React components
  - `app/` - Next.js App Router pages and layouts
  - `lib/` - Shared utilities and business logic
  - `hooks/` - Custom React hooks
  - `ai/` - AI providers and tool configurations
- **Use absolute imports with @/ alias** consistently throughout the codebase.
- **Environment variables** must be typed in `env/` directory files.

### 🧪 Testing & Reliability
- **Run `pnpm lint` after making changes** to catch TypeScript and ESLint errors early.
- **Run `pnpm build` before committing** to ensure no build errors.
- **For new features**, consider:
  - Type safety with TypeScript strict mode
  - Error boundaries for component failures
  - Loading states for async operations
  - Proper error handling with try-catch blocks

### ✅ Task Completion
- **Mark completed tasks in `TASK.md`** immediately after finishing them.
- Add new sub-tasks or TODOs discovered during development to `TASK.md` under a "Discovered During Work" section.
- **Use the TodoWrite tool** during implementation to track progress within the conversation.

### 📎 Style & Conventions

#### Framework & Architecture
- **Follow Next.js App Router conventions** for file naming and structure
- **Use Server Components by default**, Client Components only when needed
- **Tailwind CSS v4** for styling with PostCSS

#### TypeScript Rules
- **Use TypeScript with strict mode enabled**
- **No explicit `any` types** - Always use proper types or `unknown` when type is truly unknown
- **Write proper TypeScript types** for all function parameters and returns:
  ```typescript
  export async function fetchData(id: string): Promise<DataType> {
    // Implementation
  }
  ```
- **Use optional chaining (`?.`)** and nullish coalescing (`??`) operators
- **Exhaustive checks in switch statements** - Handle all cases or add a default

#### Code Quality
- **No unused variables** - Remove or prefix with underscore if intentionally unused (e.g., `_unusedParam`)
- **No unused imports** - Clean up imports that aren't referenced in the file
- **Prefer `const` over `let`** - Only use `let` when reassignment is necessary
- **No console.log in production code** - Use proper logging utilities or remove debug statements

### 📚 Documentation & Explainability
- **Update `README.md`** when new features are added, dependencies change, or setup steps are modified.
- **Comment non-obvious code** and ensure everything is understandable to a mid-level developer.
- When writing complex logic, **add an inline `// Reason:` comment** explaining the why, not just the what.
- **Use JSDoc comments** for exported functions and components.

### 🧠 AI Behavior Rules
- **Never assume missing context. Ask questions if uncertain.**
- **Never hallucinate packages** - verify in package.json before importing.
- **Always confirm file paths and module names** exist before referencing them in code or tests.
- **Never delete or overwrite existing code** unless explicitly instructed to or if part of a task from `TASK.md`.
- **Follow security best practices** - never commit secrets, always validate user input.