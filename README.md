<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Global Environmental Risk Matrix (BERM v2.0) — Technical Write-up</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#eef2f0;
    --paper-raised:#ffffff;
    --ink:#12202b;
    --ink-soft:#485a63;
    --line:#d7ded9;
    --accent:#1f8f63;
    --accent-soft:#e4f2ea;
    --code-bg:#0f1b24;
    --code-text:#cfe8db;
    --warn:#a3620a;
    --warn-soft:#faf1e2;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{ margin:0; background:var(--paper); color:var(--ink); font-family:'IBM Plex Sans', sans-serif; line-height:1.65; }
  a{color:var(--accent);}
  .layout{ display:grid; grid-template-columns:220px minmax(0,720px); justify-content:center; gap:56px; max-width:1120px; margin:0 auto; padding:56px 24px 120px; }

  nav.toc{ position:sticky; top:48px; align-self:start; font-size:12.5px; }
  .toc-label{ font-family:'JetBrains Mono', monospace; font-size:10.5px; letter-spacing:.12em; text-transform:uppercase; color:var(--ink-soft); margin-bottom:12px; }
  .toc a{ display:block; color:var(--ink-soft); text-decoration:none; padding:5px 0 5px 12px; border-left:2px solid var(--line); }
  .toc a:hover{ color:var(--ink); border-color:var(--accent); }

  main{min-width:0;}
  .eyebrow{ font-family:'JetBrains Mono', monospace; font-size:10.5px; letter-spacing:.14em; text-transform:uppercase; color:var(--accent); margin-bottom:8px; }
  h1{ font-family:'JetBrains Mono', monospace; font-size:clamp(24px,4vw,32px); margin:0 0 10px; font-weight:700; letter-spacing:-.01em; }
  p.tagline{ color:var(--ink-soft); font-size:15.5px; max-width:60ch; margin:0 0 44px; }

  section{ margin-bottom:44px; scroll-margin-top:44px; }
  h2{ font-family:'JetBrains Mono', monospace; font-size:18px; margin:0 0 14px; font-weight:600; border-bottom: 1px solid var(--line); padding-bottom: 6px; }
  h3{ font-family:'JetBrains Mono', monospace; font-size:14px; margin:20px 0 8px; font-weight:600; color:var(--ink); }
  p{ color:var(--ink-soft); font-size:15px; margin:0 0 12px; text-align: justify; }
  code{ font-family:'JetBrains Mono', monospace; background:var(--paper-raised); border:1px solid var(--line); padding:1px 5px; border-radius:4px; font-size:13px; color:var(--ink); }

  .formula-box{
    background:var(--code-bg); color:var(--code-text); font-family:'JetBrains Mono', monospace;
    border-radius:8px; padding:18px 20px; font-size:13.5px; margin:14px 0; line-height:1.8; overflow-x:auto;
  }
  .formula-box .comment{ color:#7d93a0; }

  ul.clean{ list-style:none; margin:10px 0; padding:0; }
  ul.clean li{ padding:9px 0; border-top:1px solid var(--line); font-size:14.5px; color:var(--ink-soft); }
  ul.clean li:last-child{ border-bottom:1px solid var(--line); }
  ul.clean strong{ color:var(--ink); }

  .pipeline{
    background:var(--paper-raised); border:1px solid var(--line); border-radius:10px;
    padding:20px 22px; font-family:'JetBrains Mono', monospace; font-size:12.5px; color:var(--ink-soft);
    line-height:2; margin:14px 0;
  }
  .pipeline .step{ color:var(--accent); font-weight:600; }

  .callout{
    border-radius:10px; padding:18px 20px; margin:16px 0; font-size:14.5px;
  }
  .callout.honest{ background:var(--warn-soft); border:1px solid #e9d2ac; color:var(--ink); }
  .callout.honest .eyebrow{ color:var(--warn); }
  .callout.good{ background:var(--accent-soft); border:1px solid #b8dccb; color:var(--ink); }
  .callout.good .eyebrow{ color:var(--accent); }

  .stack-grid{ display:flex; flex-wrap:wrap; gap:8px; margin-top:10px; }
  .stack-pill{ font-family:'JetBrains Mono', monospace; font-size:12px; background:var(--paper-raised); border:1px solid var(--line); padding:6px 11px; border-radius:7px; color:var(--ink); }

  footer{ margin-top:56px; padding-top:20px; border-top:1px solid var(--line); font-family:'JetBrains Mono', monospace; font-size:11px; color:var(--ink-soft); display: flex; justify-content: space-between; flex-wrap: wrap; gap: 10px; }

  @media (max-width:820px){
    .layout{ grid-template-columns:1fr; padding:32px 20px 100px; }
    nav.toc{ position:sticky; top:0; background:var(--paper); z-index:10; display:flex; flex-wrap:wrap; gap:2px 14px; padding-bottom:10px; border-bottom:1px solid var(--line); }
    .toc a{ border-left:none; border-bottom:none; padding:5px 2px; }
  }
</style>
</head>
<body>
<div class="layout">

  <nav class="toc" aria-label="Table of contents">
    <div class="toc-label">Contents</div>
    <a href="#intro">1. Introduction</a>
    <a href="#math">2. Risk Scoring Math</a>
    <a href="#data">3. Data Sources</a>
    <a href="#arch">4. Architecture</a>
    <a href="#crypto">5. Encryption Pipeline</a>
    <a href="#uses">6. Realistic Applications</a>
    <a href="#case-studies">7. Crisis Case Studies</a>
    <a href="#stack">8. Tech Stack</a>
  </nav>

  <main>
    <div class="eyebrow">Technical write-up</div>
    <h1>Global Environmental Risk Matrix (BERM v2.0)</h1>
    <p class="tagline">A decentralized, client-side risk-visualization prototype combining public health indicators with static multi-vector reference data. Built to demonstrate zero-data frontend architectures, sandboxed API integration, and edge browser-based cryptography for a general audience.</p>

    <section id="intro">
      <h2>1. Introduction</h2>
      <p>This is an independent, solo-built frontend software project. It functions entirely within a local browser sandbox—devoid of any backend server layers, central databases, or personal tracking cookies. Designed as a professional portfolio demonstration and architectural learning exercise, it showcases geo-spatial mapping, live public indicator parsing, and hardware-accelerated client-side cryptography. It is explicitly not an officially deployed or validated analytical instrument for any international agency, health network, or government institution.</p>
    </section>

    <section id="math">
      <h2>2. Risk Scoring Math</h2>
      <p>The dashboard calculates an illustrative dynamic threat index by adding a country's foundational baseline risk variable to weighted adjustments derived from the user's active interface toggles:</p>
      <div class="formula-box">
        R_dynamic = M_base + Σ Δ_layer
        <br><span class="comment">// R_dynamic: Cumulative risk score calculated locally in volatile client RAM</span>
        <br><span class="comment">// M_base: Pre-calibrated regional baseline multiplier representing historical disease burdens</span>
      </div>
      <p>Dynamic vector weight coefficients utilized inside this demo application:</p>
      <ul class="clean">
        <li><strong>Δ_viper</strong> (Arid/Desert Venoms) = +0.15</li>
        <li><strong>Δ_marine</strong> (Marine Neurotoxins) = +0.12</li>
        <li><strong>Δ_fungal</strong> (Resistant Fungi clusters) = +0.22</li>
        <li><strong>Δ_synthetic</strong> (Advanced Biosecurity Surveillance Flags) = +0.35</li>
      </ul>
      <p>The system sums these indicators and automatically maps the score onto a transparent risk scale: <strong>HIGH RISK</strong> &ge; 1.9, <strong>MODERATE RISK</strong> 1.3–1.9, and <strong>LOW RISK</strong> &lt; 1.3.</p>
      <div class="callout honest">
        <div class="eyebrow">Being direct about this</div>
        <p style="margin:0;">These specific layers and algebraic constants were selected to demonstrate operational state changes within the application UI, rather than being refined via predictive epidemiological modeling. It serves as a working scoring <em>mechanism</em> to evaluate how decentralized data strings mix, not as a verified clinical or border security diagnostics instrument.</p>
      </div>
    </section>

    <section id="data">
      <h2>3. Data Sources</h2>
      <h3>Live Ingested Metric Data</h3>
      <p>To verify the frontend's ability to fetch and parse external structures in real time, one authentic indicator is drawn directly from the open public Global Health Observatory OData API. The script invokes a native browser <code>fetch()</code> request to target the country's most recent life expectancy at birth record (index: <code>WHOSIS_000001</code>). This exchange is performed directly from the client's IP address with zero middleware or API keys required.</p>
      <h3>Static Reference Matrices</h3>
      <p>High-consequence environmental, zoonotic, and mycological risk summaries assigned per country exist as static structural objects written directly into the source file. These elements are loosely modeled on general public knowledge—such as familiar regional venomous species distributions or known pathogen patterns. They are not pulling from an live algorithmic data stream and have not been validated against active clinical or toxinology registries, serving as contextual reference text within the UI.</p>
      <h3>System Accuracy &amp; Informational Reliability</h3>
      <p>The system's live indicator outputs are exactly as reliable as the public global endpoints serving them. However, by decoupling data visualization from an application-specific backend server, the platform achieves total operational uptime immunity against dedicated database crashes, server configuration drops, or host credential expiration. If an external API is blocked or goes offline, the application cleanly falls back to its immutable internal static layers without failing.</p>
    </section>

    <section id="arch">
      <h2>4. Client-Side Architecture &amp; Zero-Data Storage Policy</h2>
      <p>The application enforces a strict, uncompromising <strong>Zero-Data Storage Policy</strong>. Because it is written as a unified, static front-end file, it possesses no physical mechanism to ingest or retain information outside of the current terminal. Its internal architecture yields precise security and reliability benefits:</p>
      <ul class="clean">
        <li><strong>No Relational Storage Footprint:</strong> There are no SQL or NoSQL databases, backend cloud logs, tracking pixels, or user state accounts.</li>
        <li><strong>Transient Memory Isolation:</strong> All calculations, spatial interactions, chosen passphrases, and interface layer toggles exist purely inside the browser's temporary, volatile RAM.</li>
        <li><strong>Total Volatility:</strong> The moment the operator reloads the page, navigates away, or exits the browser tab, the entire operational state machine is permanently deleted.</li>
      </ul>
      <div class="callout honest">
        <div class="eyebrow">Scope check</div>
        <p style="margin:0;">While a zero-trace lifecycle naturally inherits the standard advantages of basic unprivileged static websites, it is explicitly outlined here to highlight the project's layout approach: proving that multi-layered biological mapping can be evaluated at the edge without necessitating the surveillance liabilities of centralized database servers.</p>
      </div>
    </section>

    <section id="crypto">
      <h2>5. Encryption Pipeline &amp; Scannable QR Codes</h2>
      <p>The core technical feature of this system is an functional, edge-native symmetric cryptographic subsystem. When an operator types a symmetric key into the interface to lock a regional risk snapshot, the following pipeline executes instantly within the browser kernel via hardware-accelerated instructions:</p>
      <div class="pipeline">
        <span class="step">1. Passphrase Key Derivation</span> — The user's input string is fed into a native PBKDF2 primitive using SHA-256, performing 150,000 iterations over a high-entropy 16-byte random salt generated via <code>crypto.getRandomValues()</code> to construct a robust 256-bit symmetric cryptographic key.<br>
        <span class="step">2. Symmetric AES-GCM Encryption</span> — The raw JSON data block containing the calculated risk factors and current timestamp is transformed into ciphertext via the Advanced Encryption Standard in Galois/Counter Mode (AES-256-GCM), utilizing an independent 12-byte initialization vector (IV).<br>
        <span class="step">3. Binary-to-Text Serialization</span> — The generated salt, initialization vector, and raw ciphertext are compiled and encoded into standard, clean Base64 string bundles.<br>
        <span class="step">4. QR Matrix Transformation</span> — This text string package is converted directly into a clean vector graphic via <code>qrcode.js</code>, producing an encrypted QR code ready to be read by external field devices.
      </div>
      <p>Because the app leverages the browser's audited <code>crypto.subtle</code> layer, security checking is absolute. If a single bit of the scannable QR matrix text code is altered, or if a verifying officer inputs a mismatched passkey, the Galois Message Authentication Code (GMAC) check fails automatically. Instead of outputting corrupted or false variables, the engine throws a native exception and completely blocks data access, making unauthorized modifications obvious.</p>
      <div class="callout good">
        <div class="eyebrow">What this is</div>
        <p style="margin:0;">A robust, fully functional implementation of audited symmetric encryption standards running locally on user hardware. A mathematically sound feature demonstrating direct, secure, and disconnected client-side data serialization.</p>
      </div>
      <div class="callout honest">
        <div class="eyebrow">What this isn't</div>
        <p style="margin:0;">This architecture is not a public-key infrastructure (PKI), does not handle asymmetric identity tokens, and does not establish a network communication tunnel. Because no key-exchange mechanism is built into the script, both parties must distribute and share the symmetric passkey out-of-band beforehand.</p>
      </div>
    </section>

    <section id="uses">
      <h2>6. Realistic Applications &amp; Global Utility</h2>
      <p>The BERM v2.0 layout introduces an innovative structural roadmap for data validation across several critical real-world domains:</p>
      <ul class="clean">
        <li><strong>Privacy-Insulated Border Security:</strong> Customs, transit hubs, and immigration desks can verify incoming transit health matrices without tracking, logging, or centralizing the individual travel histories or personal identity markers of passengers, minimizing data privacy conflicts.</li>
        <li><strong>Infrastructure and Emergency Logistics:</strong> Field deployment vectors, maritime vessels, and non-governmental medical responses operating in regions with disrupted, monitored, or fragile infrastructure can parse, modify, and carry environmental vulnerability indexes with them entirely offline.</li>
        <li><strong>Oman Institutional Prototype Case:</strong> In countries balancing highly active trade hubs alongside specific regional environmental ecological zones (such as managing incoming international trade in Muscat alongside localized ecological vectors or regional toxinology exposures in Salalah), this layout offers rapid localized risk assessment. It enables local authorities to model dynamic vector trends locally at check-points without requiring a massive central server roll-out. *Note: This deployment remains an independent design prototype, showing client-side data manipulation options rather than active institutional deployment.</li>
      </ul>
    </section>

    <section id="case-studies">
      <h2>7. Real-World Public Health Case Studies</h2>
      <p>The core necessity of a decentralized, disconnected risk framework is highlighted by historical public health crises where database latency, rigid network demands, or geopolitical airspace border closures compromised coordination.</p>
      <h3>Case Study 1: Andes Orthohantavirus (Argentina)</h3>
      <p>During historical high-consequence Hantavirus outbreaks in South America, local clusters often outpaced the communication networks of centralized health departments. The BERM v2.0 prototype directly mirrors this reality by explicitly exposing a data reporting interval lag indicator (e.g., 4–9 days) directly within the interface. By isolating static environmental and zoonotic vectors from real-time networks, local containment teams can continue calculating field safety markers and regional dryness vectors completely offline, independent of broken external data links.</p>
      <h3>Case Study 2: Airspace Redirections &amp; Border Controls</h3>
      <p>In high-consequence global health contingencies, commercial flights carrying suspected exposures have faced international airspace rejections, preventing scheduled arrivals and forcing emergency technical diversions to alternate international hubs (such as Canada). During these high-friction situations, clearing aircraft requires quick, secure data validation that satisfies both the landing airport's security standards and international data protection acts. By utilizing encrypted QR tokens, an aircraft's threat profile can be audited locally at the runway edge with zero centralized server lookups. This allows customs officials to quickly verify critical safety data without triggering administrative logjams or data leak risks.</p>
    </section>

    <section id="stack">
      <h2>8. Tech Stack</h2>
      <div class="stack-grid">
        <span class="stack-pill">HTML5 / CSS3 (Semantic Layout)</span>
        <span class="stack-pill">Tailwind CSS (Responsive UI Assembly)</span>
        <span class="stack-pill">Vanilla EcmaScript (Asynchronous State Machine)</span>
        <span class="stack-pill">Leaflet.js 1.9.4 (Interactive Canvas Mapping)</span>
        <span class="stack-pill">CartoDB Dark Matter Tiles (High-Contrast Theme)</span>
        <span class="stack-pill">Font Awesome 6 (Vector Visual Cues)</span>
        <span class="stack-pill">qrcode.js (Client Text Vector Generation)</span>
        <span class="stack-pill">Web Crypto API (Subtle Cryptographic Primitives)</span>
        <span class="stack-pill">Public GHO OData API (Open Data Fetch Node)</span>
      </div>
    </section>

    <footer>
      <span>Global Health Risk Dashboard — Technical Write-up Edition (2026)</span>
      <span>Distributed under the MIT License</span>
    </footer>
    
    <section style="margin-top: 30px; padding: 15px; background: var(--paper-raised); border: 1px solid var(--line); border-radius: 6px; font-family: 'JetBrains Mono', monospace; font-size: 11px; color: var(--ink-soft);">
      <strong>MIT LICENSE</strong><br><br>
      Copyright (c) 2026 Global Risk Intelligence Framework Project Contributors<br><br>
      Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:<br><br>
      The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.<br><br>
      THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
    </section>
  </main>
</div>
</body>
</html>
