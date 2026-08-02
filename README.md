🌐 Global Environmental Risk Matrix (BERM v2.0) & HEAL-V3 Architecture
A decentralized, client-side health informatics prototype combining high-scale geospatial epidemiology with interactive local primary care workflows. Built to demonstrate zero-data frontend architectures, sandboxed public API integrations, and edge browser-based hardware cryptography.

Live Demo: One Health BERM v2.0

1. Introduction
This repository contains an independent, solo-built health informatics platform designed by a Senior UX Researcher and Health Systems Architect. Operating entirely within a local browser sandbox, the system runs completely free of backend server layers, central databases, or tracking liabilities.

As a professional portfolio demonstration and architectural exploration, it showcases the feasibility of tracking complex biological vectors, parsing live international indicator streams, and executing hardware-accelerated client-side cryptography at the edge. It is explicitly not an officially deployed or validated analytical instrument for any international agency or government institution.

2. Risk Scoring Math & Threat Indicators
To maintain architectural scalability across emerging threats, BERM v2.0 uses a single, standardized mathematical scoring function rather than maintaining separate, hardcoded codebases for individual pathogens:

R
d
y
n
a
m
i
c
=
M
b
a
s
e
+
∑
i
=
1
n
(
w
i
⋅
Δ
i
)
R 
dynamic
​
 =M 
base
​
 +∑ 
i=1
n
​
 (w 
i
​
 ⋅Δ 
i
​
 )

Variable Definitions
Variable	Description	Range
R
d
y
n
a
m
i
c
R 
dynamic
​
 	Cumulative regional biosecurity threat index	0.0 – 3.0+
M
b
a
s
e
M 
base
​
 	Pre-calibrated regional baseline multiplier	0.5 – 1.5
Δ
i
Δ 
i
​
 	Normalized dynamic input metric for variable 
i
i	0.0 – 1.0
w
i
w 
i
​
 	Pathogen-specific weighting coefficient	0.0 – 1.0 (Σ w_i = 1.0)
Risk Classification Scale
The system projects 
R
d
y
n
a
m
i
c
R 
dynamic
​
  onto an absolute risk classification scale:

Risk Level	
R
d
y
n
a
m
i
c
R 
dynamic
​
  Range	Recommended Action
🔴 HIGH RISK	≥ 1.9	Immediate intervention required
🟡 MODERATE RISK	1.3 – 1.9	Enhanced surveillance
🟢 LOW RISK	< 1.3	Standard monitoring
Universal Risk Pipeline
text
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
Example Dynamic Inputs (Δᵢ)
Normalized environmental indicators used by the risk engine:

Δ_temperature (Sea Surface Temp Anomaly) = 0.75

Δ_rainfall (Deviation from historical average) = 0.60

Δ_transit (Global shipping disruption index) = 0.30

Pathogen Weight Calibration Mechanics (w_i)
The weighting coefficients (
w
i
w 
i
​
 ) are pre-calibrated, static values derived from established epidemiological methodologies. They are loaded from a configuration file rather than computed in real-time.

text
┌─────────────────────────────────────────────────────────────────────────────┐
│                 THREE-TIER WEIGHT CALIBRATION FRAMEWORK                     │
├─────────────────────────────────────────────────────────────────────────────┤
│  1. MULTIVARIATE REGRESSION MODELING (Data-Driven / Empirical)              │
│     β_i = Adjusted Odds Ratios from historical outbreak logs                │
│                                                                             │
│  2. REPRODUCTIVE NUMBER SENSITIVITY (Mathematical / Epidemiology)           │
│     w_i ≈ ∂R₀ / ∂(Variable_i)  [Estimated via pre-run numerical models]   │
│                                                                             │
│  3. TRIPARTITE ONE HEALTH CONSENSUS (Qualitative-to-Quantitative)           │
│     w_i = Standardized risk matrices (WHO JRA OT / FAO / WOAH guidelines)   │
└─────────────────────────────────────────────────────────────────────────────┘
1. Multivariate Logistic Regression Modeling
For predicting outbreak probability, the log-odds of an outbreak are modeled as:

