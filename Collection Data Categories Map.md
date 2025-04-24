# 🗂️ **Collection Data Categories Map v1.3**

| 🔖 **Version** | 📅 **Updated** | ✍️ **Author** | 🛠 **Usage** |
|---------------|---------------|---------------|-------------|
| 1.3 | 2025-04-24 | [@tabalizer](https://twitter.com/tabalizer) | Master taxonomy for collecting, storing & exchanging entity-relation data across investigations, compliance, threat-intel and KYC workflows.|

> **JSON-Schema:** `https://example.org/schemas/collection-map-v1.3.schema.json`  
> **Legend:** **\*** = Mandatory 🛈 = Optional

---

## ⚡ Quick-Guide (60-Second Reference)

| Category | Minimum Fields (⭐) | Typical Source |
|----------|--------------------|----------------|
| 👤 **Individual** | `ind_ID*`, `FullName*`, `Nationality*` | Passport scan, PEP list |
| 🏢 **Organization** | `org_ID*`, `LegalName*`, `Jurisdiction*` | OpenCorporates, SEC filing |
| 💰 **Asset** | `asset_ID*`, `CurrentOwner*`, `Location` | Customs manifest |
| 🏠 **Property** | `prop_ID*`, `Address*`, `OwnerID*` | Land registry |
| 📅 **Event** | `event_ID*`, `DateTime*`, `Parties` | SIEM log, police report |

---

## 🔗 **Relations & Identifiers**

Every entity carries a **prefixed primary key**:

| Entity | Prefix | Example |
|--------|--------|---------|
| Individual | `ind_` | `ind_2f37c9` |
| Organization | `org_` | `org_a122d0` |
| Asset | `asset_` | `asset_b85e12` |
| Property | `prop_` | `prop_f93a1d` |
| Event | `event_` | `event_67ef30` |

Foreign-keys reference these IDs to define relationships (e.g. `CurrentOwnerID → ind_ID / org_ID`).

---

## 💰 **Assets**

### 🚗 Physical Assets
- **asset_ID\***  
- **Name🛈**  
- **Model🛈**  
- **Type🛈** (`Vehicle`, `HighValueItem`, `ManufacturedGood`)  
- **CurrentOwnerID\*** (`ind_` / `org_`)  
- **PreviousOwnerIDs🛈** (array)  
- **Location** (geoJSON)  
- **ComplianceTags🛈** (`ExportControl`, `DualUse`, etc.)

### 💾 Digital Assets
- **asset_ID\***  
- **VirtualID\*** (hash / contract address)  
- **AssetType** (`NFT`, `Cryptowallet`, `DomainName` …)  
- **StorageLocation🛈** (URL / CID)  
- **CurrentOwnerID\***  
- **AccessPermissions🛈** (ACL list)  
- **ComplianceTags🛈**

---

## 🏠 **Property**

- **prop_ID\***  
- **Address\*** (street, city, country, postal code)  
- **GeoCoordinates🛈** (lat, lon)  
- **OwnerID\*** (`ind_` or `org_`)  
- **PropertyType🛈** (`Residential`, `Commercial`, `Industrial`, `Land`)  
- **Area🛈** (m²)  
- **UsageDescription🛈**  
- **ComplianceTags🛈** (`GDPR_Location`, `SanctionedRegion`)

---

## 🏢 **Organizations**

- **org_ID\***  
- **LegalName\***  
- **Jurisdiction\*** (ISO 3166-2)  
- **LegalForm🛈** (`Ltd`, `PLC`, `NPO` …)  
- **RegisteredAddress🛈**  
- **ContactInfo🛈** (phone, email, URL)  
- **KeyPersonnel🛈** (array of `ind_ID`)  
- **UltimateBeneficialOwners🛈** (`ind_ID` / `org_ID`)  
- **FinancialStatus🛈** (balance, credit score)  
- **ProductsAndServices🛈**  
- **ComplianceTags🛈** (`PEP`, `Sanctioned`, `OFAC_list`)

### 🤝 Relations & Affiliations
- **Subsidiaries🛈** (`org_ID[]`)  
- **Stakeholders🛈** (`ind_ID[]` / `org_ID[]`)  
- **IndustryAssociations🛈**

### 🏗️ Infrastructure & Assets
- **Facilities🛈** (`prop_ID[]`)  
- **Equipment🛈** (`asset_ID[]`)

---

## 👤 **Individuals**

- **ind_ID\***  
- **FullName\***  
- **Aliases🛈**  
- **Nationality\*** (`Primary`, `Secondary`)  
- **BirthDate🛈**  
- **Biometrics🛈** (`FingerprintHash`, `DNA_ID`)  
- **ResidentialAddress🛈**  
- **WorkplaceAddress🛈**  
- **Occupation🛈**  
- **RiskFactors🛈** (`PEP`, `TerrorWatchlist` …)  
- **FinancialStanding🛈**  
- **ContactChannels🛈** (phone, email, Signal, Telegram …)  
- **ComplianceTags🛈** (`GDPR_Art9`, `Minor`, `HighProfile`)

---

## 📅 **Events**

- **event_ID\***  
- **Title\***  
- **DateTime\*** (ISO 8601, UTC)  
- **Duration🛈**  
- **Location🛈** (`Physical`, `Digital`)  
- **InvolvedPartyIDs\*** (`ind_ID[]`, `org_ID[]`, `asset_ID[]`, `prop_ID[]`)  
- **EventType\*** (`SecurityIncident`, `SafetyBreach`, `Transaction`, `Meeting`)  
- **Description🛈**  
- **Outcome🛈**  
- **ComplianceTags🛈** (`GDPR_Breach`, `SAR_Required`)

---

## ⚖️ **Compliance & Governance**

Each record SHOULD include:

| Field | Purpose |
|-------|---------|
| **LegalBasis** | GDPR Art. 6 / CCPA / other justification |
| **SensitivityLevel** | `Public`, `Internal`, `Confidential`, `Restricted` |
| **RetentionPeriod** | e.g. `5y`, `7y`, `Indefinite` |
| **DataController** | Responsible legal entity |
| **CollectionMethod** | `Manual`, `API`, `OSINT`, `Sensor` |

---

## 📜 **License**

Content licensed under [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt with attribution.
