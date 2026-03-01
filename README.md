<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Rafey Ahmed — GitHub Profile</title>

  <!-- Fonts (optional but recommended) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">

  <style>
    /* ============================
      RAFey - Neo Brutalist Profile
      Single-file: HTML + CSS + JS
      ============================ */

    :root{
      --black:#000000;
      --white:#ffffff;
      --offwhite:#f5f5f0;
      --gray:#333333;
      --gray-mid:#666666;
      --gray-light:#999999;

      --accent:#ff3366;
      --accent-dark:#cc0033;

      --green:#00ff88;
      --blue:#0066ff;
      --yellow:#ffcc00;

      --border-lg:4px solid var(--black);
      --border-md:3px solid var(--black);
      --border-sm:2px solid var(--black);

      --shadow-sm:4px 4px 0 var(--black);
      --shadow-md:6px 6px 0 var(--black);
      --shadow-lg:8px 8px 0 var(--black);

      --radius:18px;
      --mono:"Space Mono", monospace;
      --display:"Bebas Neue", sans-serif;
    }

    *{ box-sizing:border-box; margin:0; padding:0; }
    html{ scroll-behavior:smooth; }
    body{
      background:var(--offwhite);
      color:var(--black);
      font-family:var(--mono);
      overflow-x:hidden;
    }

    /* Noise overlay */
    body:before{
      content:"";
      position:fixed;
      inset:0;
      pointer-events:none;
      z-index:9999;
      opacity:.06;
      mix-blend-mode:multiply;
      background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='240'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='240' height='240' filter='url(%23n)' opacity='.35'/%3E%3C/svg%3E");
    }

    /* Layout container */
    .wrap{
      width:min(1200px, 94vw);
      margin:22px auto 40px;
      display:flex;
      flex-direction:column;
      gap:18px;
    }

    /* Header */
    header{
      background:var(--black);
      color:var(--white);
      border:var(--border-lg);
      box-shadow:var(--shadow-md);
      border-radius:var(--radius);
      padding:18px 18px;
      position:sticky;
      top:12px;
      z-index:300;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
    }
    .logo{
      font-family:var(--display);
      letter-spacing:.04em;
      font-size:28px;
      color:var(--green);
      text-shadow:2px 2px 0 var(--accent);
      line-height:1;
      user-select:none;
    }
    nav{
      display:flex;
      align-items:center;
      gap:16px;
      flex-wrap:wrap;
      justify-content:flex-end;
    }
    nav a{
      color:var(--white);
      text-decoration:none;
      font-size:12px;
      letter-spacing:.16em;
      text-transform:uppercase;
      position:relative;
      padding-bottom:4px;
    }
    nav a:after{
      content:"";
      position:absolute;
      left:0;
      bottom:0;
      height:2px;
      width:0;
      background:var(--green);
      transition:width .2s ease;
    }
    nav a:hover{ color:var(--green); }
    nav a:hover:after{ width:100%; }

    /* Main grid */
    .main{
      display:grid;
      grid-template-columns: 360px 1fr;
      gap:18px;
      align-items:start;
    }

    @media (max-width: 980px){
      .main{ grid-template-columns: 1fr; }
      header{ position:relative; top:0; }
    }

    /* Left profile card */
    .profile{
      background:var(--white);
      border:var(--border-lg);
      box-shadow:var(--shadow-lg);
      border-radius:var(--radius);
      padding:18px;
      position:sticky;
      top:102px;
    }
    @media (max-width: 980px){
      .profile{ position:relative; top:0; }
    }

    .avatarWrap{
      width:120px;
      height:120px;
      border:var(--border-md);
      box-shadow:var(--shadow-md);
      border-radius:999px;
      overflow:hidden;
      background:var(--offwhite);
      margin-bottom:14px;
    }
    .avatarWrap img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
    }

    .name{
      font-family:var(--display);
      font-size:34px;
      line-height:1;
      letter-spacing:.02em;
      margin-bottom:6px;
    }
    .handle{
      color:var(--gray-mid);
      font-size:12px;
      margin-bottom:10px;
    }
    .tagline{
      font-size:12.5px;
      line-height:1.55;
      margin-bottom:14px;
    }

    .btnRow{
      display:flex;
      gap:10px;
      margin-bottom:14px;
      flex-wrap:wrap;
    }
    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:10px 12px;
      border:var(--border-md);
      box-shadow:var(--shadow-sm);
      border-radius:14px;
      font-size:12px;
      text-decoration:none;
      cursor:pointer;
      user-select:none;
      transition:transform .12s ease;
    }
    .btn:active{ transform:translate(2px,2px); box-shadow:none; }
    .btn.primary{ background:var(--black); color:var(--white); }
    .btn.primary:hover{ color:var(--green); }
    .btn.ghost{ background:var(--white); color:var(--black); }
    .btn.ghost:hover{ background:var(--offwhite); }

    .meta{
      display:flex;
      flex-direction:column;
      gap:10px;
      margin-top:10px;
      border-top:var(--border-sm);
      padding-top:12px;
    }
    .metaItem{
      display:flex;
      align-items:center;
      gap:10px;
      font-size:12px;
      color:var(--black);
      word-break:break-word;
    }
    .ico{
      width:22px;
      height:22px;
      border:var(--border-sm);
      border-radius:8px;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      font-weight:700;
      box-shadow:2px 2px 0 var(--black);
      background:var(--offwhite);
      flex:0 0 auto;
    }

    .links{
      margin-top:14px;
      border-top:var(--border-sm);
      padding-top:12px;
      display:flex;
      flex-direction:column;
      gap:10px;
    }
    .links a{
      text-decoration:none;
      color:var(--blue);
      font-size:12px;
    }
    .links a:hover{
      color:var(--accent);
      text-decoration:underline;
    }

    /* Right content */
    .content{
      display:flex;
      flex-direction:column;
      gap:18px;
    }

    .panel{
      background:var(--white);
      border:var(--border-lg);
      box-shadow:var(--shadow-lg);
      border-radius:var(--radius);
      padding:18px;
    }

    .kicker{
      display:flex;
      align-items:center;
      gap:10px;
      font-size:11px;
      text-transform:uppercase;
      letter-spacing:.18em;
      color:var(--gray-mid);
      margin-bottom:8px;
    }
    .liveDot{
      width:9px;height:9px;border-radius:999px;
      background:var(--green);
      border:2px solid var(--black);
      box-shadow:2px 2px 0 var(--black);
      animation:pulse 1.8s infinite;
    }
    @keyframes pulse{
      0%{ transform:scale(1); opacity:1; }
      50%{ transform:scale(1.18); opacity:.75; }
      100%{ transform:scale(1); opacity:1; }
    }

    .heroTitle{
      font-family:var(--display);
      font-size: clamp(42px, 6vw, 74px);
      line-height:.92;
      letter-spacing:-.01em;
      margin-bottom:8px;
    }
    .heroTitle .accent{ color:var(--accent); text-shadow:3px 3px 0 var(--black); }
    .heroTitle .outline{
      -webkit-text-stroke: 3px var(--black);
      color:transparent;
    }

    .heroText{
      font-size:13px;
      line-height:1.65;
      color:var(--gray);
      max-width:68ch;
      margin-bottom:14px;
    }

    .chips{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin-top:6px;
    }
    .chip{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:8px 10px;
      border:var(--border-md);
      box-shadow:var(--shadow-sm);
      border-radius:999px;
      font-size:12px;
      background:var(--offwhite);
    }
    .chip b{ color:var(--black); }

    .grid2{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:14px;
    }
    @media (max-width: 820px){ .grid2{ grid-template-columns:1fr; } }

    .card{
      background:var(--offwhite);
      border:var(--border-md);
      box-shadow:var(--shadow-md);
      border-radius:var(--radius);
      padding:14px;
    }
    .card h3{
      font-family:var(--display);
      font-size:26px;
      letter-spacing:.02em;
      margin-bottom:8px;
    }
    .card p{
      font-size:12.5px;
      line-height:1.6;
      color:var(--gray);
    }

    /* Code panel */
    .codeTop{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
      border-bottom:var(--border-sm);
      padding-bottom:10px;
      margin-bottom:12px;
    }
    .fileTag{
      font-size:12px;
      color:var(--gray);
    }
    .dotRow{ display:flex; gap:8px; }
    .dot{
      width:12px;height:12px;border-radius:999px;
      border:2px solid var(--black);
      box-shadow:2px 2px 0 var(--black);
    }
    .dot.r{ background:var(--accent); }
    .dot.y{ background:var(--yellow); }
    .dot.g{ background:var(--green); }

    pre{
      background:var(--white);
      border:var(--border-md);
      border-radius:16px;
      box-shadow:var(--shadow-sm);
      padding:14px;
      overflow:auto;
      font-size:12px;
      line-height:1.55;
    }
    code{ font-family:var(--mono); }
    .muted{ color:var(--gray-mid); }

    /* Footer */
    footer{
      text-align:center;
      font-size:11px;
      color:var(--gray-mid);
      padding:10px 0 0;
    }
    footer b{ color:var(--black); }
  </style>
