# 🌐 Global Environmental Risk Matrix (BERM v2.0) & HEAL-V3 Architecture

A decentralized, client-side health informatics prototype combining high-scale
geospatial epidemiology with interactive local primary care workflows. Built to
demonstrate zero-data frontend architectures, sandboxed public API integrations,
and edge browser-based hardware cryptography.

**Live Demo:** One Health BERM v2.0

---

## 1. Introduction

This repository contains an independent, solo-built health informatics platform
designed by a Senior UX Researcher and Health Systems Architect. Operating
entirely within a local browser sandbox, the system runs completely free of
backend server layers, central databases, or tracking liabilities.

As a professional portfolio demonstration and architectural exploration, it
showcases the feasibility of tracking complex biological vectors, parsing live
international indicator streams, and executing hardware-accelerated client-side
cryptography at the edge. It is explicitly **not** an officially deployed or
validated analytical instrument for any international agency or government
institution.

---

## 2. Risk Scoring Mathematics

### 2.1 The Core Equation

BERM v2.0 uses a single, standardized mathematical scoring function rather than
maintaining separate, hardcoded codebases for individual pathogens:

$$
R_{\text{dynamic}} = M_{\text{base}} + \sum_{i=1}^{n} \left( w_i \cdot \Delta_i \right)
$$

### 2.2 Why This Equation Works

The equation is deliberately additive rather than multiplicative, for three
reasons rooted in epidemiological practice:

- **Additive structure preserves interpretability.** Each environmental
  signal contributes an independent, auditable increment to the final risk
  index. Public-health officers can trace exactly how much a temperature
  anomaly versus a rainfall deviation contributed to the final score — an
  essential property for IHR 2005 reporting and legal defensibility.

- **Weighting separates signal from noise.** The coefficient $w_i$ is
  pre-calibrated from published literature, so an uninformative variable
  (e.g., a transit delay with $w_i = 0.05$) cannot dominate the index even
  if its raw value spikes. This mirrors the structure of composite indices
  used by WHO, FAO, and WOAH under the Joint Risk Assessment framework.

- **Baseline anchoring prevents false alarms.** Because $M_{\text{base}}$
  is fixed per region, a country with historically high endemic burden
  does not continuously flag as HIGH RISK. Only *deviations above baseline*
  move the score — the same logic behind CDC's epidemic threshold curves.

### 2.3 Variable Definitions

| Variable | Description | Range |
|---|---|---|
| $R_{\text{dynamic}}$ | Cumulative regional biosecurity threat index | 0.0 – 3.0+ |
| $M_{\text{base}}$ | Pre-calibrated regional baseline multiplier | 0.5 – 1.5 |
| $\Delta_i$ | Normalized dynamic input metric for variable $i$ | 0.0 – 1.0 |
| $w_i$ | Pathogen-specific weighting coefficient | 0.0 – 1.0 ($\sum w_i = 1.0$) |

### 2.4 Risk Classification Scale

| Risk Level | $R_{\text{dynamic}}$ Range | Recommended Action |
|---|---|---|
| 🔴 HIGH RISK | $\geq 1.9$ | Immediate intervention required |
| 🟡 MODERATE RISK | $1.3 - 1.9$ | Enhanced surveillance |
| 🟢 LOW RISK | $< 1.3$ | Standard monitoring |

### 2.5 Example Dynamic Inputs

Normalized environmental indicators used by the risk engine:

| Indicator | Value | Interpretation |
|---|---|---|
| $\Delta_{\text{temperature}}$ (Sea Surface Temp Anomaly) | 0.75 | Strong positive anomaly |
| $\Delta_{\text{rainfall}}$ (Deviation from historical average) | 0.60 | Moderate excess rainfall |
| $\Delta_{\text{transit}}$ (Global shipping disruption index) | 0.30 | Mild logistics disruption |

---

## 3. Weight Calibration Mechanics ($w_i$)

The weighting coefficients $w_i$ are pre-calibrated, static values derived from
established epidemiological methodologies. They are loaded from a configuration
file rather than computed in real time.

### 3.1 Three-Tier Calibration Framework

**Tier 1 — Multivariate Regression Modeling (empirical).**
Coefficients $\beta_i$ are drawn from adjusted odds ratios reported in
historical outbreak logs.

