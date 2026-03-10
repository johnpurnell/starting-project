# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
bun dev        # Start development server at http://localhost:3000
bun build      # Production build
bun start      # Start production server
bun lint       # Run ESLint
```

No test runner is configured in this project.

## Architecture

This is a **Next.js 16 App Router** project using React 19, TypeScript, and Tailwind CSS v4.

- `app/layout.tsx` — Root layout with Geist font setup (sans + mono) and global metadata
- `app/page.tsx` — Home page (Server Component by default)
- `app/globals.css` — Global styles using Tailwind v4's `@import "tailwindcss"` syntax with CSS variable theming (`--background`, `--foreground`) and dark mode via `prefers-color-scheme`

**Key conventions:**
- Path alias `@/*` maps to the project root (e.g., `@/app/...`, `@/components/...`)
- All files in `app/` are Server Components unless marked `"use client"`
- Tailwind v4 is configured via `@tailwindcss/postcss` — no `tailwind.config.js` needed; theme customization goes in `globals.css` under `@theme`
- ESLint uses `eslint-config-next` with Core Web Vitals and TypeScript rules
