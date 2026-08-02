# 🌐 Global Environmental Risk Matrix (BERM v2.0) & HEAL-V3 Architecture

A decentralized, client-side health informatics prototype combining high-scale geospatial epidemiology with interactive local primary care workflows. Built to demonstrate zero-data frontend architectures, sandboxed public API integrations, and edge browser-based hardware cryptography.

---

## 1. Introduction
This repository contains an independent, solo-built health informatics platform designed by a Senior UX Researcher and Health Systems Architect. Operating entirely within a local browser sandbox, the system runs completely free of backend server layers, central databases, or tracking liabilities. 

As a professional portfolio demonstration and architectural exploration, it showcases the feasibility of tracking complex biological vectors, parsing live international indicator streams, and executing hardware-accelerated client-side cryptography at the edge. It is explicitly not an officially deployed or validated analytical instrument for any international agency or government institution.

---

## 2. Risk Scoring Math & Threat Indicators

To maintain architectural scalability across emerging threats, BERM v2.0 uses a single, standardized mathematical scoring function rather than maintaining separate, hardcoded codebases for individual pathogens:

$$R_{dynamic} = M_{base} + \sum_{i=1}^{n} \left( w_i \cdot \Delta_{\text{layer}, i} \right)$$

Where:
* **$R_{dynamic}$**: Cumulative regional biosecurity threat index computed locally in volatile client RAM.
* **$M_{base}$**: Pre-calibrated regional baseline multiplier representing historical zoonotic and ecological disease burdens.
* **$\Delta_{\text{layer}, i}$**: Dynamic input metric for environmental, logistics, or clinical variables ($0.0 \le \Delta \le 1.0$).
* **$w_i$**: Pathogen-specific **weighting coefficient** calibrated to the biological sensitivity of the target pathogen.

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                    UNIVERSAL DYNAMIC RISK PIPELINE                      │
├─────────────────────────────────────────────────────────────────────────┤
│  STATIC BASELINE DATA         DYNAMIC LIVE STREAM           LOGIC       │
│ ┌──────────────────────┐    ┌─────────────────────┐    ┌──────────────┐ │
│ │ Population Density   │    │ Sea Temp / Rainfall │    │              │ │
│ │ Healthcare Capacity  │ ──►│ Transit Delays      │ ──►│ Risk Scoring │ │
│ │ Historical Outbreaks │    │ Real-time Vectors   │    │ Engine       │ │
│ └──────────────────────┘    └─────────────────────┘    └──────────────┘ │
└─────────────────────────────────────────────────────────────────────────┘
Demonstration Layer Vector Coefficients:$\Delta_{viper}$ (Arid/Desert Venoms & Toxinology Shifts) = $+0.15$$\Delta_{marine}$ (Marine Neurotoxins & Coastal Microalgae) = $+0.12$$\Delta_{fungal}$ (Antimicrobial Resistant Fungi clusters) = $+0.22$$\Delta_{synthetic}$ (Advanced Biosecurity Surveillance Flags) = $+0.35$The system dynamically sums these values and projects them onto an absolute risk classification scale:🔴 HIGH RISK: $R_{dynamic} \ge 1.9$🟡 MODERATE RISK: $1.3 \le R_{dynamic} < 1.9$🟢 LOW RISK: $R_{dynamic} < 1.3$Pathogen Weight Calibration Mechanics ($w_1, w_2, w_3$)The weighting coefficients ($w_i$) represent a pathogen's specific biological sensitivity to environmental, climatic, and supply-chain drivers. The engine ingests calibrated weight profiles derived from three established epidemiological methodologies:Plaintext┌─────────────────────────────────────────────────────────────────────────────┐
│                 THREE-TIER WEIGHT CALIBRATION FRAMEWORK                     │
├─────────────────────────────────────────────────────────────────────────────┤
│  1. MULTIVARIATE REGRESSION MODELING (Data-Driven / Empirical)              │
│     w_i = Adjusted Odds Ratios / Beta Coefficients (β) from historical logs │
│                                                                             │
│  2. REPRODUCTIVE NUMBER SENSITIVITY (Mathematical / Epidemiology)           │
│     w_i = ∂R0 / ∂(Variable_i)  [Partial derivative of R0 transmission]      │
│                                                                             │
│  3. TRIPARTITE ONE HEALTH CONSENSUS (Qualitative-to-Quantitative)           │
│     w_i = Standardized risk matrices (WHO JRA OT / FAO / WOAH guidelines)   │
└─────────────────────────────────────────────────────────────────────────────┘
Empirical Multivariate Regression: Coefficients ($w_i$) correspond directly to the adjusted odds ratios ($\beta$) established in peer-reviewed outbreak literature:$$\ln\left(\frac{P_{\text{outbreak}}}{1 - P_{\text{outbreak}}}\right) = \beta_0 + w_1(\text{Temp}) + w_2(\text{Rainfall}) + w_3(\text{Transit Delay})$$Dynamic $R_0$ Sensitivity Analysis: For vector-borne pathogens, $w_i$ represents the partial derivative of the Basic Reproduction Number ($R_0$) with respect to environmental variables ($w_i = \frac{\partial R_0}{\partial (\text{Variable}_i)}$).Tripartite One Health Consensus Mapping: Accepts qualitative-to-quantitative risk weight matrices mapped directly from the WHO Joint Risk Assessment Operational Tool (JRA OT).🦠 Comprehensive Pathogen Classification & Triage MatricesBERM v2.0 maps multi-vector public health threats at the human-animal-environmental interface (One Health). Below is the operational matrix of priority transboundary pathogens monitored within the platform's localized edge-triage architecture.1. Zoonotic Viral Hemorrhagic Fevers (VHFs)High-consequence pathogens characterized by severe vascular damage, high case-fatality rates, and primary animal-to-human spillover vectors.Ebola Virus Disease (EBOV / Zaire, Sudan, Bundibugyo, Taï Forest)Transmission Vectors: Fruit bats (Pteropodidae family) serve as the natural reservoir; secondary transmission via direct contact with blood, secretions, organs, or bodily fluids of infected humans or non-human primates.Spread Potential ($R_0$): 1.5 – 2.5 (High localized amplification risk)Clinical Triage Symptoms: Sudden onset of debilitating fever, profound fatigue, myalgia (muscle pain), severe arthralgia (joint pain), headache, and sore throat. Progresses rapidly to persistent vomiting, severe watery diarrhea, maculopapular rash, impaired kidney and liver function, and profound internal and external hemorrhaging.Marburg Virus Disease (MARV)Transmission Vectors: Rousettus aegyptiacus fruit bats inhabiting caves and mines; human-to-human transmission mirrors Ebola via direct contact with broken skin or mucous membranes and infected bodily fluids.Spread Potential ($R_0$): 1.6 – 2.0 (Extreme virulence)Clinical Triage Symptoms: Severe headache, high fever, extreme malaise, and severe muscle aches. Progresses by day three to severe watery diarrhea, abdominal pain, cramping, nausea, vomiting, non-itchy rash, spontaneous mucosal bleeding, and shock.Lassa Fever (Lassa Mammarenavirus)Transmission Vectors: Natal multimammate mouse (Mastomys natalensis) via direct contact with food or household items contaminated with rodent urine or feces; secondary human-to-human transmission occurs in nosocomial settings.Spread Potential ($R_0$): 1.0 – 1.6 (Endemic spillover focus)Clinical Triage Symptoms: Gradual onset of low-grade fever, general weakness, headache, sore throat, myalgia, chest pain, nausea, vomiting, diarrhea, facial swelling, fluid in the lung cavity, mucosal bleeding, and neurological symptoms (hearing loss).Crimean-Congo Hemorrhagic Fever (CCHF)Transmission Vectors: Hyalomma genus ticks serve as both reservoir and vector; transmission occurs via tick bites or direct contact with infectious blood or tissues of viremic livestock.Spread Potential ($R_0$): Vector-density dependent (High localized spikes)Clinical Triage Symptoms: Sharp, sudden onset of high fever, headache, backache, joint pain, severe stomach pain, vomiting, flushed face, ecchymosis (severe bruising), and uncontrolled bleeding at injection sites.2. Respiratory & Airspace Threats (High Pandemigenic Potential)Pathogens exhibiting rapid droplet, aerosol, or airborne mutability with significant potential for international containment failure via global aviation networks.Highly Pathogenic Avian Influenza (H5N1, H7N9, H9N2)Transmission Vectors: Wild migratory waterfowl and domestic poultry; transmission occurs via direct inhalation of dry feces/respiratory secretions.Spread Potential ($R_0$): Variable (Low sustained human-to-human; high mutational threat)Clinical Triage Symptoms: High fever (>38°C), cough, shortness of breath, dyspnea, rapid progression to severe lower respiratory tract distress, primary viral pneumonia, Acute Respiratory Distress Syndrome (ARDS), and multi-organ failure.Middle East Respiratory Syndrome Coronavirus (MERS-CoV)Transmission Vectors: Dromedary camels (Camelus dromedarius) act as primary reservoir; human-to-human transmission occurs via close contact and respiratory droplets.Spread Potential ($R_0$): 0.3 – 0.8 (Nosocomial amplification spikes)Clinical Triage Symptoms: Fever, dry cough, shortness of breath, chills, myalgia, severe atypical pneumonia, gastrointestinal distress, and rapid progression to acute renal failure.Nipah Virus Encephalitis (NiV)Transmission Vectors: Fruit bats (Pteropus genus) via consumption of raw date palm sap contaminated with bat saliva/urine; secondary amplification via swine hosts or respiratory secretions.Spread Potential ($R_0$): 0.4 – 0.6 (Extremely high case-fatality rate: 40% to 75%)Clinical Triage Symptoms: Acute respiratory infection accompanied by intense headache, dizziness, drowsiness, disorientation, acute encephalitis, seizures, and rapid progression to coma within 24–48 hours.3. Vector-Borne Climate Shift PathogensPathogens experiencing significant geographic range expansions due to shifting ecological zones, changing rainfall patterns, and rising global temperatures.Anaplasmosis (Anaplasma phagocytophilum)Transmission Vectors: Blacklegged ticks (Ixodes scapularis) and Western blacklegged ticks (Ixodes pacificus); vector boundaries expanding northwards due to warming seasonal microclimates.Spread Potential ($R_0$): Vector-density dependent (Correlates with tick questing activity and host mammal density)Clinical Triage Symptoms: Fever, severe headache, muscle aches, chills, confusion, and nausea. Severe complications include respiratory failure, bleeding disorders, kidney failure, and septic shock if treatment with doxycycline is delayed.Rift Valley Fever (RVF)Transmission Vectors: Aedes and Culex mosquitoes; amplification occurs via contact with blood/body fluids of infected ruminant livestock during heavy rainfall events.Spread Potential ($R_0$): Vector-density dependentClinical Triage Symptoms: Sudden influenza-like fever, joint pain, retro-orbital headache, photophobia. Critical cases progress to ocular disease, meningoencephalitis, or severe hemorrhagic syndrome with icterus.Dengue (DENV), Chikungunya (CHIKV) & Zika (ZIKV) VirusesTransmission Vectors: Aedes aegypti and Aedes albopictus mosquitoes operating within expanding tropical/subtropical urban boundaries.Clinical Triage Symptoms: Severe retro-orbital headache, joint/muscle aches ("breakbone fever"), maculopapular rash, plasma leakage (Severe Dengue), chronic bilateral polyarthralgia (Chikungunya), and congenital anomalies/Guillain-Barré syndrome (Zika).
---

