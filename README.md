<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ronfar623.github.io</title>
<style>
  :root {
    --bg-color: #1a1a1e;
    --card-bg: #26262b;
    --card-border: #3f3f46;
    --text-color: #f4f4f5;
    --text-dim: #a1a1aa;
    --accent-color: #3b82f6;
    --accent-hover: #2563eb;
    --accent-glow: rgba(59, 130, 246, 0.35);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
  }

  /* Ambient background glow */
  body::before {
    content: "";
    position: fixed;
    top: -300px;
    left: 50%;
    transform: translateX(-50%);
    width: 900px;
    height: 600px;
    background: radial-gradient(ellipse at center, var(--accent-glow) 0%, transparent 65%);
    opacity: 0.3;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }

  /* ---------- Header ---------- */
  header { padding: 28px 0; }

  .nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 12px;
    font-weight: 600;
    font-size: 1.05rem;
    color: var(--text-color);
    text-decoration: none;
  }

  .logo-mark {
    display: grid;
    place-items: center;
    width: 36px;
    height: 36px;
    border-radius: 9px;
    background: linear-gradient(135deg, var(--accent-color), #1d4ed8);
    color: #fff;
    font-weight: 700;
    font-size: 1rem;
    box-shadow: 0 4px 14px var(--accent-glow);
  }

  .nav-links a.github {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 8px 14px;
    border: 1px solid var(--card-border);
    border-radius: 8px;
    color: var(--text-dim);
    font-size: 0.9rem;
    font-weight: 500;
    text-decoration: none;
    transition: border-color 0.2s ease, background-color 0.2s ease, color 0.2s ease;
  }

  .nav-links a.github:hover {
    border-color: var(--accent-color);
    background-color: rgba(59, 130, 246, 0.08);
    color: var(--text-color);
  }

  /* ---------- Intro ---------- */
  .intro {
    padding-top: 24px;
    padding-bottom: 8px;
    text-align: center;
  }

  .intro h1 {
    font-size: clamp(1.8rem, 4vw, 2.4rem);
    font-weight: 700;
    letter-spacing: -0.01em;
    margin-bottom: 10px;
  }

  .intro p {
    color: var(--text-dim);
    font-size: 1rem;
  }

  /* ---------- Projects ---------- */
  .section { padding: 32px 0 40px; }

  .section-title {
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--text-dim);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-title::after {
    content: "";
    flex: 1;
    height: 1px;
    background: var(--card-border);
  }

  .project-card {
    display: grid;
    grid-template-columns: 1fr 1.1fr;
    background-color: var(--card-bg);
    border: 1px solid var(--card-border);
    border-radius: 14px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
  }

  .project-card:hover {
    transform: translateY(-3px);
    border-color: rgba(59, 130, 246, 0.5);
    box-shadow: 0 12px 32px rgba(0, 0, 0, 0.45), 0 0 0 1px rgba(59, 130, 246, 0.15);
  }

  .project-info { padding: 32px; display: flex; flex-direction: column; }

  .project-info h2 { font-size: 1.45rem; font-weight: 600; margin-bottom: 12px; }

  .project-info p {
    color: var(--text-dim);
    line-height: 1.65;
    font-size: 0.95rem;
    margin-bottom: 20px;
  }

  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 28px; }

  .tag {
    font-size: 0.75rem;
    font-weight: 500;
    color: var(--text-dim);
    background: #18181b;
    border: 1px solid var(--card-border);
    padding: 4px 10px;
    border-radius: 6px;
  }

  .tag.highlight {
    color: #93c5fd;
    border-color: rgba(59, 130, 246, 0.4);
    background: rgba(59, 130, 246, 0.1);
  }

  .project-actions { margin-top: auto; display: flex; gap: 12px; flex-wrap: wrap; }

  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 10px 18px;
    border-radius: 8px;
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.2s ease, transform 0.15s ease, border-color 0.2s ease;
  }

  .btn-primary {
    background-color: var(--accent-color);
    color: #fff;
    box-shadow: 0 4px 14px var(--accent-glow);
  }

  .btn-primary:hover { background-color: var(--accent-hover); transform: translateY(-1px); }

  .btn-secondary {
    background: transparent;
    color: var(--text-dim);
    border: 1px solid var(--card-border);
  }

  .btn-secondary:hover {
    color: var(--text-color);
    border-color: var(--accent-color);
    background-color: rgba(59, 130, 246, 0.06);
  }

  /* ---------- Project preview (CSS mock of the visualizer) ---------- */
  .project-preview {
    background: #4a4a52;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 40px 28px;
    border-left: 1px solid var(--card-border);
    box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.4);
    overflow: hidden;
  }

  .mock-screen {
    width: 100%;
    max-width: 340px;
    aspect-ratio: 16 / 10;
    background: #000;
    border: 1px solid #333;
    border-radius: 4px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.6);
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    animation: float 5s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
  }

  .mock-video {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 68%;
    height: 62%;
    background: rgba(12, 12, 15, 0.75);
    border: 2px dashed rgba(255, 255, 255, 0.9);
    border-radius: 3px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .mock-badge {
    background: rgba(0, 0, 0, 0.85);
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 6px;
    padding: 8px 12px;
    text-align: center;
    line-height: 1.5;
  }

  .mock-badge .l1 { color: #60a5fa; font-size: 0.72rem; font-weight: 600; }
  .mock-badge .l2 { color: #e4e4e7; font-size: 0.66rem; }
  .mock-badge .l3 { color: #a1a1aa; font-size: 0.6rem; }

  /* ---------- Footer ---------- */
  footer {
    margin-top: auto;
    border-top: 1px solid var(--card-border);
    padding: 28px 0;
  }

  .footer-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    color: var(--text-dim);
    font-size: 0.85rem;
  }

  .footer-inner a {
    color: var(--text-dim);
    text-decoration: none;
    transition: color 0.2s ease;
  }

  .footer-inner a:hover { color: var(--accent-color); }

  /* ---------- Entrance animation ---------- */
  .fade-in {
    opacity: 0;
    transform: translateY(14px);
    animation: fadeUp 0.7s ease forwards;
  }

  .fade-in.d2 { animation-delay: 0.15s; }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  @media (prefers-reduced-motion: reduce) {
    .fade-in, .mock-screen { animation: none; opacity: 1; transform: none; }
  }

  /* ---------- Responsive ---------- */
  @media (max-width: 760px) {
    .project-card { grid-template-columns: 1fr; }
    .project-preview {
      border-left: none;
      border-top: 1px solid var(--card-border);
      padding: 32px 24px;
    }
  }
</style>
</head>
<body>

<header class="container fade-in">
  <nav class="nav">
    <a class="logo" href="index.html">
      <span class="logo-mark">r</span>
      <span>ronfar623</span>
    </a>
    <div class="nav-links">
      <a class="github" href="https://github.com/ronfar623" target="_blank" rel="noopener">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor" aria-hidden="true">
          <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
        </svg>
        GitHub
      </a>
    </div>
  </nav>
</header>

<main>

  <section class="section container fade-in d2" id="projects">
    <div class="section-title">Projects</div>

    <a class="project-card" href="visualizer.html" style="text-decoration:none;color:inherit;">
      <div class="project-info">
        <h2>Display Scaling Visualizer</h2>
        <p>
          An interactive tool for understanding how video output scales onto a display.
          Pick your video resolution, display size, aspect ratio, and scaling mode —
          then see exactly how your content lands on the screen, complete with
          diagonal size, PPI, and a live scaling preview.
        </p>
        <div class="tags">
          <span class="tag highlight">JavaScript</span>
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">Display Scaling</span>
          <span class="tag">Aspect Ratio</span>
        </div>
        <div class="project-actions">
          <span class="btn btn-primary">Open Visualizer
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
          </span>
          <span class="btn btn-secondary" onclick="event.stopPropagation(); window.open('https://github.com/ronfar623/ronfar623.github.io', '_blank');">Source</span>
        </div>
      </div>
      <div class="project-preview" aria-hidden="true">
        <div class="mock-screen">
          <div class="mock-video">
            <div class="mock-badge">
              <div class="l1">1920 × 1080</div>
              <div class="l2">16:9 &middot; 1080p</div>
              <div class="l3">Integer scaling</div>
            </div>
          </div>
        </div>
      </div>
    </a>
  </section>
</main>

<footer class="fade-in d2">
  <div class="container footer-inner">
    <span>&copy; <span id="year"></span> Michael Koopman &middot; <a href="mailto:ronfar623@gmail.com">ronfar623@gmail.com</a></span>
    <span><a href="https://github.com/ronfar623" target="_blank" rel="noopener">github.com/ronfar623</a></span>
  </div>
</footer>

<script>
  document.getElementById('year').textContent = new Date().getFullYear();
</script>

</body>

