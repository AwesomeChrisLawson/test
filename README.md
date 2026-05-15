<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Pistopher Lawbum — Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet"/>
  <style>
    .my-5 {
    margin-top: 0 !important;
}
 .markdown-body h1 {
    display: none;
}
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
    :root {
      --ink: #0f0e0b;
      --cream: #f5f0e8;
      --accent: #c8432b;
      --muted: #8a8070;
      --rule: #d6cfc2;
    }
 
    html { scroll-behavior: smooth; }
 
    body {
      background: var(--cream);
      color: var(--ink);
      font-family: 'DM Mono', monospace;
      font-size: 14px;
      line-height: 1.6;
      overflow-x: hidden;
    }
 
    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 999;
    }
 
    /* ── HEADER ── */
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 2rem 4rem;
      border-bottom: 1px solid var(--rule);
      position: sticky;
      top: 0;
      background: var(--cream);
      z-index: 100;
      animation: fadeDown 0.6s ease both;
    }
 
    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      letter-spacing: 0.02em;
    }
    .logo span { color: var(--accent); font-style: italic; }
 
    nav { display: flex; gap: 2.5rem; }
    nav a {
      text-decoration: none;
      color: var(--muted);
      font-size: 0.75rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      transition: color 0.2s;
    }
    nav a:hover { color: var(--accent); }
 
    /* ── HERO ── */
    .hero {
      min-height: 88vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      border-bottom: 1px solid var(--rule);
    }
 
    .hero-left {
      padding: 6rem 4rem;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      border-right: 1px solid var(--rule);
      animation: fadeUp 0.8s 0.2s ease both;
    }
 
    .hero-eyebrow {
      font-size: 0.7rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 1.5rem;
    }
    .hero-eyebrow::before {
      content: '— ';
      color: var(--accent);
    }
 
    h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.5rem, 6vw, 6rem);
      line-height: 1.05;
      font-weight: 700;
      margin-bottom: 2rem;
    }
    h1 em {
      font-style: italic;
      color: var(--accent);
    }
 
    .hero-desc {
      max-width: 36ch;
      color: var(--muted);
      line-height: 1.8;
      margin-bottom: 3rem;
    }
 
    .btn-group { display: flex; gap: 1rem; flex-wrap: wrap; }
 
    .btn {
      display: inline-block;
      padding: 0.75rem 1.75rem;
      font-family: 'DM Mono', monospace;
      font-size: 0.72rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      text-decoration: none;
      border: 1px solid var(--ink);
      color: var(--ink);
      transition: background 0.2s, color 0.2s;
    }
    .btn:hover { background: var(--ink); color: var(--cream); }
    .btn.solid { background: var(--accent); border-color: var(--accent); color: var(--cream); }
    .btn.solid:hover { background: var(--ink); border-color: var(--ink); }
 
    .hero-right {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 4rem;
      position: relative;
      overflow: hidden;
      animation: fadeUp 0.8s 0.4s ease both;
    }
 
    /* Decorative abstract shape */
    .hero-right::before {
      content: '';
      position: absolute;
      width: 340px;
      height: 340px;
      border-radius: 60% 40% 70% 30% / 40% 60% 30% 70%;
      background: linear-gradient(135deg, #e8c8a0 0%, #d4a87a 50%, #c8432b22 100%);
      animation: morph 8s ease-in-out infinite;
    }
 
    .hero-initials {
      position: relative;
      font-family: 'Playfair Display', serif;
      font-size: 9rem;
      font-weight: 700;
      color: var(--cream);
      mix-blend-mode: overlay;
      user-select: none;
      letter-spacing: -0.04em;
    }
 
    .scroll-hint {
      position: absolute;
      bottom: 2rem;
      left: 50%;
      transform: translateX(-50%);
      font-size: 0.65rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.5rem;
      animation: fadeUp 1s 1s ease both;
    }
    .scroll-hint::after {
      content: '';
      width: 1px;
      height: 40px;
      background: var(--muted);
      animation: scrollLine 1.8s ease-in-out infinite;
    }
 
    /* ── MARQUEE ── */
    .marquee-wrap {
      overflow: hidden;
      border-bottom: 1px solid var(--rule);
      padding: 1rem 0;
      background: var(--ink);
      color: var(--cream);
    }
    .marquee-track {
      display: flex;
      gap: 3rem;
      animation: marquee 22s linear infinite;
      white-space: nowrap;
    }
    .marquee-track span {
      font-size: 0.7rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      flex-shrink: 0;
    }
    .marquee-track span.dot { color: var(--accent); font-size: 1rem; line-height: 1; }
 
    /* ── WORK ── */
    #work { padding: 6rem 4rem; }
 
    .section-label {
      font-size: 0.65rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 3rem;
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--rule);
    }
 
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0;
      border: 1px solid var(--rule);
    }
 
    .project-card {
      border-right: 1px solid var(--rule);
      border-bottom: 1px solid var(--rule);
      padding: 2.5rem 2rem;
      position: relative;
      overflow: hidden;
      cursor: pointer;
      transition: background 0.3s;
    }
    .project-card:nth-child(3n) { border-right: none; }
    .project-card:nth-last-child(-n+3) { border-bottom: none; }
    .project-card:hover { background: var(--ink); color: var(--cream); }
    .project-card:hover .project-tag { color: var(--accent); }
    .project-card:hover .project-num { color: rgba(255,255,255,0.1); }
    .project-card:hover .project-arrow { opacity: 1; transform: translate(0,0); }
 
    .project-num {
      font-family: 'Playfair Display', serif;
      font-size: 3.5rem;
      font-weight: 700;
      color: var(--rule);
      line-height: 1;
      margin-bottom: 1.5rem;
      transition: color 0.3s;
    }
 
    .project-tag {
      font-size: 0.65rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 0.75rem;
      transition: color 0.3s;
    }
 
    .project-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      line-height: 1.25;
      margin-bottom: 0.75rem;
    }
 
    .project-desc {
      font-size: 0.78rem;
      color: var(--muted);
      line-height: 1.7;
    }
    .project-card:hover .project-desc { color: rgba(255,255,255,0.6); }
 
    .project-arrow {
      position: absolute;
      bottom: 1.5rem;
      right: 1.5rem;
      font-size: 1.2rem;
      opacity: 0;
      transform: translate(-6px, 6px);
      transition: opacity 0.3s, transform 0.3s;
    }
 
    /* ── ABOUT ── */
    #about {
      display: grid;
      grid-template-columns: 1fr 1fr;
      border-top: 1px solid var(--rule);
    }
 
    .about-left {
      padding: 6rem 4rem;
      border-right: 1px solid var(--rule);
    }
 
    .about-left h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 3.5vw, 3.2rem);
      line-height: 1.2;
      margin-bottom: 2rem;
    }
    .about-left h2 em { font-style: italic; color: var(--accent); }
 
    .about-left p {
      color: var(--muted);
      line-height: 1.85;
      max-width: 42ch;
      margin-bottom: 1.25rem;
    }
 
    .skills-list {
      margin-top: 2.5rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }
    .skill-tag {
      padding: 0.35rem 0.85rem;
      border: 1px solid var(--rule);
      font-size: 0.68rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
    }
 
    .about-right {
      padding: 6rem 4rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
 
    .stat-block {
      padding: 2rem 0;
      border-bottom: 1px solid var(--rule);
    }
    .stat-block:last-child { border-bottom: none; }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 3rem;
      line-height: 1;
      color: var(--ink);
    }
    .stat-num span { color: var(--accent); }
    .stat-label {
      font-size: 0.7rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--muted);
      margin-top: 0.25rem;
    }
 
    /* ── CONTACT ── */
    #contact {
      background: var(--ink);
      color: var(--cream);
      padding: 6rem 4rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      border-top: 1px solid var(--rule);
    }
 
    .contact-left h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.5rem, 4vw, 4rem);
      line-height: 1.1;
      margin-bottom: 1.5rem;
    }
    .contact-left h2 em { font-style: italic; color: var(--accent); }
 
    .contact-left p {
      color: rgba(245,240,232,0.5);
      line-height: 1.8;
      max-width: 40ch;
    }
 
    .contact-right {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
      justify-content: center;
    }
 
    .contact-link {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.5rem 0;
      border-bottom: 1px solid rgba(245,240,232,0.1);
      text-decoration: none;
      color: var(--cream);
      transition: color 0.2s;
    }
    .contact-link:hover { color: var(--accent); }
    .contact-link-label {
      font-size: 0.65rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: rgba(245,240,232,0.4);
      margin-bottom: 0.25rem;
    }
    .contact-link-value {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
    }
    .contact-link-arrow { font-size: 1.2rem; }
 
    /* ── FOOTER ── */
    footer {
      background: var(--ink);
      color: rgba(245,240,232,0.3);
      border-top: 1px solid rgba(245,240,232,0.08);
      padding: 1.5rem 4rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.65rem;
      letter-spacing: 0.1em;
    }
 
    /* ── ANIMATIONS ── */
    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-12px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes marquee {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }
    @keyframes morph {
      0%, 100% { border-radius: 60% 40% 70% 30% / 40% 60% 30% 70%; }
      33%  { border-radius: 30% 70% 40% 60% / 60% 30% 70% 40%; }
      66%  { border-radius: 50% 50% 60% 40% / 30% 70% 50% 50%; }
    }
    @keyframes scrollLine {
      0%   { transform: scaleY(0); transform-origin: top; }
      50%  { transform: scaleY(1); transform-origin: top; }
      50.1%{ transform: scaleY(1); transform-origin: bottom; }
      100% { transform: scaleY(0); transform-origin: bottom; }
    }
 
    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      header { padding: 1.5rem 2rem; }
      nav { gap: 1.5rem; }
      .hero { grid-template-columns: 1fr; }
      .hero-left { padding: 4rem 2rem 3rem; }
      .hero-right { min-height: 280px; padding: 2rem; }
      #work { padding: 4rem 2rem; }
      .projects-grid { grid-template-columns: 1fr; }
      .project-card { border-right: none !important; }
      #about { grid-template-columns: 1fr; }
      .about-left { padding: 4rem 2rem; border-right: none; border-bottom: 1px solid var(--rule); }
      .about-right { padding: 4rem 2rem; }
      #contact { grid-template-columns: 1fr; padding: 4rem 2rem; }
      footer { padding: 1.5rem 2rem; flex-direction: column; gap: 0.5rem; text-align: center; }
    }
  </style>
