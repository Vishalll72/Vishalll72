<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vishal Kumar — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --bg3: #181820;
    --border: rgba(255,255,255,0.07);
    --border2: rgba(255,255,255,0.13);
    --cyan: #00e5c8;
    --cyan-dim: rgba(0,229,200,0.12);
    --cyan-glow: rgba(0,229,200,0.25);
    --text: #e8e8f0;
    --muted: #6b6b82;
    --muted2: #9494aa;
    --accent: #7c6ef4;
    --accent-dim: rgba(124,110,244,0.12);
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* grid lines bg */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,200,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,200,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 32px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: center;
    margin-bottom: 64px;
    padding-bottom: 48px;
    border-bottom: 1px solid var(--border);
  }

  .tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--cyan);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin-bottom: 20px;
    padding: 6px 12px;
    border: 1px solid rgba(0,229,200,0.25);
    border-radius: 4px;
    background: var(--cyan-dim);
    width: fit-content;
  }

  .tag::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--cyan);
    border-radius: 50%;
    animation: pulse 2s ease infinite;
  }

  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.7); }
  }

  h1 {
    font-size: clamp(36px, 6vw, 58px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 12px;
  }

  h1 .first { color: var(--text); }
  h1 .last {
    color: var(--cyan);
    position: relative;
  }

  .subtitle {
    font-size: 15px;
    color: var(--muted2);
    font-family: var(--mono);
    margin-bottom: 28px;
  }

  .subtitle span { color: var(--accent); }

  .cta-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 22px;
    font-size: 13px;
    font-family: var(--sans);
    font-weight: 600;
    letter-spacing: 0.01em;
    border-radius: 6px;
    cursor: pointer;
    transition: all 0.18s ease;
    text-decoration: none;
  }

  .btn-primary {
    background: var(--cyan);
    color: #000;
    border: none;
  }
  .btn-primary:hover { background: #00fff3; transform: translateY(-1px); }

  .btn-ghost {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border2);
  }
  .btn-ghost:hover { border-color: var(--cyan); color: var(--cyan); transform: translateY(-1px); }

  .avatar-box {
    position: relative;
    flex-shrink: 0;
  }

  .avatar {
    width: 140px;
    height: 140px;
    border-radius: 20px;
    background: linear-gradient(135deg, var(--accent) 0%, var(--cyan) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 52px;
    font-weight: 800;
    color: #fff;
    position: relative;
    z-index: 1;
    font-family: var(--sans);
  }

  .avatar-glow {
    position: absolute;
    inset: -8px;
    border-radius: 26px;
    background: radial-gradient(ellipse, var(--cyan-glow) 0%, transparent 70%);
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    margin-bottom: 56px;
    background: var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .stat {
    background: var(--bg2);
    padding: 24px 20px;
    text-align: center;
  }

  .stat-num {
    font-size: 26px;
    font-weight: 800;
    color: var(--cyan);
    font-family: var(--mono);
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    font-family: var(--mono);
  }

  /* ── SECTION HEADER ── */
  .section-head {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 28px;
  }

  .section-head h2 {
    font-size: 13px;
    font-family: var(--mono);
    color: var(--muted2);
    text-transform: uppercase;
    letter-spacing: 0.15em;
    font-weight: 400;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-num {
    font-size: 11px;
    font-family: var(--mono);
    color: var(--muted);
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
    margin-bottom: 56px;
  }

  .project-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s ease, transform 0.2s ease;
    cursor: default;
  }

  .project-card:hover {
    border-color: var(--border2);
    transform: translateY(-2px);
  }

  .project-card.featured {
    border-color: rgba(0,229,200,0.3);
    grid-column: span 2;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--cyan-dim), transparent);
  }

  .project-card.featured::before {
    background: linear-gradient(90deg, transparent, var(--cyan), transparent);
    opacity: 0.4;
  }

  .project-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 12px;
  }

  .project-icon {
    width: 38px; height: 38px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    background: var(--bg3);
    border: 1px solid var(--border);
    flex-shrink: 0;
  }

  .project-badge {
    font-family: var(--mono);
    font-size: 10px;
    padding: 3px 9px;
    border-radius: 20px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .badge-live {
    background: rgba(0,229,200,0.12);
    color: var(--cyan);
    border: 1px solid rgba(0,229,200,0.25);
  }

  .badge-internal {
    background: rgba(124,110,244,0.12);
    color: #a89cf8;
    border: 1px solid rgba(124,110,244,0.25);
  }

  .badge-sole {
    background: rgba(255,180,0,0.1);
    color: #ffb800;
    border: 1px solid rgba(255,180,0,0.25);
  }

  .project-name {
    font-size: 17px;
    font-weight: 600;
    margin-bottom: 6px;
    margin-top: 14px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted2);
    line-height: 1.6;
    font-family: var(--mono);
  }

  .project-url {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    margin-top: 16px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .project-url::before {
    content: '↗';
    color: var(--cyan);
  }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 56px; }

  .skill-group { margin-bottom: 24px; }

  .skill-group-label {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 12px;
  }

  .skills-wrap {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .skill-chip {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 7px 14px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 6px;
    font-size: 13px;
    font-family: var(--mono);
    color: var(--muted2);
    transition: all 0.15s ease;
  }

  .skill-chip:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    background: var(--cyan-dim);
  }

  .skill-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── CONNECT ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    margin-bottom: 56px;
  }

  .connect-card {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 18px 20px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.18s ease;
  }

  .connect-card:hover {
    border-color: var(--border2);
    transform: translateX(3px);
    color: var(--cyan);
  }

  .connect-icon {
    width: 38px; height: 38px;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    background: var(--bg3);
    flex-shrink: 0;
  }

  .connect-label {
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 2px;
  }

  .connect-handle {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
  }

  /* ── GITHUB STATS ── */
  .stats-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 56px;
  }

  .gh-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }

  .gh-card img {
    width: 100%;
    display: block;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
  }

  .footer span { color: var(--cyan); }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .header { animation: fadeUp 0.5s ease both; }
  .stats-row { animation: fadeUp 0.5s 0.1s ease both; }
  .projects-grid { animation: fadeUp 0.5s 0.15s ease both; }
  .skills-section { animation: fadeUp 0.5s 0.2s ease both; }
  .connect-grid { animation: fadeUp 0.5s 0.25s ease both; }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div>
      <div class="tag">Available for opportunities</div>
      <h1>
        <span class="first">Vishal </span><span class="last">Kumar</span>
      </h1>
      <p class="subtitle">Full Stack Developer <span>//</span> Web Designer</p>
      <div class="cta-row">
        <a href="mailto:vishalsingh58912@gmail.com" class="btn btn-primary">Get in touch</a>
        <a href="https://www.linkedin.com/in/vishal-kumar-a03b90243" target="_blank" class="btn btn-ghost">LinkedIn ↗</a>
      </div>
    </div>
    <div class="avatar-box">
      <div class="avatar-glow"></div>
      <div class="avatar">VK</div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat">
      <div class="stat-num">4+</div>
      <div class="stat-label">Projects Shipped</div>
    </div>
    <div class="stat">
      <div class="stat-num">3+</div>
      <div class="stat-label">Years Coding</div>
    </div>
    <div class="stat">
      <div class="stat-num">10+</div>
      <div class="stat-label">Tech Stack</div>
    </div>
    <div class="stat">
      <div class="stat-num">∞</div>
      <div class="stat-label">Learning</div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section-head">
    <h2>Projects</h2>
    <div class="section-line"></div>
    <div class="section-num">04</div>
  </div>

  <div class="projects-grid">
    <div class="project-card featured">
      <div class="project-header">
        <div class="project-icon">📚</div>
        <span class="project-badge badge-live">Live</span>
      </div>
      <div class="project-name">Freepare</div>
      <div class="project-desc">Exam preparation platform — CAT & GMAT algorithm engine built with a scalable content infrastructure. End-to-end system design, from question engine to analytics.</div>
      <div class="project-url">freepare.com</div>
    </div>

    <div class="project-card">
      <div class="project-header">
        <div class="project-icon">📁</div>
        <div style="display:flex;gap:6px">
          <span class="project-badge badge-internal">Internal</span>
          <span class="project-badge badge-sole">Solely Built</span>
        </div>
      </div>
      <div class="project-name">Zenith File Transfer</div>
      <div class="project-desc">Internal file transfer system built from scratch for Zenith India. Handles secure, fast transfers across the org.</div>
      <div class="project-url">files.zenithindia.org</div>
    </div>

    <div class="project-card">
      <div class="project-header">
        <div class="project-icon">📖</div>
        <div style="display:flex;gap:6px">
          <span class="project-badge badge-internal">Internal</span>
          <span class="project-badge badge-sole">Solely Built</span>
        </div>
      </div>
      <div class="project-name">Zenith Docs</div>
      <div class="project-desc">Internal documentation portal for Zenith India — organized, searchable company knowledge base built solo.</div>
      <div class="project-url">docs.zenithindia.org</div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="skills-section">
    <div class="section-head">
      <h2>Skills & Tools</h2>
      <div class="section-line"></div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">// Frontend</div>
      <div class="skills-wrap">
        <div class="skill-chip"><span class="skill-dot" style="background:#61dafb"></span>React</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#fff"></span>Next.js</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#e34f26"></span>HTML5</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#1572b6"></span>CSS3</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#38bdf8"></span>Tailwind</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#7952b3"></span>Bootstrap</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#f24e1e"></span>Figma</div>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">// Backend & Database</div>
      <div class="skills-wrap">
        <div class="skill-chip"><span class="skill-dot" style="background:#68a063"></span>Node.js</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#444"></span>Express.js</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#4db33d"></span>MongoDB</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#336791"></span>PostgreSQL</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#00758f"></span>MySQL</div>
      </div>
    </div>

    <div class="skill-group">
      <div class="skill-group-label">// Language & Tools</div>
      <div class="skills-wrap">
        <div class="skill-chip"><span class="skill-dot" style="background:#f7df1e"></span>JavaScript</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#00599c"></span>C++</div>
        <div class="skill-chip"><span class="skill-dot" style="background:#f05032"></span>Git</div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-head">
    <h2>Connect</h2>
    <div class="section-line"></div>
  </div>

  <div class="connect-grid">
    <a href="https://www.linkedin.com/in/vishal-kumar-a03b90243" target="_blank" class="connect-card">
      <div class="connect-icon">💼</div>
      <div>
        <div class="connect-label">LinkedIn</div>
        <div class="connect-handle">vishal-kumar-a03b90243</div>
      </div>
    </a>
    <a href="mailto:vishalsingh58912@gmail.com" class="connect-card">
      <div class="connect-icon">✉️</div>
      <div>
        <div class="connect-label">Email</div>
        <div class="connect-handle">vishalsingh58912@gmail.com</div>
      </div>
    </a>
    <a href="https://twitter.com/vishalll72" target="_blank" class="connect-card">
      <div class="connect-icon">🐦</div>
      <div>
        <div class="connect-label">Twitter / X</div>
        <div class="connect-handle">@vishalll72</div>
      </div>
    </a>
    <a href="https://leetcode.com/vishalsingh58912/" target="_blank" class="connect-card">
      <div class="connect-icon">⚡</div>
      <div>
        <div class="connect-label">LeetCode</div>
        <div class="connect-handle">vishalsingh58912</div>
      </div>
    </a>
  </div>

  <!-- GITHUB STATS -->
  <div class="section-head">
    <h2>GitHub Stats</h2>
    <div class="section-line"></div>
  </div>

  <div class="stats-section">
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api?username=vishalll72&show_icons=true&theme=tokyonight&bg_color=111118&border_color=1e1e2e&title_color=00e5c8&text_color=9494aa&icon_color=7c6ef4&hide_border=false&border_radius=12" alt="GitHub Stats">
    </div>
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs?username=vishalll72&layout=compact&theme=tokyonight&bg_color=111118&border_color=1e1e2e&title_color=00e5c8&text_color=9494aa&hide_border=false&border_radius=12" alt="Top Languages">
    </div>
    <div class="gh-card" style="grid-column: span 2;">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=vishalll72&theme=tokyonight&background=111118&border=1e1e2e&stroke=1e1e2e&ring=00e5c8&fire=7c6ef4&currStreakLabel=00e5c8&sideLabels=9494aa&dates=6b6b82&hide_border=false&border_radius=12" alt="GitHub Streak" style="width:100%">
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <p>Built with <span>passion</span> · Bihar, India · <span>vishalsingh58912@gmail.com</span></p>
  </div>

</div>
</body>
</html>
