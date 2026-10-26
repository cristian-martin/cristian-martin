# Hi, I'm Cristian Martin

Software engineer in Charlotte, NC. I build AI-powered products end to end — iOS and web apps, ML pipelines, and payments — and ship them.

**[cristian-martin.vercel.app](https://cristian-martin.vercel.app)** · [Résumé](https://cristian-martin.vercel.app/resume.pdf) · [LinkedIn](https://www.linkedin.com/in/cristian-flores-dev/) · cristian.msf23@gmail.com

---

## What I've built

The projects below are private repos (they're products, not samples). I'm happy to add you as a read-only collaborator or walk through the code on a call — just ask.

### Tristim — skin-tone colorimetry & AI shade matching · iOS + web
Face scan → scientifically grounded color profile → real product matches.
- SwiftUI + ARKit app with an **on-device CoreML classifier** (MobileNetV3, ~100 ms) and Gemini Vision fallback; 96% of scans never leave the phone
- Hand-written **CIELAB / ΔE2000** engine in Swift and TypeScript, validated against 15k spectrophotometer measurements
- Next.js 15 backend (~40 routes) on Vertex AI + Gemini; Python/OpenCV pipeline that extracts Lab color from product images
- **Self-improving loop:** Cloudflare Worker + D1 → GitHub Actions retraining → CoreML export → in-app model update
- Ran lighting experiments proving the camera can't recover b*, re-architected, and wrote it down so it never gets re-tried

`Swift` `SwiftUI` `ARKit` `CoreML` `PyTorch` `TypeScript` `Next.js` `Vertex AI` `Cloudflare Workers` `GitHub Actions` `Python` `OpenCV`

### StellarTip — card-to-stablecoin tipping for hospitality workers
Guest scans a QR code and pays by card; the worker receives USDC on Stellar in seconds.
- Stripe Checkout → verified webhook → idempotent on-chain payout
- Stellar SDK: automatic custodial wallets (funding + USDC trustline), memo'd payments, explorer links
- Drizzle ORM on Neon Postgres, Auth.js magic links, worker and admin dashboards

`TypeScript` `Next.js 16` `Stripe` `Stellar SDK` `Drizzle ORM` `PostgreSQL` `Auth.js`

### OpenClaw Wealth Engine — tooling for an autonomous trading agent
Deterministic, auditable tools so an LLM agent can research and trade without free-form web access.
- 19 Python CLIs with JSON-only output: SEC EDGAR 13F + XBRL, FRED, FMP, Marketaux, OpenFIGI, USASpending, PatentsView
- Cross-fund consensus scorer, **dynamic risk engine** (limits adapt to realized P&L and VIX regime), Alpaca execution with bracket orders and append-only audit logs

`Python` `pandas` `Alpaca API` `SEC EDGAR` `FRED` `agent tooling`

---

## Background

- B.S. Information Systems Technology — Miami Dade College (Dec 2025)
- iOS/AR developer intern (City of Coral Gables), QA automation (TestCafe, SoapUI, Playwright), technical support
- English / Spanish

## Public code

- [`portfolio`](https://github.com/cristian-martin/portfolio) — this site: React 19 + TypeScript + Vite + Tailwind, deployed on Vercel
- More coming: I'm extracting the ΔE2000 color engine into a standalone package with tests
