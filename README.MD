<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mohamad Ibrahim – GitHub Profile README</title>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d0f14;
      --surface: #12151c;
      --card: #181c26;
      --border: #1f2535;
      --accent: #4f8ef7;
      --accent2: #38d9a9;
      --accent3: #f7a74f;
      --text: #e2e8f7;
      --muted: #7a8299;
      --glow: rgba(79,142,247,0.18);
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'JetBrains Mono', monospace;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 3rem 1.5rem;
      overflow-x: hidden;
    }

    /* Ambient background blobs */
    body::before, body::after {
      content: '';
      position: fixed;
      border-radius: 50%;
      filter: blur(120px);
      opacity: 0.09;
      pointer-events: none;
      z-index: 0;
    }
    body::before {
      width: 600px; height: 600px;
      background: var(--accent);
      top: -100px; left: -200px;
    }
    body::after {
      width: 500px; height: 500px;
      background: var(--accent2);
      bottom: 0; right: -150px;
    }

    .readme {
      position: relative;
      z-index: 1;
      width: 100%;
      max-width: 780px;
    }

    /* ── HEADER ── */
    .header {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
      padding: 0 0 2.5rem 0;
      border-bottom: 1px solid var(--border);
      animation: fadeUp 0.6s ease both;
    }

    .header-top {
      display: flex;
      align-items: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .wave { font-size: 2rem; animation: wave 2s infinite; display: inline-block; }
    @keyframes wave {
      0%, 100% { transform: rotate(0deg); }
      20% { transform: rotate(20deg); }
      40% { transform: rotate(-10deg); }
      60% { transform: rotate(15deg); }
    }

    .name {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 2.4rem;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--text) 40%, var(--accent));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .badges {
      display: flex;
      gap: 0.5rem;
      flex-wrap: wrap;
      margin-top: 0.25rem;
    }

    .badge {
      font-size: 0.72rem;
      font-weight: 700;
      padding: 0.25rem 0.75rem;
      border-radius: 2px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }
    .badge-blue  { background: rgba(79,142,247,0.15); color: var(--accent); border: 1px solid rgba(79,142,247,0.3); }
    .badge-green { background: rgba(56,217,169,0.12); color: var(--accent2); border: 1px solid rgba(56,217,169,0.25); }
    .badge-amber { background: rgba(247,167,79,0.12); color: var(--accent3); border: 1px solid rgba(247,167,79,0.25); }

    .tagline {
      color: var(--muted);
      font-size: 0.95rem;
      line-height: 1.7;
      max-width: 580px;
      margin-top: 0.75rem;
    }

    .tagline strong { color: var(--accent2); font-weight: 700; }

    /* ── SECTION ── */
    .section {
      margin-top: 2.5rem;
      animation: fadeUp 0.6s ease both;
    }
    .section:nth-child(2) { animation-delay: 0.1s; }
    .section:nth-child(3) { animation-delay: 0.2s; }
    .section:nth-child(4) { animation-delay: 0.3s; }

    .section-label {
      font-family: 'Syne', sans-serif;
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1.25rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    .section-title {
      font-family: 'Syne', sans-serif;
      font-size: 1.35rem;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 1rem;
    }

    /* ── LANGUAGE LOGOS GRID ── */
    .logos-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.85rem;
    }

    .logo-item {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 0.5rem 0.85rem;
      font-size: 0.82rem;
      color: var(--muted);
      transition: border-color 0.2s, color 0.2s, box-shadow 0.2s, transform 0.2s;
      cursor: default;
    }
    .logo-item:hover {
      border-color: var(--accent);
      color: var(--text);
      box-shadow: 0 0 16px var(--glow);
      transform: translateY(-2px);
    }
    .logo-item img {
      width: 20px;
      height: 20px;
      object-fit: contain;
    }

    /* ── TOOLS GRID ── */
    .tools-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 0.85rem;
    }

    .tool-item {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 0.5rem 0.85rem;
      font-size: 0.82rem;
      color: var(--muted);
      transition: border-color 0.2s, color 0.2s, box-shadow 0.2s, transform 0.2s;
      cursor: default;
    }
    .tool-item:hover {
      border-color: var(--accent2);
      color: var(--text);
      box-shadow: 0 0 16px rgba(56,217,169,0.15);
      transform: translateY(-2px);
    }
    .tool-item img {
      width: 20px;
      height: 20px;
      object-fit: contain;
    }

    /* ── CONNECT ── */
    .connect-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1.5rem 1.75rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .connect-text {
      font-size: 0.9rem;
      color: var(--muted);
      line-height: 1.7;
    }

    .connect-links {
      display: flex;
      gap: 0.75rem;
      flex-wrap: wrap;
    }

    .connect-btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.55rem 1.1rem;
      border-radius: 5px;
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-decoration: none;
      transition: opacity 0.2s, transform 0.2s;
    }
    .connect-btn:hover { opacity: 0.85; transform: translateY(-1px); }

    .btn-github {
      background: rgba(255,255,255,0.08);
      color: var(--text);
      border: 1px solid var(--border);
    }
    .btn-email {
      background: rgba(79,142,247,0.15);
      color: var(--accent);
      border: 1px solid rgba(79,142,247,0.3);
    }
    .btn-linkedin {
      background: rgba(56,217,169,0.1);
      color: var(--accent2);
      border: 1px solid rgba(56,217,169,0.25);
    }

    /* ── FOOTER ── */
    .footer {
      margin-top: 3rem;
      padding-top: 1.5rem;
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.75rem;
      color: var(--muted);
      flex-wrap: wrap;
      gap: 0.5rem;
      animation: fadeUp 0.6s ease 0.4s both;
    }

    .footer-dot { color: var(--accent); margin: 0 0.4rem; }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 520px) {
      .name { font-size: 1.7rem; }
      body { padding: 2rem 1rem; }
    }
  </style>
