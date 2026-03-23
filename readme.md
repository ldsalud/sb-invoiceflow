<div align="center">

# 🍃 SB InvoiceFlow

### Full-Featured Invoice Management SaaS

**🧪 Live Demo (Test Mode) → [sbinvoiceflow.com](https://sbinvoiceflow.com)**

[![Next.js](https://img.shields.io/badge/Next.js_16-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://stripe.com)
[![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma)](https://prisma.io)

> 💼 **THIS APP IS FOR SALE OR RENT!** A complete, production-ready SaaS template with all features fully implemented.  
> Perfect for startups, agencies, or entrepreneurs looking to launch fast. [Contact us ↓](#-app-for-salerental)

</div>

---

## 📸 What Is SB InvoiceFlow?

A **fully-featured Invoice Management SaaS** built from scratch with enterprise-grade architecture. Every feature is production-ready: multi-tenant teams, automated billing, Stripe subscriptions, REST API, role-based access, and more.


**Live Demo → [sbinvoiceflow.com](https://sbinvoiceflow.com)**

---

## ✨ Feature Highlights

### 💼 Core Business Features
| Feature | Details |
|---|---|
| **Invoice Lifecycle** | Draft → Sent → Viewed → Partial → Paid / Overdue / Cancelled |
| **Recurring Invoices** | Weekly / Monthly / Quarterly / Yearly — auto-generated via Vercel Cron at 02:00 UTC |
| **Client Management** | Full CRUD, invoice history, revenue totals, soft delete |
| **PDF Export** | A4 layout, company logo, branded theme (jsPDF) |
| **Multi-Currency** | 135+ currencies with live exchange rates, daily auto-refresh |
| **Pay-by-Link** | Public `/pay/[id]` page with Stripe Elements for client payments |
| **Bulk Actions** | Bulk send, cancel, CSV export (up to 2,000 rows, Business plan) |

### 🔐 Auth & Security
| Feature | Details |
|---|---|
| **Email OTP on every login** | 6-digit code via Resend; `otpPending` JWT flag gates dashboard |
| **2FA** | Time-limited OTP on login, email change, and registration |
| **Rate Limiting** | IP-based on auth endpoints + API v1; sliding-window per API key |
| **Security Headers** | CSP, HSTS, X-Frame-Options: DENY, Permissions-Policy on all routes |
| **OWASP Audited** | 0 known CVEs — Prisma ORM only (no raw SQL), bcrypt, httpOnly cookies |
| **Middleware Auth** | All 20+ dashboard routes protected; OTP-pending gate; CSRF excluded |

### 👥 Team & Approval Workflow *(Business Plan)*
- Members submit invoices → auto-routed to `PENDING_APPROVAL`
- Owner + all Admins notified via email; approve or reject with reason
- Rejected invoices stay editable and re-submittable
- Live approval badge in sidebar + priority notification bell

### 🌐 Public REST API *(Business Plan)*
- Bearer token (`sbk_live_...` format, SHA-256 hashed in DB)
- Full CRUD: invoices, clients, payments, recurring, analytics, dashboard
- Rate-limited: 120 req/60s per key, 30 req/60s per IP (pre-auth)
- Paginated responses: `{ data: ..., meta: { total, page, limit, pages } }`

### 🪝 Webhooks *(Business Plan)*
- Up to 20 HTTPS endpoints; 10 supported events
- HMAC-SHA256 signed (`X-Webhook-Signature`), pause/resume, delivery log, retry

### 📊 Analytics & Dashboard
- Revenue stats, monthly area chart (Recharts), overdue alerts
- ⌘K Command Palette — real-time search across invoices, clients, payments
- Notification bell — approval queue, overdue, recently paid, priority-sorted

### 💬 Support & Notifications
- Live in-app support chat (Pro/Business) via Server-Sent Events
- Browser push notifications via VAPID (payment, approval, recurring, invite)
- 14 transactional email templates via Resend

### 🛠️ Staff Admin Panel
- Platform-wide user management, suspension, plan distribution
- Immutable staff audit log, announcement banner system
- Staff roles: `STAFF_VIEWER` / `STAFF_SUPPORT` / `STAFF_ADMIN`

---

## 🧱 Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | Next.js 16 (App Router, Server Actions, Turbopack) |
| **Language** | TypeScript (strict) |
| **Database** | PostgreSQL via Supabase + Prisma ORM |
| **Auth** | NextAuth.js v5 (JWT, Prisma adapter, httpOnly cookies) |
| **Payments** | Stripe (Elements, Checkout, Connect, Subscriptions, Webhooks) |
| **Email** | Resend (14 templates) |
| **File Storage** | Supabase Storage (company logos) |
| **Styling** | Tailwind CSS + shadcn/ui |
| **Charts** | Recharts |
| **PDF** | jsPDF + jspdf-autotable |
| **Push** | Web Push API (VAPID) |
| **Realtime** | Server-Sent Events (SSE) |
| **Testing** | Vitest (58 unit tests) + Playwright (E2E) |
| **Deployment** | Vercel (with Cron jobs) |
| **Currency API** | ExchangeRate-API |

---

## 🏗️ Architecture Highlights

- **Static landing page** (`○`) — pre-rendered at build time, no auth call at request time
- **Edge-compatible middleware** — JWT-only auth at the edge; no Prisma/bcrypt in middleware
- **Server Actions** for mutations — no client-side `fetch()` for forms
- **Team context helper** — every query scoped to the correct `userId`, prevents IDOR
- **Plan limits enforced server-side** — every mutation checks `PLAN_LIMITS[plan]`
- **0 raw SQL** — 100% Prisma ORM throughout 96 API routes
- **Turbopack** build (Next.js 16 default) — 66s production build

---

## 📦 Project Scale

| Metric | Count |
|---|---|
| API routes | **96** |
| Pages | **40+** |
| Prisma models | **20+** |
| Email templates | **14** |
| Unit tests | **58 passing** |
| Lines of code | **~25,000** |

---

## 💼 App For Sale/Rental

### 🏪 Purchase Options

This complete SaaS application is available for:

#### 💰 **Outright Purchase**
- Full ownership of all source code
- Complete documentation and setup guide
- White-label ready (rebrand as your own)
- All features included (no restrictions)
- Perfect for: Agencies, entrepreneurs, startups

#### 📅 **Monthly Rental/License**
- Use the codebase for your business
- Regular updates and bug fixes
- Technical support included
- Lower upfront cost
- Perfect for: Testing the market, MVP launch

### ✨ What You Get

- ✅ **Complete codebase** — All 25,000+ lines of production code
- ✅ **96 API routes** — Fully tested and documented
- ✅ **40+ pages** — Dashboard, auth, billing, admin panel
- ✅ **Stripe integration** — Subscriptions, Connect, payments ready
- ✅ **Authentication** — NextAuth.js with 2FA/OTP
- ✅ **Multi-tenant** — Teams, roles, approvals built-in
- ✅ **REST API** — Rate-limited, paginated, production-ready
- ✅ **Email system** — 14 transactional templates (Resend)
- ✅ **Push notifications** — Web Push API (VAPID)
- ✅ **Real-time features** — SSE for live updates
- ✅ **Admin panel** — User management, analytics, audit logs
- ✅ **Database schema** — 20+ Prisma models, optimized queries
- ✅ **Security hardened** — OWASP audited, 0 CVEs
- ✅ **Deployment ready** — Vercel config, cron jobs, webhooks

### 🎯 Perfect For

- 🚀 **Entrepreneurs** — Launch your invoice SaaS in days, not months
- 🏢 **Agencies** — White-label for clients or internal use
- 💡 **Startups** — Skip MVP development, go straight to market
- 🛠️ **Developers** — Learn modern SaaS architecture patterns

### 📬 Contact for Pricing

| | |
|---|---|
| **GitHub** | [@miyako-enterprises](https://github.com/miyako-enterprises/) |
| **Email** | owner@miyako-enterprises.com |
| **Live Demo** | [sbinvoiceflow.com](https://sbinvoiceflow.com) |

> 💡 **Want to see more?** I'm happy to:
> - Do a live walkthrough of all features
> - Share private repo access for code review
> - Discuss customization options
> - Explain the architecture in detail

---

<div align="center">

**Live Demo (Test Mode) → [sbinvoiceflow.com](https://sbinvoiceflow.com)**

💼 **This app is available for purchase or rental.**

</div>
