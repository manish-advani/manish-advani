<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Manesh Kumar Advani — Full-Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Sora:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --surface2: #18181f;
    --border: #2a2a38;
    --accent: #7c5cfc;
    --accent2: #fc5c7d;
    --accent3: #5cf4d8;
    --text: #e8e8f0;
    --muted: #7a7a90;
    --mono: 'Space Mono', monospace;
    --sans: 'Sora', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    font-size: 16px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* Background grid */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,92,252,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,92,252,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* Glow orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(120px);
    pointer-events: none;
    z-index: 0;
    opacity: 0.18;
  }
  .orb-1 { width: 500px; height: 500px; background: var(--accent); top: -150px; right: -100px; }
  .orb-2 { width: 400px; height: 400px; background: var(--accent2); bottom: 100px; left: -100px; }
  .orb-3 { width: 300px; height: 300px; background: var(--accent3); top: 50%; left: 50%; }

  main { position: relative; z-index: 1; }

  /* ─── HERO ─── */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 80px 24px 60px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .hero-inner {
    width: 100%;
    animation: fadeUp 0.8s ease both;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(124,92,252,0.12);
    border: 1px solid rgba(124,92,252,0.3);
    border-radius: 100px;
    padding: 6px 16px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--accent);
    margin-bottom: 28px;
    letter-spacing: 0.05em;
  }

  .hero-badge::before {
    content: '';
    width: 7px; height: 7px;
    background: var(--accent3);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  .hero-name {
    font-size: clamp(2.4rem, 7vw, 5.5rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    margin-bottom: 16px;
  }

  .hero-name .line-2 {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-title {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    color: var(--muted);
    font-weight: 300;
    margin-bottom: 32px;
    letter-spacing: 0.02em;
  }

  .hero-title strong { color: var(--accent3); font-weight: 600; }

  .hero-desc {
    max-width: 580px;
    color: #aaabb8;
    margin-bottom: 40px;
    font-size: 1rem;
  }

  .hero-links {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 12px 24px;
    border-radius: 10px;
    font-family: var(--sans);
    font-size: 14px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.2s ease;
    cursor: pointer;
    border: none;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--accent), #9b7cff);
    color: #fff;
    box-shadow: 0 4px 20px rgba(124,92,252,0.35);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(124,92,252,0.5); }

  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); background: rgba(124,92,252,0.06); }

  .btn-whatsapp {
    background: rgba(37,211,102,0.12);
    color: #25d366;
    border: 1px solid rgba(37,211,102,0.3);
  }
  .btn-whatsapp:hover { background: rgba(37,211,102,0.2); }

  /* ─── SECTIONS ─── */
  .section {
    padding: 80px 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .section-label {
    font-family: var(--mono);
    font-size: 11px;
    letter-spacing: 0.15em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .section-title {
    font-size: clamp(1.6rem, 4vw, 2.5rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    margin-bottom: 48px;
    line-height: 1.1;
  }

  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 0 24px;
  }

  /* ─── SKILLS ─── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 20px;
  }

  .skill-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    transition: border-color 0.2s, transform 0.2s;
    position: relative;
    overflow: hidden;
  }

  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.2s;
  }

  .skill-card:hover { border-color: rgba(124,92,252,0.4); transform: translateY(-3px); }
  .skill-card:hover::before { opacity: 1; }

  .skill-card-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
  }

  .skill-icon {
    width: 40px; height: 40px;
    border-radius: 10px;
    display: grid;
    place-items: center;
    font-size: 20px;
    background: rgba(124,92,252,0.12);
  }

  .skill-card-title { font-weight: 700; font-size: 15px; }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 3px 10px;
    font-size: 12px;
    color: var(--muted);
    font-family: var(--mono);
    transition: color 0.2s, border-color 0.2s;
  }

  .skill-card:hover .tag { color: #b0b0c8; border-color: #3a3a4a; }

  /* ─── PROJECTS ─── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }

  .project-card:hover { border-color: rgba(124,92,252,0.4); transform: translateY(-4px); box-shadow: 0 20px 60px rgba(0,0,0,0.4); }

  .project-emoji { font-size: 32px; margin-bottom: 16px; display: block; }

  .project-card h3 {
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 8px;
  }

  .project-card p {
    color: var(--muted);
    font-size: 14px;
  }

  .project-card-accent {
    position: absolute;
    bottom: -20px; right: -20px;
    width: 80px; height: 80px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(124,92,252,0.2), transparent);
    transition: transform 0.3s;
  }

  .project-card:hover .project-card-accent { transform: scale(2); }

  /* ─── FOCUS TABLE ─── */
  .focus-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
  }

  .focus-item {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    font-size: 14px;
    font-weight: 600;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }

  .focus-item span { display: block; font-size: 24px; margin-bottom: 8px; }
  .focus-item:hover { border-color: var(--accent); color: var(--accent); background: rgba(124,92,252,0.06); }

  /* ─── CONNECT ─── */
  .connect-box {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 24px;
    padding: clamp(32px, 5vw, 60px);
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .connect-box::before {
    content: '';
    position: absolute;
    inset: -2px;
    border-radius: 26px;
    background: linear-gradient(135deg, var(--accent), var(--accent2), var(--accent3));
    z-index: -1;
    opacity: 0.4;
  }

  .connect-box h2 {
    font-size: clamp(1.6rem, 4vw, 2.5rem);
    font-weight: 800;
    margin-bottom: 12px;
    letter-spacing: -0.02em;
  }

  .connect-box p {
    color: var(--muted);
    margin-bottom: 32px;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
  }

  .connect-links {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 12px;
  }

  /* ─── FOOTER ─── */
  footer {
    text-align: center;
    padding: 32px 24px;
    color: var(--muted);
    font-size: 13px;
    font-family: var(--mono);
    border-top: 1px solid var(--border);
  }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-in.visible { opacity: 1; transform: translateY(0); }

  /* ─── NAV ─── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 16px 24px;
    backdrop-filter: blur(20px);
    background: rgba(10,10,15,0.8);
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav-logo {
    font-family: var(--mono);
    font-size: 14px;
    font-weight: 700;
    color: var(--accent);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 24px;
    list-style: none;
  }

  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 14px;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--text); }

  /* ─── CODE BLOCK ─── */
  .code-block {
    background: #0d0d14;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 24px;
    font-family: var(--mono);
    font-size: 13px;
    line-height: 1.8;
    overflow-x: auto;
    margin-top: 24px;
  }

  .code-key { color: var(--accent2); }
  .code-val { color: var(--accent3); }
  .code-punct { color: var(--muted); }
  .code-str { color: #a8ff78; }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 768px) {
    .orb-1 { width: 300px; height: 300px; }
    .orb-2 { width: 250px; height: 250px; }
    .orb-3 { display: none; }

    .nav-links { display: none; }

    .hero { padding: 100px 20px 60px; }

    .section { padding: 60px 20px; }

    .skills-grid,
    .projects-grid { grid-template-columns: 1fr; }

    .focus-grid { grid-template-columns: repeat(2, 1fr); }

    .btn { padding: 10px 18px; font-size: 13px; }
  }

  @media (max-width: 480px) {
    .focus-grid { grid-template-columns: 1fr 1fr; }
    .hero-links { flex-direction: column; align-items: flex-start; }
    .connect-links { flex-direction: column; align-items: center; }
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<nav>
  <a href="#" class="nav-logo">MKA.dev</a>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#connect">Connect</a></li>
  </ul>
</nav>

<main>
  <!-- HERO -->
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-badge">Available for new opportunities</div>
      <h1 class="hero-name">
        <span class="line-1">Manesh Kumar</span><br>
        <span class="line-2">Advani</span>
      </h1>
      <p class="hero-title">
        Full-Stack Developer &nbsp;·&nbsp; <strong>PHP · Laravel · WordPress</strong> &nbsp;·&nbsp; Dubai, UAE 📍
      </p>
      <p class="hero-desc">
        PHP Developer with 5+ years of experience building scalable web applications, backend systems, and SEO-optimized platforms. Specialized in iGaming, live streaming, CRM/ERP, and affiliate marketing solutions.
      </p>
      <div class="hero-links">
        <a href="https://linkedin.com/in/manesh-kumar-advani" target="_blank" class="btn btn-primary">
          <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a href="mailto:manishotic@gmail.com" class="btn btn-outline">
          <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
          Email Me
        </a>
        <a href="https://wa.me/971509570380" target="_blank" class="btn btn-whatsapp">
          <svg width="16" height="16" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.126 1.532 5.857L.057 23.998l6.305-1.652A11.954 11.954 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.805 9.805 0 01-5.031-1.386l-.361-.214-3.741.981 1.001-3.648-.235-.374A9.796 9.796 0 012.182 12C2.182 6.58 6.58 2.182 12 2.182S21.818 6.58 21.818 12 17.42 21.818 12 21.818z"/></svg>
          WhatsApp
        </a>
        <a href="https://digitaladexperts.com/" target="_blank" class="btn btn-outline">
          🏢 Company
        </a>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- SKILLS -->
  <section class="section fade-in" id="skills">
    <div class="section-label">// technical_skills</div>
    <h2 class="section-title">What I Build With</h2>

    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">🔧</div>
          <div class="skill-card-title">Backend Development</div>
        </div>
        <div class="skill-tags">
          <span class="tag">PHP 5/7/8</span>
          <span class="tag">Laravel</span>
          <span class="tag">OOP</span>
          <span class="tag">MVC</span>
          <span class="tag">REST API</span>
          <span class="tag">SOAP</span>
          <span class="tag">AJAX</span>
          <span class="tag">JSON</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">🎨</div>
          <div class="skill-card-title">CMS & Platforms</div>
        </div>
        <div class="skill-tags">
          <span class="tag">WordPress</span>
          <span class="tag">Custom Themes</span>
          <span class="tag">Plugin Dev</span>
          <span class="tag">WP REST API</span>
          <span class="tag">Magento</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">🌐</div>
          <div class="skill-card-title">Frontend Development</div>
        </div>
        <div class="skill-tags">
          <span class="tag">JavaScript ES6+</span>
          <span class="tag">React.js</span>
          <span class="tag">Next.js</span>
          <span class="tag">TypeScript</span>
          <span class="tag">jQuery</span>
          <span class="tag">Alpine.js</span>
          <span class="tag">Tailwind CSS</span>
          <span class="tag">Bootstrap</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">💾</div>
          <div class="skill-card-title">Databases</div>
        </div>
        <div class="skill-tags">
          <span class="tag">MySQL</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">MongoDB</span>
          <span class="tag">SQL Server</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">📈</div>
          <div class="skill-card-title">SEO & Performance</div>
        </div>
        <div class="skill-tags">
          <span class="tag">Technical SEO</span>
          <span class="tag">On-page SEO</span>
          <span class="tag">Core Web Vitals</span>
          <span class="tag">PageSpeed</span>
          <span class="tag">GA4</span>
          <span class="tag">Search Console</span>
          <span class="tag">Yoast</span>
          <span class="tag">Rank Math</span>
        </div>
      </div>

      <div class="skill-card">
        <div class="skill-card-header">
          <div class="skill-icon">⚙️</div>
          <div class="skill-card-title">DevOps & Tools</div>
        </div>
        <div class="skill-tags">
          <span class="tag">Git</span>
          <span class="tag">Docker</span>
          <span class="tag">Jira</span>
          <span class="tag">Trello</span>
          <span class="tag">Linux</span>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- PROJECTS -->
  <section class="section fade-in" id="projects">
    <div class="section-label">// project_highlights</div>
    <h2 class="section-title">What I've Built</h2>

    <div class="projects-grid">
      <div class="project-card">
        <span class="project-emoji">🎮</span>
        <h3>iGaming Platforms</h3>
        <p>Scalable, secure gaming systems built for high traffic and real-time interactions.</p>
        <div class="project-card-accent"></div>
      </div>
      <div class="project-card">
        <span class="project-emoji">📺</span>
        <h3>Live Streaming Systems</h3>
        <p>Laravel + WordPress + REST APIs powering real-time media delivery at scale.</p>
        <div class="project-card-accent"></div>
      </div>
      <div class="project-card">
        <span class="project-emoji">🏢</span>
        <h3>CRM / ERP / HRMS</h3>
        <p>Enterprise business applications for internal ops, HR, and resource management.</p>
        <div class="project-card-accent"></div>
      </div>
      <div class="project-card">
        <span class="project-emoji">🤝</span>
        <h3>Affiliate Portals</h3>
        <p>Marketing dashboards with analytics, tracking, and partner management systems.</p>
        <div class="project-card-accent"></div>
      </div>
      <div class="project-card">
        <span class="project-emoji">🔍</span>
        <h3>SEO-Optimized Sites</h3>
        <p>High-traffic lead generation websites built around Core Web Vitals and search rankings.</p>
        <div class="project-card-accent"></div>
      </div>
      <div class="project-card">
        <span class="project-emoji">🏗️</span>
        <h3>Modular Architecture</h3>
        <p>Clean, maintainable, reusable codebases designed for long-term scalability.</p>
        <div class="project-card-accent"></div>
      </div>
    </div>

    <div class="code-block">
<span class="code-punct">$</span><span class="code-key">projects</span> <span class="code-punct">= [</span><br>
&nbsp;&nbsp;<span class="code-str">'iGaming'</span> <span class="code-punct">=></span> <span class="code-val">'Scalable, secure gaming systems'</span><span class="code-punct">,</span><br>
&nbsp;&nbsp;<span class="code-str">'Streaming'</span> <span class="code-punct">=></span> <span class="code-val">'Laravel + WordPress + REST APIs'</span><span class="code-punct">,</span><br>
&nbsp;&nbsp;<span class="code-str">'CRM/ERP'</span> <span class="code-punct">=></span> <span class="code-val">'Enterprise business applications'</span><span class="code-punct">,</span><br>
&nbsp;&nbsp;<span class="code-str">'Affiliate'</span> <span class="code-punct">=></span> <span class="code-val">'Marketing dashboards with analytics'</span><span class="code-punct">,</span><br>
&nbsp;&nbsp;<span class="code-str">'SEO'</span> <span class="code-punct">=></span> <span class="code-val">'High-traffic lead generation'</span><span class="code-punct">,</span><br>
<span class="code-punct">];</span>
    </div>
  </section>

  <div class="divider"></div>

  <!-- FOCUS -->
  <section class="section fade-in">
    <div class="section-label">// focus_areas</div>
    <h2 class="section-title">Core Focus</h2>
    <div class="focus-grid">
      <div class="focus-item"><span>⚡</span>PHP & Laravel</div>
      <div class="focus-item"><span>🌐</span>WordPress Dev</div>
      <div class="focus-item"><span>🔌</span>API-Driven Apps</div>
      <div class="focus-item"><span>🔍</span>SEO Architecture</div>
      <div class="focus-item"><span>🚀</span>Performance</div>
      <div class="focus-item"><span>✨</span>Clean Code</div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- CONNECT -->
  <section class="section fade-in" id="connect">
    <div class="connect-box">
      <div class="section-label" style="margin-bottom:16px;">// let_s_connect</div>
      <h2>Open to New Opportunities</h2>
      <p>Looking for roles in PHP, Laravel, WordPress, iGaming platforms, streaming systems, and SaaS products. Let's build something great together.</p>
      <div class="connect-links">
        <a href="https://linkedin.com/in/manesh-kumar-advani" target="_blank" class="btn btn-primary">
          LinkedIn
        </a>
        <a href="mailto:manishotic@gmail.com" class="btn btn-outline">
          manishotic@gmail.com
        </a>
        <a href="https://wa.me/971509570380" target="_blank" class="btn btn-whatsapp">
          +971 50 957 0380
        </a>
        <a href="https://digitaladexperts.com/" target="_blank" class="btn btn-outline">
          digitaladexperts.com
        </a>
      </div>
    </div>
  </section>
</main>

<footer>
  <p>© 2025 Manesh Kumar Advani &nbsp;·&nbsp; Dubai, UAE &nbsp;·&nbsp; Built with clean code ✦</p>
</footer>

<script>
  // Scroll fade-in
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

  // Staggered card animation
  document.querySelectorAll('.skill-card, .project-card, .focus-item').forEach((el, i) => {
    el.style.transitionDelay = `${i * 0.05}s`;
  });
</script>
</body>
</html>
