# Badan Warisan Malaysia - Membership App

![Project Status](https://img.shields.io/badge/Status-Active-success)
![React](https://img.shields.io/badge/React-18-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)
![Vite](https://img.shields.io/badge/Vite-6.x-purple)
![Supabase](https://img.shields.io/badge/Supabase-Auth_&_DB-47C16E)

## Overview
A responsive progressive web application (PWA) designed for **Badan Warisan Malaysia** (Malaysia Heritage Trust) to manage membership operations. The application digitizes the membership experience, allowing users to securely authenticate, manage their profiles, and engage with heritage initiatives seamlessly across web and mobile browsers.

## Main Features
- **Secure Authentication**: End-to-end email and password authentication powered by Supabase.
- **Member Dashboard**: Personalized dashboard for managing membership profiles.
- **Responsive Layout**: Designed mobile-first using Tailwind CSS, scaling cleanly for desktop and tablet users.
- **Accessible UI**: Fully accessible interactive components built with Radix UI Primitives.
- **Optimized Performance**: Lightning-fast build times and hot module replacement driven by Vite.

## Tech Stack
- **Frontend Framework**: React 18, TypeScript, Vite
- **Styling & UI**: Tailwind CSS v4, PostCSS, Radix UI (Headless components)
- **Icons**: Lucide React
- **Backend & Database**: Supabase (PostgreSQL Auth & User Metadata)
- **Form Handling**: React Hook Form
- **Data Visualization**: Recharts

---

## 📸 Screenshots
*(Placeholder for project screenshots - add them in `./docs` and link them here)*
> **1. Login Screen** | **2. User Profile Dashboard**

---

## 🚀 Quick Start & Setup

### Prerequisites
- [Node.js](https://nodejs.org/en/) (v18+ recommended)
- [npm](https://www.npmjs.com/) or `pnpm`
- A [Supabase](https://supabase.com/) account for database functionality

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/badan-warisan-membership.git
cd badan-warisan-membership
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Variables
Copy the example environment file and insert your Supabase credentials:
```bash
cp .env.example .env
```
Update your `.env` with:
```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

### 4. Supabase Setup
- Create a new project in your Supabase dashboard.
- Enable **Email Authentication**.
- Profile data (name, phone) is handled directly by `user_metadata` without the need for complex SQL migrations.
- *(For custom tables, see `DATABASE_SETUP.md`)*.

### 5. Run Locally
```bash
npm run dev
```
Navigate to `http://localhost:3000` to view the application.

---

## 📂 Folder Structure

```
.
├── src/
│   ├── assets/       # Static images and icons
│   ├── components/   # Reusable UI components and specific screens (e.g. LoginScreen)
│   ├── contexts/     # React context providers (AuthContext)
│   ├── lib/          # Utilities and Supabase initialization clients
│   ├── services/     # API request structures and services
│   ├── styles/       # Global CSS and Tailwind directives
│   └── types/        # TypeScript interfaces and type definitions
├── .env.example      # Environment variable template
├── vite.config.ts    # Vite bundler configuration
```

## Target Users / Use Cases
- **BWM Members**: Existing members needing digital access to update their contact details, renew memberships, or review latest initiatives.
- **BWM Administrators**: Require a scalable, secure backend (Supabase) to track registrations, manage updates, and ensure member privacy.
- **Public Users**: People looking to join the heritage trust, allowing a seamless onboarding and signup sequence.

## Current Limitations
- Authentication currently relies on Email/Password. OAuth providers (Google, Apple) have not yet been enabled.
- Web-based implementation mimics the mobile experience but is not currently wrapped natively (e.g., React Native/Capacitor).
- Offline capabilities (Service Workers) are limited natively.

## Future Improvements
- [ ] Incorporate PWA properties to allow native "Install to Home Screen" prompts on mobile OS.
- [ ] Build administrative dashboard routes using Supabase Row Level Security (RLS) rules.
- [ ] Replace local asset hosting with a dedicated CDN.

## License
Distributed under the MIT License. See `LICENSE` for more information.

## Author
Jason Xu Jiachen
