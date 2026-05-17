# Badan Warisan Membership PWA

A mobile-first React and Supabase membership portal prototype for registration, authentication, profiles, events, tickets, and heritage-community engagement.

## Why I Built This

Membership organizations need a smoother way to onboard members, keep profile data up to date, manage events, and provide digital membership experiences. This project explores how a heritage-focused organization could digitize common membership workflows through a responsive web app backed by Supabase.

The repository is framed as a portfolio-ready PWA prototype, not as a claim that the system is currently deployed in production for Badan Warisan Malaysia.

## Features

- Email/password authentication using Supabase Auth.
- Sign-up, login, logout, and protected member experience.
- Member profile and address completion flows.
- Membership registration, renewal, success, and digital card screens.
- Event listing, event details, registration, ticket, and payment-selection flows.
- Donation and donation-history screens.
- Community wall, heritage passport, journal, leaderboard, and FAQ-related UI.
- Admin QR/scanner screen for ticket or membership validation concepts.
- Reusable UI primitives built with Radix-style components.
- Mobile-first layout with Tailwind CSS.
- Safe `.env.example` for Supabase and Google Maps configuration.

## Tech Stack

- **Frontend:** React, TypeScript, Vite
- **Styling:** Tailwind CSS, PostCSS
- **UI components:** Radix UI primitives, custom reusable components
- **Backend / Auth:** Supabase Auth and Supabase client
- **Database:** Supabase/PostgreSQL schema migration file included
- **Forms:** React Hook Form
- **Charts / UI data:** Recharts
- **Utilities:** Lucide React, QR-code-related libraries, HTML5 QR code scanning library

## Architecture / System Design

```text
React PWA
  -> AuthContext
  -> Supabase client
  -> Supabase Auth / PostgreSQL

Screens and workflows
  -> membership registration
  -> profile and address completion
  -> events, tickets, donation, community, admin scanner
```

- **Frontend:** `src/App.tsx` coordinates the main screen flow, while feature screens live in `src/components/`.
- **Backend/API:** `src/lib/supabase.ts` initializes the Supabase client from Vite environment variables.
- **Authentication:** `src/contexts/AuthContext.tsx` manages session state, sign-in, sign-up, profile updates, address completion, phone OTP hooks, and sign-out.
- **Database/storage:** `supabase_migration_memberships_v5_complete.sql` documents the intended Supabase/PostgreSQL schema. The app also uses Supabase user metadata for profile-related values.
- **Deployment:** The app is a Vite frontend and can be deployed to static hosting, but Supabase environment variables must be configured on the host.
- **External services:** Real payment processing and production SMS/OTP setup require provider configuration outside this repo.

## My Contributions

- Built the React/TypeScript membership portal structure and major user flows.
- Implemented Supabase client setup and auth context handling.
- Added profile, address, membership, event, ticket, donation, and admin scanner screens.
- Organized reusable UI components and service modules.
- Added Supabase setup documentation and a migration file for the intended database structure.
- Added safe environment-variable documentation without exposing real credentials.

## What I Learned

- How to structure a larger frontend around feature screens, shared UI primitives, and auth context state.
- How Supabase Auth, user metadata, and database tables can support membership workflows.
- Why documentation should clearly separate implemented prototype behavior from production services such as payments and SMS.
- How to make a domain-specific app read as a real product instead of a generic CRUD demo.

## Screenshots / Demo

No screenshots are currently tracked in this repository.

Evidence to add later:

- `docs/screenshots/login.png`
- `docs/screenshots/member-dashboard.png`
- `docs/screenshots/membership-card.png`
- `docs/screenshots/event-registration.png`
- `docs/screenshots/admin-scanner.png`
- Short mobile walkthrough video.

## Setup

1. Clone the repository.

   ```bash
   git clone https://github.com/Jason421412/badan-warisan-membership-pwa.git
   cd badan-warisan-membership-pwa
   ```

2. Install dependencies.

   ```bash
   npm install
   ```

3. Create a local environment file from the safe example.

   ```bash
   cp .env.example .env
   ```

4. Add your own Supabase project values.

   ```env
   VITE_SUPABASE_URL=https://your-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your-anon-key
   VITE_GOOGLE_MAPS_API_KEY=your_google_maps_api_key_here
   ```

5. Configure Supabase.

   - Create a Supabase project.
   - Enable email/password authentication.
   - Review `docs/SUPABASE_SETUP.md`.
   - Apply or adapt `supabase_migration_memberships_v5_complete.sql` only after checking it against your Supabase project.

6. Run the development server.

   ```bash
   npm run dev
   ```

7. Open the local URL shown by Vite.

## Future Improvements

- Add production-ready Row Level Security policies and document them clearly.
- Add screenshots and a short demo video.
- Add form validation tests and auth-flow tests.
- Replace prototype payment screens with real provider integration only if credentials and backend handling are implemented safely.
- Add admin role separation and route-level access control.
- Add CI for type-checking, linting, and build verification.
- Remove unused dependencies and split large UI flows into smaller route-based modules.
