# LandingForge — AI Landing Page Generator

Generate 3 unique landing page UI variations instantly from a single text prompt, rendered live in the browser.

---

## What it does

You type a product idea. The app calls Google Gemini 2.0 Flash and generates 3 completely different React landing page designs side by side:

- **Minimal Luxury** — clean, whitespace-heavy, elegant
- **Dark Tech** — dark mode, neon accents, SaaS-style
- **Playful Bold** — bright colors, neo-brutalist, chunky borders

Each variation is rendered live using Sandpack so you can see the actual UI, switch to code view, and copy the source.

---

## Tech Stack

- **Next.js 14** (App Router)
- **React 18** + **TypeScript**
- **Tailwind CSS** — styling
- **Framer Motion** — animations
- **Lucide React** — icons
- **Google Gemini 2.0 Flash** — AI code generation
- **Sandpack by CodeSandbox** — live in-browser code preview
- **Vercel** — deployment

---

## Getting Started

### 1. Install dependencies
```bash
npm install
```

### 2. Add your API key

Create a `.env.local` file in the root:
```
GOOGLE_GENERATIVE_AI_API_KEY=your_key_here
```

Get a free key at: https://aistudio.google.com/app/apikey

### 3. Run the dev server
```bash
npm run dev
```

Open http://localhost:3000

---

## Project Structure
```
landing-gen/
├── app/
│   ├── api/
│   │   ├── generate/
│   │   │   └── route.ts       # Gemini API — generates 3 variations
│   │   └── models/
│   │       └── route.ts       # Lists available Gemini models
│   ├── globals.css            # Dark theme + Tailwind base
│   ├── layout.tsx             # Root layout with fonts
│   └── page.tsx               # Main UI — search bar + results grid
├── components/
│   ├── VariationCard.tsx      # Sandpack card with preview/code toggle
│   └── SkeletonCard.tsx       # Loading skeleton
├── .env.local                 # Your API key (not committed)
├── next.config.js
├── tailwind.config.ts
└── package.json
```

---

## How it works

1. User enters a prompt describing their product
2. The app sends the prompt to `/api/generate`
3. The API calls Gemini 2.0 Flash 3 times sequentially (to avoid rate limits), each time with a different design style persona
4. Gemini returns pure React + Tailwind JSX code for each variation
5. The code is rendered live in 3 Sandpack instances side by side
6. User can toggle between Preview and Code view on each card

---

## Deployment

Deployed on Vercel. Add `GOOGLE_GENERATIVE_AI_API_KEY` as an environment variable in your Vercel project settings before deploying.

---

## License

MIT
