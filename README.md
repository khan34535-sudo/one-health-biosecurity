# Global Environmental Risk Matrix (BERM v2.0) — Technical Write-up

A decentralized, client-side risk-visualization prototype combining public health indicators with static multi-vector reference data. Built to demonstrate zero-data frontend architectures, sandboxed API integration, and edge browser-based cryptography for a general audience.

---

## 1. Introduction
This is an independent, solo-built frontend software project. It functions entirely within a local browser sandbox—devoid of any backend server layers, central databases, or personal tracking cookies. Designed as a professional portfolio demonstration and architectural learning exercise, it showcases geo-spatial mapping, live public indicator parsing, and hardware-accelerated client-side cryptography. It is explicitly not an officially deployed or validated analytical instrument for any international agency, health network, or government institution.

---

## 2. Risk Scoring Math
The dashboard calculates an illustrative dynamic threat index by adding a country's foundational baseline risk variable to weighted adjustments derived from the user's active interface toggles:

$$R_{dynamic} = M_{base} + \sum \Delta_{layer}$$

* **$R_{dynamic}$**: Cumulative risk score calculated locally in volatile client RAM.
* **$M_{base}$**: Pre-calibrated regional baseline multiplier representing historical disease burdens.

### Dynamic vector weight coefficients utilized inside this demo application:
* **$\Delta_{viper}$** (Arid/Desert Venoms) = $+0.15$
* **$\Delta_{marine}$** (Marine Neurotoxins) = $+0.12$
* **$\Delta_{fungal}$** (Resistant Fungi clusters) = $+0.22$
* **$\Delta_{synthetic}$** (Advanced Biosecurity Surveillance Flags) = $+0.35$

The system sums these indicators and automatically maps the score onto a transparent risk scale: **HIGH RISK** $\ge 1.9$, **MODERATE RISK** $1.3 \text{ -- } 1.9$, and **LOW RISK** $< 1.3$.

> ⚠️ **Being direct about this**
> These specific layers and algebraic constants were selected to demonstrate operational state changes within the application UI, rather than being refined via predictive epidemiological modeling. It serves as a working scoring *mechanism* to evaluate how decentralized data strings mix, not as a verified clinical or border security diagnostics instrument.

---

## 3. Data Sources

### Live Ingested Metric Data
To verify the frontend's ability to fetch and parse external structures in real time, one authentic indicator is drawn directly from the open public Global Health Observatory OData API. The script invokes a native browser `fetch()` request to target the country's most recent life expectancy at birth record (index: `WHOSIS_000001`). This exchange is performed directly from the client's IP address with zero middleware or API keys required.

### Static Reference Matrices
High-consequence environmental, zoonotic, and mycological risk summaries assigned per country exist as static structural objects written directly into the source file. These elements are loosely modeled on general public knowledge—such as familiar regional venomous species distributions or known pathogen patterns. They are not pulling from a live algorithmic data stream and have not been validated against active clinical or toxinology registries, serving as contextual reference text within the UI.

### System Accuracy & Informational Reliability
The system's live indicator outputs are exactly as reliable as the public global endpoints serving them. However, by decoupling data visualization from an application-specific backend server, the platform achieves total operational uptime immunity against dedicated database crashes, server configuration drops, or host credential expiration. If an external API is blocked or goes offline, the application cleanly falls back to its immutable internal static layers without failing.

---

## 4. Client-Side Architecture & Zero-Data Storage Policy
The application enforces a strict, uncompromising **Zero-Data Storage Policy**. Because it is written as a unified, static front-end file, it possesses no physical mechanism to ingest or retain information outside of the current terminal. Its internal architecture yields precise security and reliability benefits:

* **No Relational Storage Footprint:** There are no SQL or NoSQL databases, backend cloud logs, tracking pixels, or user state accounts.
* **Transient Memory Isolation:** All calculations, spatial interactions, chosen passphrases, and interface layer toggles exist purely inside the browser's temporary, volatile RAM.
* **Total Volatility:** The moment the operator reloads the page, navigates away, or exits the browser tab, the entire operational state machine is permanently deleted.

> ⚠️ **Scope check**
> While a zero-trace lifecycle naturally inherits the standard advantages of basic unprivileged static websites, it is explicitly outlined here to highlight the project's layout approach: proving that multi-layered biological mapping can be evaluated at the edge without necessitating the surveillance liabilities of centralized database servers.

---

