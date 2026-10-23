<sub>🇧🇷 [Versão em português](README.pt-BR.md)</sub>

# Hi, I'm Túlio 👋

Full-stack developer. I build products from zero to production: database, back end, web,
mobile, and the integrations that keep the business running (payments, WhatsApp, AI).

**Main stack:** TypeScript · Node.js · Next.js · React Native (Expo) · Flutter · PostgreSQL / Supabase · GraphQL

> The repositories for my products are private. Below is what each one does and the problems I
> solved in them. Happy to walk through the code on a call.

---

## 🗓️ Qiki — WhatsApp scheduling for salons and barbershops

SaaS where customers book, reschedule, and cancel appointments by chatting with a bot on WhatsApp,
while the salon manages everything from a web dashboard.

<p align="center"><img src="assets/qiki.gif" width="260" alt="Customer booking an appointment with the Qiki bot on WhatsApp"></p>

**Stack:** Next.js · TypeScript · Node.js · PostgreSQL (Supabase) · WhatsApp Cloud API (Meta) · Asaas · OpenAI

- **Secure multi-tenancy:** tenant isolation enforced in two layers in PostgreSQL (Row Level
  Security + composite foreign keys), verified by integration tests and penetration testing
  (OWASP ZAP).
- **Conversation engine:** pure, testable state machine; AI helps understand the message, but
  availability checks and booking never depend on it.
- **No double bookings:** a Postgres exclusion constraint, tested under real concurrency.
- **Payments:** recurring subscriptions (credit card and Pix) with idempotent webhooks, automatic
  refunds, and chargeback handling.
- **Web security:** nonce-based CSP, SSRF and open-redirect protection, rate limiting, and CAPTCHA.
- **LGPD (Brazil's GDPR):** transactional data-subject erasure, automatic data retention, and logs
  free of personal data.
- Public booking page, reminders, waitlist, open-slot offers, and Google Calendar sync.

**Status:** approved by Meta, preparing for launch.

---

## 🦫 Cashtor — stress-free personal finance

Money management app for Android, iOS, and web, featuring Beto, an AI assistant that answers
questions like "how much did I spend on food this month?".

<p align="center">
  <img src="assets/cashtor-inicio.gif" width="220" alt="Cashtor home screen with balance, budgets, and transactions">
  <img src="assets/cashtor-metas.gif" width="220" alt="Goals in Cashtor">
  <img src="assets/cashtor-beto.gif" width="220" alt="Beto, the AI assistant, summarizing the month's spending">
</p>

**Stack:** React Native (Expo) · TypeScript · Supabase (Postgres, Auth, Edge Functions) · OpenAI

- Accounts, credit cards with billing cycles and installments, categories, goals, and recurring bills.
- **Import a credit card bill from a photo:** AI reads the image and the app creates the transactions.
- **Family mode:** shared household finances, invite-only.
- **Security and privacy:** AI key kept off the device (JWT-protected Edge Function), per-user AI
  usage limits, RLS, biometric lock, a mode that hides amounts, full account and data deletion,
  and nightly database backups.
- Remote kill switches to turn AI features off without shipping a new release.

**Status:** being published on the Google Play Store.

---

## 🏪 Fluxy — retail management and point of sale *(in development)*

Management system for retail stores: products, inventory, sales, customers, suppliers, and store credit.

**Stack:** Flutter (Android, web, and desktop) · GraphQL (Apollo Server) · Node.js · MongoDB · SQLite

- **Works offline:** local database (SQLite) with a sync service to the server.
- Barcode scanning, checkout, store credit, and purchase orders.
- Inventory report with CSV and Excel export.
- One codebase for mobile, browser, and desktop, with a responsive layout and light and dark themes.

**Next steps:** Brazilian electronic invoicing (NF-e), sales commissions, and more reports.

---

📫 **Contact:** [tsalmeida1988@gmail.com](mailto:tsalmeida1988@gmail.com) · [LinkedIn](https://www.linkedin.com/in/tulio-almeida/)
