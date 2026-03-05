# 📍 NeedFinder

> **Find What You Need. Right Now.**

NeedFinder helps people find things they desperately need right now: bathrooms, baby changing stations, quiet spaces, dog-friendly spots, and overnight parking for van lifers.

**Tagline:** "Find what you need. Right now."

---

## 🌐 Live URLs

- **Landing Page:** https://bummerland17.github.io/needfinder/
- **Web App:** https://bummerland17.github.io/needfinder/app/

---

## 📦 Modules

| Module | Icon | What it finds |
|--------|------|---------------|
| Bathroom | 🚽 | Public restrooms near you |
| Changing Table | 👶 | Baby changing stations |
| Quiet Space | 🤫 | Meditation rooms, prayer rooms |
| Dog-Friendly | 🐕 | Parks and cafes that welcome dogs |
| Overnight Parking | 🚐 | RV spots, truck stops, overnight lots |

---

## 🏗️ Architecture

### Landing Page (`/index.html`)
- Pure HTML/CSS — no frameworks
- Dark modern design, mobile-first
- Email capture via [FormSubmit.co](https://formsubmit.co) → `hello@pantrymate.net`
- "Launching Spring 2026" badge
- Mock map preview
- CTA to the web app

### Web App (`/app/index.html`)
- **Map:** [Leaflet.js](https://leafletjs.com/) with CartoDB dark tiles (free, no API key)
- **Location data:** Google Maps JavaScript API with Places library
- **API key:** `AIzaSyAuBYyoyqOvNalVNrnff1giboFsG_tXGfI`
- Geolocation API for user position
- Results shown as pins on map + scrollable bottom panel
- One-tap Google Maps directions link

---

## ⚠️ API Notes

### What Works Now
- ✅ Leaflet map (free, no key needed)
- ✅ Browser geolocation
- ✅ Landing page email capture (FormSubmit.co)
- ✅ Full app UI/UX

### What Needs Verification
- ⚠️ **Google Places API** — The key `AIzaSyAuBYyoyqOvNalVNrnff1giboFsG_tXGfI` must have:
  1. **Maps JavaScript API** enabled
  2. **Places API** enabled
  3. HTTP referrer restriction set to `bummerland17.github.io/*` (or unrestricted for testing)
  
  The app uses `google.maps.places.PlacesService` (JavaScript SDK) which is the correct browser approach — avoids CORS issues with the REST endpoint.

### CORS Note
The REST endpoint `maps.googleapis.com/maps/api/place/nearbysearch/json` does NOT work from browsers due to CORS. The app uses the JavaScript API instead (`libraries=places`), which is the standard approach for browser-based apps.

---

## 💳 Stripe

- **Product:** NeedFinder Pro
- **Price:** $2.99/month recurring
- **Payment Link:** https://buy.stripe.com/6oU6oGbFidsg1fN9BGbsc0b

---

## 🚀 Deployment

Files are deployed to GitHub Pages from the `main` branch root:
- `/index.html` → landing page
- `/app/index.html` → web app

---

## 📁 File Structure

```
needfinder/
├── index.html        # Landing page
├── app/
│   └── index.html    # Web app (map + search)
└── README.md
```

---

## 🗺️ Roadmap

- [ ] Community spot submissions (Google Form → manual review)
- [ ] User ratings & photos
- [ ] Offline-first caching (Service Worker)
- [ ] iOS/Android native apps
- [ ] NeedFinder Pro: saved spots, offline maps, no ads
- [ ] Moderator tools for community data

---

*Made for people who really, really need to go right now. 🚽*
