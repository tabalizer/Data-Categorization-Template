# 🗂️ Collection Data Categories Map v.2.0 🚀
*A cheat-sheet for structuring intelligence inputs*

| 🔠 | **Reliability (Source)** | 🔢 | **Credibility (Info)** |
|---|--------------------------|---|------------------------|
| A | Always reliable          | 1 | Confirmed by direct observation |
| B | Usually reliable         | 2 | Verified by independent sources |
| C | Fairly reliable          | 3 | Logical / probable |
| D | Doubtful                 | 4 | Possible, unverified |
| E | Unreliable               | 5 | Improbable |
| F | Cannot be judged         | 6 | Contradictory / false |

> **Tip 🔧** Tag every record “`<Reliability><Credibility>`” (e.g. **B2**) at ingest to speed triage and analytic weighting.

---

## 🎯 Priority Flags
| Flag | Meaning | When to use |
|------|---------|-------------|
| 🔥 **HOT** | Immediate operational impact | Real-time threat, active target |
| ⏳ **TIM** | Time-sensitive | Opportunity window < 72 h |
| 🧊 **COLD** | Background | Strategic, no urgency |

---

## 🌐 Collection Pillars (10 core buckets)

### 1. 👤 Individuals
- **🆔 Identity** – name, aliases, biometric keys  
- **📍 Presence** – current & historic locations (lat/long, time-stamps)  
- **🎖️ Role & Rank** – official, community, covert  
- **📞 Comms** – phone, email, handles, crypto-IDs  
- **💰 Holdings** – bank refs, crypto wallets, high-value assets  
- **🤝 Networks** – associates, family, org ties (link-chart ready)  

### 2. 🏢 Organizations
- **🏷️ Identity** – legal name, branding, registration No.  
- **🏗️ Structure** – hierarchy, key leaders, subsidiaries  
- **📍 Footprint** – HQ & global sites (geo-JSON ready)  
- **💳 Financials** – accounts, revenue streams, sanctions risk  
- **🔗 External Links** – partners, suppliers, hostile peers  

### 3. 🏠 Properties & Sites
- **📍 Geo-loc** – address, coordinates, locality context  
- **📝 Specs** – area, construction, utilities, entry points  
- **🔒 Security** – access controls, CCTV, guards, alarms  
- **⛩️ Cover** – front companies, false signage, dual-use indicators  

### 4. 🏎️ Physical Assets
- **🚗 Vehicles / Equipment** – make, model, VIN/serial, condition  
- **💎 High-Value Items** – art, bullion, weapons, bespoke tech  
- **📦 Inventory Chains** – supplier → depot → field unit  

### 5. 💾 Digital Assets
- **🌐 Hosting** – domain, IP, cloud tenancy, country routing  
- **🔐 Access** – credential lists, MFA seeds, privileged roles  
- **📜 Audit Trails** – last login, data exfil events, ownership changes  

### 6. 💬 Communications
- **📞 Voice** – call detail records, IMSI/IMEI, push-to-talk IDs  
- **💻 Messaging** – Telegram, Signal, IRC, forums  
- **📧 Email** – headers, routing, PGP keys  
- **📻 RF/SAT** – frequency, modulation, TDoA fixes  

### 7. 🛰️ Geospatial & Movement
- **🌍 Imagery** – optical, SAR, IR, drone captures (sensor, pass-time)  
- **🚚 Mobility** – cell-tower pings, ADS-B, AIS, license-plate ALPR  
- **🛣️ Routes** – pattern-of-life, choke points, fallback sites  

### 8. 💳 Financial & Economic
- **🏦 Accounts** – IBAN, correspondent bank, balance snapshots  
- **🪙 Crypto** – addresses, mixers, NFT holdings, exchange KYC docs  
- **📈 Transactions** – amounts, counterparties, typologies (trade-based ML, hawala)  

### 9. 📅 Events & Incidents
- **🕒 When** – start, end, duration, time-zone  
- **🌍 Where** – geo-point, physical/digital domain  
- **❓ Why** – intent, ideology, profit, coercion  
- **⚙️ How** – TTPs, malware family, weapon system, protest tactics  
- **📊 Impact** – casualties, cost, reputational, legal  

### 10. 📢 Influence & Media
- **📰 Coverage** – headlines, outlets, sentiment score  
- **🤖 Social Bots** – bot-nets, amplification metrics, sock-puppets  
- **🎯 Target Audience** – demographic, language, grievances  

---

## 🧩 Cross-Cutting Metadata
| Field | Purpose |
|-------|---------|
| 🗂️ **Case/Op ID** | tie back to operation or requirement |
| 🔐 **Classification** | e.g. *SECRET//REL NORWAY-FVEY* |
| 🏷️ **Handling Caveats** | *ORCON*, *NOFORN*, *EYES+UK* |
| 🔄 **Chain of Custody** | hash values, collector, timestamp |
| ✍️ **Analyst Notes** | evaluation, gaps, next-step tasks |

---

## ⛔ Common Pitfalls / Risk Factors ⚠️
- **Over-collection 📈** – drowns analysts; define “nice-to-have” vs “need-to-have”.
- **Source bleed 🩸** – same HUMINT reused across reports → circular reporting.
- **Metadata leaks 🔓** – careless EXIF, share-links exposing targets.
- **Legal overstep ⚖️** – check domestic SIGINT & privacy statutes before tasking.

---

## 📖 ReadMe
| | |
|---|---|
| **✍️ Author** | [@tabalizer](https://twitter.com/tabalizer) |
| **📌 Usage** | Copy sections into your collection plan or MISP tags; adjust emojis as needed. |
| **📅 Version** | **v.2.0** *(24 Apr 2025)* |
| **🔄 Changelog** | Added priority flags, reliability/credibility matrix, comms & influence pillars, risk pitfalls. |
| **🆕 Updated** | 24.04.2025 |
| **📜 License** | [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

> **Balanced view ✅ / ⚠️**  
> The framework accelerates structured ingestion **but** can be mis-applied as a bureaucratic checkbox. Keep it **lean**—collect only what drives decisions, and revisit fields quarterly to cull dead weight.

---
