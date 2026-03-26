<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ayusman Samantaray — Developer Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e17;
    --surface: #0f1521;
    --surface2: #141c2e;
    --border: #1e2d47;
    --accent: #3b82f6;
    --accent2: #06b6d4;
    --accent3: #8b5cf6;
    --text: #e2e8f0;
    --muted: #64748b;
    --green: #10b981;
    --mono: 'JetBrains Mono', monospace;
    --display: 'Syne', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.7;
    min-height: 100vh;
  }

  /* Grid noise overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(59,130,246,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(59,130,246,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    display: flex;
    align-items: flex-start;
    gap: 28px;
    margin-bottom: 40px;
    padding-bottom: 32px;
    border-bottom: 1px solid var(--border);
    animation: fadeUp 0.6s ease both;
  }

  .avatar {
    width: 72px;
    height: 72px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--accent), var(--accent3));
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--display);
    font-size: 28px;
    font-weight: 800;
    color: #fff;
    flex-shrink: 0;
    box-shadow: 0 0 0 1px rgba(59,130,246,0.3), 0 8px 32px rgba(59,130,246,0.2);
  }

  .header-info { flex: 1; }

  .name {
    font-family: var(--display);
    font-size: 28px;
    font-weight: 800;
    color: #fff;
    letter-spacing: -0.5px;
    line-height: 1.2;
  }

  .title-line {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 6px;
    flex-wrap: wrap;
  }

  .title {
    font-size: 12px;
    color: var(--muted);
    font-weight: 400;
  }

  .dot { color: var(--border); }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.5px;
    text-transform: uppercase;
  }

  .badge-green { background: rgba(16,185,129,0.1); color: var(--green); border: 1px solid rgba(16,185,129,0.2); }
  .badge-blue  { background: rgba(59,130,246,0.1); color: var(--accent); border: 1px solid rgba(59,130,246,0.2); }

  .badge .dot-live {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: pulse 2s infinite;
  }

  .tagline {
    margin-top: 12px;
    color: var(--muted);
    font-size: 12px;
    max-width: 520px;
    line-height: 1.6;
  }

  .tagline strong { color: var(--text); font-weight: 500; }

  .links {
    display: flex;
    gap: 12px;
    margin-top: 14px;
    flex-wrap: wrap;
  }

  .link-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 8px;
    font-size: 11px;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid var(--border);
    color: var(--muted);
    background: var(--surface);
    transition: all 0.2s;
  }

  .link-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(59,130,246,0.06);
  }

  .link-btn svg { width: 13px; height: 13px; }

  /* ── SECTIONS ── */
  .section {
    margin-bottom: 32px;
    animation: fadeUp 0.6s ease both;
  }

  .section:nth-child(2) { animation-delay: 0.08s; }
  .section:nth-child(3) { animation-delay: 0.14s; }
  .section:nth-child(4) { animation-delay: 0.20s; }
  .section:nth-child(5) { animation-delay: 0.26s; }
  .section:nth-child(6) { animation-delay: 0.32s; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
  }

  .section-label {
    font-family: var(--display);
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT ── */
  .about-text {
    color: #94a3b8;
    font-size: 12.5px;
    line-height: 1.8;
    padding: 20px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    border-left: 3px solid var(--accent);
  }

  .about-text strong { color: var(--text); font-weight: 500; }

  /* ── SKILLS GRID ── */
  .skills-grid {
    display: flex;
    flex-direction: column;
    gap: 14px;
  }

  .skill-row {
    display: flex;
    align-items: flex-start;
    gap: 16px;
  }

  .skill-category {
    font-size: 10px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--muted);
    width: 80px;
    flex-shrink: 0;
    padding-top: 6px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
  }

  .skill-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 11px;
    border-radius: 8px;
    font-size: 11px;
    font-weight: 500;
    background: var(--surface2);
    border: 1px solid var(--border);
    color: var(--text);
    transition: all 0.2s;
  }

  .skill-tag:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(59,130,246,0.06);
    transform: translateY(-1px);
  }

  .skill-tag img {
    width: 14px;
    height: 14px;
    object-fit: contain;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  @media (max-width: 600px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    padding: 18px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    text-decoration: none;
    color: inherit;
    display: block;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.2s;
  }

  .project-card:hover { border-color: rgba(59,130,246,0.3); transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,0.3); }
  .project-card:hover::before { opacity: 1; }

  .project-name {
    font-family: var(--display);
    font-size: 13px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .project-desc {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 12px;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .ptag {
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    background: rgba(59,130,246,0.08);
    color: var(--accent);
    border: 1px solid rgba(59,130,246,0.15);
  }

  /* ── EXPERIENCE ── */
  .exp-list { display: flex; flex-direction: column; gap: 10px; }

  .exp-card {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 14px;
    padding: 16px 18px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    transition: border-color 0.2s;
  }

  .exp-card:hover { border-color: rgba(59,130,246,0.25); }

  .exp-icon {
    width: 36px; height: 36px;
    border-radius: 8px;
    background: var(--surface2);
    border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
  }

  .exp-org {
    font-family: var(--display);
    font-size: 12px;
    font-weight: 700;
    color: #fff;
  }

  .exp-role {
    font-size: 11px;
    color: var(--accent2);
    margin-top: 1px;
  }

  .exp-desc {
    font-size: 11px;
    color: var(--muted);
    margin-top: 5px;
    line-height: 1.6;
  }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .stat-img {
    width: 100%;
    border-radius: 10px;
    border: 1px solid var(--border);
    display: block;
  }

  /* ── FOOTER ── */
  .footer {
    margin-top: 40px;
    padding-top: 24px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: gap;
    gap: 12px;
  }

  .quote {
    font-size: 11px;
    color: var(--muted);
    font-style: italic;
  }

  .quote em { color: var(--accent); font-style: normal; }

  .footer-links { display: flex; gap: 12px; }
  .footer-link { font-size: 11px; color: var(--muted); text-decoration: none; }
  .footer-link:hover { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  /* ── INLINE ICON SVGs ── */
  .ico { display: inline-flex; }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="avatar">AS</div>
    <div class="header-info">
      <div class="name">Ayusman Samantaray</div>
      <div class="title-line">
        <span class="title">B.Tech CSE · GCEK Bhawanipatna</span>
        <span class="dot">·</span>
        <span class="badge badge-green"><span class="dot-live"></span>Open to Opportunities</span>
        <span class="badge badge-blue">Final Year</span>
      </div>
      <p class="tagline">
        <strong>Full-Stack Developer</strong> &amp; <strong>AI/ML Enthusiast</strong> — building automation tools, intelligent systems, and scalable web applications. Passionate about bridging software engineering with machine learning to solve real-world problems.
      </p>
      <div class="links">
        <a class="link-btn" href="https://www.linkedin.com/in/ayusman-samantaray-153906284/" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="link-btn" href="https://github.com/Ayusman23" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
          GitHub
        </a>
        <a class="link-btn" href="https://ayusman23.github.io/Personal-Portfolio/" target="_blank">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z"/><path d="M2 12h20M12 2a15.3 15.3 0 014 10 15.3 15.3 0 01-4 10 15.3 15.3 0 01-4-10 15.3 15.3 0 014-10z"/></svg>
          Portfolio
        </a>
        <a class="link-btn" href="mailto:ayusmansamantaray08@email.com">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Email
        </a>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">About</span>
      <div class="section-line"></div>
    </div>
    <div class="about-text">
      I'm a final-year <strong>Computer Science & Engineering</strong> student with a strong foundation in full-stack development and growing expertise in <strong>AI/ML</strong>. I enjoy building end-to-end systems — from intuitive frontends to scalable backends and intelligent prediction models. My internship experience spans national-level organizations including <strong>DRDO</strong> and <strong>Hindustan Aeronautics Ltd</strong>, where I built production-grade enterprise systems. I'm currently seeking <strong>software engineering roles</strong> where I can contribute meaningfully from day one while continuing to grow.
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">Tech Stack</span>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">

      <div class="skill-row">
        <span class="skill-category">Languages</span>
        <div class="skill-tags">
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="">Python</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="">JavaScript</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="">C++</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="">C</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="">SQL</span>
        </div>
      </div>

      <div class="skill-row">
        <span class="skill-category">Frontend</span>
        <div class="skill-tags">
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="">React.js</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="">HTML5</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="">CSS3</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" alt="">Bootstrap</span>
        </div>
      </div>

      <div class="skill-row">
        <span class="skill-category">Backend</span>
        <div class="skill-tags">
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="">Node.js</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="" style="filter:invert(1)">Express</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" alt="">Django</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dot-net/dot-net-original.svg" alt="">.NET</span>
        </div>
      </div>

      <div class="skill-row">
        <span class="skill-category">Databases</span>
        <div class="skill-tags">
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="">MongoDB</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="">MySQL</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="">PostgreSQL</span>
        </div>
      </div>

      <div class="skill-row">
        <span class="skill-category">Tools</span>
        <div class="skill-tags">
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="">Git</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="" style="filter:invert(0.6)">GitHub</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg" alt="">Azure</span>
          <span class="skill-tag"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" alt="">Docker</span>
        </div>
      </div>

    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">Projects</span>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <a class="project-card" href="https://github.com/Ayusman23/Disease-Prediction_Doctor-Recommendation_APP.git" target="_blank">
        <div class="project-name">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#3b82f6" stroke-width="2"><path d="M22 12h-4l-3 9L9 3l-3 9H2"/></svg>
          Disease Prediction App
        </div>
        <div class="project-desc">MERN + Python ML application for healthcare — predicts diseases and recommends specialist doctors based on symptoms.</div>
        <div class="project-tags">
          <span class="ptag">React</span>
          <span class="ptag">Node.js</span>
          <span class="ptag">Python</span>
          <span class="ptag">ML</span>
          <span class="ptag">MongoDB</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/Ayusman23/Ai-Virtual-Assistant.git" target="_blank">
        <div class="project-name">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#06b6d4" stroke-width="2"><path d="M12 2a3 3 0 003-3"/><path d="M19 10v2a7 7 0 01-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/><rect x="9" y="2" width="6" height="11" rx="3"/></svg>
          AI Virtual Assistant
        </div>
        <div class="project-desc">Personal AI voice assistant with face recognition, natural language processing, and Gemini API integration for intelligent task automation.</div>
        <div class="project-tags">
          <span class="ptag">Python</span>
          <span class="ptag">Gemini API</span>
          <span class="ptag">OpenCV</span>
          <span class="ptag">NLP</span>
        </div>
      </a>

    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">Experience</span>
      <div class="section-line"></div>
    </div>
    <div class="exp-list">

      <div class="exp-card">
        <div class="exp-icon">🛡️</div>
        <div>
          <div class="exp-org">ITR, DRDO — Balasore</div>
          <div class="exp-role">Web Research Intern</div>
          <div class="exp-desc">Designed and developed a Canteen Management System using the .NET Framework and MySQL, deployed internally for staff and facility use at a premier defence research organization.</div>
        </div>
      </div>

      <div class="exp-card">
        <div class="exp-icon">✈️</div>
        <div>
          <div class="exp-org">Hindustan Aeronautics Ltd (HAL)</div>
          <div class="exp-role">Web Development Intern</div>
          <div class="exp-desc">Gained hands-on experience developing enterprise-grade web solutions, working within strict security and reliability standards at India's premier aerospace manufacturer.</div>
        </div>
      </div>

      <div class="exp-card">
        <div class="exp-icon">💻</div>
        <div>
          <div class="exp-org">Cipherbyte Technologies</div>
          <div class="exp-role">Web Development Intern</div>
          <div class="exp-desc">Built responsive web components and improved UI/UX across client-facing products, with focus on cross-browser compatibility and clean component architecture.</div>
        </div>
      </div>

    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-header">
      <span class="section-label">GitHub Activity</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-row">
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api?username=Ayusman23&show_icons=true&theme=transparent&bg_color=0f1521&title_color=3b82f6&text_color=94a3b8&icon_color=06b6d4&border_color=1e2d47&hide_border=false" alt="GitHub Stats">
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ayusman23&layout=compact&theme=transparent&bg_color=0f1521&title_color=3b82f6&text_color=94a3b8&border_color=1e2d47&hide_border=false" alt="Top Languages">
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="quote">"The best way to predict the future is to <em>invent it.</em>"</div>
    <div class="footer-links">
      <a class="footer-link" href="mailto:ayusmansamantaray08@email.com">ayusmansamantaray08@email.com</a>
    </div>
  </div>

</div>
</body>
</html>