</head>

<body>
  <div class="wrap">

    <header>
      <div class="logo">RAFey // DEV</div>
      <nav>
        <a href="#about">About</a>
        <a href="#stack">Stack</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <div class="main">

      <!-- LEFT: Profile -->
      <aside class="profile">
        <div class="avatarWrap">
          <!-- Replace with your image -->
          <img src="https://images.unsplash.com/photo-1544723795-3fb6469f5b39?auto=format&fit=crop&w=400&q=80" alt="Profile" />
        </div>

        <div class="name">Abdul Rafey Ahmed</div>
        <div class="handle">@itsabdulrafey</div>
        <div class="tagline">
          React.js App Developer — working with <b>React.js</b> and <b>Redux</b>.
          Clean UI, strong logic, and product-first delivery.
        </div>

        <div class="btnRow">
          <a class="btn primary" href="#projects">View Work</a>
          <a class="btn ghost" href="#contact">Hire / Contact</a>
        </div>

        <div class="meta">
          <div class="metaItem"><span class="ico">🏢</span> Codistan</div>
          <div class="metaItem"><span class="ico">📍</span> Islamabad, Pakistan</div>
          <div class="metaItem"><span class="ico">🕒</span> <span id="localTime">--:--</span> <span class="muted">(Asia/Karachi)</span></div>
          <div class="metaItem"><span class="ico">✉️</span> <a href="mailto:hi@rafeyahmed.com">hi@rafeyahmed.com</a></div>
        </div>

        <div class="links">
          <a href="https://www.linkedin.com/in/itsabdulrafey/" target="_blank" rel="noreferrer">LinkedIn</a>
          <a href="https://www.rafeyahmed.com" target="_blank" rel="noreferrer">Website</a>
          <a href="https://www.rafeyahmed.com/links" target="_blank" rel="noreferrer">Links</a>
        </div>
      </aside>

      <!-- RIGHT: Content -->
      <main class="content">

        <!-- HERO -->
        <section class="panel" id="about">
          <div class="kicker"><span class="liveDot"></span> Available for freelance / full-time</div>

          <h1 class="heroTitle">
            Build <span class="accent">fast</span><br />
            <span class="outline">product UIs</span>
          </h1>

          <p class="heroText">
            I build modern web apps with clean architecture, pixel-perfect UI, and scalable state management.
            If you want a dev who ships features and keeps code maintainable — I’m your guy.
          </p>

          <div class="chips">
            <div class="chip">⚡ <b>React</b> + Redux</div>
            <div class="chip">🧠 <b>TypeScript</b> ready</div>
            <div class="chip">🎨 <b>Neo-Brutalist</b> UI</div>
            <div class="chip">🧩 Component systems</div>
          </div>
        </section>

        <!-- STACK + HIGHLIGHTS -->
        <section class="grid2" id="stack">
          <div class="card">
            <h3>Stack</h3>
            <p>
              React.js, Redux Toolkit, MUI, Tailwind, REST APIs, JWT Auth, Vite/Next.js, Git workflows.
              Focus: fast UI, clean components, reusable patterns.
            </p>
          </div>

          <div class="card">
            <h3>What I deliver</h3>
            <p>
              Dashboards, admin panels, portals, ticketing systems, and production-ready UI features.
              I keep code readable and scalable — not just “working”.
            </p>
          </div>
        </section>

        <!-- PROJECTS -->
        <section class="panel" id="projects">
          <div class="kicker">Selected work</div>

          <div class="grid2">
            <div class="card">
              <h3>IT Helpdesk Chatbot</h3>
              <p>AI chatbot UI + ticket preview flows + draft forms (feedback/remarks/assignee/reminder).</p>
            </div>
            <div class="card">
              <h3>University Portals</h3>
              <p>Dashboards & portals with role-based UI, clean navigation, and data-driven screens.</p>
            </div>
          </div>
        </section>

        <!-- CODE PANEL (GitHub vibe) -->
        <section class="panel">
          <div class="codeTop">
            <div class="fileTag"><b>itsabdulrafey</b> / <span class="muted">README.md</span></div>
            <div class="dotRow">
              <span class="dot r"></span>
              <span class="dot y"></span>
              <span class="dot g"></span>
            </div>
          </div>

          <pre><code>&lt;!-- Paste this into GitHub Pages (index.html) --&gt;
