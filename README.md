<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tu Nombre — Portfolio</title>
  <meta name="description" content="Desarrollador full-stack. Construyo productos digitales limpios y escalables." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #ffffff;
      --bg-secondary: #f5f5f3;
      --text: #1a1a18;
      --text-secondary: #6b6b66;
      --text-tertiary: #a8a8a3;
      --border: rgba(0,0,0,0.10);
      --border-mid: rgba(0,0,0,0.18);
      --green-light: #E1F5EE;
      --green-mid: #9FE1CB;
      --green: #1D9E75;
      --green-dark: #0F6E56;
      --green-darker: #085041;
      --blue-light: #E6F1FB;
      --blue-mid: #B5D4F4;
      --blue: #185FA5;
      --purple-light: #EEEDFE;
      --purple-mid: #CECBF6;
      --purple: #3C3489;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --bg: #1a1a18;
        --bg-secondary: #242422;
        --text: #f0efeb;
        --text-secondary: #a8a8a3;
        --text-tertiary: #6b6b66;
        --border: rgba(255,255,255,0.10);
        --border-mid: rgba(255,255,255,0.18);
        --green-light: #04342C;
        --green-mid: #085041;
        --green: #5DCAA5;
        --green-dark: #9FE1CB;
        --green-darker: #E1F5EE;
        --blue-light: #042C53;
        --blue-mid: #0C447C;
        --blue: #85B7EB;
        --purple-light: #26215C;
        --purple-mid: #3C3489;
        --purple: #AFA9EC;
      }
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 0 1.25rem;
    }

    main {
      max-width: 680px;
      width: 100%;
      padding: 4rem 0 6rem;
    }

    /* Badge */
    .badge {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      background: var(--bg-secondary);
      border: 0.5px solid var(--border-mid);
      border-radius: 100px;
      padding: 5px 14px;
      font-size: 12px;
      font-family: 'Space Mono', monospace;
      color: var(--text-secondary);
      letter-spacing: 0.03em;
      margin-bottom: 1.5rem;
    }

    .badge-dot {
      width: 7px; height: 7px;
      border-radius: 50%;
      background: var(--green);
      animation: pulse 2.2s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.45; transform: scale(0.85); }
    }

    /* Hero */
    h1 {
      font-family: 'Space Mono', monospace;
      font-size: clamp(28px, 6vw, 40px);
      font-weight: 700;
      line-height: 1.15;
      letter-spacing: -0.02em;
      margin-bottom: 0.75rem;
    }

    h1 span { color: var(--green); }

    .tagline {
      font-size: 16px;
      color: var(--text-secondary);
      font-weight: 300;
      margin-bottom: 2.5rem;
      line-height: 1.65;
      max-width: 520px;
    }

    /* Stats */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      margin-bottom: 2.5rem;
    }

    .stat-card {
      background: var(--bg-secondary);
      border-radius: 8px;
      padding: 1rem;
      text-align: center;
    }

    .stat-num {
      font-family: 'Space Mono', monospace;
      font-size: 24px;
      font-weight: 700;
      color: var(--text);
      display: block;
      line-height: 1;
      margin-bottom: 4px;
    }

    .stat-label {
      font-size: 11px;
      color: var(--text-tertiary);
      display: block;
    }

    /* Divider */
    .divider {
      height: 0.5px;
      background: var(--border);
      margin: 2.25rem 0;
    }

    /* Section label */
    .section-label {
      font-family: 'Space Mono', monospace;
      font-size: 10px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--text-tertiary);
      margin-bottom: 1rem;
    }

    /* Skills */
    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 2.5rem;
    }

    .chip {
      font-family: 'Space Mono', monospace;
      font-size: 11px;
      padding: 5px 12px;
      border-radius: 4px;
      border: 0.5px solid var(--border);
      background: var(--bg);
      color: var(--text);
    }

    .chip.green { background: var(--green-light); border-color: var(--green-mid); color: var(--green-dark); }
    .chip.blue  { background: var(--blue-light);  border-color: var(--blue-mid);  color: var(--blue);  }
    .chip.purple{ background: var(--purple-light); border-color: var(--purple-mid); color: var(--purple); }

    /* Projects */
    .projects { display: grid; gap: 12px; margin-bottom: 2.5rem; }

    .project-card {
      background: var(--bg);
      border: 0.5px solid var(--border);
      border-radius: 12px;
      padding: 1.1rem 1.25rem;
      transition: border-color 0.15s;
      text-decoration: none;
      color: inherit;
      display: block;
    }

    .project-card:hover { border-color: var(--border-mid); }

    .project-top {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 6px;
    }

    .project-name {
      font-family: 'Space Mono', monospace;
      font-size: 14px;
      font-weight: 700;
      color: var(--text);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .project-icon { font-size: 15px; color: var(--text-tertiary); }

    .project-stars {
      font-family: 'Space Mono', monospace;
      font-size: 11px;
      color: var(--text-tertiary);
      display: flex;
      align-items: center;
      gap: 4px;
      white-space: nowrap;
    }

    .project-desc {
      font-size: 13px;
      color: var(--text-secondary);
      line-height: 1.55;
      margin-bottom: 10px;
    }

    .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }

    .tag {
      font-family: 'Space Mono', monospace;
      font-size: 10px;
      padding: 3px 8px;
      border-radius: 3px;
      background: var(--bg-secondary);
      color: var(--text-secondary);
      border: 0.5px solid var(--border);
      display: inline-flex;
      align-items: center;
      gap: 4px;
    }

    .lang-dot {
      width: 8px; height: 8px;
      border-radius: 50%;
      display: inline-block;
      flex-shrink: 0;
    }

    /* Availability */
    .availability {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 12px;
      font-family: 'Space Mono', monospace;
      color: var(--green-dark);
      padding: 7px 14px;
      border: 0.5px solid var(--green-mid);
      border-radius: 6px;
      background: var(--green-light);
      margin-bottom: 1.25rem;
    }

    /* Contact */
    .contact-row { display: flex; flex-wrap: wrap; gap: 10px; }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      font-family: 'Space Mono', monospace;
      font-size: 11px;
      padding: 8px 16px;
      border-radius: 6px;
      border: 0.5px solid var(--border-mid);
      background: var(--bg);
      color: var(--text);
      cursor: pointer;
      transition: background 0.12s, border-color 0.12s;
      text-decoration: none;
    }

    .btn:hover { background: var(--bg-secondary); border-color: var(--border-mid); }

    .btn.primary {
      background: var(--green-dark);
      border-color: var(--green-dark);
      color: #fff;
    }

    .btn.primary:hover { background: var(--green-darker); border-color: var(--green-darker); }

    /* SVG Icons inline fallback */
    .icon-svg { width: 14px; height: 14px; fill: none; stroke: currentColor; stroke-width: 1.8; stroke-linecap: round; stroke-linejoin: round; vertical-align: middle; }

    @media (max-width: 480px) {
      .stats-row { grid-template-columns: repeat(3, 1fr); }
      h1 { font-size: 26px; }
    }
  </style>
