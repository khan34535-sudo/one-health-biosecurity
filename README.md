# 🌐 Global Environmental Risk Matrix (BERM v2.0) & HEAL-V3 Architecture

A decentralized, client-side health informatics prototype combining high-scale geospatial epidemiology with interactive local primary care workflows. Built to demonstrate zero-data frontend architectures, sandboxed public API integrations, and edge browser-based hardware cryptography.

---

## 1. Introduction
This repository contains an independent, solo-built health informatics platform designed by a Senior UX Researcher and Health Systems Architect. Operating entirely within a local browser sandbox, the system runs completely free of backend server layers, central databases, or tracking liabilities. 

As a professional portfolio demonstration and architectural exploration, it showcases the feasibility of tracking complex biological vectors, parsing live international indicator streams, and executing hardware-accelerated client-side cryptography at the edge. It is explicitly not an officially deployed or validated analytical instrument for any international agency or government institution.

---

## 2. Risk Scoring Math & Threat Indicators
The application calculates a dynamic regional threat index by synthesizing an immutable baseline geographic risk profile with real-time adjustments selected via the user interface toggles:

$$R_{dynamic} = M_{base} + \sum \Delta_{layer}$$

Where:
* **$R_{dynamic}$**: Cumulative environmental risk score calculated locally in volatile client RAM.
* **$M_{base}$**: Pre-calibrated regional baseline multiplier representing historical zoonotic and ecological disease burdens.
* **$\Delta_{layer}$**: Dynamic vector weight coefficients applied via UI interaction switches.

### Dynamic Vector Weight Coefficients Injected inside the Engine:
* **$\Delta_{viper}$** (Arid/Desert Venoms & Toxinology Shifts) = $+0.15$
* **$\Delta_{marine}$** (Marine Neurotoxins & Coastal Microalgae) = $+0.12$
* **$\Delta_{fungal}$** (Antimicrobial Resistant Fungi clusters) = $+0.22$
* **$\Delta_{synthetic}$** (Advanced Biosecurity Surveillance Flags) = $+0.35$

The system dynamically sums these values and projects them onto an absolute risk classification scale:
* 🔴 **HIGH RISK**: $R_{dynamic} \ge 1.9$
* 🟡 **MODERATE RISK**: $1.3 \le R_{dynamic} < 1.9$
* 🟢 **LOW RISK**: $R_{dynamic} < 1.3$

> ⚠️ **Methodological Scope Note**
> These specific layer modifiers and algebraic constants are selected to demonstrate rapid state-handling, reactivity, and structural visualization within the UI. They serve to evaluate how decentralized data strings mix under high-stress triage conditions, rather than functioning as active, predictive epidemiological models.

---

## 🦠 Comprehensive Pathogen Classification & Triage Matrices

BERM v2.0 maps multi-vector public health threats at the human-animal-environmental interface (**One Health**). Below is the operational matrix of priority transboundary pathogens monitored within the platform's localized edge-triage architecture.

### 1. Zoonotic Viral Hemorrhagic Fevers (VHFs)
High-consequence pathogens characterized by severe vascular damage, high case-fatality rates, and primary animal-to-human spillover vectors.

* **Ebola Virus Disease (EBOV / Zaire, Sudan, Bundibugyo, Taï Forest)**
    * *Transmission Vectors:* Fruit bats (*Pteropodidae* family) serve as the natural reservoir; secondary transmission via direct contact with blood, secretions, organs, or bodily fluids of infected humans or non-human primates.
    * *Spread Potential ($R_0$):* **1.5 – 2.5** (High localized amplification risk)
    * *Clinical Triage Symptoms:* Sudden onset of debilitating fever, profound fatigue, myalgia (muscle pain), severe arthralgia (joint pain), headache, and sore throat. Progresses rapidly to persistent vomiting, severe watery diarrhea, maculopapular rash, impaired kidney and liver function, and profound internal and external hemorrhaging (e.g., bleeding from gums, hematemesis, melena).