**Tier 2 — Reproductive Number Sensitivity (mathematical).**
For vector-borne pathogens, $w_i$ approximates the partial derivative of the
basic reproduction number with respect to each environmental variable:

$$
w_i \approx \frac{\partial R_0}{\partial \text{Variable}_i}
$$

**Tier 3 — Tripartite One Health Consensus (qualitative-to-quantitative).**
Standardized risk matrices from WHO JRA OT, FAO, and WOAH guidelines are mapped
directly onto $w_i$.

### 3.2 Multivariate Logistic Regression

For predicting outbreak probability, the log-odds of an outbreak are modeled as:

$$
\ln\left(\frac{P_{\text{outbreak}}}{1 - P_{\text{outbreak}}}\right)
= \beta_0 + \beta_1 \cdot \text{Temp} + \beta_2 \cdot \text{Rainfall}
+ \beta_3 \cdot \text{TransitDelay} + \dots
$$

where $\beta$ coefficients are derived from peer-reviewed outbreak literature.

---

## 4. Industry Applications

BERM v2.0 is designed for sectors where **offline resilience, data sovereignty,
and rapid local triage** matter more than centralized analytics.

### 4.1 Public Health & Epidemiology
- **Border health authorities** verifying incoming transit health matrices
  without logging passenger identity (IHR 2005 Article 23 compliance).
- **Rural clinics** in newly affected vector zones that lack real-time lab
  connectivity.
- **Outbreak investigation teams** requiring field-deployable risk scoring
  independent of cloud uptime.

### 4.2 Agriculture & Food Safety
- **Produce exporters** sealing harvest timestamps and water-safety indices
  into encrypted QR codes for border inspection (Case Study: *Cyclospora
  cayetanensis*).
- **Livestock movement tracking** aligned with WOAH terrestrial animal health
  codes.

### 4.3 Maritime & Coastal Management
- **Shellfish bed monitoring** for *Vibrio vulnificus* blooms driven by
  sea-surface temperature anomalies.
- **Port health officers** screening crews without centralized database
  dependencies.

### 4.4 Humanitarian & Disaster Response
- **Refugee transit hubs** generating and verifying encrypted health manifests
  at the runway edge.
- **NGO field teams** operating during infrastructure collapse (Case Study:
  Andes Orthohantavirus border diversions).

### 4.5 Aviation & Transit
- **Airline medical desks** performing pre-boarding risk stratification without
  retaining passenger data.

---

## 5. Why This Is a Public Health Tool for the Public

Most public-health software is built **for institutions** — ministries,
hospitals, and reference laboratories with IT departments. BERM v2.0 is built
**for the public**: individual clinicians, community health workers, students,
and citizens who need defensible risk information without surrendering personal
data to a central server.

Three design commitments make this possible:

1. **Zero-Data Storage Policy.** No SQL, no NoSQL, no backend logs, no
   tracking pixels, no user accounts. Every computation lives in volatile
   browser RAM and is destroyed on tab close.
2. **No API Keys, No Vendor Lock-In.** Live metrics are pulled directly from
   the WHO Global Health Observatory OData endpoint from the client's own IP
   address, with no middleware.
3. **Client-Side Cryptography.** All encrypted QR tokens use the browser's
   native `window.crypto.subtle` (PBKDF2 + AES-256-GCM), so verification
   happens entirely on the device — no certificate authority, no server round
   trip.

The result is a tool that any member of the public can run offline, on any
modern browser, without creating an account or trusting a third party with
their health context.

---

## 6. Pathogen Classification & Triage Matrices

BERM v2.0 maps multi-vector public health threats at the human-animal-environmental
interface (One Health). Below is the operational matrix of priority
transboundary pathogens monitored within the platform's localized edge-triage
architecture.

### 6.1 Zoonotic Viral Hemorrhagic Fevers (VHFs)

| Pathogen | Transmission Vectors | Spread Potential ($R_0$) | Clinical Triage Symptoms |
|---|---|---|---|
| Ebola Virus Disease (EBOV) | Fruit bats (*Pteropodidae*); direct contact with bodily fluids | 1.5 – 2.5 | Sudden fever, fatigue, myalgia; progression to vomiting, diarrhea, hemorrhage |
| Marburg Virus Disease (MARV) | *Rousettus aegyptiacus* fruit bats; human-to-human contact | 1.6 – 2.0 | Severe headache, high fever; progression to mucosal bleeding, shock |
| Lassa Fever | *Mastomys natalensis* mouse; nosocomial transmission | 1.0 – 1.6 | Gradual fever, weakness, sore throat; neurological symptoms incl. hearing loss |
| Crimean-Congo Hemorrhagic Fever (CCHF) | *Hyalomma* ticks; infected livestock tissue | Vector-density dependent | Sudden high fever, joint pain; uncontrolled bleeding |