</head>
<body>
<main>

  <div class="badge">
    <span class="badge-dot"></span>
    Disponible para proyectos
  </div>

  <h1>Hola, soy<br><span>Tu Nombre</span></h1>
  <p class="tagline">Desarrollador full-stack enfocado en construir productos digitales limpios, escalables y con gran experiencia de usuario.</p>

  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-num">3+</span>
      <span class="stat-label">años experiencia</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">12</span>
      <span class="stat-label">repos públicos</span>
    </div>
    <div class="stat-card">
      <span class="stat-num">5</span>
      <span class="stat-label">tecnologías core</span>
    </div>
  </div>

  <div class="divider"></div>

  <div class="section-label">Stack técnico</div>
  <div class="skills-grid">
    <span class="chip green">React</span>
    <span class="chip green">Node.js</span>
    <span class="chip blue">TypeScript</span>
    <span class="chip blue">PostgreSQL</span>
    <span class="chip purple">Python</span>
    <span class="chip purple">Docker</span>
    <span class="chip">REST APIs</span>
    <span class="chip">Git / GitHub</span>
    <span class="chip">Tailwind CSS</span>
    <span class="chip">CI / CD</span>
  </div>

  <div class="section-label">Proyectos destacados</div>
  <div class="projects">

    <a class="project-card" href="https://github.com/tuusuario/nombre-proyecto" target="_blank" rel="noopener">
      <div class="project-top">
        <div class="project-name">
          <!-- Sustituye el SVG por el icono que prefieras -->
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
          nombre-del-proyecto
        </div>
        <div class="project-stars">
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          48
        </div>
      </div>
      <p class="project-desc">Descripción concisa del proyecto: qué problema resuelve, para quién y cuál es su valor principal. Dos líneas máximo para mantenerlo legible.</p>
      <div class="project-tags">
        <span class="tag"><span class="lang-dot" style="background:#3178c6"></span>TypeScript</span>
        <span class="tag"><span class="lang-dot" style="background:#61dafb"></span>React</span>
        <span class="tag">API REST</span>
      </div>
    </a>

    <a class="project-card" href="https://github.com/tuusuario/backend-api" target="_blank" rel="noopener">
      <div class="project-top">
        <div class="project-name">
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
          backend-api-example
        </div>
        <div class="project-stars">
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          22
        </div>
      </div>
      <p class="project-desc">API RESTful con autenticación JWT, manejo de errores robusto y documentación automática con Swagger. Preparada para escalar horizontalmente con Docker.</p>
      <div class="project-tags">
        <span class="tag"><span class="lang-dot" style="background:#68a063"></span>Node.js</span>
        <span class="tag">PostgreSQL</span>
        <span class="tag">Docker</span>
        <span class="tag">Swagger</span>
      </div>
    </a>

    <a class="project-card" href="https://github.com/tuusuario/data-dashboard" target="_blank" rel="noopener">
      <div class="project-top">
        <div class="project-name">
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>
          data-dashboard
        </div>
        <div class="project-stars">
          <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          15
        </div>
      </div>
      <p class="project-desc">Dashboard interactivo para visualizar métricas en tiempo real con filtros dinámicos, gráficos personalizables y exportación a CSV/Excel.</p>
      <div class="project-tags">
        <span class="tag"><span class="lang-dot" style="background:#3572A5"></span>Python</span>
        <span class="tag">Pandas</span>
        <span class="tag">Chart.js</span>
      </div>
    </a>

  </div>

  <div class="divider"></div>

  <div class="section-label">Contacto</div>

  <div class="availability">
    <span class="badge-dot"></span>
    Disponible para trabajo freelance o tiempo completo
  </div>

  <div class="contact-row">
    <a class="btn primary" href="mailto:tu@email.com">
      <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      tu@email.com
    </a>
    <a class="btn" href="https://linkedin.com/in/tuperfil" target="_blank" rel="noopener">
      <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a class="btn" href="https://github.com/tuusuario" target="_blank" rel="noopener">
      <svg class="icon-svg" aria-hidden="true" viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
      GitHub
    </a>
  </div>

</main>
</body>
</html>
