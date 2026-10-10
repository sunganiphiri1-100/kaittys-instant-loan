# Kaitty's Instant Loans — full-stack starter

Stack: Next.js + Supabase Auth + PostgreSQL + private Storage.

## Setup
1. Install Node.js 20+.
2. Create a Supabase project.
3. In Supabase SQL Editor, run `supabase/schema.sql`.
4. Copy `.env.example` to `.env.local` and fill in the project URL and anon/publishable key.
5. Run `npm install`, then `npm run dev`, and open `http://localhost:3000`.
6. Register your first borrower account. To grant admin access, run this in Supabase SQL Editor after replacing the email:
   `UPDATE public.profiles SET role='admin' WHERE id=(SELECT id FROM auth.users WHERE email='YOUR-ADMIN-EMAIL');`
7. Sign out and back in. The `/admin` route is admin-only. Public registration always creates borrowers.

## Included
- Real hosted authentication via Supabase (once configured).
- Role stored in a database profile, not selected at login.
- Server-side admin checks and PostgreSQL row-level security.
- Private document bucket with per-user access rules.
- Loan applications, status listing and admin approval/rejection actions.

## Important
This is a starter that requires setup and independent testing, not a deployed or certified production service. Do not use real NRC/selfie data until you test RLS with separate accounts, confirm storage policies, enable email confirmation, add admin MFA, audit logs, rate limiting, backups and recovery testing, and complete security and legal review. Never expose a service-role key. Verify Zambian lending, privacy, disclosure and licensing requirements. Flyer rates (20% for 2 weeks, 40% for 4 weeks) are merely carried forward and must be confirmed. Mobile-money integration, repayment ledger, disbursement tracking, notifications and downloadable PDF generation are not yet implemented in this starter.
