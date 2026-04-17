# Circle PWA — Deploy Guide

## 🚀 Deploy in 3 minutes (Free, no account needed)

### Option 1 — Netlify Drop (Easiest, recommended)
1. Go to **https://app.netlify.com/drop**
2. Drag the entire `circle` folder onto the page
3. Done! You get a live URL like `https://random-name.netlify.app`
4. Share that URL with real users

### Option 2 — Netlify with custom domain
1. Sign up free at https://netlify.com
2. "New site from Git" or drag & drop the folder
3. Optionally add a custom domain (e.g. `circleapp.com`) in Settings → Domain

### Option 3 — Vercel
1. Go to https://vercel.com/new
2. Drag & drop folder or connect GitHub repo
3. Click Deploy

### Option 4 — GitHub Pages
1. Create a GitHub repo
2. Upload all 5 files to the repo root
3. Settings → Pages → Deploy from main branch
4. Live at `https://yourusername.github.io/circle`

---

## 📱 How users install it as an app

### On iPhone (Safari)
1. Open the URL in Safari
2. Tap the **Share** button (square with arrow)
3. Tap **"Add to Home Screen"**
4. Tap **"Add"**
5. Circle appears on home screen like a native app ✅

### On Android (Chrome)
1. Open the URL in Chrome
2. Tap the **three dots** menu → **"Add to Home Screen"**
3. Or Chrome shows an automatic banner — tap **"Install"**
4. Circle appears on home screen ✅

---

## 📁 Files included

| File | Purpose |
|---|---|
| `index.html` | The complete app — all screens, all flows |
| `manifest.json` | PWA config (app name, icon, colors) |
| `sw.js` | Service worker (offline support) |
| `icon.svg` | App icon |
| `README.md` | This file |

---

## ✅ What's working in this MVP

- **Onboarding** — 3 swipeable slides + skip
- **Signup / Login** — email + password (demo, localStorage)
- **Email verification** screen (simulated)
- **6-step profile setup:**
  - Name, DOB (scrollable picker), gender, GPS location
  - Photo upload (3–6 photos, append-only)
  - Height slider (cm / inches auto-convert)
  - Occupation + religion
  - Friend tags (exactly 3 from 20)
  - 6 personality questions
  - Dating preferences (private to matchmakers)
- **Home dashboard** — level/points, stats, my singles, activity
- **Intros tab** — Pending / Matches / Activity
- **Introduce flow** — single carousel → QR code → context note → sent
- **QR scan landing** — public page (no app needed), 3 actions
- **Chat** — real-time messages (simulated replies)
- **Profile page** — edit, matchmakers, level
- **Notifications center**
- **Settings** — edit, privacy, delete account (GDPR)
- **Gamification** — points, 6 levels, progress bar
- **PWA install** — add to home screen on iOS & Android
- **Offline support** — service worker caches app
- **Deep link routing** — `#scan/ID` opens QR landing directly

---

## 🔧 Next steps for production

To turn this MVP into a real product, you'll need:

1. **Backend** — Supabase (free tier) or Firebase
   - Real auth (email verification, password reset)
   - User profiles stored in database
   - Real-time chat (Supabase Realtime / Firebase)
   - QR codes that expire after 72 hours

2. **Push notifications** — Web Push API + VAPID keys

3. **Hosting** — Netlify or Vercel (both free for MVPs)

4. **Domain** — Namecheap ~$12/year

---

## 💡 Testing tips

- Use two different browsers (or incognito) to test both Single and Matchmaker flows
- The QR "Simulate scan" button lets you test the full intro flow without another device
- Data is saved in your browser's localStorage (clears when you clear browser data)
