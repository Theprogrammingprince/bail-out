# Welcome to your Lovable project

## Project info

**URL**: https://bailout.ng

# Bailout

Bailout is a digital financial access platform for Nigerian micro, small, and medium-sized enterprises (MSMEs). It is designed to make funding opportunities easier to discover, understand, and pursue by connecting businesses with relevant loans, grants, advisory support, and growth resources.

This repository contains the frontend experience for the Bailout platform, including its public landing page and an interactive loan/grant application prototype.

## Product focus

Bailout is built around the challenges MSMEs face when seeking capital:

- Finding credible loans and grants in a fragmented funding landscape
- Understanding eligibility requirements and application processes
- Building the financial visibility lenders need to assess risk
- Accessing practical guidance for sustainable business growth

The product direction includes a two-sided marketplace that can match businesses with suitable funding instruments, support credit intelligence, and provide anonymized market insight to institutions.

## Current experience

The current frontend includes:

- A responsive single-page product website
- A three-step loan/grant application flow covering personal, business, and financial information
- Product sections covering MSME financing, advisory, growth acceleration, and financial tools
- Funding-match, grant-discovery, credit-risk, secure-disbursement, and market-intelligence feature areas
- Language support for English, Yoruba, Hausa, Igbo, and Nigerian Pidgin
- Optional welcome text-to-speech through a Supabase Edge Function with browser speech fallback

> **Prototype note:** Application submission is currently simulated in the browser. The form does not yet persist applications or connect applicants to live lenders, grants, credit bureaus, or disbursement systems.

## Tech stack

- React 18 and TypeScript
- Vite
- Tailwind CSS
- shadcn/ui and Radix UI primitives
- React Router
- TanStack React Query
- Supabase Edge Functions
- Vitest and Testing Library

## Getting started

### Prerequisites

- Node.js 18 or newer
- npm, or Bun if you prefer the repository's existing lockfile

### Installation

```bash
git clone <repository-url>
cd bail-out
npm install
```

### Run locally

```bash
npm run dev
```

Vite will print the local URL, usually `http://localhost:5173`.

## Available scripts

| Command | Purpose |
| --- | --- |
| `npm run dev` | Start the Vite development server |
| `npm run build` | Create a production build |
| `npm run build:dev` | Create a development-mode build |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint |
| `npm run test` | Run the test suite once |
| `npm run test:watch` | Run Vitest in watch mode |

## Environment variables

The multilingual welcome audio uses the Supabase Edge Function configured in `src/contexts/LanguageContext.tsx`. To enable it locally, create a `.env.local` file with:

```bash
VITE_SUPABASE_URL=<your-supabase-project-url>
VITE_SUPABASE_PUBLISHABLE_KEY=<your-supabase-publishable-key>
```

The `welcome-tts` function also requires an `ELEVENLABS_API_KEY` configured as a Supabase secret. If the function is unavailable, the app falls back to the browser's built-in speech synthesis where supported.

Never commit credentials or private keys to the repository.

## Project structure

```text
src/
├── components/       Reusable product sections and UI components
├── contexts/          Shared application state, including language support
├── integrations/      Supabase client and generated types
├── pages/             Route-level pages
├── App.tsx            Application providers and routing
└── main.tsx           Application entry point

supabase/
└── functions/        Supabase Edge Functions
```

## Ownership

Bailout is currently designed, built, and maintained by a sole developer. The codebase favors a focused, modular frontend foundation that can grow into the full funding marketplace as backend integrations and production workflows are introduced.

## Status

This project is under active development. The public website and interaction flows are available for product exploration; financial matching, application persistence, identity verification, lender integrations, and production safeguards remain part of the roadmap.
