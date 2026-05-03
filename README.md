# My Tasks — Deployment Guide

A personal todo app with deadlines, reminders, and spillover tracking.
Syncs across all your devices. 100% free.

---

## Step 1 — Set up Supabase (database + auth)

1. Go to https://supabase.com and click **Start for free**
2. Create a new project (choose any name, e.g. "my-tasks")
3. Wait ~2 minutes for it to provision
4. Go to **SQL Editor** → **New query**
5. Paste the contents of `supabase-setup.sql` and click **Run**
6. Go to **Project Settings** → **API**
7. Copy:
   - **Project URL** (looks like `https://xxxx.supabase.co`)
   - **anon public** key (long string under "Project API keys")

---

## Step 2 — Add your Supabase credentials to the app

Open `index.html` and find these two lines near the top of the `<script>` tag:

```js
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
```

Replace the placeholder values with your actual URL and anon key.

---

## Step 3 — Deploy to Vercel (free hosting)

1. Go to https://github.com and create a new **public** repository (e.g. "my-tasks")
2. Upload `index.html` to the repository (drag & drop works fine)
3. Go to https://vercel.com and click **Sign up** (use your GitHub account)
4. Click **Add New → Project**
5. Import your GitHub repo
6. Click **Deploy** — no configuration needed

Vercel will give you a URL like `https://my-tasks-abc123.vercel.app`

**Bookmark that URL** — open it on any device, sign in, and your tasks sync instantly.

---

## Optional: Custom domain

In Vercel → your project → **Settings → Domains**, you can add a free custom subdomain or connect your own domain.

---

## Features

- Sign up / sign in with email & password
- Add tasks with deadline, priority (high/med/low), and category
- Tasks grouped by: Overdue, Due today, Due soon, Upcoming, No deadline
- **Spillover detection** — tasks created on one day that are now overdue on a later day
- Stats bar: active, due today, overdue, spillovers
- Browser push notifications (1 hour before, 15 min before, at deadline)
- Real-time sync — add on your phone, see it instantly on your laptop
- Dark mode supported automatically

---

## Free tier limits (more than enough for personal use)

| Service | Free tier |
|---------|-----------|
| Supabase | 500 MB database, 50,000 monthly active users |
| Vercel | Unlimited deploys, 100 GB bandwidth/month |
