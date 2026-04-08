<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Narasimha | Data Analyst Portfolio</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Inter:wght@300;400;500;600;700;800&display=swap');

*{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#0d1117;--bg2:#161b22;--bg3:#21262d;
  --border:#30363d;--border2:#444c56;
  --text:#e6edf3;--text2:#8b949e;
  --blue:#58a6ff;--green:#3fb950;--purple:#d2a8ff;
  --orange:#ffa657;--pink:#ff7b72;--cyan:#39d353;
}

body{background:var(--bg);color:var(--text);font-family:'Inter',sans-serif;overflow-x:hidden;min-height:100vh}

canvas#particles{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none}

.page{position:relative;z-index:1;max-width:900px;margin:0 auto;padding:2rem 1.5rem}

/* HERO */
.hero{text-align:center;padding:3rem 0 2rem;perspective:800px}
.avatar-ring{position:relative;width:120px;height:120px;margin:0 auto 1.5rem}
.avatar-ring svg{width:120px;height:120px;animation:spin-ring 6s linear infinite}
.avatar-inner{position:absolute;inset:12px;border-radius:50%;background:linear-gradient(135deg,#1f6feb,#388bfd,#58a6ff);display:flex;align-items:center;justify-content:center;font-size:2.6rem;font-weight:800;color:#fff;box-shadow:0 0 30px #58a6ff55}

@keyframes spin-ring{to{transform:rotate(360deg)}}

.hero h1{font-size:clamp(1.6rem,5vw,2.6rem);font-weight:800;background:linear-gradient(120deg,#58a6ff 0%,#d2a8ff 50%,#ffa657 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;animation:shimmer 4s ease infinite;background-size:200%}
@keyframes shimmer{0%{background-position:0%}50%{background-position:100%}100%{background-position:0%}}

.hero h2{font-size:1rem;color:var(--text2);margin:.5rem 0 1.5rem;font-weight:400}
.typing{color:var(--blue);font-family:'Fira Code',monospace;font-size:.95rem;min-height:1.4em}
.typing::after{content:'|';animation:blink .7s step-end infinite}
@keyframes blink{50%{opacity:0}}

/* SOCIAL */
.social-row{display:flex;gap:.75rem;justify-content:center;flex-wrap:wrap;margin-top:1.25rem}
.social-btn{display:inline-flex;align-items:center;gap:.5rem;padding:.5rem 1.1rem;border-radius:8px;font-size:.85rem;font-weight:500;text-decoration:none;border:.5px solid transparent;transition:transform .2s,box-shadow .2s;cursor:pointer}
.social-btn:hover{transform:translateY(-3px) scale(1.03)}
.social-btn.linkedin{background:#0a66c2;color:#fff}
.social-btn.linkedin:hover{box-shadow:0 8px 24px #0a66c255}
.social-btn.insta{background:linear-gradient(135deg,#f58529,#dd2a7b,#8134af);color:#fff}
.social-btn.insta:hover{box-shadow:0 8px 24px #dd2a7b55}

/* SECTION */
.section{margin:2.5rem 0}
.section-title{font-size:.75rem;font-weight:600;letter-spacing:.12em;text-transform:uppercase;color:var(--text2);display:flex;align-items:center;gap:.6rem;margin-bottom:1.25rem}
.section-title::after{content:'';flex:1;height:.5px;background:var(--border)}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:.75rem}
.about-item{background:var(--bg2);border:.5px solid var(--border);border-radius:10px;padding:.9rem 1.1rem;display:flex;align-items:flex-start;gap:.75rem;transition:transform .2s,border-color .2s,box-shadow .2s,opacity .5s}
.about-item:hover{transform:translateY(-4px) rotateX(3deg);border-color:var(--border2);box-shadow:0 12px 32px #0009}
.about-icon{font-size:1.2rem;line-height:1;flex-shrink:0;margin-top:2px}
.about-item p{font-size:.85rem;color:var(--text2);line-height:1.55}
.about-item p strong{color:var(--text);font-weight:500}

/* TECH BADGES */
.tech-grid{display:flex;flex-wrap:wrap;gap:.6rem}
.tech-badge{display:inline-flex;align-items:center;gap:.45rem;padding:.45rem .9rem;border-radius:6px;font-size:.8rem;font-weight:500;border:.5px solid transparent;transition:transform .2s,box-shadow .2s;cursor:default;position:relative;overflow:hidden}
.tech-badge::before{content:'';position:absolute;inset:0;background:linear-gradient(120deg,transparent 40%,rgba(255,255,255,.08) 50%,transparent 60%);transform:translateX(-100%);transition:transform .5s}
.tech-badge:hover::before{transform:translateX(100%)}
.tech-badge:hover{transform:translateY(-3px) scale(1.05);box-shadow:0 6px 20px #0007}
.dot{width:6px;height:6px;border-radius:50%;flex-shrink:0}
.py{background:#1e3a5f;color:#58a6ff;border-color:#1f6feb}.py .dot{background:#58a6ff}
.sql{background:#1a2d1a;color:#3fb950;border-color:#238636}.sql .dot{background:#3fb950}
.pg{background:#1a2633;color:#47a3d4;border-color:#226090}.pg .dot{background:#47a3d4}
.pd{background:#18163a;color:#a78bfa;border-color:#6e40c9}.pd .dot{background:#a78bfa}
.np{background:#00334a;color:#4ec9b0;border-color:#007acc}.np .dot{background:#4ec9b0}
.ml{background:#27211a;color:#ffa657;border-color:#9e6a03}.ml .dot{background:#ffa657}
.pbi{background:#2b220a;color:#f2c94c;border-color:#8b6914}.pbi .dot{background:#f2c94c}
.tab{background:#2a1712;color:#e97627;border-color:#993b10}.tab .dot{background:#e97627}
.js{background:#2a2400;color:#d4c000;border-color:#7a6e00}.js .dot{background:#d4c000}
.st{background:#1a0b33;color:#ff4b9a;border-color:#8b0050}.st .dot{background:#ff4b9a}

/* STATS */
.stats-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:1rem}
.stat-card{background:var(--bg2);border:.5px solid var(--border);border-radius:12px;overflow:hidden;transition:transform .2s,box-shadow .2s,opacity .5s;position:relative}
.stat-card::after{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(88,166,255,.04),rgba(210,168,255,.04));pointer-events:none}
.stat-card:hover{transform:translateY(-5px) rotateY(2deg);box-shadow:0 16px 40px #0009}
.stat-card img{width:100%;display:block}

/* LEARNING */
.learn-list{display:flex;flex-direction:column;gap:.6rem}
.learn-item{background:var(--bg2);border:.5px solid var(--border);border-left:2px solid var(--blue);border-radius:0 8px 8px 0;padding:.7rem 1rem;font-size:.875rem;color:var(--text2);display:flex;align-items:center;gap:.75rem;transition:transform .2s,border-color .2s,opacity .5s}
.learn-item:hover{transform:translateX(6px);border-left-color:var(--purple);color:var(--text)}
.learn-item span.pill{font-size:.7rem;padding:.2rem .55rem;border-radius:99px;background:#21262d;border:.5px solid var(--border2);color:var(--text2);white-space:nowrap;margin-left:auto}

/* PROJECTS */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:.75rem}
.proj-card{background:var(--bg2);border:.5px solid var(--border);border-radius:10px;padding:1rem 1.1rem;transition:transform .2s,box-shadow .2s,border-color .2s,opacity .5s;cursor:default}
.proj-card:hover{transform:translateY(-5px) scale(1.02);border-color:var(--border2);box-shadow:0 10px 30px #0009}
.proj-lang{display:inline-flex;align-items:center;gap:.35rem;font-size:.72rem;color:var(--text2);margin-bottom:.5rem}
.proj-lang-dot{width:8px;height:8px;border-radius:50%}
.proj-card h3{font-size:.9rem;font-weight:500;color:var(--text);margin-bottom:.35rem}
.proj-card p{font-size:.78rem;color:var(--text2);line-height:1.5}

/* FOOTER */
.footer{text-align:center;padding:2rem 0 1rem;color:var(--text2);font-size:.82rem}
.view-counter{display:inline-flex;align-items:center;gap:.5rem;background:var(--bg2);border:.5px solid var(--border);border-radius:8px;padding:.5rem 1rem;margin:.75rem 0;font-family:'Fira Code',monospace;font-size:.85rem}
.view-counter span.num{color:var(--blue);font-weight:600}
.pulse-dot{width:8px;height:8px;border-radius:50%;background:var(--green);animation:pulse 1.5s ease infinite}
@keyframes pulse{0%,100%{transform:scale(1);opacity:1}50%{transform:scale(1.5);opacity:.5}}

.tilt{transform-style:preserve-3d;transition:transform .15s ease, box-shadow .15s ease, opacity .5s}
</style>
</head>
<body>

<canvas id="particles"></canvas>

<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-ring">
      <svg viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="60" cy="60" r="54" stroke="url(#grad1)" stroke-width="2.5" stroke-dasharray="6 4" stroke-linecap="round"/>
        <circle cx="60" cy="60" r="47" stroke="url(#grad2)" stroke-width="1" opacity=".4"/>
        <circle cx="60" cy="6" r="4" fill="#58a6ff"/>
        <circle cx="114" cy="60" r="3" fill="#d2a8ff"/>
        <circle cx="60" cy="114" r="4" fill="#ffa657"/>
        <defs>
          <linearGradient id="grad1" x1="0" y1="0" x2="120" y2="120">
            <stop stop-color="#58a6ff"/><stop offset=".5" stop-color="#d2a8ff"/><stop offset="1" stop-color="#ffa657"/>
          </linearGradient>
          <linearGradient id="grad2" x1="120" y1="0" x2="0" y2="120">
            <stop stop-color="#ffa657"/><stop offset="1" stop-color="#58a6ff"/>
          </linearGradient>
        </defs>
      </svg>
      <div class="avatar-inner">N</div>
    </div>
    <h1>Hi, I'm Narasimha 👋</h1>
    <h2>B.Tech CSE · Aspiring Data Analyst</h2>
    <div class="typing" id="typing-text"></div>
    <div class="social-row">
      <a class="social-btn linkedin" href="https://www.linkedin.com/in/thulabandhu-narasimha-219083321/" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="social-btn insta" href="https://www.instagram.com/narasimha._.thulabandhu/" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
        Instagram
      </a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section">
    <div class="section-title">About me</div>
    <div class="about-grid">
      <div class="about-item tilt"><div class="about-icon">🎓</div><p><strong>B.Tech CSE</strong> student passionate about Data Analytics &amp; Software Dev</p></div>
      <div class="about-item tilt"><div class="about-icon">💻</div><p><strong>Python · SQL · JS</strong> — data-driven problem solving at the core</p></div>
      <div class="about-item tilt"><div class="about-icon">📊</div><p>Focused on <strong>Data Analysis, AI</strong>, and impactful real-world projects</p></div>
      <div class="about-item tilt"><div class="about-icon">🎯</div><p>Goal: <strong>Data Analyst</strong> contributing to data-driven decisions</p></div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section">
    <div class="section-title">Tech stack</div>
    <div class="tech-grid">
      <span class="tech-badge py"><span class="dot"></span>Python</span>
      <span class="tech-badge sql"><span class="dot"></span>SQL</span>
      <span class="tech-badge pg"><span class="dot"></span>PostgreSQL</span>
      <span class="tech-badge pd"><span class="dot"></span>Pandas</span>
      <span class="tech-badge np"><span class="dot"></span>NumPy</span>
      <span class="tech-badge ml"><span class="dot"></span>Matplotlib</span>
      <span class="tech-badge pbi"><span class="dot"></span>Power BI</span>
      <span class="tech-badge tab"><span class="dot"></span>Tableau</span>
      <span class="tech-badge js"><span class="dot"></span>JavaScript</span>
      <span class="tech-badge st"><span class="dot"></span>Streamlit</span>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section">
    <div class="section-title">GitHub stats</div>
    <div class="stats-row">
      <div class="stat-card tilt">
        <img src="https://github-readme-stats.vercel.app/api?username=Narasimha2308&theme=tokyonight&show_icons=true&hide_border=true&bg_color=161b22&title_color=58a6ff&text_color=8b949e&icon_color=d2a8ff" alt="GitHub Stats"/>
      </div>
      <div class="stat-card tilt">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Narasimha2308&theme=tokyonight&hide_border=true&background=161b22&ring=58a6ff&fire=ffa657&currStreakLabel=d2a8ff" alt="Streak Stats"/>
      </div>
    </div>
    <div style="margin-top:1rem" class="stat-card tilt">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Narasimha2308&layout=compact&theme=tokyonight&hide_border=true&bg_color=161b22&title_color=58a6ff&text_color=8b949e" alt="Top Languages" style="width:100%;display:block"/>
    </div>
  </div>

  <!-- CURRENTLY LEARNING -->
  <div class="section">
    <div class="section-title">Currently learning</div>
    <div class="learn-list">
      <div class="learn-item">📘 <span>Advanced SQL — Joins, Window Functions, CTEs</span><span class="pill">In Progress</span></div>
      <div class="learn-item">📊 <span>Data Visualization with Power BI &amp; Tableau</span><span class="pill">Active</span></div>
      <div class="learn-item">🐍 <span>Python for Data Analysis &amp; Automation</span><span class="pill">Ongoing</span></div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-title">Featured projects</div>
    <div class="projects-grid">
      <div class="proj-card tilt">
        <div class="proj-lang"><span class="proj-lang-dot" style="background:#3572A5"></span>Python</div>
        <h3>Job Application Tracker</h3>
        <p>Automate and manage job applications with smart tracking &amp; analytics</p>
      </div>
      <div class="proj-card tilt">
        <div class="proj-lang"><span class="proj-lang-dot" style="background:#e38c00"></span>Python + SQL</div>
        <h3>Sales Data Analysis</h3>
        <p>End-to-end sales pipeline analysis with actionable insights</p>
      </div>
      <div class="proj-card tilt">
        <div class="proj-lang"><span class="proj-lang-dot" style="background:#f2c94c"></span>Power BI</div>
        <h3>Business Dashboard</h3>
        <p>Interactive KPI dashboard for data-driven decision making</p>
      </div>
      <div class="proj-card tilt">
        <div class="proj-lang"><span class="proj-lang-dot" style="background:#ff4b9a"></span>Python · BART</div>
        <h3>AI Text Summarizer</h3>
        <p>BART-powered NLP summarizer deployed via Streamlit</p>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="view-counter">
      <span class="pulse-dot"></span>
      Profile views &nbsp;<span class="num" id="view-num">0</span>
    </div>
    <p>⭐ From Narasimha — Keep Learning 🚀</p>
  </div>

</div>

<script>
/* ---- PARTICLE CANVAS ---- */
const canvas = document.getElementById('particles');
const ctx = canvas.getContext('2d');
let W, H, pts = [];

function resize() {
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

const COLORS = ['#58a6ff','#d2a8ff','#ffa657','#3fb950','#ff7b72'];
for (let i = 0; i < 80; i++) {
  pts.push({
    x: Math.random() * window.innerWidth,
    y: Math.random() * window.innerHeight,
    vx: (Math.random() - .5) * .3,
    vy: (Math.random() - .5) * .3,
    r: Math.random() * 1.8 + .5,
    c: COLORS[Math.floor(Math.random() * COLORS.length)],
    a: Math.random() * .6 + .2
  });
}

function drawParticles() {
  ctx.clearRect(0, 0, W, H);
  pts.forEach(p => {
    p.x += p.vx; p.y += p.vy;
    if (p.x < 0) p.x = W; if (p.x > W) p.x = 0;
    if (p.y < 0) p.y = H; if (p.y > H) p.y = 0;
    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
    ctx.fillStyle = p.c;
    ctx.globalAlpha = p.a;
    ctx.fill();
    ctx.globalAlpha = 1;
  });
  pts.forEach((a, i) => {
    pts.slice(i + 1).forEach(b => {
      const d = Math.hypot(a.x - b.x, a.y - b.y);
      if (d < 120) {
        ctx.beginPath();
        ctx.moveTo(a.x, a.y);
        ctx.lineTo(b.x, b.y);
        ctx.strokeStyle = a.c;
        ctx.globalAlpha = (1 - d / 120) * .15;
        ctx.lineWidth = .5;
        ctx.stroke();
        ctx.globalAlpha = 1;
      }
    });
  });
  requestAnimationFrame(drawParticles);
}
drawParticles();

/* ---- TYPING ANIMATION ---- */
const phrases = [
  'Python • SQL • Data Visualization',
  'Building impactful data projects',
  'Aspiring Data Analyst',
  'Learning every single day'
];
let pi = 0, ci = 0, deleting = false;
const typingEl = document.getElementById('typing-text');

function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    typingEl.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) {
      deleting = true;
      setTimeout(type, 1800);
      return;
    }
  } else {
    typingEl.textContent = phrase.slice(0, --ci);
    if (ci === 0) {
      deleting = false;
      pi = (pi + 1) % phrases.length;
    }
  }
  setTimeout(type, deleting ? 40 : 80);
}
type();

/* ---- VIEW COUNTER ---- */
let v = 0;
const target = Math.floor(Math.random() * 200) + 1200;
const vEl = document.getElementById('view-num');
const iv = setInterval(() => {
  v += Math.ceil((target - v) / 8);
  vEl.textContent = v.toLocaleString();
  if (v >= target) clearInterval(iv);
}, 30);

/* ---- 3D TILT on hover ---- */
document.querySelectorAll('.tilt').forEach(el => {
  el.addEventListener('mousemove', e => {
    const r = el.getBoundingClientRect();
    const x = (e.clientX - r.left) / r.width - .5;
    const y = (e.clientY - r.top) / r.height - .5;
    el.style.transform = `rotateY(${x * 14}deg) rotateX(${-y * 14}deg) scale(1.03)`;
  });
  el.addEventListener('mouseleave', () => {
    el.style.transform = 'rotateY(0) rotateX(0) scale(1)';
  });
});

/* ---- INTERSECTION OBSERVER fade-in ---- */
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.opacity = '1';
      e.target.style.transform = e.target.style.transform.replace('translateY(20px)', 'translateY(0)');
    }
  });
}, { threshold: .1 });

document.querySelectorAll('.about-item,.proj-card,.learn-item,.stat-card').forEach(el => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(20px)';
  obs.observe(el);
});
</script>
</body>
</html>
