# Steady Ledger — CuraDebt funnel site

A static, no-build site: two offer pages (Tax Relief, Debt Relief), each
with its own thank-you page where the CuraDebt widget goes. Deploy as-is
to Netlify — no build step needed.

## Deploy to Netlify

1. Go to app.netlify.com → **Add new site** → **Deploy manually**.
2. Drag the whole `steady-ledger` folder onto the upload area (or zip it
   first and upload the zip — either works).
3. Once it's live, go to **Site settings → Change site name** to pick
   your own `.netlify.app` subdomain, or add a custom domain.

If you'd rather connect a GitHub repo for auto-deploys instead of
drag-and-drop, push this folder to a repo and connect it in Netlify —
`netlify.toml` is already set up, no build command needed (publish
directory is `.`).

## Before you go live — fill these in

- **Replace every `REPLACE-WITH-YOUR-DOMAIN`** in `index.html`,
  `tax-relief.html`, `debt-relief.html`, `robots.txt`, and
  `sitemap.xml` with your actual Netlify (or custom) domain.
- **Install the CuraDebt widget.** In your CuraDebt dashboard:
  Dashboard → "Configure the widget" → copy the JavaScript snippet →
  paste it into `tax-relief-thank-you.html` AND
  `debt-relief-thank-you.html`, inside the `#widget-slot` div (marked
  clearly with an HTML comment in both files).
- **Add your tracking pixel / postback.** Dashboard → "Set up
  tracking" → same two thank-you pages, same spot, so leads tie back
  to your account.
- **Fill in `privacy-policy.html` and `terms.html`.** Every
  `[BRACKETED]` placeholder — business name, contact email, effective
  date — needs a real value. These are templates, not legal advice;
  have someone qualified review the final wording, especially since
  debt relief advertising is federally regulated.

## Before you run paid traffic

- **Check with your CuraDebt affiliate manager which ad platforms
  you're actually cleared to use.** Google Ads requires certification
  for debt-relief lead generation specifically — this could rule out
  that channel entirely for the Debt Relief page. Confirm before you
  spend anything.
- **Don't add specific savings claims** ("reduce your debt by X%",
  "average client saves...") anywhere on these pages. The FTC's
  Telemarketing Sales Rule specifically bars debt relief advertisers
  and lead generators from claiming a dollar amount or percentage
  saved without documented proof — this is one of the most enforced
  rules in this vertical.
- **Don't brand the site as CuraDebt itself** (logo, copyright line,
  page titles). This site is deliberately built as an independent
  "Steady Ledger" brand that refers visitors to a specialist — check
  your affiliate agreement, but most programs require this kind of
  separation.
- **Check state rules** if you're targeting specific states — debt
  settlement advertising rules vary, and a few states restrict debt
  settlement companies outright.

## File map

- `index.html` — home page, links to both offers
- `tax-relief.html` / `debt-relief.html` — the two SEO content pages
- `tax-relief-thank-you.html` / `debt-relief-thank-you.html` — widget install pages
- `privacy-policy.html`, `terms.html` — legal pages (need your details filled in)
- `404.html` — custom not-found page
- `css/style.css` — shared design system
- `netlify.toml` — redirects (`/tax`, `/debt`, `/privacy`, `/terms`) + custom 404
- `robots.txt`, `sitemap.xml` — basic SEO hygiene, thank-you pages excluded from indexing
