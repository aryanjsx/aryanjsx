<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aryan Kumar</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Instrument+Serif:ital@0;1&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --ink: #0a0a0f;
  --paper: #f5f0e8;
  --paper2: #ede8dd;
  --accent: #c84b2f;
  --accent2: #1a3a5c;
  --gold: #b8860b;
  --muted: #7a7060;
  --border: #d4cfc4;
  --mono: 'JetBrains Mono', monospace;
  --serif: 'Instrument Serif', serif;
  --sans: 'Space Grotesk', sans-serif;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  background: var(--paper);
  color: var(--ink);
  font-family: var(--sans);
  font-size: 14px;
  line-height: 1.6;
  max-width: 860px;
  margin: 0 auto;
  padding: 48px 28px;
  position: relative;
}

/* grain overlay */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 999;
  opacity: 0.35;
}

/* ── HERO ─────────────────────────────────────────── */
.hero {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 32px;
  align-items: end;
  padding-bottom: 32px;
  border-bottom: 2px solid var(--ink);
  margin-bottom: 40px;
  animation: fadeUp 0.6s ease both;
}

.hero-left {}

.eyebrow {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: 8px;
}

.hero-name {
  font-family: var(--serif);
  font-size: clamp(52px, 9vw, 88px);
  font-weight: 400;
  line-height: 0.95;
  letter-spacing: -0.02em;
  color: var(--ink);
  margin-bottom: 16px;
}

.hero-name em {
  font-style: italic;
  color: var(--accent);
}

.hero-desc {
  color: var(--muted);
  font-size: 15px;
  max-width: 420px;
  line-height: 1.7;
}

.hero-right {
  text-align: right;
}

.hero-meta {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--muted);
  line-height: 2;
}

.hero-meta a {
  color: var(--accent2);
  text-decoration: none;
  border-bottom: 1px solid currentColor;
}

.hero-meta strong {
  color: var(--ink);
  font-weight: 600;
}

/* ── STATUS PILL ──────────────────────────────────── */
.status-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--ink);
  color: var(--paper);
  border-radius: 100px;
  padding: 6px 16px;
  font-size: 11px;
  font-family: var(--mono);
  letter-spacing: 0.05em;
  margin-top: 20px;
}

.status-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #4ade80;
  animation: pulse 2s ease infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(74,222,128,0.4); }
  50% { opacity: 0.8; box-shadow: 0 0 0 4px rgba(74,222,128,0); }
}

/* ── SECTION ──────────────────────────────────────── */
.section {
  margin-bottom: 48px;
  animation: fadeUp 0.6s ease both;
}

.section:nth-child(2) { animation-delay: 0.08s; }
.section:nth-child(3) { animation-delay: 0.16s; }
.section:nth-child(4) { animation-delay: 0.24s; }
.section:nth-child(5) { animation-delay: 0.32s; }

