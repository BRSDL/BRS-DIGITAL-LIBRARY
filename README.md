# BRS Digital Library — Zero-Cost Pilot Launch Pack

This package is designed for a controlled pilot before spending on VPS hosting.

## Architecture
- Node.js + Express web app
- PostgreSQL via Supabase Free tier (persistent DB)
- Render Free web service for the Node app
- Socket.IO + WebRTC for small live-study rooms
- BigRock domain: brsdigitallibrary.com
- Manual/offline membership activation during pilot
- Razorpay is optional and disabled until live credentials are supplied

Render Free supports Node web services, custom domains, managed TLS and WebSockets, but free services sleep after 15 minutes of inactivity and their local filesystem is ephemeral. Therefore this version uses PostgreSQL instead of SQLite. Supabase Free provides PostgreSQL with a 500 MB database quota.

## Safety posture
The public pilot is configured for adults (18+) only. Do not admit minors until a verifiable parent/guardian consent flow has been legally reviewed and implemented. The legal pack includes a future guardian-consent template.

The app includes:
- strict anti-recording / anti-capture rules in the legal documents
- prohibition on screenshots, screen recording, redistribution and face/video misuse
- report endpoint and admin report queue
- camera-off option
- no recording by BRS by default
- membership/admin controls
- Terms, Privacy Notice, Community Safety Rules, Refund Policy, Recording/Video Notice, Guardian template and Incident Report form

## Deployment today
1. Create a free Supabase project and copy its Postgres connection string.
2. Create a free Render Web Service from this package/repository.
3. Add environment variables from .env.example.
4. Build: npm install
5. Start: npm start
6. Add custom domain brsdigitallibrary.com in Render.
7. At BigRock, point the domain DNS records exactly as Render instructs.
8. Test /api/health, registration, admin login, manual membership and a two-device live room.

## Admin
Set ADMIN_EMAIL and ADMIN_PASSWORD before first production boot. The first startup creates the admin account.

## Pilot membership
During the pilot, collect ₹250/month or ₹650/3 months offline if desired, then activate the member from Admin. Keep a separate accounting record/receipt for every cash payment.

## Legal note
These documents are operational templates, not a substitute for an Indian lawyer. No Terms/Privacy Notice can guarantee immunity or make a platform "legally bulletproof". Before admitting minors or opening unrestricted public user-generated video, obtain a lawyer's review of the final entity details, privacy/data processing, consumer/refund terms, child safety, intermediary obligations and incident-response process.
