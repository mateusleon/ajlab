# Gemini Instructions for ajlab

As a senior software engineer assistant, you MUST adhere to these foundational mandates and workflows when working on the `ajlab` project. These instructions take absolute precedence over general defaults.

## Project Context & Architecture

- **Workspace:** Nx Monorepo
- **Package Manager:** `yarn`
- **Framework:** Angular 21.2+ (Standalone components, Signals, Control Flow syntax)
- **Application:** `apps/shell` (Main shell application)
- **Build/Test Tooling:** Vite, Vitest, AnalogJS, Playwright
- **Linting/Formatting:** ESLint, Prettier

## Foundational Mandates

- **Nx Ecosystem:** ALWAYS use `yarn nx` to run tasks (serve, build, test, lint, e2e). Prefer Nx generators (`yarn nx g ...`) for creating new components, services, or libraries.
- **Angular Best Practices:**
  - Prefer **Standalone Components** over NgModules.
  - Utilize **Angular Signals** for state management and reactive programming.
  - Use the **new Control Flow syntax** (`@if`, `@for`, `@switch`).
  - Follow the [Angular Style Guide](https://angular.dev/style-guide).
- **Testing:**
  - Write unit tests using **Vitest** and **AnalogJS** testing utilities.
  - Use **Playwright** for end-to-end (E2E) testing.
  - Every change or new feature MUST include corresponding tests.
- **Code Style:**
  - Adhere to the existing ESLint and Prettier configurations. Run `yarn nx lint shell` and `yarn prettier --write .` before finalizing changes.
  - Follow the established naming conventions (kebab-case for files, PascalCase for classes).

## Operational Workflows

### Research & Strategy
- Before implementing, map dependencies and validate assumptions using `yarn nx graph`.
- For bug fixes, reproduce the failure with a test case before applying the fix.

### Execution
- **Atomic Changes:** Keep changes surgical and focused on the task at hand.
- **Automation:** Use `yarn nx format:write` to ensure code consistency.
- **Validation:** Always run `yarn nx run-many -t lint test build e2e` (or specific project tasks) to verify integrity.

### Commit Guidelines
- Use clear, concise commit messages that explain the "why" and follow project conventions.
- Never stage or commit changes unless explicitly requested.

## Specific Tooling Guidance

- **AnalogJS:** Since this project uses AnalogJS plugins, leverage its features for SSR/SSG and Vite-based development where appropriate.
- **Styling:** Use SCSS for styling, following the BEM or a similar component-based methodology as established in `apps/shell/src/app/app.scss`.
