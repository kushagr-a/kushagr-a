<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kushagra Bharti — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080c14;
    --surface: #0d1524;
    --surface2: #111d30;
    --border: #1e2f4a;
    --accent: #00e5ff;
    --accent2: #7c3aed;
    --accent3: #f59e0b;
    --text: #e2eaf5;
    --muted: #6b82a0;
    --green: #22d3a5;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 40px;
    align-items: center;
    margin-bottom: 64px;
    animation: fadeUp 0.7s ease both;
  }

  .avatar-wrap {
    position: relative;
    width: 120px;
    height: 120px;
    flex-shrink: 0;
  }

  .avatar-wrap::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent), var(--accent2), var(--accent3), var(--accent));
    animation: spin 4s linear infinite;
    z-index: 0;
  }

  .avatar-wrap img {
    position: relative;
    z-index: 1;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    border: 4px solid var(--bg);
  }

  .avatar-placeholder {
    position: relative;
    z-index: 1;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: linear-gradient(135deg, #1a2540, #0d1524);
    border: 4px solid var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 42px;
  }

  .hero-info {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .tag-line {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 3px;
    text-transform: uppercase;
    opacity: 0.8;
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 5vw, 46px);
    font-weight: 800;
    line-height: 1.05;
    background: linear-gradient(135deg, #e2eaf5 0%, var(--accent) 60%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-handle {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--muted);
  }

  .hero-links {
    display: flex;
    gap: 12px;
    margin-top: 4px;
    flex-wrap: wrap;
  }

  .badge-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 14px;
    border-radius: 100px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    text-decoration: none;
    border: 1px solid;
    transition: all 0.25s ease;
    letter-spacing: 0.5px;
  }

  .badge-link.linkedin {
    border-color: #0077b5;
    color: #5db8e8;
    background: rgba(0,119,181,0.08);
  }
  .badge-link.linkedin:hover {
    background: rgba(0,119,181,0.2);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0,119,181,0.25);
  }

  .stat-row {
    display: flex;
    gap: 24px;
    margin-top: 8px;
    flex-wrap: wrap;
  }

  .stat-item {
    display: flex;
    align-items: center;
    gap: 6px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .stat-item strong {
    color: var(--text);
    font-weight: 600;
  }

  /* ── SECTION ── */
  .section {
    margin-bottom: 48px;
    animation: fadeUp 0.7s ease both;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 24px;
  }

  .section-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 12px var(--accent);
    flex-shrink: 0;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--muted);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  /* ── ABOUT CARDS ── */
  .about-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 12px;
  }

  .about-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 18px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: all 0.25s ease;
    position: relative;
    overflow: hidden;
  }

  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .about-card:hover {
    border-color: rgba(0,229,255,0.3);
    transform: translateY(-3px);
    box-shadow: 0 12px 32px rgba(0,0,0,0.4);
  }

  .about-card:hover::before { opacity: 1; }

  .about-icon {
    font-size: 18px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .about-text {
    font-size: 13px;
    line-height: 1.6;
    color: #a0b4c8;
    font-family: 'JetBrains Mono', monospace;
  }

  .about-text strong {
    color: var(--text);
    font-weight: 600;
  }

  /* ── TECH STACK ── */
  .tech-categories {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .tech-category {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 20px 24px;
    transition: border-color 0.25s;
  }

  .tech-category:hover {
    border-color: rgba(0,229,255,0.2);
  }

  .tech-category-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
    opacity: 0.7;
  }

  .tech-pills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pill {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 5px 12px;
    border-radius: 8px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    transition: all 0.2s ease;
    cursor: default;
  }

  .pill:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 16px rgba(0,0,0,0.3);
  }

  .pill .dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }

  /* pill color themes */
  .pill-cyan   { border-color: rgba(0,229,255,0.25); color: #7ee8f5; }
  .pill-cyan:hover { background: rgba(0,229,255,0.08); }
  .pill-purple { border-color: rgba(124,58,237,0.3); color: #c4b5fd; }
  .pill-purple:hover { background: rgba(124,58,237,0.08); }
  .pill-amber  { border-color: rgba(245,158,11,0.3); color: #fcd34d; }
  .pill-amber:hover { background: rgba(245,158,11,0.08); }
  .pill-green  { border-color: rgba(34,211,165,0.3); color: #6ee7b7; }
  .pill-green:hover { background: rgba(34,211,165,0.08); }
  .pill-rose   { border-color: rgba(244,63,94,0.3); color: #fda4af; }
  .pill-rose:hover { background: rgba(244,63,94,0.08); }
  .pill-blue   { border-color: rgba(59,130,246,0.3); color: #93c5fd; }
  .pill-blue:hover { background: rgba(59,130,246,0.08); }

  /* ── GITHUB STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }

  @media (max-width: 500px) {
    .stats-grid { grid-template-columns: 1fr; }
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .stat-card:hover {
    border-color: rgba(0,229,255,0.25);
    transform: translateY(-4px);
    box-shadow: 0 16px 40px rgba(0,0,0,0.4);
  }

  .stat-card::after {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 80px; height: 80px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(0,229,255,0.06), transparent 70%);
  }

  .stat-value {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent), #7c3aed);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* ── LANG BAR ── */
  .lang-bar-wrap {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    margin-top: 12px;
  }

  .lang-bar-title {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
  }

  .lang-bar {
    height: 10px;
    border-radius: 100px;
    overflow: hidden;
    display: flex;
    margin-bottom: 16px;
  }

  .lang-bar-seg {
    height: 100%;
    transition: all 0.3s ease;
  }

  .lang-legend {
    display: flex;
    flex-wrap: wrap;
    gap: 10px 20px;
  }

  .lang-item {
    display: flex;
    align-items: center;
    gap: 7px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .lang-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .lang-pct { color: var(--text); font-weight: 600; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 24px;
    border-top: 1px solid var(--border);
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    animation: fadeUp 0.7s ease 0.5s both;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes spin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .section:nth-child(1) { animation-delay: 0.1s; }
  .section:nth-child(2) { animation-delay: 0.2s; }
  .section:nth-child(3) { animation-delay: 0.3s; }
  .section:nth-child(4) { animation-delay: 0.4s; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-placeholder">🧑‍💻</div>
    </div>
    <div class="hero-info">
      <div class="tag-line">Backend Engineer · Full Stack Dev</div>
      <div class="hero-name">Kushagra Bharti</div>
      <div class="hero-handle">@kushagr-a · Chandigarh University</div>
      <div class="stat-row">
        <span class="stat-item">👥 <strong>3</strong> followers</span>
        <span class="stat-item">➤ <strong>5</strong> following</span>
        <span class="stat-item">⭐ <strong>2</strong> stars</span>
        <span class="stat-item">📦 <strong>194</strong> commits</span>
      </div>
      <div class="hero-links">
        <a href="https://linkedin.com/in/kushbharti16/" class="badge-link linkedin" target="_blank">
          <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot"></div>
      <div class="section-title">About</div>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="about-card">
        <div class="about-icon">🔭</div>
        <div class="about-text"><strong>Building</strong> backend systems with Node.js, Express &amp; Prisma</div>
      </div>
      <div class="about-card">
        <div class="about-icon">👯</div>
        <div class="about-text"><strong>Open to</strong> Full Stack &amp; Backend real-world collaborations</div>
      </div>
      <div class="about-card">
        <div class="about-icon">🌱</div>
        <div class="about-text"><strong>Learning</strong> TypeScript &amp; Data Structures &amp; Algorithms</div>
      </div>
      <div class="about-card">
        <div class="about-icon">🤝</div>
        <div class="about-text"><strong>Seeking help</strong> with Advanced DSA &amp; System Design</div>
      </div>
      <div class="about-card">
        <div class="about-icon">💬</div>
        <div class="about-text"><strong>Ask me about</strong> Node.js, APIs, MongoDB, Prisma &amp; Backend Dev</div>
      </div>
      <div class="about-card">
        <div class="about-icon">⚡</div>
        <div class="about-text"><strong>Fun fact:</strong> Prefers building real-world projects over tutorials 🚀</div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot" style="background: var(--accent2); box-shadow: 0 0 12px var(--accent2);"></div>
      <div class="section-title">Tech Stack</div>
      <div class="section-line"></div>
    </div>
    <div class="tech-categories">

      <div class="tech-category">
        <div class="tech-category-label">Languages</div>
        <div class="tech-pills">
          <span class="pill pill-amber"><span class="dot" style="background:#f7df1e"></span>JavaScript</span>
          <span class="pill pill-blue"><span class="dot" style="background:#007acc"></span>TypeScript</span>
          <span class="pill pill-cyan"><span class="dot" style="background:#00add8"></span>Go</span>
          <span class="pill pill-rose"><span class="dot" style="background:#f44336"></span>Java</span>
          <span class="pill pill-purple"><span class="dot" style="background:#00599c"></span>C++</span>
          <span class="pill pill-rose"><span class="dot" style="background:#e10098"></span>GraphQL</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-label">Backend & Runtime</div>
        <div class="tech-pills">
          <span class="pill pill-green"><span class="dot" style="background:#6da55f"></span>Node.js</span>
          <span class="pill pill-cyan"><span class="dot" style="background:#404d59"></span>Express.js</span>
          <span class="pill pill-purple"><span class="dot" style="background:#e0234e"></span>NestJS</span>
          <span class="pill pill-amber"><span class="dot" style="background:#000"></span>Fastify</span>
          <span class="pill pill-cyan"><span class="dot" style="background:#000"></span>Bun</span>
          <span class="pill pill-blue"><span class="dot" style="background:#000"></span>Socket.io</span>
          <span class="pill pill-rose"><span class="dot" style="background:#8f0000"></span>Node-RED</span>
          <span class="pill pill-amber"><span class="dot" style="background:#000"></span>JWT</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-label">Databases & ORM</div>
        <div class="tech-pills">
          <span class="pill pill-green"><span class="dot" style="background:#4ea94b"></span>MongoDB</span>
          <span class="pill pill-blue"><span class="dot" style="background:#316192"></span>PostgreSQL</span>
          <span class="pill pill-amber"><span class="dot" style="background:#4479a1"></span>MySQL</span>
          <span class="pill pill-rose"><span class="dot" style="background:#dd0031"></span>Redis</span>
          <span class="pill pill-cyan"><span class="dot" style="background:#3ecf8e"></span>Supabase</span>
          <span class="pill pill-blue"><span class="dot" style="background:#3982ce"></span>Prisma</span>
          <span class="pill pill-amber"><span class="dot" style="background:#039be5"></span>Firebase</span>
          <span class="pill pill-green"><span class="dot" style="background:#07405e"></span>SQLite</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-label">Messaging & Infrastructure</div>
        <div class="tech-pills">
          <span class="pill pill-cyan"><span class="dot" style="background:#000"></span>Apache Kafka</span>
          <span class="pill pill-amber"><span class="dot" style="background:#ff6600"></span>RabbitMQ</span>
          <span class="pill pill-green"><span class="dot" style="background:#009639"></span>Nginx</span>
          <span class="pill pill-blue"><span class="dot" style="background:#0db7ed"></span>Docker</span>
          <span class="pill pill-rose"><span class="dot" style="background:#2c5263"></span>Jenkins</span>
          <span class="pill pill-purple"><span class="dot" style="background:#311c87"></span>Apollo GraphQL</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-label">Cloud & Deployment</div>
        <div class="tech-pills">
          <span class="pill pill-cyan"><span class="dot" style="background:#46e3b7"></span>Render</span>
          <span class="pill pill-amber"><span class="dot" style="background:#000"></span>Netlify</span>
          <span class="pill pill-blue"><span class="dot" style="background:#000"></span>Vercel</span>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-label">Frontend & Tools</div>
        <div class="tech-pills">
          <span class="pill pill-cyan"><span class="dot" style="background:#61dafb"></span>React</span>
          <span class="pill pill-amber"><span class="dot" style="background:#f05033"></span>Git</span>
          <span class="pill pill-green"><span class="dot" style="background:#121011"></span>GitHub</span>
          <span class="pill pill-rose"><span class="dot" style="background:#ff6c37"></span>Postman</span>
          <span class="pill pill-green"><span class="dot" style="background:#85ea2d"></span>Swagger</span>
          <span class="pill pill-rose"><span class="dot" style="background:#c21325"></span>Jest</span>
          <span class="pill pill-amber"><span class="dot" style="background:#8d6748"></span>Mocha</span>
          <span class="pill pill-rose"><span class="dot" style="background:#f22f46"></span>Twilio</span>
        </div>
      </div>

    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-header">
      <div class="section-dot" style="background: var(--accent3); box-shadow: 0 0 12px var(--accent3);"></div>
      <div class="section-title">GitHub Stats</div>
      <div class="section-line"></div>
    </div>

    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-value">194</div>
        <div class="stat-label">Total Commits</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">10</div>
        <div class="stat-label">Pull Requests</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">2</div>
        <div class="stat-label">Stars Earned</div>
      </div>
      <div class="stat-card">
        <div class="stat-value">0</div>
        <div class="stat-label">Issues Opened</div>
      </div>
    </div>

    <div class="lang-bar-wrap">
      <div class="lang-bar-title">Most Used Languages</div>
      <div class="lang-bar">
        <div class="lang-bar-seg" style="width:67.49%; background:#f7df1e;"></div>
        <div class="lang-bar-seg" style="width:21.57%; background:#007acc;"></div>
        <div class="lang-bar-seg" style="width:8.13%;  background:#00add8;"></div>
        <div class="lang-bar-seg" style="width:1.32%;  background:#563d7c;"></div>
        <div class="lang-bar-seg" style="width:1.03%;  background:#b4ca65;"></div>
        <div class="lang-bar-seg" style="width:0.46%;  background:#e34c26;"></div>
      </div>
      <div class="lang-legend">
        <div class="lang-item"><span class="lang-dot" style="background:#f7df1e"></span> JavaScript <span class="lang-pct">67.49%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#007acc"></span> TypeScript <span class="lang-pct">21.57%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#00add8"></span> Go <span class="lang-pct">8.13%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#563d7c"></span> CSS <span class="lang-pct">1.32%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#b4ca65"></span> EJS <span class="lang-pct">1.03%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#e34c26"></span> HTML <span class="lang-pct">0.46%</span></div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    kushagr-a · built with ❤️ &amp; backend vibes
  </div>

</div>
</body>
</html>
