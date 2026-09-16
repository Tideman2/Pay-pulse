# Pay-pulse
A high-performance, full-stack bill payment engine built with Next.js (App Router) and the VTpass API, implementing secure Server Actions, Next.js Middleware route protection, and real-time transaction tracking.


# ⚡ VTPass Bill Payment Engine

A secure, full-stack bill payment platform engineered to demonstrate advanced Next.js architecture patterns. This application interfaces with the **VTpass REST API** to handle live utility service vending, airtime top-ups, and data bundle subscriptions.

## 🚀 Key Architectural Concepts Implemented

*   **Safe Colocation:** Component logic, utility helpers (`table-utils`), and styling sheets are contained cleanly within route folders to maintain isolated feature domains.
*   **Hybrid Rendering Engine:** Utilizes React Server Components (RSC) for lightning-fast server-side data fetching alongside Client Components for responsive UI state adjustments.
*   **Secure Server Actions:** Bypasses standard exposed API routes to run core database mutations and external gateway endpoints directly on the server.
*   **Idempotent Requests:** Uses a custom timezone-locked (`Africa/Lagos`) 12+ character unique numeric string algorithm to prevent transaction double-billing.
*   **Robust Boundary Protection:** Next.js Middleware intercepts incoming network headers to parse `httpOnly` authentication cookies before executing any data payload.

## 🛠️ Tech Stack

*   **Framework:** Next.js (App Router)
*   **Language:** TypeScript
*   **Validation:** Zod (Server-side structural shape assertions)
*   **API Gateway:** VTpass Sandbox REST API
*   **State & Caching:** Next.js Data Cache Layer

## ⚙️ Environment Variables Setup

Create a `.env.local` file in the root directory of your project. **Never commit this file to public version control.**

```env
# VTpass API Credentials (Obtained from developer dashboard sandbox)
VTPASS_API_KEY="your_api_key_here"
VTPASS_SECRET_KEY="your_secret_key_here"
VTPASS_PUBLIC_KEY="your_public_key_here"

# Authentication Token Secrets
JWT_SECRET="generate_a_secure_long_random_hash_here"

# Network Configuration Defaults
NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

## 🛠️ Getting Started

### 1. Clone the repository
```bash
git clone https://github.com
cd your-repo-name
```

### 2. Install dependencies
```bash
pnpm install
# or
yarn install
```

### 3. Run the development server
```bash
pnpm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
