<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Rafey Ahmed — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Bebas+Neue&family=Antonio:wght@100;300;400;700&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #000000;
    --white: #ffffff;
    --offwhite: #f5f5f0;
    --accent: #ff3366;
    --accent-dark: #cc0033;
    --green: #00ff88;
    --blue: #0066ff;
    --yellow: #ffcc00;
    --gray-dark: #1a1a1a;
    --gray-mid: #333333;
    --gray-light: #666666;
    --shadow-sm: 4px 4px 0 var(--black);
    --shadow-md: 6px 6px 0 var(--black);
    --shadow-lg: 8px 8px 0 var(--black);
    --border-sm: 2px solid var(--black);
    --border-md: 3px solid var(--black);
    --border-lg: 4px solid var(--black);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--offwhite);
    color: var(--black);
    font-family: 'Space Mono', monospace;
    overflow-x: hidden;
    cursor: crosshair;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9999;
    opacity: 0.5;
  }

  /* ── HEADER ── */
  header {
    background: var(--black);
    color: var(--white);
    padding: 0 2rem;
    height: 64px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: var(--border-lg);
    position: sticky;
    top: 0;
    z-index: 300;
    animation: fadeInDown 0.5s ease both;
  }

  .header-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem;
    letter-spacing: 0.08em;
    color: var(--green);
    text-shadow: 2px 2px 0 var(--accent);
  }

  .header-nav {
    display: flex;
    gap: 1.5rem;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .header-nav a {
    color: var(--white);
    text-decoration: none;
    position: relative;
    padding-bottom: 2px;
    transition: color 0.15s ease;
  }

  .header-nav a::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 0; height: 2px;
    background: var(--green);
    transition: width 0.2s ease;
  }

  .header-nav a:hover { color: var(--green); }
  .header-nav a:hover::after { width: 100%; }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr 1fr;
    min-height: calc(100vh - 64px);
    border-bottom: var(--border-lg);
  }

  .hero-left {
    padding: 4rem 3rem;
    border-right: var(--border-lg);
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 2rem;
    animation: slideInLeft 0.7s ease both 0.1s;
  }

  .hero-eyebrow {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gray-light);
  }

  .live-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--green);
    animation: livePulse 2s infinite;
  }

  .hero-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(4rem, 8vw, 7rem);
    line-height: 0.9;
    letter-spacing: -0.01em;
  }

  .hero-title .line-accent { color: var(--accent); display: block; }
  .hero-title .line-outline {
    -webkit-text-stroke: 3px var(--black);
    color: transparent;
    display: block;
  }

  .hero-desc {
    font-size: 0.8rem;
    line-height: 1.9;
    color: var(--gray-mid);
    max-width: 380px;
    border-left: 4px solid var(--yellow);
    padding-left: 1rem;
  }

  .hero-cta {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn {
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 0.75rem 1.5rem;
    border: var(--border-md);
    cursor: crosshair;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    transition: transform 0.15s ease, box-shadow 0.15s ease;
    font-weight: 700;
  }

  .btn-primary {
    background: var(--accent);
    color: var(--white);
    box-shadow: var(--shadow-md);
  }

  .btn-primary:hover {
    transform: translate(-3px, -3px);
    box-shadow: 9px 9px 0 var(--black);
  }

  .btn-outline {
    background: transparent;
    color: var(--black);
    box-shadow: var(--shadow-sm);
  }

  .btn-outline:hover {
    background: var(--black);
    color: var(--white);
    transform: translate(-3px, -3px);
    box-shadow: 9px 9px 0 var(--accent);
  }

  /* ── HERO RIGHT ── */
  .hero-right {
    background: var(--black);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 3rem;
    gap: 2.5rem;
    animation: slideInRight 0.7s ease both 0.2s;
    position: relative;
    overflow: hidden;
  }

  .hero-right::before {
    content: 'RAFEY';
    font-family: 'Bebas Neue', sans-serif;
    font-size: 12rem;
    color: rgba(255,255,255,0.03);
    position: absolute;
    letter-spacing: 0.1em;
    pointer-events: none;
    user-select: none;
  }

  .status-card {
    width: 100%;
    max-width: 380px;
    border: var(--border-md);
    border-color: var(--green);
    box-shadow: 6px 6px 0 var(--green);
    padding: 1.5rem;
    background: var(--gray-dark);
    position: relative;
  }

  .status-label {
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--green);
    margin-bottom: 0.75rem;
  }

  .status-item {
    display: flex;
    align-items: flex-start;
    gap: 0.75rem;
    padding: 0.6rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.08);
    color: var(--white);
    font-size: 0.72rem;
  }

  .status-item:last-child { border-bottom: none; }

  .status-icon {
    font-size: 1rem;
    min-width: 20px;
    text-align: center;
  }

  .status-text { line-height: 1.5; }
  .status-text strong { color: var(--yellow); display: block; font-size: 0.65rem; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 2px; }

  .typing-block {
    width: 100%;
    max-width: 380px;
    background: var(--gray-dark);
    border: var(--border-md);
    border-color: var(--gray-mid);
    box-shadow: 6px 6px 0 rgba(255,51,102,0.35);
    padding: 1.25rem 1.5rem;
  }

  .typing-prompt {
    font-size: 0.65rem;
    color: var(--green);
    margin-bottom: 0.5rem;
    letter-spacing: 0.1em;
  }

  .typing-text {
    font-family: 'Space Mono', monospace;
    font-size: 0.8rem;
    color: var(--white);
    min-height: 1.4em;
  }

  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    vertical-align: middle;
    margin-left: 2px;
    animation: blink 1s infinite;
  }

  /* ── SECTION BASE ── */
  section { border-bottom: var(--border-lg); }

  .section-header {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    padding: 1.5rem 3rem;
    border-bottom: var(--border-md);
    background: var(--black);
    color: var(--white);
  }

  .section-num {
    font-family: 'Antonio', sans-serif;
    font-size: 3rem;
    font-weight: 700;
    color: var(--accent);
    line-height: 1;
  }

  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.2rem;
    letter-spacing: 0.05em;
  }

  .section-tag {
    margin-left: auto;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gray-light);
    border: 1px solid var(--gray-mid);
    padding: 0.25rem 0.75rem;
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
  }

  .about-card {
    padding: 2.5rem 2rem;
    border-right: var(--border-md);
    animation: fadeInUp 0.6s ease both;
  }

  .about-card:last-child { border-right: none; }

  .about-card-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
  }

  .about-card-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.4rem;
    letter-spacing: 0.05em;
    margin-bottom: 0.75rem;
    color: var(--black);
  }

  .about-card p {
    font-size: 0.72rem;
    line-height: 1.8;
    color: var(--gray-mid);
  }

  .about-card:nth-child(1) { background: var(--yellow); }
  .about-card:nth-child(2) { background: var(--white); }
  .about-card:nth-child(3) { background: var(--offwhite); }

  /* ── TECH ── */
  .tech-section { background: var(--black); }

  .tech-grid {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    border-top: var(--border-md);
  }

  .tech-item {
    padding: 1.75rem 1.25rem;
    border-right: 2px solid var(--gray-mid);
    border-bottom: 2px solid var(--gray-mid);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.75rem;
    transition: background 0.15s ease, transform 0.15s ease;
    cursor: crosshair;
    position: relative;
    overflow: hidden;
  }

  .tech-item::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--accent);
    transform: scaleY(0);
    transform-origin: bottom;
    transition: transform 0.2s ease;
    z-index: 0;
  }

  .tech-item:hover::before { transform: scaleY(1); }
  .tech-item:hover .tech-name { color: var(--white); }

  .tech-icon {
    font-size: 1.8rem;
    position: relative;
    z-index: 1;
  }

  .tech-name {
    font-size: 0.6rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gray-light);
    text-align: center;
    position: relative;
    z-index: 1;
    transition: color 0.15s ease;
  }

  /* ── STATS MARQUEE ── */
  .marquee-wrap {
    background: var(--accent);
    border-top: var(--border-md);
    border-bottom: var(--border-md);
    overflow: hidden;
    padding: 1rem 0;
    white-space: nowrap;
  }

  .marquee-track {
    display: inline-flex;
    gap: 3rem;
    animation: marqueeScroll 20s linear infinite;
  }

  .marquee-item {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.3rem;
    letter-spacing: 0.1em;
    color: var(--white);
    display: flex;
    align-items: center;
    gap: 1rem;
    white-space: nowrap;
  }

  .marquee-sep {
    color: var(--yellow);
    font-size: 1rem;
  }

  /* ── GITHUB STATS ── */
  .stats-section { background: var(--offwhite); }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
  }

  .stats-pane {
    padding: 3rem;
    border-right: var(--border-md);
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    animation: fadeInUp 0.6s ease both;
  }

  .stats-pane:last-child { border-right: none; }

  .stats-pane-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    letter-spacing: 0.05em;
    border-bottom: var(--border-sm);
    padding-bottom: 0.75rem;
  }

  .stats-img-wrap {
    border: var(--border-md);
    box-shadow: var(--shadow-lg);
    overflow: hidden;
    background: var(--white);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .stats-img-wrap:hover {
    transform: translate(-4px, -4px);
    box-shadow: 12px 12px 0 var(--black);
  }

  .stats-img-wrap img {
    display: block;
    width: 100%;
    height: auto;
  }

  /* ── CONTACT ── */
  .contact-section {
    background: var(--black);
    color: var(--white);
  }

  .contact-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .contact-left {
    padding: 4rem 3rem;
    border-right: var(--border-lg);
    border-color: var(--gray-mid);
    display: flex;
    flex-direction: column;
    gap: 2rem;
    justify-content: center;
  }

  .contact-big {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3rem, 5vw, 5.5rem);
    line-height: 0.95;
    letter-spacing: -0.01em;
  }

  .contact-big .accent { color: var(--accent); }
  .contact-big .green { color: var(--green); }

  .contact-sub {
    font-size: 0.72rem;
    color: var(--gray-light);
    line-height: 1.9;
    max-width: 360px;
  }

  .contact-right {
    padding: 4rem 3rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    justify-content: center;
    align-items: flex-start;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    text-decoration: none;
    color: var(--white);
    padding: 1.25rem 1.75rem;
    border: 2px solid var(--gray-mid);
    width: 100%;
    max-width: 360px;
    transition: border-color 0.15s, background 0.15s, transform 0.15s, box-shadow 0.15s;
    font-size: 0.75rem;
    letter-spacing: 0.05em;
    position: relative;
    overflow: hidden;
  }

  .contact-link::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 4px;
    background: var(--accent);
    transform: scaleY(0);
    transition: transform 0.2s ease;
  }

  .contact-link:hover {
    border-color: var(--accent);
    transform: translate(-4px, -4px);
    box-shadow: 8px 8px 0 var(--accent);
  }

  .contact-link:hover::before { transform: scaleY(1); }

  .contact-link-icon { font-size: 1.4rem; }
  .contact-link-label { display: flex; flex-direction: column; gap: 2px; }
  .contact-link-label span:first-child { font-size: 0.6rem; color: var(--gray-light); letter-spacing: 0.15em; text-transform: uppercase; }
  .contact-link-label span:last-child { font-size: 0.8rem; font-weight: 700; }

  /* ── FOOTER ── */
  footer {
    background: var(--gray-dark);
    color: var(--gray-light);
    padding: 1.5rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    border-top: var(--border-lg);
    border-color: var(--gray-mid);
  }

  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.2rem;
    color: var(--white);
    letter-spacing: 0.1em;
  }

  .footer-copy span { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(60px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes slideInLeft {
    from { opacity: 0; transform: translateX(-40px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes slideInRight {
    from { opacity: 0; transform: translateX(40px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes livePulse {
    0%, 100% { box-shadow: 0 0 0 0 rgba(0,255,136,0.7); }
    50% { box-shadow: 0 0 0 6px rgba(0,255,136,0); }
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }
  @keyframes marqueeScroll {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }
  @keyframes glitch {
    0% { transform: translate(0); }
    20% { transform: translate(-2px, 2px); }
    40% { transform: translate(-2px, -2px); }
    60% { transform: translate(2px, 2px); }
    80% { transform: translate(2px, -2px); }
    100% { transform: translate(0); }
  }

  /* ── SCROLL REVEAL ── */
  .reveal { opacity: 0; transform: translateY(40px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .hero { grid-template-columns: 1fr; }
    .hero-right { min-height: 60vh; }
    .about-grid { grid-template-columns: 1fr; }
    .about-card { border-right: none; border-bottom: var(--border-md); }
    .tech-grid { grid-template-columns: repeat(3, 1fr); }
    .stats-grid { grid-template-columns: 1fr; }
    .stats-pane { border-right: none; border-bottom: var(--border-md); }
    .contact-inner { grid-template-columns: 1fr; }
    .contact-left { border-right: none; border-bottom: 2px solid var(--gray-mid); }
    .section-header { padding: 1.25rem 1.5rem; }
    .section-num { font-size: 2rem; }
    .hero-left { padding: 2.5rem 1.5rem; }
    footer { flex-direction: column; gap: 0.5rem; text-align: center; }
    .header-nav { display: none; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="header-logo">RA/</div>
  <nav class="header-nav">
    <a href="#about">About</a>
    <a href="#tech">Stack</a>
    <a href="#stats">Stats</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">
      <span class="live-dot"></span>
      <span>Available for Collaboration</span>
    </div>

    <h1 class="hero-title">
      <span class="line-outline">RAFEY</span>
      <span>AHMED</span>
      <span class="line-accent">.</span>
    </h1>

    <p class="hero-desc">
      Open-Source Enthusiast · Learning in Public · MERN Stack Developer.<br/>
      Building things on the web, one commit at a time. Ask me anything — except Maths 😅
    </p>

    <div class="hero-cta">
      <a href="mailto:hi@rafeyahmed.com" class="btn btn-primary">✉ Say Hello</a>
      <a href="https://github.com/itsabdulrafey" target="_blank" class="btn btn-outline">⌥ GitHub</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="status-card">
      <div class="status-label">// current_status.json</div>

      <div class="status-item">
        <span class="status-icon">🔭</span>
        <div class="status-text">
          <strong>Working On</strong>
          Something Interesting™
        </div>
      </div>
      <div class="status-item">
        <span class="status-icon">🌱</span>
        <div class="status-text">
          <strong>Learning</strong>
          MERN Stack — MongoDB, Express, React, Node
        </div>
      </div>
      <div class="status-item">
        <span class="status-icon">👯</span>
        <div class="status-text">
          <strong>Open To</strong>
          Dev Project Collaborations
        </div>
      </div>
      <div class="status-item">
        <span class="status-icon">🤔</span>
        <div class="status-text">
          <strong>Need Help With</strong>
          Competitive Programming
        </div>
      </div>
      <div class="status-item">
        <span class="status-icon">⚡</span>
        <div class="status-text">
          <strong>Fun Fact</strong>
          Wasting time gaming is a valid hobby
        </div>
      </div>
    </div>

    <div class="typing-block">
      <div class="typing-prompt">$ whoami --verbose</div>
      <div class="typing-text" id="typing-out"></div><span class="cursor"></span>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track" id="marquee-track">
    <span class="marquee-item">Open Source <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">MERN Stack <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Learning In Public <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">React Developer <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Next.js Enthusiast <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">JavaScript <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Tailwind CSS <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">hi@rafeyahmed.com <span class="marquee-sep">✦</span></span>
    <!-- duplicate for seamless loop -->
    <span class="marquee-item">Open Source <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">MERN Stack <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Learning In Public <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">React Developer <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Next.js Enthusiast <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">JavaScript <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">Tailwind CSS <span class="marquee-sep">✦</span></span>
    <span class="marquee-item">hi@rafeyahmed.com <span class="marquee-sep">✦</span></span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <div class="section-num">01</div>
    <div class="section-title">About Me</div>
    <div class="section-tag">Who is Rafey?</div>
  </div>
  <div class="about-grid">
    <div class="about-card reveal">
      <span class="about-card-icon">🚀</span>
      <div class="about-card-title">Builder</div>
      <p>I build web applications with modern JavaScript technologies. Currently deep in the MERN stack, shipping features and learning every day.</p>
    </div>
    <div class="about-card reveal">
      <span class="about-card-icon">🌐</span>
      <div class="about-card-title">Open Source</div>
      <p>I believe in building in public and sharing knowledge. If I learn something new, I share it. That's the cycle that makes our community stronger.</p>
    </div>
    <div class="about-card reveal">
      <span class="about-card-icon">🎮</span>
      <div class="about-card-title">Human</div>
      <p>When I'm not coding, I'm gaming. Yep, most of my free time goes there. No regrets. Life's about balance — or the lack of it.</p>
    </div>
  </div>
</section>

<!-- TECH STACK -->
<section id="tech" class="tech-section">
  <div class="section-header">
    <div class="section-num">02</div>
    <div class="section-title">Tech Stack</div>
    <div class="section-tag">Tools & Technologies</div>
  </div>

  <div class="tech-grid">
    <div class="tech-item reveal"><span class="tech-icon">⚡</span><span class="tech-name">JavaScript</span></div>
    <div class="tech-item reveal"><span class="tech-icon">⚛️</span><span class="tech-name">React</span></div>
    <div class="tech-item reveal"><span class="tech-icon">▲</span><span class="tech-name">Next.js</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🟢</span><span class="tech-name">Node.js</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🍃</span><span class="tech-name">MongoDB</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🚂</span><span class="tech-name">Express</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🎨</span><span class="tech-name">Tailwind CSS</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🅱️</span><span class="tech-name">Bootstrap</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🔷</span><span class="tech-name">Material UI</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🔴</span><span class="tech-name">Redux</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🐍</span><span class="tech-name">Python</span></div>
    <div class="tech-item reveal"><span class="tech-icon">➕</span><span class="tech-name">C++</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🌐</span><span class="tech-name">HTML5</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🎨</span><span class="tech-name">CSS3</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🔵</span><span class="tech-name">jQuery</span></div>
    <div class="tech-item reveal"><span class="tech-icon">🐙</span><span class="tech-name">Git</span></div>
    <div class="tech-item reveal"><span class="tech-icon">⚙️</span><span class="tech-name">GitHub Actions</span></div>
    <div class="tech-item reveal"><span class="tech-icon">📦</span><span class="tech-name">NPM</span></div>
  </div>
</section>

<!-- GITHUB STATS -->
<section id="stats" class="stats-section">
  <div class="section-header">
    <div class="section-num">03</div>
    <div class="section-title">GitHub Data</div>
    <div class="section-tag">@itsabdulrafey</div>
  </div>

  <div class="stats-grid">
    <div class="stats-pane reveal">
      <div class="stats-pane-title">Activity Overview</div>
      <div class="stats-img-wrap">
        <img src="https://github-readme-stats.vercel.app/api?username=itsabdulrafey&theme=radical&border=false&include_all_commits=true&count_private=true" alt="GitHub Stats" loading="lazy" />
      </div>
      <div class="stats-img-wrap">
        <img src="https://github-profile-trophy.vercel.app/?username=itsabdulrafey&theme=radical&no-frame=false&no-bg=true&margin-w=4" alt="GitHub Trophies" loading="lazy" />
      </div>
    </div>

    <div class="stats-pane reveal">
      <div class="stats-pane-title">Contribution Streak</div>
      <div class="stats-img-wrap">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=itsabdulrafey&theme=radical&hide_border=false" alt="GitHub Streak" loading="lazy" />
      </div>
      <div style="padding: 2rem; border: var(--border-md); box-shadow: var(--shadow-md); background: var(--black); color: var(--white);">
        <div style="font-family: 'Bebas Neue', sans-serif; font-size: 1.1rem; letter-spacing: 0.08em; color: var(--green); margin-bottom: 1rem;">// life_hack.sh</div>
        <p style="font-size: 0.75rem; line-height: 1.9; color: rgba(255,255,255,0.7);">
          Learn new tech 🔥<br/>
          Share what you've learned 🎉<br/>
          Repeat. Commit. Ship.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" class="contact-section">
  <div class="section-header" style="border-color: var(--gray-mid);">
    <div class="section-num">04</div>
    <div class="section-title">Let's Connect</div>
    <div class="section-tag">Get In Touch</div>
  </div>

  <div class="contact-inner">
    <div class="contact-left">
      <div class="contact-big">
        LET'S<br/>
        <span class="accent">BUILD</span><br/>
        <span class="green">TOGETHER</span>
      </div>
      <p class="contact-sub">
        Got a project idea? Want to collaborate on something cool?
        Or just want to talk dev stuff — reach out. I'm always down
        to connect with fellow builders.
      </p>
    </div>

    <div class="contact-right">
      <a href="mailto:hi@rafeyahmed.com" class="contact-link reveal">
        <span class="contact-link-icon">✉️</span>
        <div class="contact-link-label">
          <span>Email</span>
          <span>hi@rafeyahmed.com</span>
        </div>
      </a>
      <a href="https://github.com/itsabdulrafey" target="_blank" class="contact-link reveal">
        <span class="contact-link-icon">🐙</span>
        <div class="contact-link-label">
          <span>GitHub</span>
          <span>@itsabdulrafey</span>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">RA/</div>
  <div class="footer-copy">Rafey Ahmed · <span>hi@rafeyahmed.com</span> · Built with 🔥 and ☕</div>
  <div style="font-size: 0.6rem; letter-spacing: 0.1em;">OPEN SOURCE · LEARNING IN PUBLIC</div>
</footer>

<script>
  // ── Typing Effect ──
  const lines = [
    "Rafey Ahmed",
    "MERN Stack Dev",
    "Open Source Fan",
    "Learning in Public",
    "Nice to meet you!",
  ];
  let li = 0, ci = 0, deleting = false;
  const el = document.getElementById("typing-out");

  function type() {
    const cur = lines[li];
    if (!deleting) {
      el.textContent = cur.slice(0, ++ci);
      if (ci === cur.length) { deleting = true; return setTimeout(type, 1600); }
    } else {
      el.textContent = cur.slice(0, --ci);
      if (ci === 0) { deleting = false; li = (li + 1) % lines.length; }
    }
    setTimeout(type, deleting ? 50 : 90);
  }
  type();

  // ── Scroll Reveal ──
  const reveals = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        e.target.style.transitionDelay = (i * 0.07) + 's';
        e.target.classList.add('visible');
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(r => obs.observe(r));
</script>

</body>
</html>
