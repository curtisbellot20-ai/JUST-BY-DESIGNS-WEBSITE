# Just By Design LLC — Website Project

South Florida's premier luxury event draping & trussing company.

---

## Project Structure

```
just-by-design-project/
│
├── index.html                  # Main website
├── pamphlet.html               # Luxury event guide (popup download)
│
├── assets/
│   ├── audio/
│   │   ├── Draped_Elegance.mp3         ✅ Ready
│   │   └── ELEGANCIA_ENVOLVIDA.mp3     ⬅ Add this file here
│   ├── images/                         # Add custom photos here
│   └── video/                          # Add custom videos here
│
└── docs/
    └── README.md               # This file
```

---

## Running Locally

No build step needed. Just serve the files with any static server:

```bash
# Option 1 — Python (built-in)
python3 -m http.server 3000

# Option 2 — Node
npx serve .

# Option 3 — Claude Code live preview
# Open index.html directly in Claude Code
```

Then open: `http://localhost:3000`

---

## Files Explained

| File | Purpose |
|------|-------|
| `index.html` | Full animated website with nav, hero slideshow, services, gallery, areas, about, reviews, CTA, contact form, pamphlet popup, music player, draping canvas |
| `pamphlet.html` | Standalone luxury pamphlet — linked from popup after form submit |
| `assets/audio/Draped_Elegance.mp3` | Ambient background music track 1 |
| `assets/audio/ELEGANCIA_ENVOLVIDA.mp3` | Ambient background music track 2 *(upload needed)* |

---

## What's Still Needed

### 1. Second Music Track
Upload `ELEGANCIA_ENVOLVIDA.mp3` to `assets/audio/`

### 2. Lead Capture Backend
The popup form currently captures leads on screen only. To send leads somewhere, choose one:

**Option A — Formspree (free, instant email)**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a form → get your endpoint URL
3. In `index.html`, find `id="pp-form"` and add:
   ```html
   <form id="pp-form" action="https://formspree.io/f/YOUR_ID" method="POST">
   ```
4. Every submission emails the owner instantly

**Option B — GoHighLevel / Archkey CRM (recommended)**
1. In GoHighLevel, create a webhook under Automations
2. Copy the webhook URL
3. In `index.html`, find the form submit handler and add:
   ```js
   fetch('YOUR_WEBHOOK_URL', {
     method: 'POST',
     headers: {'Content-Type': 'application/json'},
     body: JSON.stringify({ name, email, birthday, anniversary, eventType })
   });
   ```
4. Leads flow directly into the CRM pipeline

**Option C — Netlify Forms (free dashboard)**
1. Deploy to [netlify.com](https://netlify.com) (drag & drop the folder)
2. Add `netlify` attribute to the form tag:
   ```html
   <form id="pp-form" netlify name="pamphlet-leads">
   ```
3. View all leads in the Netlify dashboard

### 3. Geo-Mapping Section
Google Maps API key needed. Get one at [console.cloud.google.com](https://console.cloud.google.com) (enable Maps JavaScript API), then provide:
- Your API key
- List of past event locations (venue name, city, event type, photo)

### 4. AI Chatbot
Claude-powered chatbot to capture inquiry details. Ready to build — just confirm the preferred backend for storing conversations.

### 5. Google Maps API Key
For the event location map section. Restrict to your domain for security.

---

## Deployment

### Netlify (Recommended — Free)
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the entire `just-by-design-project` folder
3. Site goes live instantly with a free URL
4. Connect your custom domain in settings

### Other Hosts
Any static host works — Vercel, GitHub Pages, Cloudflare Pages, or any traditional web host. Just upload all files maintaining the folder structure.

---

## Contact Info (in the site)
- **Phone:** (954) 839-7173
- **Website:** justbydesigns.com
- **Facebook:** facebook.com/Justbydesignllc
- **Instagram:** @justbydesigns
- **Hours:** Open 24 Hours

---

## SEO Coverage
The site is optimized for:
- Broward County event draping
- Miami-Dade County event draping
- Palm Beach County event draping
- Fort Lauderdale, Hollywood, Pembroke Pines, Miramar, Coral Springs
- Miami, Coral Gables, Hialeah, Aventura, Boca Raton, West Palm Beach
- Keywords: luxury event draping, custom drapery, wedding draping, structural trussing, event lighting

---

*Built with Claude — Anthropic*
