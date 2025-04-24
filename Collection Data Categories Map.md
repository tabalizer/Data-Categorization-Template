# 🌐 **Collection Data Categories Map v1.3**

> **JSON Schema**: <https://example.org/schemas/collection-map-v1.3.schema.json>  
> **Legend**: **★ Mandatory** | ℹ️ Optional

---

## 📑 Changelog
| 🔖 Version | 📅 Updated | ✍️ Author | 🛠️ Purpose |
|:---------:|:---------:|:---------:|-----------|
| **1.3** | 2025‑04‑24 | [@tabalizer](https://twitter.com/tabalizer) | Master taxonomy for collecting, storing & exchanging entity‑relation data across investigations, compliance, threat‑intel & KYC workflows |

---

## ⚡ Quick‑Guide (60‑Second Reference)
| Category | Minimum Fields | Typical Source |
|----------|----------------|----------------|
| 👤 **Individual** | `ind_ID`★, `FullName`★, `Nationality`★ | Passport scan, PEP list |
| 🏢 **Organization** | `org_ID`★, `LegalName`★, `Jurisdiction`★ | OpenCorporates, SEC filing |
| 💰 **Asset** | `asset_ID`★, `CurrentOwnerID`★, `Location` | Customs manifest |
| 🏠 **Property** | `prop_ID`★, `Address`★, `OwnerID`★ | Land registry |
| 📅 **Event** | `event_ID`★, `DateTime`★, `InvolvedPartyIDs` | SIEM log, police report |

---

## 👤 Individuals
- **ind_ID**★  
- **FullName**★  
- **Aliases**ℹ️  
- **Nationality**★ (`Primary`, `Secondary`)  
- **BirthDate**ℹ️  
- **Biometrics**ℹ️ (`FingerprintHash`, `DNA_ID`)  
- **ResidentialAddress**ℹ️  
- **WorkplaceAddress**ℹ️  
- **Occupation**ℹ️  
- **RiskFactors**ℹ️ (`PEP`, `TerrorWatchlist`, …)  
- **FinancialStanding**ℹ️  
- **ContactChannels**ℹ️ (phone, email, Signal, Telegram, …)  
- **ComplianceTags**ℹ️ (`GDPR_Art9`, `Minor`, `HighProfile`)

---

## 🏢 Organizations
- **org_ID**★  
- **LegalName**★  
- **Jurisdiction**★ (ISO 3166‑2)  
- **LegalForm**ℹ️ (`Ltd`, `PLC`, `NPO`, …)  
- **RegisteredAddress**ℹ️  
- **ContactInfo**ℹ️  
- **KeyPersonnel**ℹ️  
- **UltimateBeneficialOwners**ℹ️ (`ind_ID` / `org_ID`)  
- **FinancialStatus**ℹ️  
- **ProductsAndServices**ℹ️  
- **ComplianceTags**ℹ️ (`PEP`, `Sanctioned`, `OFAC_list`)

### 🤝 Relations & Affiliations
- **Subsidiaries**ℹ️  
- **Stakeholders**ℹ️  
- **IndustryAssociations**ℹ️

### 🏗️ Infrastructure & Assets
- **Facilities**ℹ️  
- **Equipment**ℹ️

---

## 💰 Assets

### 🚗 Physical Assets
- **asset_ID**★  
- **Name**ℹ️  
- **Model**ℹ️  
- **Type**ℹ️ (`Vehicle`, `HighValueItem`, `ManufacturedGood`)  
- **CurrentOwnerID**★ (`ind_…` / `org_…`)  
- **PreviousOwnerIDs**ℹ️  
- **Location**ℹ️ (geoJSON)  
- **ComplianceTags**ℹ️ (`ExportControl`, `DualUse`, …)

### 💾 Digital Assets
- **asset_ID**★  
- **VirtualID**★ (hash / contract address)  
- **AssetType**ℹ️ (`NFT`, `Cryptowallet`, `DomainName`, …)  
- **StorageLocation**ℹ️ (URL / CID)  
- **CurrentOwnerID**★  
- **AccessPermissions**ℹ️  
- **ComplianceTags**ℹ️

---

## 🏠 Property
- **prop_ID**★  
- **Address**★ (street, city, country, postal code)  
- **GeoCoordinates**ℹ️ (lat, lon)  
- **OwnerID**★ (`ind_…` or `org_…`)  
- **PropertyType**ℹ️ (`Residential`, `Commercial`, `Industrial`, `Land`)  
- **Area**ℹ️ (m²)  
- **UsageDescription**ℹ️  
- **ComplianceTags**ℹ️ (`GDPR_Location`, `SanctionedRegion`)

---

## 📅 Events
- **event_ID**★  
- **Title**★  
- **DateTime**★ (ISO 8601, UTC)  
- **Duration**ℹ️  
- **Location**ℹ️ (`Physical`, `Digital`)  
- **InvolvedPartyIDs**★  
- **EventType**★ (`SecurityIncident`, `SafetyBreach`, `Transaction`, `Meeting`)  
- **Description**ℹ️  
- **Outcome**ℹ️  
- **ComplianceTags**ℹ️ (`GDPR_Breach`, `SAR_Required`)

---

## 🔗 Relations & Identifiers
Every entity carries a **prefixed primary key**:

| Entity | Prefix | Example |
|--------|:------:|---------|
| Individual | `ind_` | `ind_2f37c9` |
| Organization | `org_` | `org_a122d0` |
| Asset | `asset_` | `asset_b85e12` |
| Property | `prop_` | `prop_f93a1d` |
| Event | `event_` | `event_67ef30` |

Foreign‑keys reference these IDs to define relationships  
(e.g. `CurrentOwnerID → ind_ID / org_ID`).

---

## ⚖️ Compliance & Governance
Each record **should** include:

| Field | Purpose |
|-------|---------|
| **LegalBasis** | GDPR Art. 6 / CCPA / other justification |
| **SensitivityLevel** | `Public`, `Internal`, `Confidential`, `Restricted` |
| **RetentionPeriod** | `5y`, `7y`, `Indefinite`, … |
| **DataController** | Responsible legal entity |
| **CollectionMethod** | `Manual`, `API`, `OSINT`, `Sensor` |

---

## 📜 License
Content licensed under **Creative Commons BY 4.0**.  
You are free to share and adapt with attribution.

