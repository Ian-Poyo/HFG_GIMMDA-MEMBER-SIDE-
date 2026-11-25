# GIMMDA — Member Portal

The **member** app for Hill Fitness Gym. Your members use this; you don't.

> This is repo 2 of 2. The management app is a **separate repository**: `gimmda-management`.

---

## What this is

A website. Not a project you build — a folder you serve.

```
index.html                 the app
assets/index-....js        the app code (already built)
images/gym-emblem.png      logo
fonts/dm-sans.ttf          font
vercel.json                hosting settings
```

There is **no build step**, nothing to install, nothing to compile.

**Keep all folders together.** `assets/`, `images/` and `fonts/` must sit next to
`index.html` or the app will not load.

---

## What members see

- Their **QR pass** for entry at the front desk (a new code every 30 seconds)
- How many days of membership remain
- Payment history and receipts
- Gym announcements
- Their gym's details

---

## Deploy

1. Push this repo to GitHub
2. Vercel → **Add New → Project** → import this repo
3. Framework Preset: **Other**  *(do not pick Vite — it is already built)*
4. Build Command: **leave empty**
5. Output Directory: **leave empty**
6. **Deploy**

You get `something.vercel.app`. **This is the link you give members.**

---

## Push to GitHub

```bash
git init
git add .
git commit -m "GIMMDA member portal"
git branch -M main
git remote add origin https://github.com/YOURNAME/gimmda-member.git
git push -u origin main
```

---

## Two repos, one database

```
gimmda-management  (other repo) ─┐
                                 ├──►  same Supabase database
gimmda-member      (this repo)  ─┘
```

Members sign in with the account you create for them. Link a member's portal
account from the dashboard: **Members → (member) → Link portal account**.

---

## One thing to know before promising features

Announcements sent from the dashboard appear **inside this portal only**.
There is no email or SMS delivery. Do not tell members to "watch their email."