.section-label {
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.25em;
  text-transform: uppercase;
  color: var(--muted);
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

.section-num {
  color: var(--accent);
  font-weight: 700;
}

/* ── STACK ────────────────────────────────────────── */
.stack-group {
  margin-bottom: 24px;
}

.stack-group-title {
  font-size: 11px;
  font-family: var(--mono);
  color: var(--muted);
  letter-spacing: 0.1em;
  text-transform: uppercase;
  margin-bottom: 10px;
  padding-left: 2px;
}

.stack-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.chip {
  border: 1.5px solid var(--border);
  border-radius: 6px;
  padding: 6px 14px;
  font-size: 13px;
  font-family: var(--sans);
  font-weight: 500;
  color: var(--ink);
  background: transparent;
  cursor: default;
  transition: all 0.18s ease;
  display: flex;
  align-items: center;
  gap: 7px;
}

.chip:hover {
  border-color: var(--accent);
  background: var(--accent);
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(200,75,47,0.2);
}

.chip-icon { font-size: 15px; }

/* ── STAT CARD TEXT ───────────────────────────────── */
.stat-card--text { padding: 20px 22px; }

.stat-card-title {
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 14px;
}

.stat-badges { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }

.css-badge {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  background: var(--b, #333);
  color: white;
  border-radius: 4px;
  padding: 4px 10px;
  font-family: var(--mono);
  font-size: 11px;
  font-weight: 500;
  letter-spacing: 0.03em;
  white-space: nowrap;
}

.stat-link {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid var(--accent);
  padding-bottom: 1px;
  transition: opacity 0.15s;
}
.stat-link:hover { opacity: 0.7; }

.lang-bars { display: flex; flex-direction: column; gap: 9px; }

.lang-row {
  display: grid;
  grid-template-columns: 90px 1fr 36px;
  align-items: center;
  gap: 10px;
}

.lang-name { font-size: 12px; color: var(--ink); font-weight: 500; }

.lang-bar {
  height: 6px;
  background: var(--paper2);
  border-radius: 99px;
  overflow: hidden;
}

.lang-fill { height: 100%; border-radius: 99px; }

.lang-pct {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--muted);
  text-align: right;
}

.badge-cloud { display: flex; flex-wrap: wrap; gap: 8px; }

/* ── POSTS ────────────────────────────────────────── */
.posts { display: flex; flex-direction: column; gap: 0; }

.post {
  display: grid;
  grid-template-columns: 1fr auto;
  align-items: center;
  gap: 16px;
  padding: 16px 0;
  border-bottom: 1px solid var(--border);
  text-decoration: none;
  color: inherit;
  transition: all 0.18s ease;
}

.post:first-child { border-top: 1px solid var(--border); }

.post:hover .post-title {
  color: var(--accent);
}

.post:hover .post-arrow {
  transform: translateX(4px);
  color: var(--accent);
}

.post-title {
  font-size: 14px;
  font-weight: 500;
  color: var(--ink);
  transition: color 0.18s;
  line-height: 1.4;
}

.post-arrow {
  color: var(--muted);
  font-size: 18px;
  transition: all 0.18s;
}

/* ── STATS ────────────────────────────────────────── */
.stats-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 20px;
}

.stat-card {
  border: 1.5px solid var(--border);
  border-radius: 8px;
  padding: 20px;
  background: transparent;
  transition: border-color 0.2s;
  overflow: hidden;
}

.stat-card:hover {
  border-color: var(--accent2);
}

.stat-card img {
  width: 100%;
  border-radius: 4px;
  display: block;
}

.activity-card {
  border: 1.5px solid var(--border);
  border-radius: 8px;
  padding: 20px;
  overflow: hidden;
}

.activity-card img {
  width: 100%;
  border-radius: 4px;
}

/* ── CONNECT ──────────────────────────────────────── */
.connect-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 8px;
}

.connect-link {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 14px;
  border: 1.5px solid var(--border);
  border-radius: 8px;
  text-decoration: none;
  color: var(--ink);
  font-size: 13px;
  font-weight: 500;
  transition: all 0.18s;
}

.connect-link:hover {
  border-color: var(--accent2);
  background: var(--accent2);
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(26,58,92,0.2);
}

/* ── FOOTER ───────────────────────────────────────── */
.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 32px;
  border-top: 1px solid var(--border);
  margin-top: 8px;
}

.footer-left {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--muted);
}

.footer-right img {
  vertical-align: middle;
}

/* ── DECORATIVE RULE ──────────────────────────────── */
.ornament {
  text-align: center;
  color: var(--border);
  font-size: 20px;
  letter-spacing: 0.4em;
  margin: 8px 0 36px;
}

