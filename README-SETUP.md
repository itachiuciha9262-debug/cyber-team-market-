# Cyber Team Help Admin + Client Panels

Routes: /admin/ and /client/. The existing root index.html is intentionally untouched.

## Supabase
The connected project URL and browser-safe publishable key are in config.js. Database tables, signup profile trigger and RLS policies were applied to the project previously.

## First admin account
1. Open /admin/ and create an account using your email and a strong unique password.
2. Confirm your email if Supabase requires it.
3. In Supabase SQL Editor, run this after replacing the email:

```sql
update public.profiles set role = 'admin' where email = 'YOUR_ADMIN_EMAIL';
```

4. Sign out and sign back in at /admin/.

Clients create accounts at /client/. RLS limits clients to their own service requests. Admins can view requests and update statuses.

## Security
Only the publishable key is used in browser code. Never put a service_role or secret key in config.js. This portal is for lawful customer support and authorized defensive security services.
