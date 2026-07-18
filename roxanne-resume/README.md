# Roxanne's Caregiver Resume Website

A hand-built resume site — plain HTML + CSS, no frameworks, no build step.
Everything below is 100% free.

## What's in this folder

```
index.html          the page
styles.css           all styling
assets/img/          your 4 photos, already compressed for the web
```

---

## Part 1 — Put it on GitHub (free hosting)

1. **Create a GitHub account** at github.com if you don't have one.
2. Click the **+** in the top right → **New repository**.
   - Repository name: `roxanne-resume` (any name is fine)
   - Set it to **Public**
   - Don't add a README (you already have one) — click **Create repository**.
3. On the new repo's page, click **uploading an existing file** (or drag-and-drop).
4. Drag in **all the files and folders** from this project (`index.html`, `styles.css`, and the whole `assets` folder, keeping the folder structure).
5. Scroll down, click **Commit changes**.
6. Go to the repo's **Settings** tab → **Pages** (left sidebar).
7. Under "Build and deployment" → Source: **Deploy from a branch**.
   - Branch: `main`, folder: `/ (root)` → **Save**.
8. Wait about a minute, then refresh — GitHub will show you a live URL like:
   `https://yourusername.github.io/roxanne-resume/`

That's it — your resume is live and free, forever, with no server to maintain.

---

## Part 2 — Add Cloudflare (free custom domain + speed/security)

Cloudflare doesn't host your files — GitHub already does that. Cloudflare sits
in front of it to give you a nicer domain name (instead of `.github.io`), plus
free HTTPS, caching, and basic protection.

**You'll need to buy a domain name first** (e.g. `roxannecares.com`). This is
the only step that typically costs money — usually $10–15/year from a
registrar like Namecheap, Porkbun, or Cloudflare Registrar itself (Cloudflare
sells domains at cost, no markup). If you'd rather stay 100% free, skip Part 2
and just share your `github.io` link — it works perfectly well on its own.

1. Buy your domain from any registrar.
2. Sign up free at **cloudflare.com** → **Add a site** → enter your domain.
3. Choose the **Free** plan.
4. Cloudflare scans your existing DNS records, then gives you **two
   nameservers** (e.g. `ada.ns.cloudflare.com`, `bob.ns.cloudflare.com`).
5. Go back to your domain registrar → find "Nameservers" or "DNS settings" →
   replace the existing nameservers with the two Cloudflare gave you. This can
   take a few hours to a day to fully update.
6. Back in Cloudflare, go to **DNS** → **Records** → **Add record**:
   - Type: `CNAME`
   - Name: `www` (or `@` for the bare domain, if your registrar/Cloudflare
     supports CNAME flattening on the root — Cloudflare does)
   - Target: `yourusername.github.io`
   - Proxy status: **Proxied** (orange cloud ON)
   - Save.
7. Back in your **GitHub repo → Settings → Pages**, under "Custom domain,"
   type your domain (e.g. `www.roxannecares.com`) and save. GitHub will run a
   check and issue its own free HTTPS certificate for it.
8. In Cloudflare, go to **SSL/TLS** → set encryption mode to **Full**.

Give it a little time to propagate, then visit your new domain — your resume
site loads through Cloudflare's fast global network, over HTTPS, for free.

---

## Editing your content later

Everything is in plain HTML — no code experience needed for small edits:

- Open `index.html` in any text editor (Notepad, TextEdit, or free tools like
  [VS Code](https://code.visualstudio.com/)).
- Find the text you want to change (e.g. your bio, your work dates) and edit
  it directly between the `<p>` or `<li>` tags.
- Two spots are marked `<!-- EDIT ME -->` in the Experience section — that's
  your work dates and daily duties. Update those with your real details.
- Save the file, then re-upload it to GitHub (drag it into the repo again and
  commit) — the live site updates automatically within a minute.

## Swapping photos

Replace any file inside `assets/img/` with a new photo **using the exact same
filename** (e.g. save your new headshot as `headshot.jpg`, overwriting the
old one), then re-upload to GitHub the same way.
