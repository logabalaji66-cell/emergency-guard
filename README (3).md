# 🛡️ DisasterGuard v7 — Emergency Navigator + SOS

> A Tamil Nadu disaster risk assessment and emergency navigation system with live GPS, satellite maps, AI advisor, and WhatsApp SOS.

![DisasterGuard Banner](https://img.shields.io/badge/DisasterGuard-v7-red?style=for-the-badge&logo=shield&logoColor=white)
![Tamil Nadu](https://img.shields.io/badge/Tamil%20Nadu-Emergency%20System-blue?style=for-the-badge)
![AI Powered](https://img.shields.io/badge/AI-Claude%20Sonnet-purple?style=for-the-badge)

---

## 🌟 Features

### 🗺️ Smart Location & Map
- **GPS-enabled**: If you grant location access, the map centers precisely on your GPS coordinates and Google Maps opens with your exact position as the starting point
- **City fallback**: If location is denied, simply select your city — the map and all nearby emergency locations auto-center on that city
- **Bhuvan Satellite Layer**: Uses ISRO's Bhuvan Resourcesat-1/2 LISS III Ortho satellite imagery (with OpenStreetMap fallback)
- **Real road routing**: OSRM-powered road-aligned blue routes to hospitals and shelters

### 🆘 Emergency SOS Button (Center floating button)
- **Always visible** red pulsing SOS button centered at the bottom of the screen
- Tap **SOS** → preview shows your exact GPS coordinates (or city fallback)
- One tap sends a **WhatsApp message** to the emergency contact with:
  - Your name and phone number
  - GPS coordinates + clickable Google Maps link
  - Disaster type context
  - Tamil Nadu emergency numbers (112, 108, 1913)
- **✕ dismiss button** on the corner of SOS: if it's NOT an emergency, tap ✕ to open the AI Decision Maker instead

### 🤖 AI Decision Making System
- Accessible via the ✕ dismiss on the SOS button
- Ask any disaster preparedness or emergency question
- Powered by Claude AI with Tamil Nadu context (your city, disaster type)
- Includes relevant emergency numbers in every response
- Works as a real-time advisory system even without an active emergency

### 📊 4-Step Risk Assessment
1. **Identity** — Name, mobile, city (auto-filled from GPS)
2. **Risk Factors** — Disaster type, zone details, vulnerability assessment
3. **Results** — Risk score (0–100), AI-generated action plan
4. **Emergency Map** — Hospitals and shelters with blue road routes

### 📍 Tamil Nadu Emergency Database
- 20 major government hospitals across Tamil Nadu
- 15 relief camps and safe shelters
- Coverage: Chennai, Coimbatore, Madurai, Trichy, Vellore, Salem, Tirunelveli, Thanjavur, Erode, Cuddalore, Pondicherry, Nagapattinam, Kanyakumari, and more

---

## 🚀 Getting Started

### Option 1: Open directly in browser
```bash
# Just open index.html in any modern browser
open index.html
```

### Option 2: Serve locally
```bash
# Using Python
python3 -m http.server 8080

# Using Node.js
npx serve .

# Then open http://localhost:8080
```

### Option 3: Deploy to GitHub Pages
1. Fork this repository
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your app will be live at `https://yourusername.github.io/disasterguard/`

---

## 📱 How to Use

### Normal Flow
1. Open `index.html` in your browser
2. **Allow location** when prompted (or enter your city manually)
3. Fill in your name, mobile number, and city → **Next**
4. Select disaster type, adjust risk sliders, mark vulnerable members → **Calculate Risk**
5. View your risk score and AI-generated safety steps
6. Tap **Open Emergency Map** to find nearest hospitals/shelters with routes

### Emergency SOS
1. Tap the **red SOS button** (always visible at the bottom center)
2. Your location is shown in the preview
3. Tap **Send via WhatsApp NOW** → WhatsApp opens with the pre-filled SOS message
4. Send it to alert your emergency contact

### AI Decision Maker (Non-Emergency)
1. Tap the **✕** on the corner of the SOS button
2. Type your question (e.g. "What to do during a cyclone warning?")
3. Get AI-powered advice tailored to Tamil Nadu

---

## 🏗️ Technical Stack

| Component | Technology |
|-----------|-----------|
| Map | Leaflet.js + Bhuvan WMS (ISRO) |
| Routing | OSRM (road-aligned) + Bezier fallback |
| Satellite | Resourcesat-1/2 LISS III via Bhuvan WMS |
| AI | Claude Sonnet (Anthropic API) |
| Geocoding | Nominatim (OpenStreetMap) |
| SOS | WhatsApp deep link (`wa.me`) |
| Framework | Vanilla HTML/CSS/JS (zero dependencies except Leaflet) |

---

## 📞 Emergency Numbers (Tamil Nadu)

| Service | Number |
|---------|--------|
| 🚨 Police / Universal Emergency | **112** |
| 🚑 Ambulance | **108** |
| 🔥 Fire | **101** |
| 🌊 Disaster Helpline | **1913** |
| 🏥 TNSDMA | [tnsdma.tn.gov.in](https://tnsdma.tn.gov.in) |

---

## 🔧 Configuration

### Change the SOS WhatsApp number
In `index.html`, find this line and update the number (with country code, no `+`):
```javascript
const SOS_WHATSAPP_NUMBER = '918637698767'; // 91 = India code
```

### Add more cities or locations
Find the `TN_LOCATIONS` array in the script section to add hospitals/shelters, and `CITY_COORDS` to add new city coordinates.

---

## 📸 Screenshots

> Step 1: Identity & Location Detection  
> Step 2: Risk Factor Assessment  
> Step 3: Risk Score & AI Recommendations  
> Step 4: Emergency Map with Blue Road Routes  
> SOS Button: Pulsing emergency button with WhatsApp integration  
> AI Advisor: Instant disaster decision support  

---

## 🤝 Contributing

Pull requests welcome! Ideas for improvement:
- Add more cities beyond Tamil Nadu
- Integrate NDMA real-time alert feeds
- Offline PWA support (service workers)
- Multi-language support (Tamil / Telugu)

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 👨‍💻 Built With

- 🛰️ [Bhuvan / NRSC](https://bhuvan.nrsc.gov.in) — Indian satellite imagery
- 🗺️ [Leaflet.js](https://leafletjs.com) — Interactive maps
- 🤖 [Anthropic Claude](https://anthropic.com) — AI disaster advisor
- 🏗️ [OSRM](https://project-osrm.org) — Open Source Routing Machine

---

*DisasterGuard — Protecting Tamil Nadu, one alert at a time. 🛡️*
