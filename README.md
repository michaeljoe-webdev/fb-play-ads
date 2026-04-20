# Yumri POS — FB Ads Redirect Link

A clean redirect site that sends visitors to your Google Play Store listing.
Designed to pass Facebook Ads URL verification.

**Destination:** `https://play.google.com/store/apps/details?id=com.yumri.pos`

---

## Deploy to Netlify

1. Go to [netlify.com](https://netlify.com) → **Add new site → Deploy manually**
2. Drag and drop the **`public/`** folder into the Netlify drop zone
3. Your site will be live at `https://your-site-name.netlify.app`
4. (Optional) Add a custom domain in Site Settings → Domain Management

The `_redirects` file inside `public/` handles the server-side 301 redirect automatically.

---

## Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) → **Add New Project**
2. Import this folder (or push to GitHub first, then connect)
3. Set **Root Directory** to `public` in the project settings
4. Click Deploy

The `vercel.json` at the root handles the server-side redirect.

---

## Use in Facebook Ads

Once deployed, use your Netlify/Vercel URL as the **Website URL** in your ad:

```
https://your-site-name.netlify.app
```

Facebook's crawler will:
1. Visit your URL
2. Follow the 301 redirect to play.google.com
3. Verify the destination is a legitimate app store listing ✓
4. Approve your ad

---

## Why this works

- **Server-side 301** — FB follows it and sees Google Play directly
- **Open Graph meta tags** — FB reads `og:title`, `og:description` from your page
- **No third-party shorteners** — your own domain = trusted by FB
- **Canonical tag** — signals the real destination clearly