### 6.2 Respiratory & Airspace Threats

| Pathogen | Transmission Vectors | Spread Potential ($R_0$) | Clinical Triage Symptoms |
|---|---|---|---|
| Highly Pathogenic Avian Influenza (H5N1, H7N9, H9N2) | Wild waterfowl, domestic poultry; inhalation | Variable (low sustained H2H) | High fever (>38°C), cough, dyspnea; rapid ARDS progression |
| MERS-CoV | Dromedary camels; close human contact | 0.3 – 0.8 | Fever, cough, shortness of breath; renal failure |
| Nipah Virus Encephalitis (NiV) | *Pteropus* bats; date palm sap; swine amplification | 0.4 – 0.6 | Acute respiratory infection; encephalitis, seizures, coma (40–75% CFR) |

### 6.3 Vector-Borne Climate Shift Pathogens

| Pathogen | Transmission Vectors | Spread Potential ($R_0$) | Clinical Triage Symptoms |
|---|---|---|---|
| Anaplasmosis (*Anaplasma phagocytophilum*) | *Ixodes scapularis*, *I. pacificus* ticks | Vector-density dependent | Fever, headache, myalgia; severe complications if delayed |
| Rift Valley Fever (RVF) | *Aedes*, *Culex* mosquitoes; livestock amplification | Vector-density dependent | Influenza-like fever; hemorrhagic syndrome in critical cases |
| Dengue, Chikungunya, Zika | *Aedes aegypti*, *Aedes albopictus* | Vector-density dependent | "Breakbone fever," rash; Zika causes congenital anomalies and GBS |

---

## 7. Data Sources & Resiliency

### 7.1 Live Ingested Metric

To verify the frontend's ability to fetch and parse external structures in real
time, an authentic indicator is drawn directly from the open public **Global
Health Observatory OData API**. The script invokes a native browser `fetch()`
request to target the country's most recent life expectancy at birth record
(index: `WHOSIS_000001`). This exchange is performed directly from the client's
IP address with **zero middleware or API keys required**.

### 7.2 System Accuracy & Fallback Resiliency

By decoupling data visualization from an application-specific backend server,
the platform achieves total operational uptime immunity against database
crashes, server drops, or host credential expiration. If an external API
endpoint goes offline, the application cleanly falls back to its internal
static layers without failing.

---

## 8. Client-Side Architecture & Zero-Data Storage Policy

The application enforces a strict, uncompromising **Zero-Data Storage Policy**.
Because it is written as a unified, static front-end file, it possesses no
physical mechanism to ingest or retain information outside of the current
terminal:

- **No Relational Storage Footprint.** No SQL or NoSQL databases, backend cloud
  logs, tracking pixels, or user state accounts.
- **Transient Memory Isolation.** All calculations, spatial interactions,
  chosen passphrases, and interface layer toggles exist purely inside the
  browser's temporary, volatile RAM.
- **Total Volatility.** The moment the operator reloads the page, navigates
  away, or exits the browser tab, the entire operational state machine is
  permanently deleted.

---

## 9. Encryption Pipeline & Scannable QR Codes

The system includes a hardware-accelerated symmetric cryptographic subsystem
operating within the browser kernel via `window.crypto.subtle`:

1. **Passphrase Key Derivation.** Input strings pass into a native PBKDF2
   primitive using SHA-256, performing 150,000 iterations over a 16-byte random
   salt (`crypto.getRandomValues()`) to generate a 256-bit symmetric key.
2. **Symmetric AES-GCM Encryption.** Calculated risk factors and timestamps
   convert to ciphertext via AES-256-GCM using a 12-byte initialization vector.
3. **Binary-to-Text Serialization.** Salt, IV, and ciphertext are compiled into
   Base64 string bundles.
4. **QR Matrix Transformation.** Base64 text converts directly into a vector
   graphic via `qrcode.js` for scanning by external field devices.

