# नेपाली पञ्चाङ्ग पात्रो · Nepali Moon-Focused Calendar

A single-file, zero-build **Nepali lunar calendar (पात्रो)** web app — with a live panchang engine, a mini **nakshatra wheel**, and sidereal **graha positions**. Open `Nepali_Calender.html` in any browser and it just works (fonts and BS-date library load from CDN).

## ✨ Features

- **आजको पञ्चाङ्ग** — live tithi, nakshatra, yoga, karana, वार with progress bars and `हिजो / भोलि` day markers on midnight-crossing ranges (tithis last ≈20–27 h, so a bare `HH:MM – HH:MM` range always gets day context plus its total duration).
- **मिति खोज्नुहोस् (date jump)** — pick any date (AD 1913–2034 = BS 1970–2090) in the calendar header; the grid navigates there and the full detail popup opens — past or future.
- **WCAG AA contrast** — label/accent/festival colors verified ≥4.5:1 against their surfaces in both themes.
- **नक्षत्र चक्र** — mini wheel in every day popup: 12 rashi ring, 27 nakshatra sectors, 108 pada ticks; Sun & Moon markers sit at their sidereal longitudes, so the arc between them *is* the tithi.
- **नक्षत्र विवरण** — nakshatra पाद (1–4), नामाक्षर, स्वामी, देवता per day.
- **ग्रह स्थिति** — sidereal longitudes of सूर्य…शनि + राहु/केतु with वक्री (retrograde) flags, anchored to the day's sunrise.
- **चन्द्र कला** — realistic moon rendering, illumination %, age, distance (near-apogee slow-moon days produce the longest possible tithis — now displayed honestly).
- **नेपाल सम्बत** — amanta lunar month/day derived from the lunation (कछला…कौला).
- **चाडपर्व** — festival database anchored to lunar months and tithis (सूर्योदय-anchored by default; छठ by sunset tithi, महाशिवरात्रि by midnight).
- Living sky background (day/night gradient, stars, sun & moon paths), auto dark/light theme, fully mobile-friendly.

## 🔭 How it's computed

- **Sun & Moon** — Meeus-based engine (ELP-2000 truncated terms + nutation) with **Lahiri (Chitrapaksha) ayanamsa**; tithi = 12° of Moon–Sun elongation, anchored to each day's **sunrise**.
- **Planets** — `astronomy-engine` (same library as the Nakshatra Wheel project); राहु/केतु via the Meeus mean-node polynomial. Loaded lazily from CDN; hides gracefully if offline.
- **BS ⇄ AD dates** — `bikram-sambat` npm library (CDN).
- Boundary instants (tithi/nakshatra/yoga/karana start–end) were cross-verified against `astronomy-engine` to within **±1 minute**; graha positions agree to the arcminute.

## 🚀 Run

- Locally: double-click `Nepali_Calender.html`, or `npx serve .` and open the URL.
- Vercel: import this repo → deploy (no build settings needed; `vercel.json` rewrites `/` to the app).

## 🙏 Credits

- Nakshatra metadata (lords, deities, pada name-syllables) ported from the **Nakshatra Wheel** project (`vedic astrology`).
- [astronomy-engine](https://github.com/cosinekitty/astronomy-engine), the `bikram-sambat` npm package, Google Fonts (Tiro Devanagari Sanskrit, Mukta).

*चाडपर्व मितिहरू अनुमानित हुन् — आधिकारिक पात्रोसँग रुजू गर्नुहोस्।*