## 5. Encryption Pipeline & Scannable QR Codes
The core technical feature of this system is a functional, edge-native symmetric cryptographic subsystem. When an operator types a symmetric key into the interface to lock a regional risk snapshot, the following pipeline executes instantly within the browser kernel via hardware-accelerated instructions:

1. **Passphrase Key Derivation** — The user's input string is fed into a native PBKDF2 primitive using SHA-256, performing 150,000 iterations over a high-entropy 16-byte random salt generated via `crypto.getRandomValues()` to construct a robust 256-bit symmetric cryptographic key.
2. **Symmetric AES-GCM Encryption** — The raw JSON data block containing the calculated risk factors and current timestamp is transformed into ciphertext via the Advanced Encryption Standard in Galois/Counter Mode (AES-256-GCM), utilizing an independent 12-byte initialization vector (IV).
3. **Binary-to-Text Serialization** — The generated salt, initialization vector, and raw ciphertext are compiled and encoded into standard, clean Base64 string bundles.
4. **QR Matrix Transformation** — This text string package is converted directly into a clean vector graphic via `qrcode.js`, producing an encrypted QR code ready to be read by external field devices.

Because the app leverages the browser's audited `crypto.subtle` layer, security checking is absolute. If a single bit of the scannable QR matrix text code is altered, or if a verifying officer inputs a mismatched passkey, the Galois Message Authentication Code (GMAC) check fails automatically. Instead of outputting corrupted or false variables, the engine throws a native exception and completely blocks data access, making unauthorized modifications obvious.

> 🛡️ **What this is**
> A robust, fully functional implementation of audited symmetric encryption standards running locally on user hardware. A mathematically sound feature demonstrating direct, secure, and disconnected client-side data serialization.

> ⚠️ **What this isn't**
> This architecture is not a public-key infrastructure (PKI), does not handle asymmetric identity tokens, and does not establish a network communication tunnel. Because no key-exchange mechanism is built into the script, both parties must distribute and share the symmetric passkey out-of-band beforehand.

---

## 6. Realistic Applications & Global Utility
The BERM v2.0 layout introduces an innovative structural roadmap for data validation across several critical real-world domains:

* **Privacy-Insulated Border Security:** Customs, transit hubs, and immigration desks can verify incoming transit health matrices without tracking, logging, or centralizing the individual travel histories or personal identity markers of passengers, minimizing data privacy conflicts.
* **Infrastructure and Emergency Logistics:** Field deployment vectors, maritime vessels, and non-governmental medical responses operating in regions with disrupted, monitored, or fragile infrastructure can parse, modify, and carry environmental vulnerability indexes with them entirely offline.
* **Oman Institutional Prototype Case:** In countries balancing highly active trade hubs alongside specific regional environmental ecological zones (such as managing incoming international trade in Muscat alongside localized ecological vectors or regional toxinology exposures in Salalah), this layout offers rapid localized risk assessment. It enables local authorities to model dynamic vector trends locally at check-points without requiring a massive central server roll-out. *(Note: This deployment remains an independent design prototype, showing client-side data manipulation options rather than active institutional deployment).*

---

## 7. Real-World Public Health Case Studies
The core necessity of a decentralized, disconnected risk framework is highlighted by historical public health crises where database latency, rigid network demands, or geopolitical airspace border closures compromised coordination.

### Case Study 1: Andes Orthohantavirus (Argentina)
During historical high-consequence Hantavirus outbreaks in South America, local clusters often outpaced the communication networks of centralized health departments. The BERM v2.0 prototype directly mirrors this reality by explicitly exposing a data reporting interval lag indicator (e.g., 4–9 days) directly within the interface. By isolating static environmental and zoonotic vectors from real-time networks, local containment teams can continue calculating field safety markers and regional dryness vectors completely offline, independent of broken external data links.

### Case Study 2: Airspace Redirections & Border Controls
In high-consequence global health contingencies, commercial flights carrying suspected exposures have faced international airspace rejections, preventing scheduled arrivals and forcing emergency technical diversions to alternate international hubs (such as Canada). During these high-friction situations, clearing aircraft requires quick, secure data validation that satisfies both the landing airport's security standards and international data protection acts. By utilizing encrypted QR tokens, an aircraft's threat profile can be audited locally at the runway edge with zero centralized server lookups. This allows customs officials to quickly verify critical safety data without triggering administrative logjams or data leak risks.

---

## 8. Tech Stack

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

### License

Distributed under the MIT License.

```text
MIT License

Copyright (c) 2026 Global Risk Intelligence Framework Project Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
