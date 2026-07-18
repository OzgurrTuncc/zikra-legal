# Zikra — Legal & Account Pages

Public static pages for the [Zikra: İbadet Takibi](https://play.google.com/store/apps/details?id=com.nornirdevs.zikra) Android app: privacy policy and web-based account deletion request.

Hosted here (instead of a Supabase Edge Function) because Supabase's default `*.supabase.co` domain does not serve `text/html` from Edge Functions — it force-downgrades the response to `text/plain` and applies a locking `Content-Security-Policy`, which breaks both rendering and the account-deletion page's inline script. See https://github.com/orgs/supabase/discussions/35627.

- `privacy-policy/` — the app's privacy policy.
- `delete-account/` — email-verified account deletion request form. Calls the `delete-account` Supabase Edge Function directly (JSON API, unaffected by the HTML restriction above).

This will move to `zikra.app` once that domain exists.
