# Second Nature Games — site

Static one-page site for Second Nature Games. No build step, no dependencies.

## Files

- `index.html` — the landing page
- `styles.css` — all styling
- `thanks.html` — contact form success page
- `netlify.toml` — Netlify config (publish dir + headers)

## Local preview

Open `index.html` in a browser, or run a tiny static server:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to Netlify

**Option A — drag and drop (fastest):**

1. Sign in at <https://app.netlify.com>.
2. Drag this folder onto the dashboard's "Sites" area.
3. Done. Netlify gives you a `*.netlify.app` URL.

**Option B — git-based (recommended long-term):**

1. Push this folder to a GitHub repo.
2. In Netlify: **Add new site → Import an existing project → GitHub**.
3. Pick the repo. No build command. Publish directory: `.`
4. Deploy.

## Set the contact-form notification email

Netlify auto-detects the `<form data-netlify="true">` in `index.html` on first
deploy. To route submissions to your inbox:

1. Netlify dashboard → **Forms** → select the `contact` form.
2. **Settings & usage → Form notifications → Add notification → Email
   notification**.
3. Recipient: `matt@secondnaturegames.ca`. Save.

Submissions also show in the Netlify Forms UI as a backup.

## Updating content

- **Gameplay clip** — replace the `<div class="video-placeholder">` block
  inside `<div class="video-frame">` with an `<iframe>` (YouTube embed) or a
  `<video>` tag. The frame is already 16:9.
- **Game description** — edit the two `<p>` tags inside `.prose` under the
  Hear No Evil section.
- **Team / socials** — edit the `<li class="member">` blocks under `#team`.
- **Email recipient** — change in the Netlify dashboard (see above), not in
  the HTML.

## Custom domain

In Netlify: **Site settings → Domain management → Add a domain**. Follow the
DNS instructions (either point your registrar at Netlify's nameservers, or
add a CNAME record). HTTPS is provisioned automatically.