</head>
<body>
<div class="readme">

  <!-- HEADER -->
  <header class="header">
    <div class="header-top">
      <span class="wave">👋</span>
      <span class="name">Mohamad Ibrahim</span>
    </div>
    <div class="badges">
      <span class="badge badge-blue">Computer Engineering</span>
      <span class="badge badge-green">42 Student</span>
      <span class="badge badge-amber">LIU University</span>
    </div>
    <p class="tagline">
      Passionate about <strong>programming</strong>, <strong>systems engineering</strong>, and <strong>software development</strong>.
      Always building, always learning — from low-level C to full-stack web applications.
    </p>
  </header>

  <!-- LANGUAGES -->
  <section class="section">
    <div class="section-label">01 &mdash; Languages</div>
    <div class="logos-grid">

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C"/>
        C
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++"/>
        C++
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java"/>
        Java
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5"/>
        HTML
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3"/>
        CSS
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" alt="PHP"/>
        PHP
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python"/>
        Python
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" alt="Bash"/>
        Bash
      </div>

      <div class="logo-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL"/>
        MySQL
      </div>

      <!-- Assembly – no devicon, use a clean text chip -->
      <div class="logo-item">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect width="24" height="24" rx="3" fill="#2d3650"/>
          <text x="3" y="17" font-family="monospace" font-size="11" fill="#f7a74f" font-weight="bold">ASM</text>
        </svg>
        Assembly
      </div>

    </div>
  </section>

  <!-- TOOLS -->
  <section class="section">
    <div class="section-label">02 &mdash; Tools &amp; Technologies</div>
    <div class="tools-grid">

      <div class="tool-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="VS Code"/>
        VS Code
      </div>

      <div class="tool-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/arduino/arduino-original.svg" alt="Arduino"/>
        Arduino
      </div>

      <div class="tool-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vim/vim-original.svg" alt="VIM"/>
        VIM
      </div>

      <div class="tool-item">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" style="filter:brightness(2)"/>
        GitHub
      </div>

      <!-- NetBeans – no devicon official, use a stylized chip -->
      <div class="tool-item">
        <svg width="20" height="20" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <rect width="24" height="24" rx="3" fill="#1b6ac9"/>
          <text x="2.5" y="17" font-family="monospace" font-size="9.5" fill="#ffffff" font-weight="bold">NB</text>
        </svg>
        NetBeans
      </div>

    </div>
  </section>

  <!-- CONNECT -->
  <section class="section">
    <div class="section-label">03 &mdash; Connect</div>
    <div class="connect-card">
      <p class="connect-text">
        Thanks for stopping by! Feel free to explore my repositories and reach out if you'd like to collaborate, discuss a project, or just talk code.
      </p>
      <div class="connect-links">
        <a href="https://github.com/" class="connect-btn btn-github">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
          GitHub
        </a>
        <a href="mailto:" class="connect-btn btn-email">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M2 7l10 7 10-7"/></svg>
          Email Me
        </a>
        <a href="https://linkedin.com/" class="connect-btn btn-linkedin">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <span>Mohamad Ibrahim<span class="footer-dot">·</span>Computer Engineering</span>
    <span>LIU University<span class="footer-dot">·</span>42 School</span>
  </footer>

</div>
</body>
</html>