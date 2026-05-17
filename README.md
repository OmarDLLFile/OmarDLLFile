
<style>
  @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;500;600;700&family=Exo+2:wght@300;400;600&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body, .readme-root {
    font-family: 'Exo 2', sans-serif;
    background: #080c10;
    color: #c9d1d9;
    min-height: 100vh;
  }

  .readme-root {
    max-width: 780px;
    margin: 0 auto;
    padding: 2rem 1.5rem 4rem;
    position: relative;
  }

  .scan-line {
    position: fixed;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #00ffe1aa, transparent);
    animation: scan 4s linear infinite;
    z-index: 100;
    pointer-events: none;
  }

  @keyframes scan {
    0% { top: 0; opacity: 1; }
    90% { opacity: 0.3; }
    100% { top: 100vh; opacity: 0; }
  }

  /* HEADER */
  .header {
    text-align: center;
    padding: 3rem 0 2.5rem;
    position: relative;
  }

  .header::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 60% 40% at 50% 0%, #00ffe115 0%, transparent 70%);
    pointer-events: none;
  }

  .glitch-name {
    font-family: 'Rajdhani', sans-serif;
    font-size: 3rem;
    font-weight: 700;
    letter-spacing: 6px;
    color: #fff;
    text-transform: uppercase;
    position: relative;
    display: inline-block;
  }

  .glitch-name::before,
  .glitch-name::after {
    content: attr(data-text);
    position: absolute;
    top: 0; left: 0; right: 0;
    overflow: hidden;
  }

  .glitch-name::before {
    color: #00ffe1;
    animation: glitch1 3s infinite;
    clip-path: polygon(0 20%, 100% 20%, 100% 50%, 0 50%);
  }

  .glitch-name::after {
    color: #ff4d6d;
    animation: glitch2 3s infinite;
    clip-path: polygon(0 55%, 100% 55%, 100% 80%, 0 80%);
  }

  @keyframes glitch1 {
    0%, 90%, 100% { transform: translateX(0); opacity: 0; }
    92% { transform: translateX(-3px); opacity: 0.7; }
    94% { transform: translateX(3px); opacity: 0.7; }
    96% { transform: translateX(-2px); opacity: 0.5; }
    98% { transform: translateX(0); opacity: 0; }
  }

  @keyframes glitch2 {
    0%, 91%, 100% { transform: translateX(0); opacity: 0; }
    93% { transform: translateX(3px); opacity: 0.6; }
    95% { transform: translateX(-3px); opacity: 0.6; }
    97% { transform: translateX(2px); opacity: 0.4; }
    99% { transform: translateX(0); opacity: 0; }
  }

  .title-badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.85rem;
    color: #00ffe1;
    letter-spacing: 3px;
    margin-top: 0.75rem;
    display: block;
    opacity: 0.85;
  }

  .tagline {
    font-family: 'Share Tech Mono', monospace;
    color: #8b949e;
    font-size: 0.9rem;
    margin-top: 1.5rem;
    line-height: 1.8;
  }

  .tagline span {
    color: #00ffe1;
    font-weight: 600;
  }

  /* STATUS BAR */
  .status-bar {
    display: flex;
    gap: 0.5rem;
    justify-content: center;
    flex-wrap: wrap;
    margin: 1.5rem 0 0;
  }

  .status-pill {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 1.5px;
    padding: 4px 12px;
    border-radius: 2px;
    border: 1px solid;
    text-transform: uppercase;
  }

  .pill-green { border-color: #2ea04340; color: #3fb950; background: #2ea04312; }
  .pill-cyan  { border-color: #00ffe140; color: #00ffe1; background: #00ffe112; }
  .pill-red   { border-color: #ff4d6d40; color: #ff4d6d; background: #ff4d6d12; }
  .pill-amber { border-color: #d2992040; color: #d29920; background: #d2992012; }

  /* SECTION */
  .section {
    margin: 2.5rem 0;
    opacity: 0;
    transform: translateY(16px);
    animation: fadeUp 0.5s ease forwards;
  }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }
  .section:nth-child(7) { animation-delay: 0.6s; }
  .section:nth-child(8) { animation-delay: 0.7s; }
  .section:nth-child(9) { animation-delay: 0.8s; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 1.2rem;
  }

  .section-header h2 {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.1rem;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: #fff;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, #00ffe130, transparent);
  }

  .section-icon {
    font-size: 1rem;
    color: #00ffe1;
  }

  /* CODE BLOCK */
  .code-block {
    background: #0d1117;
    border: 1px solid #21262d;
    border-left: 3px solid #00ffe1;
    border-radius: 4px;
    padding: 1.2rem 1.4rem;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.82rem;
    line-height: 2;
    color: #8b949e;
  }

  .code-block .key { color: #79c0ff; }
  .code-block .val { color: #a5d6ff; }
  .code-block .str { color: #a8ff78; }
  .code-block .comment { color: #3d4a57; }

  /* SKILL GRID */
  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 0.6rem;
  }

  .skill-tag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 1px;
    padding: 7px 10px;
    border: 1px solid #21262d;
    border-radius: 3px;
    background: #0d1117;
    color: #8b949e;
    text-align: center;
    transition: all 0.25s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .skill-tag::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 0; height: 1px;
    background: #00ffe1;
    transition: width 0.3s;
  }

  .skill-tag:hover {
    border-color: #00ffe140;
    color: #00ffe1;
    background: #00ffe108;
  }

  .skill-tag:hover::before { width: 100%; }

  /* PROJECT CARDS */
  .project-card {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 6px;
    padding: 1.2rem 1.4rem;
    margin-bottom: 0.75rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.2s;
    cursor: pointer;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--accent, #00ffe1);
    opacity: 0.5;
    transition: opacity 0.3s;
  }

  .project-card:hover {
    border-color: var(--accent, #00ffe1);
    transform: translateX(4px);
  }

  .project-card:hover::before { opacity: 1; }

  .project-card h3 {
    font-family: 'Rajdhani', sans-serif;
    font-weight: 600;
    font-size: 0.95rem;
    letter-spacing: 2px;
    color: #fff;
    margin-bottom: 0.5rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .project-card h3 .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent, #00ffe1);
    display: inline-block;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.7); }
  }

  .project-card ul {
    list-style: none;
    padding: 0;
  }

  .project-card ul li {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.78rem;
    color: #6e7681;
    padding: 2px 0;
    padding-left: 1rem;
    position: relative;
  }

  .project-card ul li::before {
    content: '›';
    position: absolute;
    left: 0;
    color: var(--accent, #00ffe1);
  }

  /* THINKING BLOCK */
  .thinking-block {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 4px;
    padding: 1.4rem;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.82rem;
    line-height: 2.2;
    position: relative;
    overflow: hidden;
  }

  .thinking-block::after {
    content: '';
    position: absolute;
    top: 0; right: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(180deg, transparent, #00ffe150, transparent);
    animation: lineSweep 4s ease-in-out infinite;
  }

  @keyframes lineSweep {
    0%, 100% { opacity: 0; }
    50% { opacity: 1; }
  }

  .thinking-block .eq-line {
    color: #3d4a57;
    margin-bottom: 0.5rem;
    font-size: 0.7rem;
    letter-spacing: 1px;
  }

  .thinking-block .logic-line {
    display: flex;
    align-items: flex-start;
    gap: 0.5rem;
    padding: 2px 0;
  }

  .thinking-block .arrow { color: #00ffe1; font-size: 0.9rem; }
  .thinking-block .text { color: #8b949e; }
  .thinking-block .em { color: #f0c674; }

  /* MODE SELECTOR */
  .mode-selector {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0.6rem;
  }

  .mode-card {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 5px;
    padding: 1rem 1.1rem;
    cursor: pointer;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .mode-card:hover, .mode-card.active {
    border-color: var(--mc, #00ffe1);
    background: #00ffe108;
  }

  .mode-card .mode-icon {
    font-size: 1.3rem;
    margin-bottom: 0.4rem;
    display: block;
  }

  .mode-card .mode-title {
    font-family: 'Rajdhani', sans-serif;
    font-weight: 600;
    font-size: 0.85rem;
    letter-spacing: 2px;
    color: #fff;
    text-transform: uppercase;
    display: block;
    margin-bottom: 0.3rem;
  }

  .mode-card .mode-desc {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.7rem;
    color: #6e7681;
    line-height: 1.5;
  }

  .mode-output {
    margin-top: 1rem;
    padding: 1rem 1.2rem;
    background: #0d1117;
    border: 1px solid #21262d;
    border-left: 3px solid #00ffe1;
    border-radius: 4px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.78rem;
    color: #8b949e;
    line-height: 1.9;
    min-height: 60px;
    transition: all 0.3s;
  }

  /* WEAK POINTS */
  .weak-list {
    list-style: none;
  }

  .weak-list li {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.8rem;
    color: #6e7681;
    padding: 6px 0 6px 1.2rem;
    border-bottom: 1px solid #21262d20;
    position: relative;
    transition: color 0.2s;
  }

  .weak-list li:hover { color: #d29920; }

  .weak-list li::before {
    content: '⚠';
    position: absolute;
    left: 0;
    color: #d2992060;
    font-size: 0.7rem;
  }

  /* STATS SECTION */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0.6rem;
  }

  .stat-card {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 5px;
    padding: 1rem;
    text-align: center;
  }

  .stat-card img {
    width: 100%;
    border-radius: 4px;
    filter: brightness(0.95);
  }

  /* PHILOSOPHY */
  .philosophy {
    text-align: center;
    padding: 2.5rem 1rem;
    position: relative;
  }

  .philosophy::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 50%, #00ffe108 0%, transparent 70%);
    pointer-events: none;
  }

  .philosophy .quote-mark {
    font-family: 'Rajdhani', sans-serif;
    font-size: 5rem;
    color: #00ffe115;
    line-height: 0.5;
    user-select: none;
    display: block;
    margin-bottom: 1rem;
  }

  .philosophy p {
    font-family: 'Rajdhani', sans-serif;
    font-size: 1.15rem;
    font-weight: 300;
    color: #8b949e;
    letter-spacing: 1px;
    line-height: 2;
    max-width: 500px;
    margin: 0 auto;
  }

  .philosophy p strong {
    color: #fff;
    font-weight: 600;
  }

  .philosophy p em {
    color: #00ffe1;
    font-style: normal;
  }

  /* DIVIDER */
  .divider {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin: 0.5rem 0;
    opacity: 0.25;
  }

  .divider span {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.6rem;
    letter-spacing: 3px;
    color: #00ffe1;
    white-space: nowrap;
  }

  .divider hr {
    flex: 1;
    border: none;
    border-top: 1px solid #00ffe1;
  }

  /* TERMINAL CURSOR */
  .cursor {
    display: inline-block;
    width: 8px; height: 14px;
    background: #00ffe1;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
    margin-left: 4px;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  /* CONNECT LINKS */
  .connect-row {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
    margin-top: 0.5rem;
  }

  .connect-btn {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 1.5px;
    padding: 6px 14px;
    border: 1px solid #21262d;
    border-radius: 3px;
    background: #0d1117;
    color: #8b949e;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
    text-transform: uppercase;
  }

  .connect-btn:hover {
    border-color: #00ffe140;
    color: #00ffe1;
    background: #00ffe108;
  }

  .skill-category {
    margin-bottom: 1rem;
  }

  .skill-category-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 3px;
    color: #3d4a57;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }
</style>

<div class="readme-root">
  <div class="scan-line"></div>

  <!-- HEADER -->
  <div class="header section">
    <span class="title-badge">// IDENTITY FILE LOADED</span>
    <h1 class="glitch-name" data-text="OMAR">OMAR</h1>
    <span class="title-badge" style="color:#8b949e; margin-top: 0.4rem; letter-spacing:2px;">Cyber Security Engineer In Progress</span>
    <p class="tagline">
      I <span>build</span> systems. I <span>break</span> them. I learn what broke.<br>
      <span style="color:#ff4d6d;">Attack surfaces</span> are just undocumented features.
    </p>
    <div class="status-bar">
      <span class="status-pill pill-green">● ACTIVE</span>
      <span class="status-pill pill-cyan">STUDENT / RESEARCHER</span>
      <span class="status-pill pill-amber">THREAT DETECTION</span>
      <span class="status-pill pill-red">BREAKING THINGS</span>
    </div>
  </div>

  <div class="divider"><hr><span>[ SYSTEM PROFILE ]</span><hr></div>

  <!-- IDENTITY LAYER -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>Identity Layer</h2>
      <div class="section-line"></div>
    </div>
    <div class="code-block">
      <div><span class="key">name</span>:        <span class="str">Omar</span></div>
      <div><span class="key">status</span>:      <span class="str">Student / Security Researcher</span>  <span class="cursor"></span></div>
      <div><span class="key">focus</span>:       <span class="val">Cyber Security + System Design Thinking</span></div>
      <div><span class="key">mission</span>:     <span class="val">Understand how systems fail in the real world</span></div>
      <div><span class="key">mindset</span>:     <span class="str">If I cannot break it, I do not understand it</span></div>
      <div style="margin-top: 0.5rem;"><span class="comment">/* Not looking for easy paths — looking for the right ones */</span></div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>Current Projects</h2>
      <div class="section-line"></div>
    </div>

    <div class="project-card" style="--accent: #00ffe1;">
      <h3><span class="dot"></span>PACKET SNIFFER → EDR PROTOTYPE</h3>
      <ul>
        <li>Captures and analyzes live network traffic in real time</li>
        <li>Detects suspicious behavioral patterns across flows</li>
        <li>Evolving toward automated blocking and alerting response</li>
        <li>Custom threat scoring on packet-level anomalies</li>
      </ul>
    </div>

    <div class="project-card" style="--accent: #79c0ff;">
      <h3><span class="dot" style="background:#79c0ff;animation-delay:0.5s;"></span>AI-POWERED IDS/IPS — SUDOSOC</h3>
      <ul>
        <li>Isolation Forest + Random Forest + XGBoost inference pipeline</li>
        <li>Real-time monitoring dashboard with live threat visualization</li>
        <li>Bilingual Arabic/English platform with matrix rain aesthetics</li>
        <li>Training pipeline on UNSW-NB15-style network flow data</li>
      </ul>
    </div>

    <div class="project-card" style="--accent: #f0c674;">
      <h3><span class="dot" style="background:#f0c674;animation-delay:1s;"></span>SMART IOT SECURITY SYSTEM</h3>
      <ul>
        <li>ESP32 with hand gesture + voice + eye tracking + face recognition</li>
        <li>Controls servo motors and buzzers via multi-modal input</li>
        <li>Sensor-based embedded automation layer</li>
      </ul>
    </div>

    <div class="project-card" style="--accent: #a5d6ff;">
      <h3><span class="dot" style="background:#a5d6ff;animation-delay:1.5s;"></span>SYSTEM MONITORING TOOL</h3>
      <ul>
        <li>Linux health and resource tracking in Bash</li>
        <li>Lightweight observability — no bloat, no dependencies</li>
        <li>Foundation toward red team tooling automation</li>
      </ul>
    </div>
  </div>

  <div class="divider"><hr><span>[ SKILL MATRIX ]</span><hr></div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>Skill Stack</h2>
      <div class="section-line"></div>
    </div>

    <div class="skill-category">
      <div class="skill-category-label">// Languages</div>
      <div class="skill-grid">
        <div class="skill-tag">C</div>
        <div class="skill-tag">C++</div>
        <div class="skill-tag">Python</div>
        <div class="skill-tag">JavaScript</div>
        <div class="skill-tag">Bash</div>
        <div class="skill-tag">PHP</div>
      </div>
    </div>

    <div class="skill-category">
      <div class="skill-category-label">// Security</div>
      <div class="skill-grid">
        <div class="skill-tag">Wireshark</div>
        <div class="skill-tag">Nmap</div>
        <div class="skill-tag">Burp Suite</div>
        <div class="skill-tag">Kali Linux</div>
        <div class="skill-tag">Scapy</div>
        <div class="skill-tag">OWASP</div>
      </div>
    </div>

    <div class="skill-category">
      <div class="skill-category-label">// Backend & AI</div>
      <div class="skill-grid">
        <div class="skill-tag">Node.js</div>
        <div class="skill-tag">Express</div>
        <div class="skill-tag">Laravel</div>
        <div class="skill-tag">MongoDB</div>
        <div class="skill-tag">MySQL</div>
        <div class="skill-tag">XGBoost</div>
        <div class="skill-tag">Isolation Forest</div>
        <div class="skill-tag">Firebase</div>
      </div>
    </div>

    <div class="skill-category">
      <div class="skill-category-label">// Embedded & Tools</div>
      <div class="skill-grid">
        <div class="skill-tag">ESP32</div>
        <div class="skill-tag">Arduino</div>
        <div class="skill-tag">Ubuntu</div>
        <div class="skill-tag">Flutter</div>
        <div class="skill-tag">Git</div>
        <div class="skill-tag">REST APIs</div>
      </div>
    </div>
  </div>

  <!-- MODE SELECTOR -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>Operating Mode</h2>
      <div class="section-line"></div>
    </div>
    <div class="mode-selector">
      <div class="mode-card" style="--mc: #00ffe1;" onclick="selectMode(this, 'security')">
        <span class="mode-icon">🕵️</span>
        <span class="mode-title">Security Research</span>
        <span class="mode-desc">Packet analysis, exploitation mindset, threat modeling</span>
      </div>
      <div class="mode-card" style="--mc: #79c0ff;" onclick="selectMode(this, 'builder')">
        <span class="mode-icon">🧱</span>
        <span class="mode-title">System Builder</span>
        <span class="mode-desc">Backend architecture, tools, automation pipelines</span>
      </div>
      <div class="mode-card" style="--mc: #f0c674;" onclick="selectMode(this, 'algorithm')">
        <span class="mode-icon">🧠</span>
        <span class="mode-title">Algorithm Thinker</span>
        <span class="mode-desc">Problem solving, ECPC training, competitive C++</span>
      </div>
      <div class="mode-card" style="--mc: #a8ff78;" onclick="selectMode(this, 'embedded')">
        <span class="mode-icon">⚙️</span>
        <span class="mode-title">Embedded Engineer</span>
        <span class="mode-desc">ESP32, IoT, hardware integration, sensor systems</span>
      </div>
    </div>
    <div class="mode-output" id="mode-output">
      <span style="color:#3d4a57;">// Select an operating mode above to reveal active objectives</span>
    </div>
  </div>

  <div class="divider"><hr><span>[ SELF DIAGNOSTICS ]</span><hr></div>

  <!-- WEAK POINTS -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>Known Vulnerabilities</h2>
      <div class="section-line"></div>
    </div>
    <div class="code-block" style="margin-bottom: 0.75rem; font-size: 0.72rem; color: #3d4a57; letter-spacing:2px;">// Transparency is the first step toward patching</div>
    <ul class="weak-list">
      <li>Advanced low-level exploitation skills — still strengthening</li>
      <li>Real enterprise SOC exposure — limited so far</li>
      <li>Production-scale security systems — not yet deployed in the wild</li>
      <li>Sometimes builds tools instead of mastering fundamentals deeply</li>
      <li>Explaining complex security concepts clearly — in progress</li>
    </ul>
  </div>

  <!-- THINKING MODEL -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>How I Think</h2>
      <div class="section-line"></div>
    </div>
    <div class="thinking-block">
      <div class="eq-line">// THREAT MODEL :: COGNITIVE FRAMEWORK</div>
      <div class="logic-line">
        <span class="arrow">→</span>
        <span class="text">System = <span class="em">Input</span> → Processing → <span style="color:#ff4d6d;">Failure points</span> → Attack surface</span>
      </div>
      <div class="logic-line">
        <span class="arrow">→</span>
        <span class="text">Every component is a <span class="em">trust boundary</span> until proven otherwise</span>
      </div>
      <div class="logic-line">
        <span class="arrow">→</span>
        <span class="text">If I cannot <span style="color:#ff4d6d;">break it</span>, I do not understand it</span>
      </div>
      <div class="logic-line">
        <span class="arrow">→</span>
        <span class="text">If I cannot <span class="em">explain it</span>, I do not own it</span>
      </div>
      <div class="logic-line">
        <span class="arrow">→</span>
        <span class="text">Complexity hides risk — <span class="em">simplify until the risk is visible</span></span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <h2>GitHub Activity</h2>
      <div class="section-line"></div>
    </div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=OmarDLLFile&show_icons=true&theme=tokyonight&bg_color=0d1117&border_color=21262d&icon_color=00ffe1&title_color=ffffff&text_color=8b949e&hide_border=false" alt="GitHub Stats" />
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=OmarDLLFile&theme=tokyonight&background=0d1117&border=21262d&ring=00ffe1&fire=ff4d6d&currStreakLabel=ffffff" alt="Streak Stats" />
      </div>
    </div>
  </div>

  <!-- PHILOSOPHY -->
  <div class="section">
    <div class="divider"><hr><span>[ CORE PHILOSOPHY ]</span><hr></div>
    <div class="philosophy">
      <span class="quote-mark">"</span>
      <p>
        Systems don't fail <strong>randomly.</strong><br>
        They fail because someone <em>assumed</em> they wouldn't.<br>
        My job is to <strong>question that assumption</strong> —<br>
        before someone else does it for me.
      </p>
    </div>
  </div>

</div>

<script>
const modeData = {
  security: {
    color: '#00ffe1',
    lines: [
      '> MODE: SECURITY RESEARCH',
      '> OBJECTIVE: Understand how systems fail before defenders do',
      '> CURRENT: Building EDR prototype — packet capture → threat scoring',
      '> STUDYING: Network exploitation, OWASP top 10, reverse engineering basics',
      '> PLATFORM: TryHackMe | Hack The Box | Custom tooling',
    ]
  },
  builder: {
    color: '#79c0ff',
    lines: [
      '> MODE: SYSTEM BUILDER',
      '> OBJECTIVE: Engineer tools that actually work in production',
      '> CURRENT: SudoSOC platform — AI-powered IDS/IPS + dashboard',
      '> STACK: Python / Node.js / Laravel / MongoDB / Firebase',
      '> PHILOSOPHY: Build it so well it becomes the reference',
    ]
  },
  algorithm: {
    color: '#f0c674',
    lines: [
      '> MODE: ALGORITHM THINKER',
      '> OBJECTIVE: Train the mind to solve under pressure',
      '> CURRENT: C++ competitive programming — ECPC prep track',
      '> FOCUS: Data structures, graph algorithms, dynamic programming',
      '> BELIEF: Algorithms are the grammar of problem solving',
    ]
  },
  embedded: {
    color: '#a8ff78',
    lines: [
      '> MODE: EMBEDDED ENGINEER',
      '> OBJECTIVE: Close the gap between software and physical systems',
      '> CURRENT: ESP32 multi-modal control — gesture + voice + vision',
      '> HW: Arduino / Servo motors / Ultrasonic / IR sensors',
      '> VISION: Security starts at the hardware boundary',
    ]
  }
};

function selectMode(el, mode) {
  document.querySelectorAll('.mode-card').forEach(c => c.classList.remove('active'));
  el.classList.add('active');
  const data = modeData[mode];
  const out = document.getElementById('mode-output');
  out.style.borderLeftColor = data.color;
  out.innerHTML = '';
  let i = 0;
  function typeLine() {
    if (i >= data.lines.length) return;
    const div = document.createElement('div');
    div.style.color = i === 0 ? data.color : '#8b949e';
    div.style.fontWeight = i === 0 ? '600' : '400';
    div.textContent = data.lines[i];
    out.appendChild(div);
    i++;
    setTimeout(typeLine, 120);
  }
  typeLine();
}
</script>