/* ── ANIMATIONS ───────────────────────────────────── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* ── RESPONSIVE ───────────────────────────────────── */
@media (max-width: 600px) {
  .hero { grid-template-columns: 1fr; }
  .hero-right { text-align: left; }
  .stats-row { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- HERO -->
<header class="hero">
  <div class="hero-left">
    <div class="eyebrow">Full-Stack &amp; Cloud Developer</div>
    <h1 class="hero-name">Aryan<br><em>Kumar</em></h1>
    <p class="hero-desc">Building AURA · crafting web experiences with React, Node.js &amp; Azure. Currently exploring the depths of networking &amp; Linux.</p>
    <div class="status-pill">
      <span class="status-dot"></span>
      Available for interesting projects
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-meta">
      <strong>Email</strong><br>
      <a href="mailto:me@aryankr.in">me@aryankr.in</a><br><br>
      <strong>Portfolio</strong><br>
      <a href="https://aryankr.in" target="_blank">aryankr.in</a><br><br>
      <strong>GitHub</strong><br>
      <a href="https://github.com/aryanjsx" target="_blank">@aryanjsx</a>
    </div>
  </div>
</header>

<div class="ornament">· · ·</div>

<!-- TECH STACK -->
<section class="section">
  <div class="section-label"><span class="section-num">01</span> Tech Stack</div>

  <div class="stack-group">
    <div class="stack-group-title">Cloud &amp; Backend</div>
    <div class="stack-chips">
      <div class="chip"><span class="chip-icon">☁️</span> Azure</div>
      <div class="chip"><span class="chip-icon">🟢</span> Node.js</div>
      <div class="chip"><span class="chip-icon">🚂</span> Express</div>
      <div class="chip"><span class="chip-icon">🔥</span> Firebase</div>
      <div class="chip"><span class="chip-icon">🔷</span> GraphQL</div>
    </div>
  </div>

  <div class="stack-group">
    <div class="stack-group-title">Frontend</div>
    <div class="stack-chips">
      <div class="chip"><span class="chip-icon">⚛️</span> React</div>
      <div class="chip"><span class="chip-icon">▲</span> Next.js</div>
      <div class="chip"><span class="chip-icon">🟨</span> JavaScript</div>
      <div class="chip"><span class="chip-icon">🎨</span> Tailwind CSS</div>
      <div class="chip"><span class="chip-icon">🌐</span> HTML / CSS</div>
    </div>
  </div>

  <div class="stack-group">
    <div class="stack-group-title">Databases</div>
    <div class="stack-chips">
      <div class="chip"><span class="chip-icon">🍃</span> MongoDB</div>
      <div class="chip"><span class="chip-icon">🐘</span> PostgreSQL</div>
      <div class="chip"><span class="chip-icon">🐬</span> MySQL</div>
    </div>
  </div>

  <div class="stack-group">
    <div class="stack-group-title">Tooling &amp; Other</div>
    <div class="stack-chips">
      <div class="chip"><span class="chip-icon">🐙</span> Git</div>
      <div class="chip"><span class="chip-icon">🐧</span> Linux</div>
      <div class="chip"><span class="chip-icon">🎨</span> Figma</div>
      <div class="chip"><span class="chip-icon">🐍</span> Python</div>
      <div class="chip"><span class="chip-icon">☕</span> Java</div>
    </div>
  </div>
</section>

<!-- GITHUB STATS -->
<section class="section">
  <div class="section-label"><span class="section-num">02</span> GitHub Stats</div>

  <div class="stats-row">
    <div class="stat-card stat-card--text">
      <div class="stat-card-title">Profile</div>
      <div class="css-badges">
        <span class="css-badge" style="--b:#24292e;">⌥ GitHub · aryanjsx</span>
        <span class="css-badge" style="--b:#1a3a5c;">👥 Followers</span>
        <span class="css-badge" style="--b:#b8860b;">⭐ Stars</span>
      </div>
      <div class="stat-cta" style="margin-top:20px;">
        <a href="https://github.com/aryanjsx" target="_blank" class="stat-link">View GitHub Profile →</a>
      </div>
    </div>
    <div class="stat-card stat-card--text">
      <div class="stat-card-title">Top Languages</div>
      <div class="lang-bars">
        <div class="lang-row"><span class="lang-name">JavaScript</span><div class="lang-bar"><div class="lang-fill" style="width:55%;background:#f7df1e;"></div></div><span class="lang-pct">55%</span></div>
        <div class="lang-row"><span class="lang-name">TypeScript</span><div class="lang-bar"><div class="lang-fill" style="width:20%;background:#3178c6;"></div></div><span class="lang-pct">20%</span></div>
        <div class="lang-row"><span class="lang-name">Python</span><div class="lang-bar"><div class="lang-fill" style="width:12%;background:#3572A5;"></div></div><span class="lang-pct">12%</span></div>
        <div class="lang-row"><span class="lang-name">CSS</span><div class="lang-bar"><div class="lang-fill" style="width:8%;background:#563d7c;"></div></div><span class="lang-pct">8%</span></div>
        <div class="lang-row"><span class="lang-name">Other</span><div class="lang-bar"><div class="lang-fill" style="width:5%;background:#7a7060;"></div></div><span class="lang-pct">5%</span></div>
      </div>
    </div>
  </div>

  <div class="activity-card">
    <div class="stat-card-title" style="margin-bottom:16px;">Tech Badges</div>
    <div class="badge-cloud">
      <span class="css-badge" style="--b:#20232a;color:#61dafb;">⚛️ React</span>
      <span class="css-badge" style="--b:#000;">▲ Next.js</span>
      <span class="css-badge" style="--b:#339933;">🟢 Node.js</span>
      <span class="css-badge" style="--b:#000;">🚂 Express</span>
      <span class="css-badge" style="--b:#0078d4;">☁️ Azure</span>
      <span class="css-badge" style="--b:#47a248;">🍃 MongoDB</span>
      <span class="css-badge" style="--b:#4169e1;">🐘 PostgreSQL</span>
      <span class="css-badge" style="--b:#e10098;">🔷 GraphQL</span>
      <span class="css-badge" style="--b:#ffca28;color:#000;">🔥 Firebase</span>
      <span class="css-badge" style="--b:#06b6d4;">🎨 Tailwind</span>
      <span class="css-badge" style="--b:#3776ab;">🐍 Python</span>
      <span class="css-badge" style="--b:#ed8b00;">☕ Java</span>
      <span class="css-badge" style="--b:#f05032;">🐙 Git</span>
      <span class="css-badge" style="--b:#333;">🐧 Linux</span>
      <span class="css-badge" style="--b:#f24e1e;">🎨 Figma</span>
    </div>
  </div>
</section>

<!-- BLOG POSTS -->
<section class="section">
  <div class="section-label"><span class="section-num">03</span> Latest Writing</div>

  <div class="posts">
    <a class="post" href="https://aryanjsx.medium.com/demystifying-binary-decimal-and-hexadecimal-in-networking-c2d425bfb157" target="_blank">
      <span class="post-title">Demystifying Binary, Decimal &amp; Hexadecimal in Networking</span>
      <span class="post-arrow">→</span>
    </a>
    <a class="post" href="https://aryanjsx.medium.com/networking-you-should-know-19ba769cbce7" target="_blank">
      <span class="post-title">Networking: You Should Know</span>
      <span class="post-arrow">→</span>
    </a>
    <a class="post" href="https://aryanjsx.medium.com/how-gpt-5-is-better-than-older-models-c9cbef2fd7ca" target="_blank">
      <span class="post-title">How GPT-5 Is Better Than Older Models</span>
      <span class="post-arrow">→</span>
    </a>
    <a class="post" href="https://aryanjsx.medium.com/%EF%B8%8F-bihar-makes-history-how-indias-first-mobile-voting-system-actually-works-b81739e8605c" target="_blank">
      <span class="post-title">Bihar Makes History: India's First Mobile Voting System</span>
      <span class="post-arrow">→</span>
    </a>
    <a class="post" href="https://aryanjsx.medium.com/react-different-9fceac072cd1" target="_blank">
      <span class="post-title">Difference Between Some Terms of React</span>
      <span class="post-arrow">→</span>
    </a>
  </div>
</section>

<!-- CONNECT -->
<section class="section">
  <div class="section-label"><span class="section-num">04</span> Connect</div>

  <div class="connect-grid">
    <a class="connect-link" href="https://linkedin.com/in/aryanjsx" target="_blank">💼 LinkedIn</a>
    <a class="connect-link" href="https://aryanjsx.medium.com/" target="_blank">✍️ Medium</a>
    <a class="connect-link" href="https://www.leetcode.com/aryanjsx" target="_blank">🧩 LeetCode</a>
    <a class="connect-link" href="https://www.geeksforgeeks.org/user/aryanjsx/" target="_blank">🌿 GFG</a>
    <a class="connect-link" href="https://instagram.com/aryanjsx" target="_blank">📸 Instagram</a>
    <a class="connect-link" href="https://fb.com/aryanjsx" target="_blank">📘 Facebook</a>
    <a class="connect-link" href="https://aryankr.in" target="_blank">🌐 Portfolio</a>
    <a class="connect-link" href="mailto:me@aryankr.in">📧 Email</a>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <span class="footer-left">© Aryan Kumar · aryankr.in</span>
  <span class="footer-right">
    <img src="https://komarev.com/ghpvc/?username=aryanjsx&label=views&color=c84b2f&style=flat-square" alt="views"/>
  </span>
</footer>

</body>
</html>