ln
⁡
(
P
o
u
t
b
r
e
a
k
1
−
P
o
u
t
b
r
e
a
k
)
=
β
0
+
β
1
⋅
Temp
+
β
2
⋅
Rainfall
+
β
3
⋅
TransitDelay
+
…
ln( 
1−P 
outbreak
​
 
P 
outbreak
​
 
​
 )=β 
0
​
 +β 
1
​
 ⋅Temp+β 
2
​
 ⋅Rainfall+β 
3
​
 ⋅TransitDelay+…

Where β coefficients are derived from peer-reviewed outbreak literature.

2. R₀ Sensitivity Analysis
For vector-borne pathogens, the weight 
w
i
w 
i
​
  represents the estimated sensitivity of the Basic Reproduction Number (R₀) to a specific environmental variable:

w
i
≈
∂
R
0
∂
Variable
i
w 
i
​
 ≈ 
∂Variable 
i
​
 
∂R 
0
​
 
​
 

In practice, this means the weight is a fixed value (e.g., w_temperature = 0.35) derived from published literature showing a correlation between R₀ and temperature for a given pathogen.

3. One Health Consensus Mapping
Accepts qualitative-to-quantitative risk weight matrices mapped directly from the WHO Joint Risk Assessment Operational Tool (JRA OT), integrating human, animal, and environmental health parameters.

3. Pathogen Classification & Triage Matrices
BERM v2.0 maps multi-vector public health threats at the human-animal-environmental interface (One Health). Below is the operational matrix of priority transboundary pathogens monitored within the platform's localized edge-triage architecture.

3.1 Zoonotic Viral Hemorrhagic Fevers (VHFs)
High-consequence pathogens characterized by severe vascular damage, high case-fatality rates, and primary animal-to-human spillover vectors.

Ebola Virus Disease (EBOV)
Attribute	Details
Transmission Vectors	Fruit bats (Pteropodidae family); secondary via direct contact with infected bodily fluids
Spread Potential (R₀)	1.5 – 2.5
Clinical Triage Symptoms	Sudden fever, fatigue, myalgia, headache; progresses to vomiting, diarrhea, hemorrhaging
Marburg Virus Disease (MARV)
Attribute	Details
Transmission Vectors	Rousettus aegyptiacus fruit bats; human-to-human via direct contact
Spread Potential (R₀)	1.6 – 2.0
Clinical Triage Symptoms	Severe headache, high fever, myalgia; progresses to severe diarrhea, mucosal bleeding, shock
Lassa Fever
Attribute	Details
Transmission Vectors	Natal multimammate mouse (Mastomys natalensis); nosocomial transmission
Spread Potential (R₀)	1.0 – 1.6
Clinical Triage Symptoms	Gradual fever, weakness, headache, sore throat; neurological symptoms including hearing loss
Crimean-Congo Hemorrhagic Fever (CCHF)
Attribute	Details
Transmission Vectors	Hyalomma genus ticks; direct contact with infected livestock tissues
Spread Potential (R₀)	Vector-density dependent
Clinical Triage Symptoms	Sudden high fever, headache, backache, joint pain; uncontrolled bleeding
3.2 Respiratory & Airspace Threats
Pathogens with significant potential for international containment failure via global aviation networks.

Highly Pathogenic Avian Influenza (H5N1, H7N9, H9N2)
Attribute	Details
Transmission Vectors	Wild migratory waterfowl and domestic poultry; direct inhalation
Spread Potential (R₀)	Variable (low sustained human-to-human)
Clinical Triage Symptoms	High fever (>38°C), cough, dyspnea; rapid progression to ARDS and multi-organ failure
Middle East Respiratory Syndrome (MERS-CoV)
Attribute	Details
Transmission Vectors	Dromedary camels; human-to-human via close contact
Spread Potential (R₀)	0.3 – 0.8
Clinical Triage Symptoms	Fever, cough, shortness of breath; rapid progression to renal failure
Nipah Virus Encephalitis (NiV)
Attribute	Details
Transmission Vectors	Fruit bats (Pteropus genus); contaminated date palm sap; swine amplification
Spread Potential (R₀)	0.4 – 0.6
Clinical Triage Symptoms	Acute respiratory infection; encephalitis, seizures, coma; 40-75% case-fatality
3.3 Vector-Borne Climate Shift Pathogens
Pathogens expanding geographically due to changing ecological zones and rising temperatures.

