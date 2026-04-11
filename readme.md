<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hari Babu — GitHub Profile README</title>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323:wght@400&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --panel: #161b22;
    --panel2: #1c2230;
    --border: #30363d;
    --neon-pink: #ff2d78;
    --neon-cyan: #00f5ff;
    --neon-purple: #bf5fff;
    --neon-green: #39ff14;
    --neon-yellow: #ffd700;
    --text: #e6edf3;
    --muted: #8b949e;
    --pixel: 4px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'VT323', monospace;
    font-size: 18px;
    overflow-x: hidden;
    position: relative;
  }

  /* Scanline overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }

  /* Pixel grid background */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,245,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,255,0.03) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 32px 20px;
    position: relative;
    z-index: 1;
  }

  /* ===== HERO ===== */
  .hero {
    position: relative;
    border: 3px solid var(--neon-cyan);
    background: var(--panel);
    padding: 0;
    overflow: hidden;
    image-rendering: pixelated;
    box-shadow: 0 0 30px rgba(0,245,255,0.3), inset 0 0 60px rgba(0,0,0,0.5);
    margin-bottom: 24px;
  }
  .hero img.banner {
    width: 100%;
    display: block;
    image-rendering: pixelated;
    filter: brightness(0.85) saturate(1.2);
  }
  .hero-overlay {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    background: linear-gradient(transparent, rgba(13,17,23,0.97));
    padding: 32px 28px 24px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
  }
  .hero-name {
    font-family: 'Press Start 2P', monospace;
    font-size: 22px;
    color: var(--neon-cyan);
    text-shadow: 0 0 12px var(--neon-cyan), 0 0 30px rgba(0,245,255,0.5);
    letter-spacing: 2px;
    animation: flicker 4s infinite;
  }
  @keyframes flicker {
    0%,95%,97%,100% { opacity: 1; }
    96% { opacity: 0.7; }
  }
  .hero-sub {
    font-family: 'VT323', monospace;
    font-size: 26px;
    color: var(--neon-pink);
    text-shadow: 0 0 8px var(--neon-pink);
    letter-spacing: 3px;
  }

  /* Typing animation strip */
  .typing-strip {
    background: var(--panel2);
    border: 2px solid var(--neon-purple);
    border-top: none;
    padding: 10px 0;
    text-align: center;
    overflow: hidden;
    position: relative;
    margin-bottom: 24px;
    box-shadow: 0 4px 20px rgba(191,95,255,0.2);
  }
  .typing-strip img { display: block; margin: 0 auto; }

  /* ===== SECTION CONTAINER ===== */
  .section {
    background: var(--panel);
    border: 2px solid var(--border);
    margin-bottom: 20px;
    position: relative;
    overflow: hidden;
  }
  .section::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }
  .section.cyan::before { background: var(--neon-cyan); box-shadow: 0 0 8px var(--neon-cyan); }
  .section.pink::before { background: var(--neon-pink); box-shadow: 0 0 8px var(--neon-pink); }
  .section.purple::before { background: var(--neon-purple); box-shadow: 0 0 8px var(--neon-purple); }
  .section.green::before { background: var(--neon-green); box-shadow: 0 0 8px var(--neon-green); }
  .section.yellow::before { background: var(--neon-yellow); box-shadow: 0 0 8px var(--neon-yellow); }

  .section-header {
    background: rgba(0,0,0,0.3);
    border-bottom: 1px solid var(--border);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-title {
    font-family: 'Press Start 2P', monospace;
    font-size: 11px;
    letter-spacing: 1px;
  }
  .section.cyan .section-title { color: var(--neon-cyan); }
  .section.pink .section-title { color: var(--neon-pink); }
  .section.purple .section-title { color: var(--neon-purple); }
  .section.green .section-title { color: var(--neon-green); }
  .section.yellow .section-title { color: var(--neon-yellow); }

  .section-body { padding: 20px; }

  /* ===== ABOUT ME ===== */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }
  .about-item {
    background: rgba(0,0,0,0.25);
    border: 1px solid var(--border);
    padding: 12px 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }
  .about-item:hover {
    border-color: var(--neon-cyan);
    box-shadow: 0 0 10px rgba(0,245,255,0.15);
  }
  .about-icon { font-size: 20px; flex-shrink: 0; }
  .about-label {
    font-family: 'Press Start 2P', monospace;
    font-size: 7px;
    color: var(--muted);
    margin-bottom: 5px;
    letter-spacing: 0.5px;
  }
  .about-value {
    font-family: 'VT323', monospace;
    font-size: 18px;
    color: var(--text);
    line-height: 1.3;
  }
  .about-center {
    grid-column: 1 / -1;
    display: flex;
    justify-content: center;
    padding: 12px 0 4px;
  }
  .about-center img { image-rendering: pixelated; }

  /* ===== TECH STACK ===== */
  .stack-category {
    margin-bottom: 20px;
  }
  .stack-category:last-child { margin-bottom: 0; }
  .stack-cat-label {
    font-family: 'Press Start 2P', monospace;
    font-size: 8px;
    color: var(--muted);
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
    letter-spacing: 1px;
  }
  .stack-cat-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }
  .icons-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    align-items: center;
  }
  .icons-row img {
    width: 44px;
    height: 44px;
    transition: transform 0.15s, filter 0.15s;
    image-rendering: auto;
  }
  .icons-row img:hover {
    transform: translateY(-4px) scale(1.1);
    filter: drop-shadow(0 0 8px var(--neon-cyan));
  }

  /* ===== GITHUB STATS ===== */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }
  .stats-grid .full { grid-column: 1 / -1; }
  .stats-grid img, .streak-img img, .langs-img img {
    width: 100%;
    border-radius: 0;
    display: block;
    image-rendering: auto;
    filter: hue-rotate(10deg) brightness(1.05);
  }
  .stats-note {
    font-family: 'Press Start 2P', monospace;
    font-size: 7px;
    color: var(--muted);
    text-align: center;
    padding: 10px 0 0;
    letter-spacing: 0.5px;
  }

  /* ===== CONNECT ===== */
  .connect-row {
    display: flex;
    justify-content: center;
    gap: 24px;
    flex-wrap: wrap;
    padding: 8px 0;
  }
  .connect-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    text-decoration: none;
    transition: transform 0.15s;
  }
  .connect-link:hover { transform: translateY(-6px); }
  .connect-link img {
    width: 52px;
    height: 52px;
    filter: drop-shadow(0 0 6px rgba(0,245,255,0.4));
  }
  .connect-label {
    font-family: 'Press Start 2P', monospace;
    font-size: 7px;
    color: var(--muted);
  }

  /* ===== FOOTER ===== */
  .footer {
    text-align: center;
    padding: 24px 0 8px;
    font-family: 'Press Start 2P', monospace;
    font-size: 8px;
    color: var(--muted);
    letter-spacing: 1px;
  }
  .footer span {
    color: var(--neon-pink);
    text-shadow: 0 0 6px var(--neon-pink);
  }

  /* Pixel corners decoration */
  .pixel-corner {
    position: absolute;
    width: 8px; height: 8px;
    background: var(--neon-cyan);
  }
  .pc-tl { top: -2px; left: -2px; }
  .pc-tr { top: -2px; right: -2px; }
  .pc-bl { bottom: -2px; left: -2px; }
  .pc-br { bottom: -2px; right: -2px; }

  /* Animated neon border on hero */
  @keyframes border-glow {
    0%, 100% { box-shadow: 0 0 20px rgba(0,245,255,0.3), inset 0 0 60px rgba(0,0,0,0.5); }
    50% { box-shadow: 0 0 40px rgba(0,245,255,0.6), 0 0 80px rgba(0,245,255,0.2), inset 0 0 60px rgba(0,0,0,0.5); }
  }
  .hero { animation: border-glow 3s ease-in-out infinite; }

  @media (max-width: 600px) {
    .about-grid { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr; }
    .hero-name { font-size: 14px; }
    .hero-sub { font-size: 20px; }
  }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO BANNER -->
  <div class="hero">
    <div class="pixel-corner pc-tl"></div>
    <div class="pixel-corner pc-tr"></div>
    <div class="pixel-corner pc-bl"></div>
    <div class="pixel-corner pc-br"></div>
    <img class="banner" src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f1b00d6c9.gif" alt="Holographic Interface"/>
    <div class="hero-overlay">
      <div class="hero-name">Hi 👋 I'm Hari Babu</div>
      <div class="hero-sub">FULL STACK WEB DEVELOPER</div>
    </div>
  </div>

  <!-- TYPING SVG -->
  <div class="typing-strip">
    <img src="https://readme-typing-svg.herokuapp.com/?font=Press+Start+2P&size=18&center=true&vCenter=true&width=600&height=55&duration=4000&color=00F5FF&lines=Welcome+to+my+Profile!;Full+Stack+Web+Developer!;Building+the+future...+one+commit+at+a+time" alt="Typing animation" />
  </div>

  <!-- ABOUT ME -->
  <div class="section cyan">
    <div class="section-header">
      <div class="section-title">// PLAYER.INFO</div>
    </div>
    <div class="section-body">
      <div class="about-grid">
        <div class="about-item">
          <span class="about-icon">🎓</span>
          <div>
            <div class="about-label">EDUCATION</div>
            <div class="about-value">B.Tech — EEE<br>(Electrical & Electronics Eng.)</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">🏆</span>
          <div>
            <div class="about-label">BEST PROJECT</div>
            <div class="about-value">TastyHub Web Application</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">🔭</span>
          <div>
            <div class="about-label">INTERESTS</div>
            <div class="about-value">Future Tech & Emerging Technologies</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">🎯</span>
          <div>
            <div class="about-label">GOAL</div>
            <div class="about-value">Building innovative web solutions that make a difference</div>
          </div>
        </div>
        <div class="about-item" style="grid-column:1/-1">
          <span class="about-icon">📫</span>
          <div>
            <div class="about-label">CONTACT</div>
            <div class="about-value">vetaharibabu087@gmail.com</div>
          </div>
        </div>
        <div class="about-center">
          <img src="https://user-images.githubusercontent.com/74038190/212284087-bbe7e86f-9e70-4434-9203-76ba3a0a07b0.gif" width="320" alt="animated"/>
        </div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section pink">
    <div class="section-header">
      <div class="section-title">// SKILL.TREE</div>
    </div>
    <div class="section-body">

      <div class="stack-category">
        <div class="stack-cat-label">⚡ FRONTEND</div>
        <div class="icons-row">
          <img src="https://skillicons.dev/icons?i=html" alt="HTML" title="HTML5"/>
          <img src="https://skillicons.dev/icons?i=css" alt="CSS" title="CSS3"/>
          <img src="https://skillicons.dev/icons?i=javascript" alt="JS" title="JavaScript"/>
          <img src="https://skillicons.dev/icons?i=react" alt="React" title="React"/>
          <img src="https://skillicons.dev/icons?i=typescript" alt="TS" title="TypeScript"/>
          <img src="https://skillicons.dev/icons?i=bootstrap" alt="Bootstrap" title="Bootstrap"/>
          <img src="https://skillicons.dev/icons?i=vite" alt="Vite" title="Vite"/>
          <img src="https://skillicons.dev/icons?i=tailwindcss" alt="Tailwind" title="TailwindCSS"/>
        </div>
      </div>

      <div class="stack-category">
        <div class="stack-cat-label">🛢 BACKEND</div>
        <div class="icons-row">
          <img src="https://skillicons.dev/icons?i=nodejs" alt="Node.js" title="Node.js"/>
          <img src="https://skillicons.dev/icons?i=express" alt="Express" title="Express.js"/>
          <img src="https://skillicons.dev/icons?i=mongodb" alt="MongoDB" title="MongoDB"/>
          <img src="https://skillicons.dev/icons?i=mysql" alt="MySQL" title="MySQL"/>
        </div>
      </div>

      <div class="stack-category">
        <div class="stack-cat-label">🔧 TOOLS & PLATFORMS</div>
        <div class="icons-row">
          <img src="https://skillicons.dev/icons?i=git" alt="Git" title="Git"/>
          <img src="https://skillicons.dev/icons?i=github" alt="GitHub" title="GitHub"/>
          <img src="https://skillicons.dev/icons?i=vscode" alt="VSCode" title="VS Code"/>
          <img src="https://skillicons.dev/icons?i=postman" alt="Postman" title="Postman"/>
          <img src="https://skillicons.dev/icons?i=figma" alt="Figma" title="Figma"/>
          <img src="https://skillicons.dev/icons?i=vercel" alt="Vercel" title="Vercel"/>
          <img src="https://skillicons.dev/icons?i=netlify" alt="Netlify" title="Netlify"/>
        </div>
      </div>

      <div class="stack-category">
        <div class="stack-cat-label">🧪 ADDITIONAL (INTERMEDIATE)</div>
        <div class="icons-row">
          <img src="https://skillicons.dev/icons?i=cs" alt="C#" title="C#"/>
          <img src="https://skillicons.dev/icons?i=py" alt="Python" title="Python"/>
        </div>
      </div>

    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="section green">
    <div class="section-header">
      <div class="section-title">// GITHUB.STATS</div>
    </div>
    <div class="section-body">
      <div class="stats-grid">
        <div>
          <img src="https://github-readme-stats.vercel.app/api?username=HariBabu&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f5ff&icon_color=ff2d78&text_color=e6edf3&border_radius=0" alt="GitHub Stats"/>
        </div>
        <div>
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=HariBabu&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=00f5ff&text_color=e6edf3&border_radius=0" alt="Top Languages"/>
        </div>
        <div class="full">
          <img src="https://streak-stats.demolab.com/?user=HariBabu&theme=tokyonight&hide_border=true&background=0d1117&ring=00f5ff&fire=ff2d78&currStreakLabel=00f5ff&sideLabels=00f5ff&dates=8b949e" alt="GitHub Streak"/>
        </div>
      </div>
      <p class="stats-note">⚠ REPLACE "HariBabu" WITH YOUR EXACT GITHUB USERNAME</p>
    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="section purple">
    <div class="section-header">
      <div class="section-title">// ACTIVITY.LOG</div>
    </div>
    <div class="section-body">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=HariBabu&theme=tokyo-night&hide_border=true&bg_color=0d1117&color=00f5ff&line=ff2d78&point=bf5fff&area=true&area_color=00f5ff" alt="Activity Graph" style="width:100%; display:block;" />
      <p class="stats-note">⚠ REPLACE "HariBabu" WITH YOUR EXACT GITHUB USERNAME</p>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section yellow">
    <div class="section-header">
      <div class="section-title">// CONNECT.EXE</div>
    </div>
    <div class="section-body">
      <div class="connect-row">
        <a href="https://www.linkedin.com/in/126a29268/" class="connect-link" target="_blank">
          <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/>
          <span class="connect-label">LINKEDIN</span>
        </a>
        <a href="https://www.instagram.com/07_hari_krishna/?hl=en" class="connect-link" target="_blank">
          <img src="https://skillicons.dev/icons?i=instagram" alt="Instagram"/>
          <span class="connect-label">INSTAGRAM</span>
        </a>
        <a href="mailto:vetaharibabu087@gmail.com" class="connect-link">
          <img src="https://skillicons.dev/icons?i=gmail" alt="Gmail"/>
          <span class="connect-label">GMAIL</span>
        </a>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    CRAFTED WITH <span>♥</span> BY HARI BABU &nbsp;|&nbsp; FULL STACK DEVELOPER
  </div>

</div>
</body>
</html>
