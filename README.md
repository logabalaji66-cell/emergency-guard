# 🛡️ DisasterGuard — Bhuvan Satellite Emergency Navigator

A real-time, AI-powered disaster risk evaluation and evacuation system built as a single HTML file. No server required — works offline in any browser.

---

## 🚀 Features

- **6 Disaster Types** — Flood, Cyclone, Earthquake, Wildfire, Landslide, Tsunami
- **Live GPS Location** — Auto-detects your city and coordinates
- **Interactive Leaflet Map** — Real satellite tiles, live risk zones, evacuation routes
- **AI Recommendations** — Streaming advice via Claude (Anthropic API)
- **Household Vulnerability Profiles** — Elderly, Children, Pregnant women, Medical conditions, Mobility issues
- **Nearest Shelters & Hospitals** — Sorted by distance with one-click routing
- **High-Risk Zone Warning** — Automatic alert banner when risk score exceeds threshold
- **Evacuation Route Planning** — Recommended + alternate routes drawn on map
- **Tamil Nadu Location Database** — Pre-loaded hospitals and shelters across TN districts

---

## 📁 File Structure

```
DisasterGuard/
├── DisasterGuard_v6_AutoCity.html   # Main app (self-contained single file)
└── README.md
```

> Everything — HTML, CSS, JavaScript, map config, location data — is in one `.html` file. No build step, no dependencies to install.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Map | [Leaflet.js](https://leafletjs.com/) v1.9.4 |
| Tiles | OpenStreetMap |
| Fonts | Google Fonts (Rajdhani + Inter) |
| AI | Anthropic Claude API (streaming) |
| GPS | Browser Geolocation API |
| Routing | Custom Haversine distance + Leaflet Polyline |
| Storage | In-memory (no backend needed) |

---

## ⚙️ Setup & Usage

### Option 1 — Open directly (no AI features)
1. Download `DisasterGuard_v6_AutoCity.html`
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari)
3. GPS and map features work immediately

### Option 2 — With AI Recommendations
The AI streaming feature calls the Anthropic API directly from the browser.

> ⚠️ For production use, proxy this through a backend to protect your API key.

To enable AI in development:
1. Set up a CORS proxy or use the [Anthropic API](https://docs.anthropic.com) directly
2. The app calls `https://api.anthropic.com/v1/messages` with `claude-sonnet-4-20250514`

---

## 🗺️ How It Works

### 3-Step Flow
```
Step 1: Identity → Name, Mobile, Role
Step 2: Risk Data → Disaster type, Location, Zone, Sliders, Vulnerability
Step 3: Report   → Risk score, Live map, AI advice, Evacuation routes
```

### Risk Score Formula
```
Score = (ZoneRisk × 0.4) + ((100 - Distance) × 0.3) + (PopDensity × 0.2)
      + VulnerabilityPoints + ZoneTypeModifier
```

| Condition | Points |
|-----------|--------|
| Elderly (60+) | +10 |
| Children (<12) | +8 |
| Pregnant women | +10 |
| Medical conditions | +10 |
| Mobility issues | +12 |
| No vehicle | +10 |
| High-risk zone type | +8 |
| Medium-risk zone type | +4 |

**Thresholds:**
- `< 40` → LOW RISK
- `40–70` → MEDIUM RISK
- `> 70` → HIGH RISK (warning banner triggered)

---

## 📍 Supported Cities (Auto-Detect)

Chennai, Coimbatore, Madurai, Trichy, Salem, Tirunelveli, Vellore, Erode, Thoothukudi, Dindigul, Thanjavur, Cuddalore, Puducherry, Kanyakumari, Ooty, Kodaikanal, and more.

---

## 🔒 Privacy

- GPS coordinates are used only in-session and never stored
- No data is sent to any server (except the Anthropic API call for AI advice)
- All risk computation happens client-side

---

## 📸 Screenshots

> Add your own screenshots here after running the project.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first.

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Credits

- Map data © [OpenStreetMap](https://www.openstreetmap.org/) contributors
- Routing library: [Leaflet.js](https://leafletjs.com/)
- AI: [Anthropic Claude](https://www.anthropic.com/)
- Disaster data references: NDMA India, Tamil Nadu SDMA