Anaplasmosis (Anaplasma phagocytophilum)
Attribute	Details
Transmission Vectors	Blacklegged ticks (Ixodes scapularis, I. pacificus); expanding northwards
Spread Potential (R₀)	Vector-density dependent
Clinical Triage Symptoms	Fever, headache, muscle aches; severe complications if treatment delayed
Rift Valley Fever (RVF)
Attribute	Details
Transmission Vectors	Aedes and Culex mosquitoes; livestock amplification
Spread Potential (R₀)	Vector-density dependent
Clinical Triage Symptoms	Influenza-like fever; critical cases progress to hemorrhagic syndrome
Dengue, Chikungunya & Zika Viruses
Attribute	Details
Transmission Vectors	Aedes aegypti and Aedes albopictus mosquitoes
Spread Potential (R₀)	Vector-density dependent
Clinical Triage Symptoms	"Breakbone fever," rash; Zika causes congenital anomalies and Guillain-Barré syndrome
4. Data Sources & Resiliency
Live Ingested Metric Data
To verify the frontend's ability to fetch and parse external structures in real time, an authentic indicator is drawn directly from the open public Global Health Observatory OData API. The script invokes a native browser fetch() request to target the country's most recent life expectancy at birth record (index: WHOSIS_000001). This exchange is performed directly from the client's IP address with zero middleware or API keys required.

System Accuracy & Fallback Resiliency
By decoupling data visualization from an application-specific backend server, the platform achieves total operational uptime immunity against database crashes, server drops, or host credential expiration. If an external API endpoint goes offline, the application cleanly falls back to its internal static layers without failing.

5. Client-Side Architecture & Zero-Data Storage Policy
The application enforces a strict, uncompromising Zero-Data Storage Policy. Because it is written as a unified, static front-end file, it possesses no physical mechanism to ingest or retain information outside of the current terminal:

No Relational Storage Footprint: No SQL or NoSQL databases, backend cloud logs, tracking pixels, or user state accounts.

Transient Memory Isolation: All calculations, spatial interactions, chosen passphrases, and interface layer toggles exist purely inside the browser's temporary, volatile RAM.

Total Volatility: The moment the operator reloads the page, navigates away, or exits the browser tab, the entire operational state machine is permanently deleted.

6. Encryption Pipeline & Scannable QR Codes
The system includes a hardware-accelerated symmetric cryptographic subsystem operating within the browser kernel via window.crypto.subtle:

Passphrase Key Derivation: Input strings pass into a native PBKDF2 primitive using SHA-256, performing 150,000 iterations over a 16-byte random salt (crypto.getRandomValues()) to generate a 256-bit symmetric key.

Symmetric AES-GCM Encryption: Calculated risk factors and timestamps convert to ciphertext via Advanced Encryption Standard in Galois/Counter Mode (AES-256-GCM) using a 12-byte initialization vector (IV).

Binary-to-Text Serialization: Salt, IV, and ciphertext are compiled into Base64 string bundles.

QR Matrix Transformation: Base64 text converts directly into a vector graphic via qrcode.js for scanning by external field devices.

Security Note: If a single bit of the scannable QR code is altered or a key mismatches, the Galois Message Authentication Code (GMAC) check fails natively, throwing an exception and completely blocking corrupted data access.

7. Global Compliance & Applications
IHR 2005 (International Health Regulations) Compliance
Allows customs, border desks, and transit hubs to verify incoming transit health matrices without tracking, logging, or centralizing passenger identity markers.

WHO-FAO-WOAH One Health Alignment
Mechanically links human, animal, and environmental parameters into a single vector array (Σ wᵢ · Δᵢ).

WMO/UN "Early Warnings for All" Initiative
Aligns with United Nations mandates for scalable Multi-Hazard Early Warning Systems (MHEWS) by providing open, vendor-neutral scoring logic on edge devices.

