# AllSet Supply LLC — Site + Email Setup Guide

Goal: `jude@allsetsupply.co` sending/receiving + this site live at `https://allsetsupply.co`.
Total cost: ~$28/yr domain + $7/mo Google Workspace. Total time: ~1 hour.

Note: `allsetsupply.com` is owned by a third party (parked since 2018, no site).
We use `.co` — matches "Co." branding anyway. Just always double-check the .co
when typing/printing the email address.

---

## Step 1 — Buy the domain (~10 min)

Confirmed available as of Jul 17, 2026: **`allsetsupply.co`** (~$28/yr)

Recommended registrar: **Cloudflare** (dash.cloudflare.com → Domain Registration) —
at-cost pricing AND it makes Step 3 (free hosting) seamless. Porkbun/Namecheap also fine.

## Step 2 — Google Workspace Business Starter ($7/user/mo)

1. workspace.google.com → Get Started
2. Business name: AllSet Supply LLC · Just you · Country: US
3. "I have a domain" → enter `allsetsupply.co`
4. Create the user: `jude@allsetsupply.co`
5. Workspace asks you to verify the domain — it gives you a TXT record.
   Add it in Cloudflare: DNS → Records → Add record → Type TXT, paste value.
6. Workspace then walks you through MX records (again in Cloudflare DNS).
   Accept the guided/automatic option if offered.
7. Wait 15–60 min for DNS propagation. Send a test email both directions.

Then in admin.google.com → Apps → Google Workspace → Gmail → Authenticate email:
turn on **DKIM** and publish the record in Cloudflare DNS. Don't skip — this is
what keeps you out of spam folders.

## Step 3 — Deploy this site free on Cloudflare Pages (~10 min)

1. Cloudflare dashboard → Workers & Pages → Create → Pages → **Upload assets**
2. Project name: `allset-supply`
3. Drag this folder (or just `index.html`) in → Deploy
4. Project → Custom domains → add `allsetsupply.co` (and `www`) —
   Cloudflare auto-creates the DNS records since the domain is already there.

Site is live with SSL, $0/mo.

## Step 4 — Wire up the old Gmail

In `allsetdistributionco@gmail.com` (and any other business gmail):
Settings → Forwarding → forward to `jude@allsetsupply.co`.

## Step 5 — Email signature

    Jude Hennigan
    Owner, AllSet Supply LLC
    jude@allsetsupply.co · allsetsupply.co

## Notes

- New domain = zero sending reputation. One-to-one outreach is fine (that's all
  this needs); no bulk sends for the first months.
- The site is a single self-contained `index.html` — edit text directly and
  re-upload to Pages to update.
- Claude can drive Steps 2.5–3 (DNS records, verification, Pages deploy) via the
  Chrome extension once you're logged in — you only do checkouts and passwords.