</head>
<body>
 
  <!-- HEADER -->
  <header>
    <div class="logo"><span>P.</span> Lawbum</div>
    <nav>
      <a href="#work">Work</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>
 
  <!-- HERO -->
  <section class="hero">
    <div class="hero-left">
      <p class="hero-eyebrow">Creative Developer &amp; Designer</p>
      <h1>Pistopher<br/><em>Lawbum</em></h1>
      <p class="hero-desc">
        Crafting digital experiences that live somewhere between art and engineering.
        I build things that look beautiful, move thoughtfully, and work reliably.
      </p>
      <div class="btn-group">
        <a href="#work" class="btn solid">View My Work</a>
        <a href="#contact" class="btn">Get in Touch</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-initials">PL</div>
      <div class="scroll-hint">Scroll</div>
    </div>
  </section>
 
  <!-- MARQUEE -->
  <div class="marquee-wrap" aria-hidden="true">
    <div class="marquee-track">
      <span>Web Design</span><span class="dot">✦</span>
      <span>UI / UX</span><span class="dot">✦</span>
      <span>Creative Development</span><span class="dot">✦</span>
      <span>Brand Identity</span><span class="dot">✦</span>
      <span>Motion Design</span><span class="dot">✦</span>
      <span>Frontend Engineering</span><span class="dot">✦</span>
      <span>Web Design</span><span class="dot">✦</span>
      <span>UI / UX</span><span class="dot">✦</span>
      <span>Creative Development</span><span class="dot">✦</span>
      <span>Brand Identity</span><span class="dot">✦</span>
      <span>Motion Design</span><span class="dot">✦</span>
      <span>Frontend Engineering</span><span class="dot">✦</span>
    </div>
  </div>
 
  <!-- WORK -->
  <section id="work">
    <div class="section-label">Selected Projects</div>
    <div class="projects-grid">
 
      <div class="project-card">
        <div class="project-num">01</div>
        <div class="project-tag">Brand Identity</div>
        <div class="project-title">The Meridian<br/>Collective</div>
        <p class="project-desc">Full visual identity and design system for a contemporary arts organisation.</p>
        <div class="project-arrow">→</div>
      </div>
 
      <div class="project-card">
        <div class="project-num">02</div>
        <div class="project-tag">Web Experience</div>
        <div class="project-title">Volta Studio<br/>Website</div>
        <p class="project-desc">Immersive editorial website with custom scroll-based animations and typography.</p>
        <div class="project-arrow">→</div>
      </div>
 
      <div class="project-card">
        <div class="project-num">03</div>
        <div class="project-tag">App Design</div>
        <div class="project-title">Arbor Finance<br/>Dashboard</div>
        <p class="project-desc">Clean, data-dense interface redesign for a fintech startup's core product.</p>
        <div class="project-arrow">→</div>
      </div>
 
      <div class="project-card">
        <div class="project-num">04</div>
        <div class="project-tag">E-Commerce</div>
        <div class="project-title">Lune Ceramics<br/>Shop</div>
        <p class="project-desc">Bespoke Shopify build for an independent ceramics studio with a strong editorial voice.</p>
        <div class="project-arrow">→</div>
      </div>
 
      <div class="project-card">
        <div class="project-num">05</div>
        <div class="project-tag">Motion</div>
        <div class="project-title">Kinetic Type<br/>Experiments</div>
        <p class="project-desc">A personal series exploring typography in motion — CSS, WebGL, and SVG.</p>
        <div class="project-arrow">→</div>
      </div>
 
      <div class="project-card">
        <div class="project-num">06</div>
        <div class="project-tag">Development</div>
        <div class="project-title">Open Source<br/>Component Kit</div>
        <p class="project-desc">A library of accessible, unstyled UI primitives for modern web projects.</p>
        <div class="project-arrow">→</div>
      </div>
 
    </div>
  </section>
 
  <!-- ABOUT -->
  <section id="about">
    <div class="about-left">
      <div class="section-label">About Me</div>
      <h2>Design that<br/>earns its <em>space.</em></h2>
      <p>
        I'm Pistopher Lawbum — a designer and developer with a stubborn belief
        that good work requires both a sharp eye and clean code.
      </p>
      <p>
        With a background spanning agencies, startups, and independent practice,
        I bring a craft-first approach to every project — from initial concept
        through to final deployment.
      </p>
      <p>
        When I'm not at a screen, I'm likely hunting for interesting typefaces,
        wandering around galleries, or overcooking risotto.
      </p>
      <div class="skills-list">
        <span class="skill-tag">Figma</span>
        <span class="skill-tag">HTML / CSS</span>
        <span class="skill-tag">JavaScript</span>
        <span class="skill-tag">React</span>
        <span class="skill-tag">GSAP</span>
        <span class="skill-tag">Webflow</span>
        <span class="skill-tag">Shopify</span>
        <span class="skill-tag">Three.js</span>
        <span class="skill-tag">Motion Design</span>
      </div>
    </div>
    <div class="about-right">
      <div class="stat-block">
        <div class="stat-num">08<span>+</span></div>
        <div class="stat-label">Years of Experience</div>
      </div>
      <div class="stat-block">
        <div class="stat-num">60<span>+</span></div>
        <div class="stat-label">Projects Shipped</div>
      </div>
      <div class="stat-block">
        <div class="stat-num">24<span>+</span></div>
        <div class="stat-label">Happy Clients</div>
      </div>
      <div class="stat-block">
        <div class="stat-num">03<span>×</span></div>
        <div class="stat-label">Award Wins</div>
      </div>
    </div>
  </section>
 
  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-left">
      <h2>Let's make<br/>something <em>good.</em></h2>
      <p>
        Have a project in mind or just want to talk design?
        I'm currently available for freelance work and select collaborations.
      </p>
    </div>
    <div class="contact-right">
      <a class="contact-link" href="mailto:hello@pistopherlawbum.com">
        <div>
          <div class="contact-link-label">Email</div>
          <div class="contact-link-value">hello@pistopherlawbum.com</div>
        </div>
        <div class="contact-link-arrow">↗</div>
      </a>
      <a class="contact-link" href="#">
        <div>
          <div class="contact-link-label">Twitter / X</div>
          <div class="contact-link-value">@pistopher</div>
        </div>
        <div class="contact-link-arrow">↗</div>
      </a>
      <a class="contact-link" href="#">
        <div>
          <div class="contact-link-label">LinkedIn</div>
          <div class="contact-link-value">Pistopher Lawbum</div>
        </div>
        <div class="contact-link-arrow">↗</div>
      </a>
      <a class="contact-link" href="#">
        <div>
          <div class="contact-link-label">GitHub</div>
          <div class="contact-link-value">pistopherlawbum</div>
        </div>
        <div class="contact-link-arrow">↗</div>
      </a>
    </div>
  </section>
 
  <!-- FOOTER -->
  <footer>
    <span>© 2026 Pistopher Lawbum. All rights reserved.</span>
    <span>Designed &amp; built with care.</span>
  </footer>
 
</body>
</html>