&lt;!-- Replace links, name, handle, image, and projects --&gt;

&lt;!-- Contact: mailto:hi@rafeyahmed.com --&gt;
&lt;!-- LinkedIn: https://www.linkedin.com/in/itsabdulrafey/ --&gt;</code></pre>
        </section>

        <!-- CONTACT -->
        <section class="panel" id="contact">
          <div class="kicker">Contact</div>
          <p class="heroText" style="margin-bottom:10px;">
            Email me directly or connect on LinkedIn. I reply fast.
          </p>

          <div class="btnRow">
            <a class="btn primary" href="mailto:hi@rafeyahmed.com">Email</a>
            <a class="btn ghost" href="https://www.linkedin.com/in/itsabdulrafey/" target="_blank" rel="noreferrer">LinkedIn</a>
            <a class="btn ghost" href="https://www.rafeyahmed.com" target="_blank" rel="noreferrer">Website</a>
          </div>
        </section>

        <footer>
          Built with <b>Neo-Brutal</b> vibes • © <span id="year"></span>
        </footer>

      </main>
    </div>
  </div>

  <script>
    // Local time (Pakistan)
    function updateTime(){
      try{
        const fmt = new Intl.DateTimeFormat('en-GB', {
          timeZone: 'Asia/Karachi',
          hour: '2-digit',
          minute: '2-digit'
        });
        document.getElementById('localTime').textContent = fmt.format(new Date());
      }catch(e){
        document.getElementById('localTime').textContent = new Date().toLocaleTimeString([], {hour:'2-digit', minute:'2-digit'});
      }
    }
    updateTime();
    setInterval(updateTime, 15000);

    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