> **Security Note.** If a single bit of the scannable QR code is altered or a
> key mismatches, the Galois Message Authentication Code (GMAC) check fails
> natively, throwing an exception and completely blocking corrupted data access.

---

## 10. Global Compliance & Standards Alignment

| Framework | Alignment |
|---|---|
| **IHR 2005** (International Health Regulations) | Allows customs, border desks, and transit hubs to verify incoming transit health matrices without tracking, logging, or centralizing passenger identity markers. |
| **WHO–FAO–WOAH One Health** | Mechanically links human, animal, and environmental parameters into a single vector array ($\sum w_i \cdot \Delta_i$). |
| **WMO/UN "Early Warnings for All"** | Aligns with UN mandates for scalable Multi-Hazard Early Warning Systems (MHEWS) by providing open, vendor-neutral scoring logic on edge devices. |

---

## 11. Real-World Public Health Case Studies

### Case Study 1 — Anaplasmosis Tick-Borne Vector Shifts
**Challenge.** Regional clinics in newly affected rural zones often lack
real-time laboratory connections, resulting in diagnostic delays.

**How BERM v2.0 helps.** The app ingests local environmental metrics (humidity,
canopy coverage, winter minimum temperatures) into the dynamic risk calculation
engine. Rural healthcare workers generate encrypted QR tokens containing local
tick density indices for patient referral manifests.

### Case Study 2 — Agricultural Produce Traceability (*Cyclospora cayetanensis*)
**Challenge.** Perishable produce spoils at border terminals within hours, while
traditional PCR testing takes days. Exporters resist uploading farm coordinates
to central databases.

**How BERM v2.0 helps.** Growers compute water-safety indices locally in
browser RAM. The app seals harvest timestamp and water test metrics into
AES-256-GCM encrypted QR codes printed on cargo manifests. Customs inspectors
scan and decrypt locally offline.

### Case Study 3 — Marine Climate Pathogens (*Vibrio vulnificus*)
**Challenge.** Bacterial blooms occur rapidly following heatwaves, threatening
shellfish beds and coastal swimmers.

**How BERM v2.0 helps.** By feeding live sea-surface temperature and salinity
indices into $R_{\text{dynamic}}$, the platform flags high-risk marine
harvesting zones weeks before clinical cases emerge.

### Case Study 4 — Andes Orthohantavirus & Border Diversions
**Challenge.** During historical outbreaks where central database links or
airspace access failed, local teams needed offline operational tools.

**How BERM v2.0 helps.** By isolating static environmental vectors from live
cloud dependencies, BERM v2.0 allows transit hubs and emergency responders to
generate and verify encrypted health manifests at the runway edge without
relying on centralized server uptime.

---

## 12. Tech Stack

| Technology | Operational Assignment |
|---|---|
| HTML5 / CSS3 | Semantic layout wrapper |
| Tailwind CSS | Responsive UI assembly via CDN |
| Vanilla JavaScript | Asynchronous state engine orchestration |
| Leaflet.js 1.9.4 | Interactive canvas mapping |
| Esri Dark Gray Canvas | High-contrast spatial base tiles (keyless) |
| Font Awesome 6 | Standardized vector indicators |
| qrcode.js | Client-side text matrix encoding |
| Web Crypto API | Hardware-accelerated symmetric cryptographic primitives |
| WHO GHO OData API | Remote metrics data fetch endpoint |

---

## 13. Multidisciplinary Foundations

This software, design logic, and data tracking philosophy are established upon
a multi-domain academic foundation:

- Honours BA in Anthropology — McMaster University
- Bachelor of Arts in Psychology — McMaster University
- Pre-Health Sciences Certificate — Mohawk College

---

## 14. Academic References & Literature

- World Health Organization (WHO), FAO, & WOAH. *Joint Risk Assessment
  Operational Tool (JRA OT): A path to implementing a One Health approach to
  address zoonotic disease threats.*
- World Health Organization. *International Health Regulations (2005) — 3rd
  Edition.*
- United Nations Office for Disaster Risk Reduction (UNDRR) & WMO. *Global
  Status of Multi-Hazard Early Warning Systems (MHEWS).*
- Centers for Disease Control and Prevention (CDC). *Anaplasmosis Epidemiology,
  Vector Ecology, and Clinical Triage Guidelines.*

---

## 15. Proprietary Usage Notice