* **Marburg Virus Disease (MARV)**
    * *Transmission Vectors:* *Rousettus aegyptiacus* fruit bats inhabiting caves and mines; human-to-human transmission mirrors Ebola via direct contact with broken skin or mucous membranes and infected bodily fluids.
    * *Spread Potential ($R_0$):* **1.6 – 2.0** (Extreme virulence)
    * *Clinical Triage Symptoms:* Severe headache, high fever, extreme malaise, and severe muscle aches. By day three, patients experience severe watery diarrhea, abdominal pain, cramping, nausea, and vomiting. Appearance of a non-itchy rash between days 2 and 7, progressing to severe hemorrhagic manifestations, spontaneous mucosal bleeding, and shock.
* **Lassa Fever (Lassa Mammarenavirus)**
    * *Transmission Vectors:* Natal multimammate mouse (*Mastomys natalensis*) via direct contact with food or household items contaminated with rodent urine or feces; secondary human-to-human transmission occurs in nosocomial (hospital) settings.
    * *Spread Potential ($R_0$):* **1.0 – 1.6** (Endemic spillover focus)
    * *Clinical Triage Symptoms:* Gradual onset beginning with low-grade fever, general weakness, and malaise. Progresses to severe headache, sore throat, myalgia, chest pain, nausea, vomiting, diarrhea, cough, and abdominal pain. Severe cases present facial swelling, fluid in the lung cavity, mucosal bleeding, and neurological symptoms (tremors, hearing loss).
* **Crimean-Congo Hemorrhagic Fever (CCHF)**
    * *Transmission Vectors:* *Hyalomma* genus ticks serve as both reservoir and vector; transmission occurs via tick bites or direct contact with infectious blood or tissues of viremic livestock (cattle, sheep, goats).
    * *Spread Potential ($R_0$):* Vector-density dependent (High localized spikes)
    * *Clinical Triage Symptoms:* Sharp, sudden onset of high fever, headache, backache, joint pain, severe stomach pain, and vomiting. Accompanied by red eyes, a flushed face, throat hyperemia, and jaundice. Severe cases present large areas of ecchymosis (severe bruising), epistaxis (nosebleeds), and uncontrolled bleeding at injection sites.
* **Other Tracked Regional Arenaviruses**
    * *Includes:* Argentine (Junín), Bolivian (Machupo), Venezuelan (Guanarito), and Brazilian (Sabiá/Chapare) Hemorrhagic Fevers.
    * *Transmission Vectors:* Specific cricetid and vesper rodent reservoirs via inhalation of aerosolized excreta during agricultural work or forest foraging.
    * *Clinical Triage Symptoms:* Insidious onset of retro-orbital pain, epigastric pain, marked conjunctivitis, and petechiae on the upper trunk, progressing to hand/tongue tremors, profound thrombocytopenia, and leukopenia.

### 2. Respiratory & Airspace Threats (High Pandemigenic Potential)
Pathogens exhibiting rapid droplet, aerosol, or airborne mutability with significant potential for international containment failure via global aviation networks.

* **Highly Pathogenic Avian Influenza (H5N1, H7N9, H9N2)**
    * *Transmission Vectors:* Wild migratory waterfowl and domestic poultry; transmission occurs via direct inhalation of dry feces/respiratory secretions, with high potential for cross-species mutation inside mammalian mixing vessels.
    * *Spread Potential ($R_0$):* Variable (Low sustained human-to-human; high mutational threat)
    * *Clinical Triage Symptoms:* High fever (greater than 38°C), cough, shortness of breath, dyspnea, sore throat, myalgia, and rapid progression to severe lower respiratory tract distress. Features atypical primary viral pneumonia, sputum production, rapid onset of Acute Respiratory Distress Syndrome (ARDS), and multi-organ failure.
* **Middle East Respiratory Syndrome Coronavirus (MERS-CoV)**
    * *Transmission Vectors:* Dromedary camels (*Camelus dromedarius*) act as the primary zoonotic reservoir; human-to-human transmission occurs via close contact and respiratory droplets, frequently amplifying in healthcare facilities.
    * *Spread Potential ($R_0$):* **0.3 – 0.8** (Nosocomial amplification spikes)
    * *Clinical Triage Symptoms:* Fever, dry cough, shortness of breath, chills, sore throat, myalgia, arthralgia, and severe atypical pneumonia. Frequently presents atypical gastrointestinal symptoms (including diarrhea and vomiting) and rapid progression to acute renal failure, especially in patients with pre-existing metabolic co-morbidities.
