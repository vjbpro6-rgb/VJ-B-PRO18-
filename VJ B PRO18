# VJ B PRO18 website

This is the source project for `https://vjbpro18.netlify.app` (the Netlify address must be created/claimed in your Netlify account).

## What is included
- Dark blue and silver responsive website
- Customer registration and login
- Admin role assigned to `vjbpro6@gmail.com`
- Admin-only video uploads to a private Supabase Storage bucket
- Customer video access while a 3-day subscription is active
- UGX 2,000 payment-request form for MTN or Airtel
- Admin dashboard to verify received payments and grant 3 days

## Important payment limitation
The project records payment requests. Automatic MTN MoMo/Airtel Money collection and provider callback verification are not connected. You need approved merchant/API credentials and a secure server-side integration. Until then, the admin must check the merchant account and manually confirm receipt in the dashboard.

## Setup (phone or computer)
1. Create a Supabase project at https://supabase.com.
2. Open SQL Editor in Supabase, paste all of `schema.sql`, and run it.
3. In Supabase Authentication settings, enable Email/Password. For easier testing you may temporarily turn off email confirmation; turn it back on before public launch.
4. In Supabase Project Settings > API, copy the Project URL and anon/public key.
5. Open `app.js` and replace `PASTE_YOUR_SUPABASE_PROJECT_URL_HERE` and `PASTE_YOUR_SUPABASE_ANON_PUBLIC_KEY_HERE` with those values. The anon key is intended for browser use; never put the service-role key in this file.
6. Register the administrator account using exactly `vjbpro6@gmail.com`. The database trigger gives this account the admin role. Use a strong password and secure that email account.
7. Test admin login and upload a small video. Register a second customer account and test that videos remain locked until an administrator verifies payment.
8. Upload the project folder contents to Netlify (or connect the project to GitHub and deploy). Set the Netlify site domain to `vjbpro18.netlify.app` if that name is available in your Netlify account.

## Security notes
- Do not share Supabase service-role keys, passwords, payment PINs, or provider secrets.
- Admin role is assigned by a database trigger based on the configured email. If changing the admin email, change it in both `app.js` and `schema.sql` before new admin registration.
- Video uploads are limited to 500 MB in the interface and storage bucket. Adjust limits if needed.
- This is a starter implementation. Have the payment integration and production security reviewed before accepting public payments.
