================================================================================
PORTIVUE — STUDENT PORTFOLIO PLATFORM (HACKATHON PROJECT)
Author / Demo Profile: Ansh Shrivastava (@ansh-shrivastava)
================================================================================

1. PROJECT OVERVIEW
-------------------
Portivue is a modern, lightweight, production-ready web application that allows
students to build professional digital portfolios showcasing their projects,
certificates, hackathons, internships, and technical skills. Every student
receives a clean, shareable public profile URL (/u/username) to share with
recruiters, companies, and peers.

2. KEY FEATURES
---------------
- Student Authentication & 5-Step Guided Onboarding (Supabase Auth)
- Protected Student Dashboard with real-time portfolio metrics
- Live Side-by-Side Profile Editor with skill tags & avatar uploads
- Portfolio Entry Management (Projects, Certificates, Hackathons, Achievements,
  Internships, Other) with title, description, outcome, optional evidence URL,
  and public/private visibility
- Transparent Evidence Attribution:
  * "Evidence linked" when a valid HTTP/HTTPS supporting URL is attached
  * "Self-reported" when no external URL is provided
  * Strictly avoids any unverified or fake certification claims
- Resource-Optimized AI Adapter (Gemma 4 Preferred):
  * Optional lightweight adapter supporting gemma-4-2b-it / gemma-4-9b-it
  * In-memory request caching + zero-cost deterministic text formatter fallback
  * Works 100% without AI enabled and never hardcodes API keys
- Sample Demonstration Portfolio for Arjun Shrivastava clearly labelled as
  "DEMO PROFILE — SAMPLE DATA"

3. PROJECT FOLDER STRUCTURE (ORGANIZED BY ROLE)
-----------------------------------------------
portivue/
├── README.txt                                  (Notepad quick-start guide)
├── README.md                                   (GitHub Markdown documentation)
├── package.json                                (Dependencies & scripts)
├── vite.config.ts                              (Vite + React + Tailwind config)
├── tsconfig.json                               (TypeScript configuration)
├── index.html                                  (Application HTML entry)
├── .env.example                                (Supabase & Gemma 4 env template)
├── .gitignore                                  (Git ignore rules for GitHub)
├── supabase/
│   └── migrations/
│       ├── 001_initial_schema_and_rls.sql      (PostgreSQL tables & RLS policies)
│       └── 002_add_portfolio_entry_outcome.sql (Entry outcome field)
└── src/
    ├── main.tsx                                (React DOM root entry)
    ├── index.css                               (Tailwind CSS styles)
    ├── App.tsx                                 (Main application & routing)
    ├── types/
    │   └── portfolio.ts                        (TypeScript interfaces & types)
    ├── lib/
    │   ├── supabase.ts                         (Supabase client & connection)
    │   └── gemmaAdapter.ts                     (Lightweight Gemma 4 AI adapter)
    ├── utils/
    │   └── validation.ts                       (URL, username & completion utils)
    └── data/
        └── demoPortfolio.ts                    (Arjun Shrivastava sample data)

4. HOW TO RUN IN VS CODE OR ANTIGRAVITY
---------------------------------------
Step 1: Extract this ZIP folder and open the "portivue" folder in VS Code or
        Google Antigravity.
Step 2: Copy ".env.example" to a new file named ".env" (your Supabase URL and
        publishable anon key are already pre-filled).
Step 3: Open your Supabase SQL Editor and run migrations in order:
        supabase/migrations/001_initial_schema_and_rls.sql
        supabase/migrations/002_add_portfolio_entry_outcome.sql
Step 4: In the terminal, install dependencies and start the dev server:
        npm install
        npm run dev
Step 5: Open http://localhost:5173 in your browser.

5. HOW TO UPLOAD TO GITHUB
--------------------------
git init
git add .
git commit -m "Initial commit: Portivue Student Portfolio Platform"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/portivue.git
git push -u origin main
================================================================================