* **Nipah Virus Encephalitis (NiV)**
    * *Transmission Vectors:* Fruit bats of the *Pteropodidae* family (*Pteropus* genus) via consumption of raw date palm sap contaminated with bat saliva or urine; secondary amplification via intermediate swine hosts or direct human-to-human respiratory secretions.
    * *Spread Potential ($R_0$):* **0.4 – 0.6** (Extremely high case-fatality rate: 40% to 75%)
    * *Clinical Triage Symptoms:* Severe acute respiratory infection (fever, cough, sore throat, acute respiratory distress) accompanied by neurological signs including intense headache, dizziness, drowsiness, disorientation, mental confusion, acute encephalitis, seizures, and rapid progression to a comatose state within 24–48 hours.
* **Severe Acute Respiratory Syndrome (SARS-CoV-1 & SARS-CoV-2)**
    * *Transmission Vectors:* Horseshoe bats (*Rhinolophus*) and intermediate amplification hosts; highly transmissible via micro-aerosol droplets, surface fomites, and long-range airborne suspension in enclosed facilities.
    * *Clinical Triage Symptoms:* Prodromal fever, dry cough, dyspnea, chills, rigors, headache, generalized myalgia, progressive hypoxemia, loss of taste/smell (anosmia/ageusia), severe interstitial pneumonia, and hyper-inflammatory cytokine storms.
* **Hantavirus Pulmonary Syndrome (HPS / Sin Nombre & Andes Virus)**
    * *Transmission Vectors:* Deer mice (*Peromyscus maniculatus*) and cotton rats via inhalation of aerosolized excreta from infested spaces; Andes virus uniquely exhibits documented human-to-human droplet transmission.
    * *Clinical Triage Symptoms:* Fever, chills, severe myalgia focusing on large muscle groups (thighs, back, shoulders), headache, dizziness, and gastrointestinal distress. Characterized by a sudden, catastrophic onset of progressive coughing, severe shortness of breath, pulmonary edema, and acute myocardial depression.

### 3. Vector-Borne Climate Shift Pathogens
Pathogens experiencing significant geographic range expansions due to shifting ecological zones, changing rainfall patterns, and rising global temperatures.

* **Rift Valley Fever (RVF)**
    * *Transmission Vectors:* *Aedes* mosquitoes (transovarial reservoirs) and *Culex* mosquitoes; amplification occurs via contact with the blood or body fluids of domestic ruminant livestock (sheep, goats, cattle) during slaughtering or veterinary care.
    * *Spread Potential ($R_0$):* Vector-density dependent (Corresponds with heavy rainfall events)
    * *Clinical Triage Symptoms:* Incubation period of 2 to 6 days followed by sudden influenza-like fever, muscle pain, joint pain, retro-orbital headache, photophobia, and anorexia. A critical minority progress to ocular disease (blurred vision, permanent retinal lesions), meningoencephalitis (seizures, vertigo), or severe hemorrhagic syndrome with massive icterus (jaundice).
* **Yellow Fever (YFV)**
    * *Transmission Vectors:* *Aedes aegypti* (urban cycle) and *Haemagogus* or *Sabethes* mosquitoes (sylvatic/jungle cycle) operating within expanding tropical boundaries.
    * *Clinical Triage Symptoms:* Initial acute phase includes fever, muscle pain (particularly backache), headache, loss of appetite, nausea, and vomiting. Following a brief 24-hour remission, 15% of patients enter a toxic phase characterized by high fever, severe jaundice (giving the disease its name due to liver damage), dark urine, abdominal pain with vomiting ("black vomit" due to gastric bleeding), epistaxis, and renal failure.
