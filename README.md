<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Futures Risk Toolkit — README</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=IBM+Plex+Mono:wght@400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #0b0e14;
      --surface: #111520;
      --card: #161c2b;
      --border: #1e2840;
      --accent: #00d4aa;
      --accent2: #3b82f6;
      --accent3: #f59e0b;
      --text: #dce6f5;
      --muted: #7a8aaa;
      --heading: #ffffff;
      --mono: 'IBM Plex Mono', monospace;
      --display: 'Syne', sans-serif;
      --body: 'DM Sans', sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--body);
      font-size: 15.5px;
      line-height: 1.75;
      min-height: 100vh;
    }

    /* ── HEADER ── */
    header {
      background: linear-gradient(135deg, #0d1220 0%, #0b1a2e 60%, #0e1a14 100%);
      border-bottom: 1px solid var(--border);
      padding: 64px 48px 52px;
      position: relative;
      overflow: hidden;
    }

    header::before {
      content: '';
      position: absolute;
      top: -80px; right: -80px;
      width: 420px; height: 420px;
      background: radial-gradient(circle, rgba(0,212,170,0.07) 0%, transparent 70%);
      border-radius: 50%;
    }
    header::after {
      content: '';
      position: absolute;
      bottom: -60px; left: -60px;
      width: 320px; height: 320px;
      background: radial-gradient(circle, rgba(59,130,246,0.06) 0%, transparent 70%);
      border-radius: 50%;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-family: var(--mono);
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--accent);
      background: rgba(0,212,170,0.08);
      border: 1px solid rgba(0,212,170,0.2);
      border-radius: 20px;
      padding: 5px 14px;
      margin-bottom: 20px;
    }
    .badge::before { content: '⬡'; font-size: 10px; }

    header h1 {
      font-family: var(--display);
      font-size: clamp(2.2rem, 5vw, 3.4rem);
      font-weight: 800;
      color: var(--heading);
      line-height: 1.1;
      letter-spacing: -0.02em;
      margin-bottom: 14px;
    }
    header h1 span { color: var(--accent); }

    header p.tagline {
      font-size: 16px;
      font-weight: 300;
      color: var(--muted);
      max-width: 560px;
      margin-bottom: 28px;
    }

    .live-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: var(--mono);
      font-size: 12.5px;
      color: var(--accent2);
      background: rgba(59,130,246,0.07);
      border: 1px solid rgba(59,130,246,0.2);
      border-radius: 6px;
      padding: 8px 16px;
      text-decoration: none;
      transition: background 0.2s;
    }
    .live-link:hover { background: rgba(59,130,246,0.14); }
    .live-link::before { content: '↗'; font-style: normal; }

    /* ── LAYOUT ── */
    .container {
      max-width: 860px;
      margin: 0 auto;
      padding: 0 40px 80px;
    }

    /* ── SECTIONS ── */
    section {
      margin-top: 56px;
    }

    h2 {
      font-family: var(--display);
      font-size: 1.55rem;
      font-weight: 700;
      color: var(--heading);
      letter-spacing: -0.01em;
      margin-bottom: 20px;
      padding-bottom: 12px;
      border-bottom: 1px solid var(--border);
      display: flex;
      align-items: center;
      gap: 10px;
    }
    h2 .icon {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 28px; height: 28px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      font-size: 13px;
      flex-shrink: 0;
    }

    h3 {
      font-family: var(--display);
      font-size: 1.05rem;
      font-weight: 600;
      color: var(--heading);
      margin: 28px 0 10px;
      letter-spacing: 0.01em;
    }

    p { margin-bottom: 12px; color: var(--text); font-weight: 300; }

    /* ── FORMULA CARDS ── */
    .formula-group {
      display: flex;
      flex-direction: column;
      gap: 14px;
      margin-top: 18px;
    }

    .formula-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent);
      border-radius: 8px;
      padding: 18px 22px;
    }
    .formula-card .step-label {
      font-family: var(--mono);
      font-size: 10.5px;
      font-weight: 500;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 8px;
    }
    .formula-card .formula {
      font-family: var(--mono);
      font-size: 13.5px;
      color: #c8d8f8;
      background: rgba(0,0,0,0.3);
      border-radius: 5px;
      padding: 10px 14px;
      margin: 8px 0;
      border: 1px solid rgba(255,255,255,0.04);
    }
    .formula-card p {
      font-size: 13.5px;
      color: var(--muted);
      margin: 6px 0 0;
    }

    /* ── FEATURE GRID ── */
    .feature-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 12px;
      margin-top: 16px;
    }
    .feature-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 14px 18px;
      font-size: 13.5px;
      color: var(--text);
      font-weight: 300;
      display: flex;
      align-items: flex-start;
      gap: 10px;
    }
    .feature-item::before {
      content: '✦';
      color: var(--accent);
      font-size: 10px;
      margin-top: 4px;
      flex-shrink: 0;
    }

    /* ── STRESS TEST SCENARIOS ── */
    .scenario-row {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 16px;
    }
    .scenario-pill {
      font-family: var(--mono);
      font-size: 12px;
      padding: 6px 14px;
      border-radius: 20px;
      border: 1px solid;
    }
    .scenario-pill.s1 { color: #fbbf24; border-color: rgba(251,191,36,0.3); background: rgba(251,191,36,0.05); }
    .scenario-pill.s2 { color: #f97316; border-color: rgba(249,115,22,0.3); background: rgba(249,115,22,0.05); }
    .scenario-pill.s3 { color: #ef4444; border-color: rgba(239,68,68,0.3); background: rgba(239,68,68,0.05); }
    .scenario-pill.s4 { color: var(--accent2); border-color: rgba(59,130,246,0.3); background: rgba(59,130,246,0.05); }

    /* ── CALLOUT BOX ── */
    .callout {
      background: rgba(0,212,170,0.04);
      border: 1px solid rgba(0,212,170,0.18);
      border-left: 3px solid var(--accent);
      border-radius: 8px;
      padding: 16px 20px;
      margin-top: 18px;
    }
    .callout p { margin: 0; font-size: 14px; }
    .callout strong { color: var(--accent); }

    /* ── TECH STACK ── */
    .tech-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 16px;
    }
    .tech-tag {
      font-family: var(--mono);
      font-size: 12px;
      padding: 5px 13px;
      border-radius: 5px;
      background: var(--card);
      border: 1px solid var(--border);
      color: var(--muted);
    }

    /* ── ENHANCEMENTS LIST ── */
    .enhance-list {
      list-style: none;
      margin-top: 14px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }
    @media (max-width: 520px) { .enhance-list { grid-template-columns: 1fr; } }
    .enhance-list li {
      font-size: 13.5px;
      color: var(--muted);
      font-weight: 300;
      padding: 8px 14px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .enhance-list li::before {
      content: '→';
      color: var(--accent3);
      font-family: var(--mono);
      font-size: 11px;
    }

    /* ── OUTCOMES ── */
    .outcome-list {
      list-style: none;
      margin-top: 14px;
      display: flex;
      flex-direction: column;
      gap: 8px;
    }
    .outcome-list li {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 14px;
      color: var(--text);
      font-weight: 300;
    }
    .outcome-list li::before {
      content: '';
      width: 6px; height: 6px;
      background: var(--accent2);
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* ── FOOTER ── */
    footer {
      background: var(--surface);
      border-top: 1px solid var(--border);
      padding: 32px 40px;
      text-align: center;
    }
    footer p { font-size: 13px; color: var(--muted); margin: 4px 0; }
    footer a { color: var(--accent); text-decoration: none; }
    footer .disclaimer {
      max-width: 600px;
      margin: 16px auto 0;
      font-size: 12px;
      color: #4a5568;
      line-height: 1.6;
      font-style: italic;
    }

    /* ── DIVIDER ── */
    .divider {
      border: none;
      border-top: 1px solid var(--border);
      margin: 0;
    }

    /* ── MARGIN CALLOUT ── */
    .margin-box {
      background: rgba(239,68,68,0.04);
      border: 1px solid rgba(239,68,68,0.18);
      border-left: 3px solid #ef4444;
      border-radius: 8px;
      padding: 16px 20px;
      margin-top: 18px;
    }
    .margin-box p { margin: 0; font-size: 14px; }
    .margin-box strong { color: #ef4444; }
  </style>
</head>
<body>

<!-- ── HEADER ── -->
<header>
  <div class="badge">Educational Prototype · Financial Risk Analytics</div>
  <h1>Futures Risk <span>Toolkit</span></h1>
  <p class="tagline">A web-based dashboard for understanding futures exposure, tick-based loss calculation, margin utilization, and stress testing logic.</p>
  <a class="live-link" href="https://arham7s.github.io/FRT/" target="_blank">arham7s.github.io/FRT</a>
</header>

<!-- ── CONTENT ── -->
<div class="container">

  <!-- Project Overview -->
  <section>
    <h2><span class="icon">◈</span> Project Overview</h2>
    <p>The Futures Risk Toolkit is an educational prototype that demonstrates how exchange-style risk evaluation works at the trade level. The system converts market price movements into monetary risk, helping users understand:</p>
    <div class="feature-grid">
      <div class="feature-item">How stop loss placement determines maximum possible loss</div>
      <div class="feature-item">How futures contract specifications impact exposure</div>
      <div class="feature-item">Why margin is different from actual risk</div>
      <div class="feature-item">How extreme market shocks affect trading capital</div>
    </div>
    <p style="margin-top:18px; font-size:13.5px; color:var(--muted);">This project is inspired by simplified workflows used in derivatives exchanges, clearing corporations, and brokerage risk management desks.</p>
  </section>

  <!-- Core Concept -->
  <section>
    <h2><span class="icon">⬡</span> Core Concept — Tick-Based Risk</h2>
    <p>Futures contracts move in minimum price increments called <strong>ticks</strong>. Each tick has a fixed monetary value, which means even small price movements can result in significant financial gains or losses.</p>
    <div class="callout">
      <p>The toolkit focuses on translating: <strong>Price Movement → Tick Movement → Monetary Risk</strong><br/>
      <span style="color:var(--muted); font-size:13px;">This is the fundamental idea behind futures risk estimation.</span></p>
    </div>
  </section>

  <!-- Trade Risk Calculation -->
  <section>
    <h2><span class="icon">∑</span> Trade Risk Calculation Logic</h2>
    <div class="formula-group">

      <div class="formula-card">
        <div class="step-label">Step 1 — Price Risk</div>
        <p>Compute the difference between entry price and stop loss price.</p>
        <div class="formula">Price Risk = | Entry Price − Stop Loss Price |</div>
        <p>Represents the maximum adverse market move tolerated.</p>
      </div>

      <div class="formula-card">
        <div class="step-label">Step 2 — Ticks at Risk</div>
        <p>Since futures move in ticks, convert price risk into tick count.</p>
        <div class="formula">Ticks at Risk = Price Risk / Tick Size</div>
        <p>Tells us how many minimum price movements are at risk.</p>
      </div>

      <div class="formula-card">
        <div class="step-label">Step 3 — Monetary Risk per Contract</div>
        <p>Each tick has a dollar value.</p>
        <div class="formula">Risk per Contract = Ticks at Risk × Tick Value</div>
        <p>Maximum possible loss on one futures contract.</p>
      </div>

      <div class="formula-card">
        <div class="step-label">Step 4 — Total Trade Risk</div>
        <p>If multiple contracts are traded:</p>
        <div class="formula">Total Trade Risk = Risk per Contract × Number of Contracts</div>
        <p>Total potential financial exposure of the trade.</p>
      </div>

    </div>
  </section>

  <!-- Margin vs Risk -->
  <section>
    <h2><span class="icon">⚠</span> Understanding Margin vs Risk</h2>
    <p>Futures trading requires traders to deposit <em>initial margin</em>, which acts as collateral. However:</p>
    <div class="margin-box">
      <p><strong>Margin is NOT the maximum possible loss.</strong></p>
    </div>
    <p style="margin-top:16px;">The toolkit highlights situations where:</p>
    <div class="feature-grid" style="margin-top:10px;">
      <div class="feature-item">Trade risk exceeds margin requirement</div>
      <div class="feature-item">Trader capital may be insufficient</div>
      <div class="feature-item">Potential default exposure can arise</div>
    </div>
    <p style="margin-top:14px; font-size:13.5px; color:var(--muted);">This is an important concept in clearing-house risk management.</p>
  </section>

  <!-- Stress Testing -->
  <section>
    <h2><span class="icon">◎</span> Stress Testing Engine</h2>
    <p>The application simulates adverse market scenarios to estimate worst-case losses using simplified SPAN-style logic.</p>

    <h3>Example Stress Scenarios</h3>
    <div class="scenario-row">
      <div class="scenario-pill s1">−2% Market Move</div>
      <div class="scenario-pill s2">−5% Volatility Shock</div>
      <div class="scenario-pill s3">−10% Extreme Stress Event</div>
      <div class="scenario-pill s4">Custom User-Defined Shock</div>
    </div>

    <h3>Shocked Price Formula</h3>
    <div class="formula-card" style="margin-top:10px;">
      <div class="step-label">Long Positions</div>
      <div class="formula">Shocked Price = Entry Price × (1 − Shock %)</div>
      <p>Loss is then computed using tick-based risk logic.</p>
    </div>

    <div class="callout" style="margin-top:16px;">
      <p>Stress testing helps users understand how volatility impacts trading capital, whether margin can absorb stress losses, and how leverage amplifies exposure.</p>
    </div>
  </section>

  <!-- Position Sizing -->
  <section>
    <h2><span class="icon">⊞</span> Position Sizing Logic</h2>
    <p>Professional traders control risk using capital-based limits.</p>
    <div class="formula-group">
      <div class="formula-card">
        <div class="step-label">Allowed Risk</div>
        <div class="formula">Allowed Risk = Account Capital × Risk %</div>
      </div>
      <div class="formula-card">
        <div class="step-label">Max Contracts Allowed</div>
        <div class="formula">Contracts Allowed = ⌊ Allowed Risk / Risk per Contract ⌋</div>
        <p>Ensures capital preservation, controlled drawdowns, and disciplined trading behaviour.</p>
      </div>
    </div>
  </section>

  <!-- Key Features -->
  <section>
    <h2><span class="icon">◆</span> Key Features</h2>
    <div class="feature-grid">
      <div class="feature-item">Tick-accurate trade risk estimation</div>
      <div class="feature-item">Support for long and short futures positions</div>
      <div class="feature-item">Margin requirement comparison</div>
      <div class="feature-item">Stress scenario loss simulation</div>
      <div class="feature-item">Contract specification reference panel</div>
      <div class="feature-item">Financial dashboard-style user interface</div>
    </div>
  </section>

  <!-- Learning Outcomes -->
  <section>
    <h2><span class="icon">◉</span> Learning Outcomes</h2>
    <p>This toolkit helps users build intuition about:</p>
    <ul class="outcome-list">
      <li>Futures contract mechanics</li>
      <li>Relationship between leverage and risk</li>
      <li>Monetary impact of stop loss placement</li>
      <li>Scenario-based risk thinking</li>
      <li>Basic exchange-style margin logic</li>
    </ul>
  </section>

  <!-- Tech Stack -->
  <section>
    <h2><span class="icon">⌥</span> Technology Stack</h2>
    <div class="tech-row">
      <div class="tech-tag">HTML</div>
      <div class="tech-tag">CSS</div>
      <div class="tech-tag">JavaScript</div>
      <div class="tech-tag">Financial Risk Modules</div>
      <div class="tech-tag">Scenario Simulation Engine</div>
      <div class="tech-tag">GitHub Pages</div>
    </div>
  </section>

  <!-- Future Enhancements -->
  <section>
    <h2><span class="icon">⟳</span> Future Enhancements</h2>
    <ul class="enhance-list">
      <li>Portfolio-level risk aggregation</li>
      <li>Multi-asset exposure dashboard</li>
      <li>P&amp;L sensitivity visualization</li>
      <li>Margin breach alerts</li>
      <li>Risk heatmaps</li>
      <li>Downloadable trade risk reports</li>
      <li>Advanced SPAN-style scenario tables</li>
      <li>Dark / light trading terminal themes</li>
    </ul>
  </section>

</div>

<!-- ── FOOTER ── -->
<footer>
  <p style="font-family: var(--display); font-size:15px; font-weight:600; color:var(--heading);">Arham Shah</p>
  <p>Engineering Student — Financial Risk Analytics &nbsp;·&nbsp; <a href="https://github.com/arham7s">github.com/arham7s</a></p>
  <p class="disclaimer">This project is intended only for educational and analytical purposes. It does not represent official margin methodologies of any exchange or clearing corporation. Trading derivatives involves substantial financial risk.</p>
</footer>

</body>
</html>
