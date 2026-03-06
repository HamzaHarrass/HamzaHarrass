<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Hamza Harrass – Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080810;
    --surface: #0e0e1a;
    --surface2: #13131f;
    --border: rgba(167,139,250,0.15);
    --purple: #a78bfa;
    --purple2: #7c3aed;
    --cyan: #22d3ee;
    --green: #4ade80;
    --text: #e2e8f0;
    --muted: #64748b;
    --accent: #f472b6;
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* BG grid */
  body::before {
    content:'';
    position:fixed;
    inset:0;
    background-image:
      linear-gradient(rgba(167,139,250,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(167,139,250,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    pointer-events:none;
    z-index:0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* HERO */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    position: relative;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 50%;
    transform: translateX(-50%);
    width: 600px; height: 300px;
    background: radial-gradient(ellipse, rgba(124,58,237,0.2) 0%, transparent 70%);
    pointer-events: none;
  }

  .status-pill {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(74,222,128,0.1);
    border: 1px solid rgba(74,222,128,0.3);
    color: var(--green);
    padding: 6px 16px;
    border-radius: 100px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    margin-bottom: 28px;
    animation: fadeDown 0.6s ease both;
  }

  .status-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%,100%{opacity:1;transform:scale(1)}
    50%{opacity:0.5;transform:scale(0.8)}
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 8vw, 80px);
    font-weight: 800;
    letter-spacing: -2px;
    line-height: 1;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  h1 .first { color: #fff; }
  h1 .last {
    background: linear-gradient(135deg, var(--purple), var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .role {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--purple);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin: 16px 0 28px;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .socials {
    display: flex;
    justify-content: center;
    gap: 12px;
    flex-wrap: wrap;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .social-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 9px 18px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid var(--border);
    background: var(--surface);
    color: var(--text);
    transition: all 0.2s;
  }
  .social-btn:hover {
    border-color: var(--purple);
    color: var(--purple);
    transform: translateY(-2px);
    box-shadow: 0 4px 20px rgba(167,139,250,0.2);
  }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--purple), transparent);
    margin: 40px 0;
    opacity: 0.4;
  }

  /* SECTION */
  .section { margin-bottom: 48px; }

  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--purple);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* CODE BLOCK */
  .code-block {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    line-height: 1.7;
  }

  .code-header {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 12px 16px;
    background: rgba(255,255,255,0.03);
    border-bottom: 1px solid var(--border);
  }

  .dot { width:10px;height:10px;border-radius:50%; }
  .dot.r{background:#ff5f57}.dot.y{background:#febc2e}.dot.g{background:#28c840}

  .code-file {
    font-size: 11px;
    color: var(--muted);
    margin-left: auto;
    font-family: 'Space Mono', monospace;
  }

  .code-body { padding: 20px 24px; }

  .ln { color: #2d2d50; margin-right: 16px; user-select: none; }
  .kw { color: #c792ea; }
  .fn { color: #82aaff; }
  .str { color: #c3e88d; }
  .key { color: var(--cyan); }
  .cm { color: #546e7a; font-style: italic; }
  .arr { color: var(--accent); }
  .br { color: #ffd700; }

  /* SKILLS GRID */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 16px;
  }

  .skill-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    transition: all 0.2s;
  }
  .skill-card:hover {
    border-color: var(--purple);
    transform: translateY(-3px);
    box-shadow: 0 8px 30px rgba(167,139,250,0.1);
  }

  .skill-title {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--purple);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 14px;
  }

  .badge-wrap { display: flex; flex-wrap: wrap; gap: 8px; }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 4px 10px;
    border-radius: 6px;
    font-size: 11px;
    font-weight: 500;
    background: rgba(167,139,250,0.08);
    border: 1px solid rgba(167,139,250,0.2);
    color: #c4b5fd;
    transition: all 0.15s;
  }
  .badge:hover {
    background: rgba(167,139,250,0.2);
    color: #fff;
  }

  .badge.cyan { background:rgba(34,211,238,0.08);border-color:rgba(34,211,238,0.2);color:#67e8f9; }
  .badge.cyan:hover { background:rgba(34,211,238,0.2);color:#fff; }
  .badge.green { background:rgba(74,222,128,0.08);border-color:rgba(74,222,128,0.2);color:#86efac; }
  .badge.green:hover { background:rgba(74,222,128,0.2);color:#fff; }
  .badge.orange { background:rgba(251,146,60,0.08);border-color:rgba(251,146,60,0.2);color:#fdba74; }
  .badge.orange:hover { background:rgba(251,146,60,0.2);color:#fff; }
  .badge.pink { background:rgba(244,114,182,0.08);border-color:rgba(244,114,182,0.2);color:#f9a8d4; }
  .badge.pink:hover { background:rgba(244,114,182,0.2);color:#fff; }

  /* EXPERIENCE */
  .exp-list { display: flex; flex-direction: column; gap: 16px; }

  .exp-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    display: grid;
    grid-template-columns: 140px 1fr;
    gap: 20px;
    transition: all 0.2s;
  }
  .exp-card:hover {
    border-color: rgba(167,139,250,0.4);
    box-shadow: 0 4px 20px rgba(167,139,250,0.08);
  }

  .exp-date {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    line-height: 1.6;
    padding-top: 2px;
  }
  .exp-date span {
    display: block;
    color: var(--purple);
    margin-bottom: 4px;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .exp-title {
    font-family: 'Syne', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: #fff;
    margin-bottom: 2px;
  }

  .exp-company {
    font-size: 12px;
    color: var(--purple);
    font-weight: 500;
    margin-bottom: 10px;
  }

  .exp-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.7;
  }

  /* EDUCATION */
  .edu-list { display: flex; flex-direction: column; gap: 12px; }

  .edu-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px 22px;
    display: flex;
    align-items: center;
    gap: 16px;
    transition: all 0.2s;
  }
  .edu-card:hover { border-color: rgba(34,211,238,0.3); }

  .edu-year {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--cyan);
    min-width: 90px;
  }

  .edu-info strong {
    font-family: 'Syne', sans-serif;
    font-size: 14px;
    font-weight: 700;
    color: #fff;
    display: block;
  }
  .edu-info em {
    font-size: 12px;
    color: var(--muted);
    font-style: normal;
  }

  /* STATS */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }

  .stat-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    text-align: center;
    transition: all 0.2s;
  }
  .stat-card:hover {
    border-color: var(--purple);
    box-shadow: 0 0 30px rgba(167,139,250,0.1);
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--purple), var(--cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .stat-label {
    font-size: 12px;
    color: var(--muted);
    margin-top: 4px;
    font-family: 'Space Mono', monospace;
  }

  /* INTERESTS */
  .interests {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }
  .interest {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 100px;
    padding: 10px 20px;
    font-size: 13px;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: all 0.2s;
  }
  .interest:hover {
    border-color: var(--purple);
    background: rgba(167,139,250,0.1);
  }

  /* FOOTER */
  .footer {
    text-align: center;
    padding: 40px 0 0;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity:0; transform:translateY(20px); }
    to   { opacity:1; transform:translateY(0); }
  }
  @keyframes fadeDown {
    from { opacity:0; transform:translateY(-10px); }
    to   { opacity:1; transform:translateY(0); }
  }

  .animate { animation: fadeUp 0.6s ease both; }

  @media(max-width:600px) {
    .exp-card { grid-template-columns: 1fr; gap: 8px; }
    .stats-grid { grid-template-columns: repeat(2,1fr); }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="status-pill">
      <span class="status-dot"></span>
      Available for opportunities
    </div>
    <h1>
      <span class="first">HAMZA </span><span class="last">HARRASS</span>
    </h1>
    <p class="role">MERN Stack &amp; Mobile Developer</p>
    <div class="socials">
      <a href="https://github.com/HamzaHarrass" class="social-btn">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="https://www.linkedin.com/in/hamzahrs/" class="social-btn">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="#0A66C2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:hamzaharrass05@gmail.com" class="social-btn">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Email
      </a>
      <a href="tel:+212680927972" class="social-btn">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.38 2 2 0 0 1 3.59 1h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.56a16 16 0 0 0 6.53 6.53l1.62-1.62a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
        +212 680927972
      </a>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section animate">
    <p class="section-label">01 — About</p>
    <div class="code-block">
      <div class="code-header">
        <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
        <span class="code-file">hamza.ts</span>
      </div>
      <div class="code-body">
        <div><span class="ln">1</span><span class="kw">const</span> <span class="fn">hamza</span><span>: Developer = {</span></div>
        <div><span class="ln">2</span>&nbsp;&nbsp;<span class="key">name</span><span>:      </span><span class="str">"Hamza Harrass"</span><span>,</span></div>
        <div><span class="ln">3</span>&nbsp;&nbsp;<span class="key">role</span><span>:      </span><span class="str">"MERN Stack &amp; Mobile Developer"</span><span>,</span></div>
        <div><span class="ln">4</span>&nbsp;&nbsp;<span class="key">location</span><span>:  </span><span class="str">"Meknès, Maroc 🇲🇦"</span><span>,</span></div>
        <div><span class="ln">5</span>&nbsp;&nbsp;<span class="key">email</span><span>:    </span><span class="str">"hamzaharrass05@gmail.com"</span><span>,</span></div>
        <div><span class="ln">6</span>&nbsp;&nbsp;<span class="key">available</span><span>: </span><span class="kw">true</span><span>,  </span><span class="cm">// Open to opportunities 🟢</span></div>
        <div><span class="ln">7</span><span>};</span></div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section animate">
    <p class="section-label">02 — Stats</p>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num">4+</div>
        <div class="stat-label">Years coding</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">5+</div>
        <div class="stat-label">Projects shipped</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">15+</div>
        <div class="stat-label">Technologies</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section animate">
    <p class="section-label">03 — Tech Stack</p>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-title">Frontend</div>
        <div class="badge-wrap">
          <span class="badge">React.js</span>
          <span class="badge">TypeScript</span>
          <span class="badge">JavaScript</span>
          <span class="badge">TailwindCSS</span>
          <span class="badge">HTML5/CSS3</span>
          <span class="badge">SASS</span>
          <span class="badge">Bootstrap</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-title">Mobile</div>
        <div class="badge-wrap">
          <span class="badge cyan">React Native</span>
          <span class="badge cyan">Expo</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-title">Backend</div>
        <div class="badge-wrap">
          <span class="badge green">Node.js</span>
          <span class="badge green">Express.js</span>
          <span class="badge green">NestJS</span>
          <span class="badge green">Laravel</span>
          <span class="badge green">PHP</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-title">Database</div>
        <div class="badge-wrap">
          <span class="badge orange">MongoDB</span>
          <span class="badge orange">MySQL</span>
          <span class="badge orange">PostgreSQL</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-title">DevOps &amp; Tools</div>
        <div class="badge-wrap">
          <span class="badge pink">Docker</span>
          <span class="badge pink">Git</span>
          <span class="badge pink">GitHub</span>
          <span class="badge pink">Figma</span>
          <span class="badge pink">Postman</span>
          <span class="badge pink">VS Code</span>
          <span class="badge pink">Jira</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-title">Methodologies</div>
        <div class="badge-wrap">
          <span class="badge">Agile/Scrum</span>
          <span class="badge">UML</span>
          <span class="badge">MERISE</span>
          <span class="badge">REST API</span>
          <span class="badge">Jest</span>
        </div>
      </div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section animate">
    <p class="section-label">04 — Experience</p>
    <div class="exp-list">
      <div class="exp-card">
        <div class="exp-date">
          <span>Aug 2024 – Feb 2025</span>
          Casablanca, Maroc
        </div>
        <div>
          <div class="exp-title">🚀 Auto Entrepreneur – Mobile Developer</div>
          <div class="exp-company">Atelier Digital – Digital Agency & AI</div>
          <div class="exp-desc">Built Buzztest — a platform connecting brands, content creators, influencers & testers. Mobile app allows influencers to browse and apply to campaigns.</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-date">
          <span>Apr 2024 – Jul 2024</span>
          Casablanca, Maroc
        </div>
        <div>
          <div class="exp-title">📱 Stage – Mobile Developer</div>
          <div class="exp-company">Atelier Digital – Digital Agency & AI</div>
          <div class="exp-desc">Developed the Buzztest mobile application from scratch using React Native.</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-date">
          <span>May 2023 – Jul 2023</span>
          Meknès, Maroc
        </div>
        <div>
          <div class="exp-title">🛒 Stage – Full Stack Developer</div>
          <div class="exp-company">GENERATION NT</div>
          <div class="exp-desc">Built a full E-Commerce platform inspired by Jumia — intuitive UI with advanced Full Stack functionalities for optimal user experience.</div>
        </div>
      </div>
      <div class="exp-card">
        <div class="exp-date">
          <span>May 2021 – Jun 2021</span>
          Tan-Tan, Maroc
        </div>
        <div>
          <div class="exp-title">🏛️ Stage – Full Stack Developer</div>
          <div class="exp-company">Trésorerie Générale</div>
          <div class="exp-desc">Developed an innovative certificate management application. Close collaboration with end users to meet specific client needs precisely.</div>
        </div>
      </div>
    </div>
  </div>

  <!-- EDUCATION -->
  <div class="section animate">
    <p class="section-label">05 — Education</p>
    <div class="edu-list">
      <div class="edu-card">
        <div class="edu-year">2022 – 2024</div>
        <div class="edu-info">
          <strong>Bac+4 – Concepteur Développeur d'Applications (RNCP37873)</strong>
          <em>Simplon / YouCode – Université Mohammed VI Polytechnique, Youssoufia</em>
        </div>
      </div>
      <div class="edu-card">
        <div class="edu-year">2019 – 2021</div>
        <div class="edu-info">
          <strong>Diplôme Technicien Spécialisé – Développement Informatique</strong>
          <em>Institut Spécialisé de Technologie Appliquée, Tan-Tan</em>
        </div>
      </div>
      <div class="edu-card">
        <div class="edu-year">2018 – 2019</div>
        <div class="edu-info">
          <strong>Baccalauréat – Sciences de la Vie et de la Terre</strong>
          <em>Lycée Al Qods, Tan-Tan</em>
        </div>
      </div>
    </div>
  </div>

  <!-- INTERESTS -->
  <div class="section animate">
    <p class="section-label">06 — Interests</p>
    <div class="interests">
      <div class="interest">✈️ Voyages</div>
      <div class="interest">⚽ Football</div>
      <div class="interest">🎮 Gaming</div>
      <div class="interest">💪 GYM</div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="footer">
    <p>Built with 💜 · Open to collaborations &amp; opportunities</p>
    <p style="margin-top:8px;">hamzaharrass05@gmail.com · +212 680927972 · Meknès, Maroc</p>
  </div>

</div>

</body>
</html>
