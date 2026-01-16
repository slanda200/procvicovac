---
layout: default
title: Čeština – výběr třídy
---

<div class="page">
  <div class="navbar">
    <a href="/" class="logo">Procvičovač</a>
    <div class="nav-right">
      <button id="mode-toggle" class="mode-btn" title="Přepnout světlý / tmavý režim">🌞</button>
      <a href="#" class="profile-btn">Přihlásit se / Profil</a>
    </div>
  </div>

  <main class="container">
    <div class="card">
      <h1>Čeština</h1>
      <p class="instruction">Vyber třídu a pokračuj na procvičování.</p>

      <div class="grade-grid">
        <a href="/cestina/1.trida/" class="grade-card">
          <span class="grade-title">1. třída</span>
          <span class="grade-desc">základy, slabiky, první cvičení</span>
        </a>

        <a href="/cestina/2.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">2. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/3.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">3. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/4.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">4. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/5.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">5. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/6.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">6. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/7.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">7. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/8.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">8. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/9.trida/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">9. třída</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
        <a href="/cestina/stredni-skola/" class="grade-card disabled" aria-disabled="true">
          <span class="grade-title">Střední škola</span>
          <span class="grade-desc">brzy přidám</span>
        </a>
      </div>
    </div>
  </main>
</div>

<style>
  /* schovat minima header */
  .site-header,
  .header,
  .post-header,
  .page-header,
  header[role="banner"],
  #site-header,
  nav[role="navigation"],
  .banner,
  .masthead,
  .site-title {
    display: none !important;
  }

  :root {
    --bg: #f8fafc;
    --card: #ffffff;
    --primary: #2563eb;
    --muted: #64748b;
    --line: #e5e7eb;
    --shadow: 0 12px 28px rgba(15, 23, 42, 0.08);
  }

  body.dark {
    --bg: #0f172a;
    --card: #111827;
    --primary: #60a5fa;
    --muted: #cbd5f5;
    --line: #1f2937;
    --shadow: 0 12px 28px rgba(15, 23, 42, 0.35);
    color: #e2e8f0;
  }

  body {
    margin: 0;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
    background: var(--bg);
    color: #0f172a;
  }

  .page { min-height: 100vh; }

  .navbar {
    background: var(--card);
    border-bottom: 1px solid var(--line);
    padding: 0.8rem 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    top: 0;
    z-index: 10;
  }

  .logo {
    font-weight: 700;
    font-size: 1.2rem;
    color: var(--primary);
    text-decoration: none;
  }

  .nav-right {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .profile-btn {
    text-decoration: none;
    color: var(--muted);
    font-weight: 600;
  }

  .mode-btn {
    border: none;
    background: transparent;
    font-size: 1.5rem;
    cursor: pointer;
  }

  .container {
    max-width: 1000px;
    margin: 2.5rem auto;
    padding: 0 1.5rem;
  }

  .card {
    background: var(--card);
    padding: 2.5rem;
    border-radius: 18px;
    box-shadow: var(--shadow);
  }

  .instruction {
    color: var(--muted);
    margin-bottom: 2rem;
    font-size: 1.05rem;
  }

  .grade-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
  }

  .grade-card {
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 1.2rem 1.4rem;
    text-decoration: none;
    color: inherit;
    display: flex;
    flex-direction: column;
    gap: 0.35rem;
    background: rgba(148, 163, 184, 0.08);
    transition: transform 0.2s ease, border-color 0.2s ease;
  }

  .grade-card:hover {
    transform: translateY(-3px);
    border-color: var(--primary);
  }

  .grade-title { font-weight: 750; font-size: 1.05rem; }
  .grade-desc { color: var(--muted); font-size: 0.95rem; }

  /* „brzy přidám“ – link vizuálně vypne */
  .grade-card.disabled {
    opacity: 0.6;
    cursor: not-allowed;
    pointer-events: none;
  }
</style>

<script>
  const toggle = document.getElementById('mode-toggle');
  if (toggle) {
    const preferDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
    const saved = localStorage.getItem('mode');
    const isDark = saved ? saved === 'dark' : preferDark;
    document.body.classList.toggle('dark', isDark);
    toggle.textContent = isDark ? '🌙' : '🌞';

    toggle.addEventListener('click', () => {
      const nowDark = document.body.classList.toggle('dark');
      toggle.textContent = nowDark ? '🌙' : '🌞';
      localStorage.setItem('mode', nowDark ? 'dark' : 'light');
    });
  }
</script>
