# Student Project Tracker - Cloud Variant (Live)

Hands-on web app development cloud deployment variant of the Student Project Tracker.

## Architecture & Differences from SQLite Version
- **Hosting**: Vercel (Serverless Node.js backend & static frontend).
- **Database**: Supabase PostgreSQL (via transaction pooler).
- **Backend**: Express app entry via `project-api.js` wrapped for serverless / local rehearsal in `server.js`.
- **Database Adapter**: `database.js` uses `pg` (`Pool`) connecting via `DATABASE_URL`.
- **Data Isolation**: Shared demo records with no authentication/login.
- **Migration Note**: Local SQLite records from the original project are **not** migrated automatically.

## Local Rehearsal Run Instructions
1. Install dependencies:
   ```powershell
   npm.cmd ci
   ```
2. Configure private environment file:
   - Copy `.env.example` to `.env`
   - Set `DATABASE_URL` to your Supabase PostgreSQL transaction pooler connection string.
   - **Important**: `DATABASE_URL` is server-only. Never expose or commit `.env`.
3. Database Setup:
   - Run the SQL statements in `schema.sql` in your Supabase SQL editor to create the `public.projects` table.
4. Start local development server:
   ```powershell
   npm.cmd start
   ```
   Opens at `http://localhost:3000`.

## Deployment Status & Hosted URL
- **Hosted URL**: *To be added after completing Vercel deployment.*

