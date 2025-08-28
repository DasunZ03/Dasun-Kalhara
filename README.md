<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Dasun Kalhara | Portfolio</title>
  <meta name="description" content="Portfolio of Dasun Kalhara (The Sun) — Teacher & Tech/ICT enthusiast from Kalawana, Sri Lanka." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Poppins:wght@600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg: #0b1020;
      --panel: rgba(255,255,255,0.06);
      --panel-strong: rgba(255,255,255,0.12);
      --text: #e6e9ef;
      --muted: #9aa4b2;
      --brand: #7c5cff;
      --brand-2: #2ee6a6;
      --ring: rgba(124,92,255,.45);
      --shadow: 0 8px 30px rgba(0,0,0,.35);
      --radius: 18px;
      --radius-sm: 12px;
      --maxw: 1100px;
      --blur: saturate(140%) blur(6px);
    }
    [data-theme="light"]{
      --bg: #f8fafc;
      --panel: rgba(10,12,18,0.06);
      --panel-strong: rgba(10,12,18,0.12);
      --text: #0e121b;
      --muted: #475569;
      --brand: #6a4dff;
      --brand-2: #0fb784;
      --ring: rgba(106,77,255,.35);
      --shadow: 0 8px 30px rgba(2,6,23,.15);
    }
    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body{
      margin:0; font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, "Helvetica Neue", Arial, sans-serif;
      color: var(--text); background: radial-gradient(1200px 800px at 80% -10%, rgba(124,92,255,.2), transparent 50%), radial-gradient(900px 600px at -10% 10%, rgba(46,230,166,.18), transparent 50%), var(--bg);
      background-attachment: fixed; line-height: 1.6;
    }
    a{ color: inherit; text-decoration: none; }
    img{ max-width: 100%; display: block; }

    /* Layout */
    .container{ width: 100%; max-width: var(--maxw); margin: 0 auto; padding: 0 20px; }
    header{
      position: sticky; top: 0; z-index: 50; backdrop-filter: var(--blur); -webkit-backdrop-filter: var(--blur);
      background: linear-gradient(to bottom, rgba(0,0,0,.2), rgba(0,0,0,0));
    }
    .nav{ display:flex; gap:16px; align-items:center; justify-content:space-between; padding:14px 0; }
    .brand{ display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:.3px; }
    .brand .logo{ width:32px; height:32px; border-radius:10px; display:grid; place-items:center; background:linear-gradient(135deg, var(--brand), var(--brand-2)); box-shadow: var(--shadow); color:white; font-weight:800; }
    .brand small{ color: var(--muted); font-weight:600; }

    .navlinks{ display:flex; gap: 14px; align-items:center; }
    .navlinks a{ padding:10px 14px; border-radius: 999px; color: var(--muted); }
    .navlinks a:hover{ color: var(--text); background: var(--panel); }
    .btn{ display:inline-flex; align-items:center; gap:10px; padding:10px 14px; border:1px solid var(--panel-strong); border-radius: 12px; background: var(--panel); box-shadow: var(--shadow); transition: transform .1s ease; }
    .btn:hover{ transform: translateY(-1px); }
    .btn-primary{ border-color: transparent; background: linear-gradient(135deg, var(--brand), var(--brand-2)); color: #0b1020; font-weight:700; }

    .theme-toggle{ border-radius: 12px; padding: 8px 12px; border: 1px solid var(--panel-strong); background: var(--panel); }

    /* Hero */
    .hero{ padding: 72px 0 36px; }
    .hero-grid{ display:grid; grid-template-columns: 1.2fr .8fr; gap: 24px; align-items:center; }
    .badge{ display:inline-flex; gap:8px; align-items:center; padding:8px 12px; border-radius:999px; background: var(--panel); border:1px solid var(--panel-strong); color: var(--muted); font-weight:600; }
    h1{ font-family: Poppins, Inter, sans-serif; font-size: clamp(34px, 5vw, 56px); line-height: 1.05; margin: 14px 0; letter-spacing: -0.02em; }
    .lead{ font-size: clamp(16px, 1.5vw, 18px); color: var(--muted); max-width: 64ch; }
    .cta-row{ display:flex; gap:12px; flex-wrap: wrap; margin-top: 22px; }

    .card{ background: linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.02)); border:1px solid var(--panel-strong); border-radius: var(--radius); padding: 18px; backdrop-filter: var(--blur); -webkit-backdrop-filter: var(--blur); box-shadow: var(--shadow); }
    .avatar{
      aspect-ratio: 1/1; border-radius: 22px; background: linear-gradient(135deg, rgba(124,92,255,.25), rgba(46,230,166,.25));
      display:grid; place-items:center; font-weight:800; font-size: 42px; color:#0b1020;
    }

    /* Sections */
    section { padding: 42px 0; }
    .section-title{ display:flex; align-items:center; justify-content:space-between; gap:12px; margin-bottom: 18px; }
    .section-title h2{ font-family: Poppins, Inter, sans-serif; font-size: clamp(22px, 2.4vw, 28px); margin:0; }
    .section-title .muted{ color: var(--muted); font-size: 14px; }

    /* Skills */
    .skills{ display:grid; grid-template-columns: repeat(4, 1fr); gap:14px; }
    .chip{ padding:10px 12px; border-radius: 12px; border:1px solid var(--panel-strong); background: var(--panel); font-weight:600; color: var(--text); display:flex; align-items:center; gap:10px; }
    .chip small{ color: var(--muted); font-weight:600; }

    /* Projects */
    .projects{ display:grid; grid-template-columns: repeat(3, 1fr); gap:16px; }
    .project-card{ display:flex; flex-direction:column; gap:12px; }
    .project-thumb{ border-radius: 14px; overflow:hidden; border: 1px solid var(--panel-strong); aspect-ratio: 16/9; background: radial-gradient(40% 100% at 0% 0%, rgba(124,92,255,.16), transparent), radial-gradient(60% 120% at 100% 100%, rgba(46,230,166,.12), transparent); display:grid; place-items:center; }
    .project-title{ font-weight:700; }
    .project-tags{ display:flex; gap:8px; flex-wrap:wrap; }
    .tag{ font-size: 12px; padding:6px 8px; background: var(--panel); border:1px solid var(--panel-strong); border-radius: 999px; color: var(--muted); }
    .project-actions{ display:flex; gap:10px; margin-top:auto; }

    /* Timeline */
    .timeline{ display:grid; gap:14px; }
    .tl-item{ display:grid; grid-template-columns: 120px 1fr; gap:14px; align-items:flex-start; }
    .tl-date{ color: var(--muted); font-weight:700; }

    /* Contact */
    .contact-grid{ display:grid; grid-template-columns: 1.3fr .7fr; gap:16px; }
    form{ display:grid; gap:12px; }
    input, textarea{ padding:12px 14px; border-radius: 12px; border:1px solid var(--panel-strong); background: var(--panel); color: var(--text); outline: none; }
    textarea{ min-height: 120px; resize: vertical; }
    input:focus, textarea:focus{ box-shadow: 0 0 0 3px var(--ring); border-color: transparent; }

    footer{ padding: 28px 0 48px; color: var(--muted); }

    /* Responsive */
    @media (max-width: 980px){
      .hero-grid{ grid-template-columns: 1fr; }
      .skills{ grid-template-columns: repeat(3, 1fr); }
      .projects{ grid-template-columns: repeat(2, 1fr); }
      .contact-grid{ grid-template-columns: 1fr; }
    }
    @media (max-width: 640px){
      .navlinks{ display:none; }
      .skills{ grid-template-columns: repeat(2, 1fr); }
      .projects{ grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="logo" aria-hidden="true">DK</div>
        <div>
          <div>Dasun Kalhara</div>
          <small>“The Sun” — ICT & Tech</small>
        </div>
      </div>
      <nav class="navlinks" aria-label="Primary">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#timeline">Timeline</a>
        <a href="#contact">Contact</a>
        <a class="btn btn-primary" href="https://github.com/" target="_blank" rel="noreferrer">GitHub</a>
      </nav>
      <button class="theme-toggle" id="themeToggle" aria-label="Toggle theme">🌗</button>
    </div>
  </header>

  <main>
    <!-- Hero -->
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <span class="badge">📍 Kalawana, Sri Lanka • Teacher & Builder</span>
          <h1>Hi, I’m Dasun — I teach ICT and build practical apps.</h1>
          <p class="lead">I’m exploring Flutter, bots, and playful simulations. Here I document what I learn and ship: clean, small tools that solve real classroom and community problems.</p>
          <div class="cta-row">
            <a class="btn btn-primary" href="#projects">See Projects</a>
            <a class="btn" href="https://github.com/USERNAME" target="_blank" rel="noreferrer">View GitHub</a>
            <a class="btn" href="mailto:youremail@example.com">Email Me</a>
          </div>
        </div>
        <div class="card">
          <div class="avatar" aria-label="Profile image placeholder">🌞</div>
          <div style="margin-top:12px">
            <div style="font-weight:700">Dasun Kalhara</div>
            <div style="color:var(--muted)">aka “The Sun” • ICT/Tech</div>
          </div>
          <div style="margin-top:12px; display:grid; gap:8px;">
            <div class="chip">🔗 <a href="https://github.com/USERNAME" target="_blank" rel="noreferrer">github.com/USERNAME</a></div>
            <div class="chip">🎥 <a href="#" target="_blank" rel="noreferrer">YouTube: The ICT Mentor</a></div>
            <div class="chip">💼 <a href="#" target="_blank" rel="noreferrer">LinkedIn</a></div>
          </div>
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about">
      <div class="container">
        <div class="section-title">
          <h2>About</h2>
          <span class="muted">Short story & focus areas</span>
        </div>
        <div class="card" style="display:grid; gap:10px;">
          <p>Hi! I’m Dasun from Kalawana. I enjoy turning ideas into simple, useful software and sharing what I learn with students and beginners. My current focus is building a <strong>Flutter QR attendance app</strong> and experimenting with <strong>Telegram bots</strong> for automation.</p>
          <p>When I teach, I emphasize fundamentals and hands-on projects. When I build, I prefer clean UI, minimal dependencies, and clear docs.</p>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills">
      <div class="container">
        <div class="section-title">
          <h2>Skills</h2>
          <span class="muted">What I use (and learn)</span>
        </div>
        <div class="skills">
          <div class="chip">🧩 HTML & CSS <small>UI layout</small></div>
          <div class="chip">⚙️ JavaScript <small>interactivity</small></div>
          <div class="chip">📱 Flutter (beginner) <small>apps</small></div>
          <div class="chip">🤖 Telegram Bots <small>automation</small></div>
          <div class="chip">🐍 Python <small>scripts</small></div>
          <div class="chip">🧪 Git & GitHub <small>versioning</small></div>
          <div class="chip">🎨 UI/UX <small>clean design</small></div>
          <div class="chip">🧭 Teaching ICT <small>fundamentals</small></div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects">
      <div class="container">
        <div class="section-title">
          <h2>Projects</h2>
          <span class="muted">Selected work & experiments</span>
        </div>
        <div class="projects">
          <!-- Project 1 -->
          <article class="card project-card">
            <div class="project-thumb" role="img" aria-label="Attendance App thumbnail">
              <svg viewBox="0 0 200 112" width="100%" height="100%" preserveAspectRatio="xMidYMid meet">
                <defs>
                  <linearGradient id="g1" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#7c5cff" stop-opacity=".6"/>
                    <stop offset="1" stop-color="#2ee6a6" stop-opacity=".5"/>
                  </linearGradient>
                </defs>
                <rect x="0" y="0" width="200" height="112" fill="url(#g1)" opacity=".18"/>
                <rect x="16" y="16" width="168" height="80" rx="10" ry="10" fill="none" stroke="#7c5cff" stroke-width="2"/>
                <rect x="28" y="28" width="68" height="18" rx="6" fill="#7c5cff" opacity=".6"/>
                <rect x="28" y="52" width="144" height="6" rx="3" fill="#2ee6a6" opacity=".7"/>
                <rect x="28" y="64" width="120" height="6" rx="3" fill="#7c5cff" opacity=".5"/>
              </svg>
            </div>
            <div class="project-title">QR Attendance (Flutter)</div>
            <p class="muted">Scan a student QR, auto‑log time, and send a WhatsApp message to parents.</p>
            <div class="project-tags">
              <span class="tag">Flutter</span>
              <span class="tag">QR</span>
              <span class="tag">WhatsApp API</span>
            </div>
            <div class="project-actions">
              <a class="btn" href="https://github.com/USERNAME/qr-attendance" target="_blank" rel="noreferrer">GitHub</a>
              <a class="btn" href="#" target="_blank" rel="noreferrer">Live Demo</a>
            </div>
          </article>

          <!-- Project 2 -->
          <article class="card project-card">
            <div class="project-thumb" role="img" aria-label="ICT Mentor thumbnail">
              <svg viewBox="0 0 200 112" width="100%" height="100%" preserveAspectRatio="xMidYMid meet">
                <rect width="200" height="112" fill="#2ee6a6" opacity=".12"/>
                <circle cx="56" cy="56" r="32" fill="#7c5cff" opacity=".5"/>
                <rect x="96" y="38" width="80" height="12" rx="6" fill="#7c5cff" opacity=".7"/>
                <rect x="96" y="58" width="64" height="8" rx="4" fill="#2ee6a6" opacity=".8"/>
              </svg>
            </div>
            <div class="project-title">ICT Mentor Notes</div>
            <p class="muted">Short lessons, demos, and code snippets for beginners learning tech basics.</p>
            <div class="project-tags">
              <span class="tag">Education</span>
              <span class="tag">Notes</span>
              <span class="tag">YouTube</span>
            </div>
            <div class="project-actions">
              <a class="btn" href="https://github.com/USERNAME/ict-mentor" target="_blank" rel="noreferrer">GitHub</a>
              <a class="btn" href="#" target="_blank" rel="noreferrer">Docs</a>
            </div>
          </article>

          <!-- Project 3 -->
          <article class="card project-card">
            <div class="project-thumb" role="img" aria-label="Telegram Bot thumbnail">
              <svg viewBox="0 0 200 112" width="100%" height="100%" preserveAspectRatio="xMidYMid meet">
                <rect width="200" height="112" fill="#7c5cff" opacity=".10"/>
                <rect x="24" y="24" width="152" height="64" rx="10" fill="none" stroke="#2ee6a6" stroke-width="2"/>
                <circle cx="56" cy="56" r="12" fill="#2ee6a6" opacity=".7"/>
                <rect x="76" y="50" width="72" height="12" rx="6" fill="#7c5cff" opacity=".6"/>
              </svg>
            </div>
            <div class="project-title">Utility Telegram Bots</div>
            <p class="muted">Simple bots for class reminders, quiz delivery, and content sharing.</p>
            <div class="project-tags">
              <span class="tag">Python</span>
              <span class="tag">Bot API</span>
              <span class="tag">Automation</span>
            </div>
            <div class="project-actions">
              <a class="btn" href="https://github.com/USERNAME/telegram-bots" target="_blank" rel="noreferrer">GitHub</a>
              <a class="btn" href="#" target="_blank" rel="noreferrer">Readme</a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- Timeline -->
    <section id="timeline">
      <div class="container">
        <div class="section-title">
          <h2>Timeline</h2>
          <span class="muted">Learning & milestones</span>
        </div>
        <div class="card timeline">
          <div class="tl-item">
            <div class="tl-date">2025</div>
            <div>Started building a <strong>Flutter QR attendance</strong> MVP and documenting the journey.</div>
          </div>
          <div class="tl-item">
            <div class="tl-date">2024</div>
            <div>Launched <strong>ICT Mentor</strong> channel to teach tech fundamentals in simple Sinhala/English.</div>
          </div>
          <div class="tl-item">
            <div class="tl-date">Earlier</div>
            <div>Explored bots, web basics, and small games to learn by doing.</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <div class="container">
        <div class="section-title">
          <h2>Contact</h2>
          <span class="muted">Let’s build something useful</span>
        </div>
        <div class="contact-grid">
          <form class="card" onsubmit="event.preventDefault(); alert('Thanks! I\'ll get back to you soon.');">
            <input aria-label="Your name" type="text" placeholder="Your name" required>
            <input aria-label="Your email" type="email" placeholder="Your email" required>
            <textarea aria-label="Your message" placeholder="How can I help?" required></textarea>
            <button class="btn btn-primary" type="submit">Send Message</button>
          </form>
          <div class="card" style="display:grid; gap:10px;">
            <div class="chip">📧 youremail@example.com</div>
            <div class="chip">📍 Kalawana, Sri Lanka</div>
            <div class="chip">💬 Telegram: @your_handle</div>
            <div class="chip">🎥 YouTube: The ICT Mentor</div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container" style="display:flex; align-items:center; justify-content:space-between; gap:12px; flex-wrap:wrap;">
      <div>© <span id="year"></span> Dasun Kalhara. Built with HTML & CSS.</div>
      <div style="display:flex; gap:10px;">
        <a class="chip" href="https://github.com/USERNAME" target="_blank" rel="noreferrer">GitHub</a>
        <a class="chip" href="#" target="_blank" rel="noreferrer">LinkedIn</a>
        <a class="chip" href="#" target="_blank" rel="noreferrer">YouTube</a>
      </div>
    </div>
  </footer>

  <script>
    // Theme toggle (persisted)
    const root = document.documentElement;
    const toggle = document.getElementById('themeToggle');
    const saved = localStorage.getItem('theme');
    if(saved){ root.setAttribute('data-theme', saved); }
    toggle.addEventListener('click', () => {
      const current = root.getAttribute('data-theme') === 'light' ? 'dark' : 'light';
      root.setAttribute('data-theme', current);
      localStorage.setItem('theme', current);
    });

    // Set year
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