8. Real-World Public Health Case Studies
Case Study 1: Anaplasmosis Tick-Borne Vector Shifts
Public Health Challenge: Regional clinics in newly affected rural zones often lack real-time laboratory connections, resulting in diagnostic delays.

How BERM v2.0 Aids Public Health: The app ingests local environmental metrics (humidity, canopy coverage, winter minimum temperatures) into the dynamic risk calculation engine. Rural healthcare workers generate encrypted QR tokens containing local tick density indices for patient referral manifests.

Case Study 2: Agricultural Produce Traceability (Cyclospora cayetanensis)
Public Health Challenge: Perishable produce spoils at border terminals within hours, while traditional PCR testing takes days. Exporters resist uploading farm coordinates to central databases.

How BERM v2.0 Aids Public Health: Growers compute water-safety indices locally in browser RAM. The app seals harvest timestamp and water test metrics into AES-256-GCM encrypted QR codes printed on cargo manifests. Customs inspectors scan and decrypt locally offline.

Case Study 3: Marine Climate Pathogens (Vibrio vulnificus)
Public Health Challenge: Bacterial blooms occur rapidly following heatwaves, threatening shellfish beds and coastal swimmers.

How BERM v2.0 Aids Public Health: By feeding live sea-surface temperature and salinity indices into R_dynamic, the platform flags high-risk marine harvesting zones weeks before clinical cases emerge.

Case Study 4: Andes Orthohantavirus & Border Diversions
Public Health Challenge: During historical outbreaks where central database links or airspace access failed, local teams needed offline operational tools.

How BERM v2.0 Aids Public Health: By isolating static environmental vectors from live cloud dependencies, BERM v2.0 allows transit hubs and emergency responders to generate and verify encrypted health manifests at the runway edge without relying on centralized server uptime.

9. Tech Stack
Technology Component	Operational Assignment
HTML5 / CSS3	Semantic layout wrapper
Tailwind CSS	Responsive UI assembly via CDN
Vanilla JavaScript	Asynchronous state engine orchestration
Leaflet.js 1.9.4	Interactive canvas mapping
CartoDB Dark Matter	High-contrast spatial base tiles
Font Awesome 6	Standardized vector indicators
qrcode.js	Client-side text matrix encoding
Web Crypto API	Hardware-accelerated symmetric cryptographic primitives
WHO GHO OData API	Remote metrics data fetch endpoint
10. Multidisciplinary Foundations
This software, design logic, and data tracking philosophy are established upon a multi-domain academic foundation:

Honours BA in Anthropology — McMaster University

Bachelor of Arts in Psychology — McMaster University

Pre-Health Sciences Certificate — Mohawk College

11. Academic References & Literature
World Health Organization (WHO), FAO, & WOAH. Joint Risk Assessment Operational Tool (JRA OT): A path to implementing a One Health approach to address zoonotic disease threats.

World Health Organization. International Health Regulations (2005) - 3rd Edition.

United Nations Office for Disaster Risk Reduction (UNDRR) & WMO. Global Status of Multi-Hazard Early Warning Systems (MHEWS).

Centers for Disease Control and Prevention (CDC). Anaplasmosis Epidemiology, Vector Ecology, and Clinical Triage Guidelines.

12. Proprietary Usage Notice
text
CONFIDENTIAL & PROPRIETARY

Copyright (c) 2026 Global Risk Intelligence Framework Project Contributors. 
All rights reserved.

This software, source code, and associated documentation are proprietary 
intellectual property. Unauthorized copying, modification, distribution, 
reverse engineering, or public utilization of this material, via any medium, 
is strictly prohibited without explicit, prior written permission from the 
copyright holders.

THE SOFTWARE IS PROVIDED "AS IS", WITH NO WARRANTIES OF ANY KIND.
13. Contributing
This is a solo-built portfolio project. While not currently open for external contributions, feedback and suggestions are welcome via GitHub Issues.

14. License
All rights reserved. See the Proprietary Usage Notice above.

