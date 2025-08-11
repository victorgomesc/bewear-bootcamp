# Copilot Instructions for AI Agents

## Project Overview
- This is a Next.js app (see `src/app/`) using TypeScript, Drizzle ORM, and Postgres.
- Database schema is defined in `src/db/schema.ts` using Drizzle's `pgTable` and column helpers.
- UI components are in `src/components/ui/`.
- Utility functions are in `src/lib/utils.ts`.

## Key Workflows
- **Development:** Start with `npm run dev` (see `README.md`).
- **Build:** Use `npm run build`.
- **Database:** Schema and migrations are managed with Drizzle ORM. See `drizzle.config.ts` for config.
- **Styling:** Uses global CSS (`src/app/globals.css`) and PostCSS (`postcss.config.mjs`).

## Patterns & Conventions
- All database tables are defined in `src/db/schema.ts` using Drizzle's builder pattern.
- UI components follow a flat structure under `src/components/ui/`.
- App routes are colocated in `src/app/` (Next.js app directory structure).
- Use TypeScript types throughout; prefer explicit types for DB models and API responses.
- Use `defaultRandom()` for UUID primary keys in Drizzle schemas.

## Integration Points
- Drizzle ORM for database access (see `src/db/index.ts` for DB instance).
- Next.js routing and API handling (see `src/app/`).
- No custom test or lint scripts are defined by default; add as needed.

## Examples
- To add a new table, extend `src/db/schema.ts`:
  ```ts
  export const exampleTable = pgTable("example", {
    id: uuid().primaryKey().defaultRandom(),
    // ...fields
  });
  ```
- To add a new UI component, place it in `src/components/ui/` and import as needed.

## References
- See `README.md` for getting started and deployment.
- See `drizzle.config.ts` for DB config.
- See Next.js docs for routing and app structure.

---
If any conventions or workflows are unclear, please ask for clarification or examples from the codebase.