* **Dengue Virus (DENV Serotypes 1-4)**
    * *Transmission Vectors:* *Aedes aegypti* and *Aedes albopictus* mosquitoes, thriving in increasing urban temperatures and poor drainage frameworks.
    * *Clinical Triage Symptoms:* High fever (up to 40°C) accompanied by severe retro-orbital pain, severe headache, joint and muscle aches ("breakbone fever"), nausea, vomiting, swollen glands, and a widespread maculopapular rash. Severe Dengue (DHF/DSS) presents with plasma leakage, severe abdominal pain, persistent vomiting, fluid accumulation, mucosal bleeding, and hypovolemic shock.
* **Chikungunya (CHIKV) & Zika (ZIKV) Viruses**
    * *Transmission Vectors:* *Aedes* genus mosquitoes experiencing rapid range expansions due to climate warming.
    * *Clinical Triage Symptoms:* Chikungunya presents with abrupt high fever, maculopapular rash, and debilitating, frequently chronic bilateral polyarthralgia. Zika presents with mild fever, pruritic rash, non-purulent conjunctivitis, and is critically linked to congenital neurological anomalies (microcephaly) and post-viral autoimmune syndromes (Guillain-Barré syndrome).
* **West Nile Virus (WNV)**
    * *Transmission Vectors:* *Culex* mosquitoes vectoring the virus from wild avian amplifier hosts; proliferating in urban wetlands due to altered precipitation patterns.
    * *Clinical Triage Symptoms:* Approximately 80% are asymptomatic. West Nile Fever presents with sudden fever, headache, body aches, joint pains, vomiting, diarrhea, or rash. Fewer than 1% develop severe West Nile Neuroinvasive Disease, characterized by high fever, neck stiffness, stupor, disorientation, coma, tremors, convulsions, muscle weakness, and acute flaccid paralysis.

---

## 4. Data Sources

### Live Ingested Metric Data
To verify the frontend's ability to fetch and parse external structures in real time, one authentic indicator is drawn directly from the open public Global Health Observatory OData API. The script invokes a native browser `fetch()` request to target the country's most recent life expectancy at birth record (index: `WHOSIS_000001`). This exchange is performed directly from the client's IP address with zero middleware or API keys required.

### Static Reference Matrices
High-consequence environmental, zoonotic, and mycological risk summaries assigned per country exist as static structural objects written directly into the source file. These elements are loosely modeled on general public knowledge—such as familiar regional venomous species distributions or known pathogen patterns. They are not pulling from a live algorithmic data stream and have not been validated against active clinical or toxinology registries, serving as contextual reference text within the UI.

### System Accuracy & Informational Reliability
The system's live indicator outputs are exactly as reliable as the public global endpoints serving them. However, by decoupling data visualization from an application-specific backend server, the platform achieves total operational uptime immunity against dedicated database crashes, server configuration drops, or host credential expiration. If an external API is blocked or goes offline, the application cleanly falls back to its immutable internal static layers without failing.

---

## 5. Client-Side Architecture & Zero-Data Storage Policy
The application enforces a strict, uncompromising **Zero-Data Storage Policy**. Because it is written as a unified, static front-end file, it possesses no physical mechanism to ingest or retain information outside of the current terminal. Its internal architecture yields precise security and reliability benefits:

* **No Relational Storage Footprint:** There are no SQL or NoSQL databases, backend cloud logs, tracking pixels, or user state accounts.
* **Transient Memory Isolation:** All calculations, spatial interactions, chosen passphrases, and interface layer toggles exist purely inside the browser's temporary, volatile RAM.
* **Total Volatility:** The moment the operator reloads the page, navigates away, or exits the browser tab, the entire operational state machine is permanently deleted.

> ⚠️ **UX/UI Architecture Principle**
> While a zero-trace lifecycle naturally inherits the standard advantages of basic unprivileged static websites, it is explicitly designed to solve a specific UX friction point: proving that multi-layered biological mapping can be evaluated at the edge without necessitating the surveillance and compliance liabilities of centralized database servers.

---

## 6. Encryption Pipeline & Scannable QR Codes
The core technical feature of this system is a functional, edge-native symmetric cryptographic subsystem. When an operator types a symmetric key into the interface to lock a regional risk snapshot, the following pipeline executes instantly within the browser kernel via hardware-accelerated instructions:

