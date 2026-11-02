# Portivue — Student Portfolio Platform

> **Your work deserves to be seen.**  
> Build your professional student identity through projects, certificates, hackathons, and achievements. One portfolio. One shareable link (`portivue.com/u/username`).

---

## Overview

**Portivue** is a modern, full-stack student portfolio platform built with **React**, **TypeScript**, **Tailwind CSS**, and **Supabase** (Authentication, PostgreSQL Database, Storage, and Row Level Security).

### Core Highlights
- **Supabase Backend & Row Level Security (RLS):** Every student owns their profile and portfolio entries. Private profiles and unpublished drafts are strictly protected at the database policy level.
- **Portfolio Entries:** Add projects, certificates, hackathons, and other work with a title, description, outcome, optional evidence URL, and public/private visibility.
- **Honest Evidence Labels:** Portfolio items automatically display **`Evidence linked`** when a supporting HTTP/HTTPS URL (GitHub repo, live deployment, credential link) is provided, or **`Self-reported`** when no link is attached—never making false verification claims.
- **Lightweight Gemma 4 AI Adapter (Optional):** Includes a configurable adapter for `gemma-4-2b-it` and `gemma-4-9b-it` with in-memory caching and a zero-cost deterministic text formatter fallback. Portivue runs 100% without AI enabled.
- **Isolated Demo Portfolio:** Features a clearly labelled sample profile (**Arjun Shrivastava**) separated from real registered database users.
- **Sample Course Links:** Certificate-category demo entries link to official course information only. They are clearly marked as examples and do not claim Arjun earned those certificates.

---

## Project Architecture (Modular Role Structure)

```text
portivue/
├── README.txt                                  # Notepad plain-text project guide
├── README.md                                   # GitHub documentation
├── package.json                                # Project dependencies & scripts
├── vite.config.ts                              # Vite bundler configuration
├── tsconfig.json                               # TypeScript compiler setup
├── index.html                                  # HTML root template
├── .env.example                                # Environment variables template
├── .gitignore                                  # Git ignore rules
├── supabase/
│   └── migrations/
│       ├── 001_initial_schema_and_rls.sql      # Database schema, indexes, triggers & RLS
│       └── 002_add_portfolio_entry_outcome.sql # Add entry outcome field
└── src/
    ├── main.tsx                                # Application bootstrap
    ├── index.css                               # Tailwind CSS imports
    ├── App.tsx                                 # Application views & dashboard
    ├── types/
    │   └── portfolio.ts                        # Data models & TypeScript types
    ├── lib/
    │   ├── supabase.ts                         # Supabase REST/Auth/Storage client
    │   └── gemmaAdapter.ts                     # Lightweight Gemma 4 adapter & cache
    ├── utils/
    │   └── validation.ts                       # Username, URL & completion validators
    └── data/
        └── demoPortfolio.ts                    # Sample portfolio (Arjun Shrivastava)
```

---

## Quick Start (VS Code & Antigravity)

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Configure environment variables:**
   ```bash
   cp .env.example .env
   ```

3. **Initialize or update the Supabase database:**
   Open the [Supabase SQL Editor](https://supabase.com/dashboard/project/btpgvxfgivzrbsyegljo/sql). For a new database, run migration `001_initial_schema_and_rls.sql`, then `002_add_portfolio_entry_outcome.sql`. For an existing database, run migration `002_add_portfolio_entry_outcome.sql`.

4. **Start the development server:**
   ```bash
   npm run dev
   ```
