# LauraAdmin 👑

Owner-only Android control centre for LauraTV.

## What it controls

- Active LauraTV announcements
- Maintenance mode
- Android release records
- Future APK upload/release management
- Future system status and analytics

## Security model

LauraAdmin uses Supabase Auth + an `admin_users` allow-list. The mobile LauraTV client only receives public active records. It does not get write access.

**Never put a Supabase service-role key in this app.**

## Setup

1. Create a brand-new Supabase project owned by you.
2. Create the owner account in Supabase Authentication.
3. Run `supabase/laura_admin_schema.sql` in that new project's SQL Editor.
4. Add your Auth user's UUID to `public.admin_users`.
5. Copy `.env.example` to `.env`.
6. Fill in your new project's URL, anon key, and owner email.
7. Run `npm install`.
8. Run `npx expo start` or `npx expo run:android`.

The existing LauraTV app and LauraTV Cowatch Render service must then be migrated to the same new Supabase project by changing their environment variables. Do not delete the old project until the migration is verified.