1. **Passphrase Key Derivation** — The user's input string is fed into a native `PBKDF2` primitive using `SHA-256`, performing 150,000 iterations over a high-entropy 16-byte random salt generated via `crypto.getRandomValues()` to construct a robust 256-bit symmetric cryptographic key.
2. **Symmetric AES-GCM Encryption** — The raw JSON data block containing the calculated risk factors and current timestamp is transformed into ciphertext via the Advanced Encryption Standard in Galois/Counter Mode (`AES-256-GCM`), utilizing an independent 12-byte initialization vector (IV).
3. **Binary-to-Text Serialization** — The generated salt, initialization vector, and raw ciphertext are compiled and encoded into standard, clean Base64 string bundles.
4. **QR Matrix Transformation** — This text string package is converted directly into a clean vector graphic via `qrcode.js`, producing an encrypted QR code ready to be read by external field devices.

Because the app leverages the browser's audited `crypto.subtle` layer, security checking is absolute. If a single bit of the scannable QR matrix text code is altered, or if a verifying officer inputs a mismatched passkey, the Galois Message Authentication Code (GMAC) check fails automatically. Instead of outputting corrupted or false variables, the engine throws a native exception and completely blocks data access, making unauthorized modifications obvious.

> 🛡️ **Cryptographic Boundary**
> This architecture is not a public-key infrastructure (PKI), does not handle asymmetric identity tokens, and does not establish an active network communication tunnel. Because no key-exchange mechanism is built into the script, both parties must distribute and share the symmetric passkey out-of-band beforehand.

---

## 7. Realistic Applications & Global Utility
The BERM v2.0 layout introduces an innovative structural roadmap for data validation across several critical real-world domains:

* **Privacy-Insulated Border Security:** Customs, transit hubs, and immigration desks can verify incoming transit health matrices without tracking, logging, or centralizing the individual travel histories or personal identity markers of passengers, minimizing data privacy conflicts under International Health Regulations (IHR 2005).
* **Infrastructure and Emergency Logistics:** Field deployment vectors, maritime vessels, and non-governmental medical responses operating in regions with disrupted, monitored, or fragile infrastructure can parse, modify, and carry environmental vulnerability indexes with them entirely offline.
* **Oman Institutional Prototype Case:** In countries balancing highly active trade hubs alongside specific regional environmental ecological zones (such as managing incoming international trade in Muscat alongside localized ecological vectors or regional toxinology exposures in Salalah), this layout offers rapid localized risk assessment. It enables local authorities to model dynamic vector trends locally at check-points without requiring a massive central server roll-out. *(Note: This deployment remains an independent design prototype, showing client-side data manipulation options rather than active institutional deployment).*

---

## 8. Real-World Public Health Case Studies
The core necessity of a decentralized, disconnected risk framework is highlighted by historical public health crises where database latency, rigid network demands, or geopolitical airspace border closures compromised coordination.

### Case Study 1: Andes Orthohantavirus (Argentina)
During historical high-consequence Hantavirus outbreaks in South America, local clusters often outpaced the communication networks of centralized health departments. The BERM v2.0 prototype directly mirrors this reality by explicitly exposing a data reporting interval lag indicator (e.g., 4–9 days) directly within the interface. By isolating static environmental and zoonotic vectors from real-time networks, local containment teams can continue calculating field safety markers and regional dryness vectors completely offline, independent of broken external data links.

### Case Study 2: Airspace Redirections & Border Controls
In high-consequence global health contingencies, commercial flights carrying suspected exposures have faced international airspace rejections, preventing scheduled arrivals and forcing emergency technical diversions to alternate international hubs. During these high-friction situations, clearing aircraft requires quick, secure data validation that satisfies both the landing airport's security standards and international data protection acts. By utilizing encrypted QR tokens, an aircraft's threat profile can be audited locally at the runway edge with zero centralized server lookups. This allows customs officials to quickly verify critical safety data without triggering administrative logjams or data leak risks.

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

## Multidisciplinary Foundations & Compliance
This software, design logic, and data tracking philosophy are established upon a multi-domain academic foundation:
* **Honours BA in Anthropology** — McMaster University
* **Bachelor of Arts in Psychology** — McMaster University
* **Pre-Health Sciences Certificate** — Mohawk College

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