### 📦 PART 2 of 2 (Paste this right below Part 1)

```markdown
## 4. Data Sources & Resiliency

### Live Ingested Metric Data
To verify the frontend's ability to fetch and parse external structures in real time, one authentic indicator is drawn directly from the open public Global Health Observatory OData API. The script invokes a native browser `fetch()` request to target the country's most recent life expectancy at birth record (index: `WHOSIS_000001`). This exchange is performed directly from the client's IP address with zero middleware or API keys required.

### System Accuracy & Fallback Resiliency
By decoupling data visualization from an application-specific backend server, the platform achieves total operational uptime immunity against database crashes, server drops, or host credential expiration. If an external API endpoint goes offline, the application cleanly falls back to its internal static layers without failing.

---

## 5. Client-Side Architecture & Zero-Data Storage Policy
The application enforces a strict, uncompromising **Zero-Data Storage Policy**. Because it is written as a unified, static front-end file, it possesses no physical mechanism to ingest or retain information outside of the current terminal:

* **No Relational Storage Footprint:** There are no SQL or NoSQL databases, backend cloud logs, tracking pixels, or user state accounts.
* **Transient Memory Isolation:** All calculations, spatial interactions, chosen passphrases, and interface layer toggles exist purely inside the browser's temporary, volatile RAM.
* **Total Volatility:** The moment the operator reloads the page, navigates away, or exits the browser tab, the entire operational state machine is permanently deleted.

---

## 6. Encryption Pipeline & Scannable QR Codes
The system includes a hardware-accelerated symmetric cryptographic subsystem operating within the browser kernel via `window.crypto.subtle`:

1. **Passphrase Key Derivation:** Input strings pass into a native `PBKDF2` primitive using `SHA-256`, performing 150,000 iterations over a 16-byte random salt (`crypto.getRandomValues()`) to generate a 256-bit symmetric key.
2. **Symmetric AES-GCM Encryption:** Calculated risk factors and timestamps convert to ciphertext via Advanced Encryption Standard in Galois/Counter Mode (`AES-256-GCM`) using a 12-byte initialization vector (IV).
3. **Binary-to-Text Serialization:** Salt, IV, and ciphertext are compiled into Base64 string bundles.
4. **QR Matrix Transformation:** Base64 text converts directly into a vector graphic via `qrcode.js` for scanning by external field devices.

If a single bit of the scannable QR code is altered or a key mismatches, the Galois Message Authentication Code (GMAC) check fails natively, throwing an exception and completely blocking corrupted data access.

---

## 7. Realistic Applications & Global Compliance

* **IHR 2005 (International Health Regulations) Compliance:** Allows customs, border desks, and transit hubs to verify incoming transit health matrices without tracking, logging, or centralizing passenger identity markers.
* **WHO-FAO-WOAH One Health Alignment:** Mechanically links human, animal, and environmental parameters into a single vector array ($\sum w_i \Delta_i$).
* **WMO/UN "Early Warnings for All" Initiative:** Aligns with United Nations mandates for scalable Multi-Hazard Early Warning Systems (MHEWS) by providing open, vendor-neutral scoring logic on edge devices.

---

## 8. Real-World Public Health Case Studies

### Case Study 1: Anaplasmosis Tick-Borne Vector Shifts
Tick-borne bacterial infections like **Anaplasmosis** (*Anaplasma phagocytophilum*) are expanding rapidly due to shifting forest microclimates and warming winters.
* **Public Health Challenge:** Regional clinics in newly affected rural zones often lack real-time laboratory connections, resulting in diagnostic delays for patients presenting with non-specific fevers and leukopenia.
* **How BERM v2.0 Aids Public Health:** The app ingests local environmental metrics (humidity, canopy coverage, winter minimum temperatures) into the dynamic risk calculation engine. Rural healthcare workers and park wardens can evaluate localized tick-questing risk scores offline, generating an encrypted QR token containing local tick density indices to attach to patient referral manifests for urban hospitals.

### Case Study 2: Agricultural Produce Traceability (*Cyclospora cayetanensis*)
*Cyclospora* is an environmentally-driven parasite that contaminates fresh agricultural produce (cilantro, berries) via flooded irrigation water.
* **Public Health Challenge:** Perishable produce spoils at border terminals within hours, while traditional laboratory PCR testing takes days. Furthermore, export conglomerates resist uploading farm coordinates to central databases due to trade privacy concerns.
* **How BERM v2.0 Aids Public Health:** Using BERM's **Zero-Data Architecture**, growers compute water-safety indices locally in browser RAM. The app seals the harvest timestamp and water test metrics into an **AES-256-GCM encrypted QR code** printed on the cargo manifest. Customs inspectors scan and decrypt the token locally offline, verifying food safety instantly without uploading sensitive supply-chain data to a cloud database.

### Case Study 3: Marine Climate Pathogens (*Vibrio vulnificus*)
*Vibrio vulnificus* is a fast-moving, flesh-eating marine bacterium triggered by rising sea-surface temperatures and coastal flooding.
* **Public Health Challenge:** Bacterial blooms occur rapidly following heatwaves, threatening commercial shellfish beds and coastal swimmers.
* **How BERM v2.0 Aids Public Health:** By feeding live sea-surface temperature and salinity indices into $R_{dynamic}$, the platform flags high-risk marine harvesting zones weeks before clinical cases emerge, allowing public health agencies to issue targeted harvesting pauses locally.

### Case Study 4: Andes Orthohantavirus & Border Diversions
During historical outbreaks where central database links or airspace access failed, local teams needed offline operational tools. By isolating static environmental vectors from live cloud dependencies, BERM v2.0 allows transit hubs and emergency responders to generate and verify encrypted health manifests at the runway edge without relying on centralized server uptime.

---

## 9. Tech Stack

| Technology Component | Operational Assignment |
| :--- | :--- |
| **HTML5 / CSS3** | Semantic layout wrapper |
| **Tailwind CSS** | Responsive UI assembly via CDN |
| **Vanilla JavaScript** | Asynchronous state engine orchestration |
| **Leaflet.js 1.9.4** | Interactive canvas mapping |
| **CartoDB Dark Matter** | High-contrast spatial base tiles |
| **Font Awesome 6** | Standardized vector indicators |
| **qrcode.js** | Client-side text matrix encoding |
| **Web Crypto API** | Hardware-accelerated symmetric cryptographic primitives |
| **WHO GHO OData API** | Remote metrics data fetch endpoint |

---

## Multidisciplinary Foundations
This software, design logic, and data tracking philosophy are established upon a multi-domain academic foundation:
* **Honours BA in Anthropology** — McMaster University
* **Bachelor of Arts in Psychology** — McMaster University
* **Pre-Health Sciences Certificate** — Mohawk College

---

## Academic References & Literature
1. **World Health Organization (WHO), FAO, & WOAH:** *Joint Risk Assessment Operational Tool (JRA OT): A path to implementing a One Health approach to address zoonotic disease threats.*
2. **World Health Organization:** *International Health Regulations (2005) - 3rd Edition.*
3. **United Nations Office for Disaster Risk Reduction (UNDRR) & WMO:** *Global Status of Multi-Hazard Early Warning Systems (MHEWS).*
4. **Centers for Disease Control and Prevention (CDC):** *Anaplasmosis Epidemiology, Vector Ecology, and Clinical Triage Guidelines.*

---

## Proprietary Usage Notice

```text
CONFIDENTIAL & PROPRIETARY

Copyright (c) 2026 Global Risk Intelligence Framework Project Contributors. All rights reserved.

This software, source code, and associated documentation are proprietary intellectual property. 
Unauthorized copying, modification, distribution, reverse engineering, or public utilization of 
this material, via any medium, is strictly prohibited without explicit, prior written permission 
from the copyright holders.

THE SOFTWARE IS PROVIDED "AS IS", WITH NO WARRANTIES OF ANY KIND.
