<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Coffee Embassy – 珈琲大使館 虎ノ門店</title>
  <meta name="description" content="Coffee Embassy 珈琲大使館 虎ノ門店 — Where every cup represents craftsmanship and tradition. Located in Toranomon, Minato City, Tokyo." />
  <meta name="keywords" content="coffee, café, Tokyo, Toranomon, Japanese coffee, espresso, matcha latte" />
  <meta property="og:title" content="Coffee Embassy – 珈琲大使館 虎ノ門店" />
  <meta property="og:description" content="Where every cup represents craftsmanship and tradition." />
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>☕</text></svg>" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #f5f0e8;
      --parchment: #ede5d0;
      --latte: #c9a87c;
      --espresso: #6b3f1e;
      --dark-roast: #2c1a0e;
      --soft-black: #1a1008;
      --text-body: #4a3728;
      --text-muted: #8a7060;
      --white: #fdfaf5;
      --shadow: rgba(44, 26, 14, 0.12);
      --shadow-deep: rgba(44, 26, 14, 0.22);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Jost', sans-serif;
      font-weight: 300;
      background: var(--cream);
      color: var(--text-body);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.2rem 5%;
      background: rgba(245, 240, 232, 0.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(107, 63, 30, 0.1);
      transition: box-shadow 0.3s;
    }
    nav.scrolled { box-shadow: 0 2px 20px var(--shadow); }

    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.35rem;
      font-weight: 500;
      color: var(--espresso);
      text-decoration: none;
      letter-spacing: 0.04em;
      line-height: 1.2;
    }
    .nav-logo span { display: block; font-size: 0.65rem; font-weight: 300; color: var(--text-muted); letter-spacing: 0.12em; font-family: 'Jost', sans-serif; }

    .nav-links { display: flex; gap: 2.5rem; list-style: none; }
    .nav-links a {
      text-decoration: none; color: var(--text-body); font-size: 0.82rem;
      letter-spacing: 0.12em; text-transform: uppercase; font-weight: 400;
      position: relative; padding-bottom: 2px;
      transition: color 0.3s;
    }
    .nav-links a::after {
      content: ''; position: absolute; bottom: 0; left: 0; width: 0; height: 1px;
      background: var(--espresso); transition: width 0.3s;
    }
    .nav-links a:hover { color: var(--espresso); }
    .nav-links a:hover::after { width: 100%; }

    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
    .hamburger span { width: 24px; height: 1.5px; background: var(--espresso); transition: all 0.3s; display: block; }
    .hamburger.open span:nth-child(1) { transform: translateY(6.5px) rotate(45deg); }
    .hamburger.open span:nth-child(2) { opacity: 0; }
    .hamburger.open span:nth-child(3) { transform: translateY(-6.5px) rotate(-45deg); }

    .mobile-menu {
      display: none; position: fixed; top: 65px; left: 0; right: 0; z-index: 99;
      background: var(--cream); padding: 2rem 5%; border-bottom: 1px solid var(--parchment);
      flex-direction: column; gap: 1.5rem;
    }
    .mobile-menu.open { display: flex; }
    .mobile-menu a { text-decoration: none; color: var(--text-body); font-size: 1rem; letter-spacing: 0.1em; text-transform: uppercase; }

    /* ── HERO ── */
    #hero {
      min-height: 100vh; display: flex; align-items: center; justify-content: center;
      text-align: center; position: relative; overflow: hidden;
      background:
        linear-gradient(to bottom, rgba(26,16,8,0.55) 0%, rgba(44,26,14,0.45) 100%),
        url('https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=1800&q=80') center/cover no-repeat;
      padding: 0 5%;
    }

    .hero-content { position: relative; z-index: 2; animation: fadeUp 1.2s ease both; }
    .hero-eyebrow {
      display: inline-block; font-size: 0.72rem; letter-spacing: 0.3em; text-transform: uppercase;
      color: var(--latte); font-weight: 400; margin-bottom: 1.5rem;
      border: 1px solid rgba(201,168,124,0.4); padding: 0.4rem 1.2rem; border-radius: 2px;
    }
    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.8rem, 7vw, 5.5rem);
      font-weight: 300; color: var(--white);
      line-height: 1.1; letter-spacing: -0.01em;
      margin-bottom: 0.6rem;
    }
    .hero-jp {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1rem, 2.5vw, 1.4rem);
      color: var(--latte); font-weight: 300; letter-spacing: 0.15em;
      margin-bottom: 1.4rem;
    }
    .hero-tagline {
      font-size: clamp(0.85rem, 1.8vw, 1rem);
      color: rgba(253,250,245,0.7); font-weight: 300;
      letter-spacing: 0.05em; max-width: 480px; margin: 0 auto 2.8rem;
      line-height: 1.7;
    }
    .hero-cta { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
    .btn-primary, .btn-outline {
      padding: 0.85rem 2.2rem; border-radius: 2px; font-size: 0.78rem;
      letter-spacing: 0.18em; text-transform: uppercase; font-family: 'Jost', sans-serif;
      font-weight: 400; cursor: pointer; text-decoration: none; transition: all 0.3s;
      display: inline-block;
    }
    .btn-primary { background: var(--latte); color: var(--soft-black); border: 1px solid var(--latte); }
    .btn-primary:hover { background: #b89460; border-color: #b89460; transform: translateY(-2px); box-shadow: 0 8px 24px rgba(201,168,124,0.3); }
    .btn-outline { background: transparent; color: var(--white); border: 1px solid rgba(253,250,245,0.5); }
    .btn-outline:hover { background: rgba(253,250,245,0.08); border-color: var(--white); transform: translateY(-2px); }

    .scroll-hint {
      position: absolute; bottom: 2.5rem; left: 50%; transform: translateX(-50%);
      display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
      color: rgba(253,250,245,0.5); font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase;
      animation: bounce 2s infinite;
    }
    .scroll-hint::after { content: ''; width: 1px; height: 32px; background: rgba(253,250,245,0.3); }

    /* ── SECTION COMMONS ── */
    section { padding: 6rem 5%; }
    .section-label {
      font-size: 0.68rem; letter-spacing: 0.3em; text-transform: uppercase;
      color: var(--latte); font-weight: 400; margin-bottom: 0.8rem; display: block;
    }
    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 400; color: var(--dark-roast);
      line-height: 1.15; margin-bottom: 1.5rem;
    }
    .section-divider {
      width: 48px; height: 1px; background: var(--latte); margin-bottom: 1.8rem;
    }

    /* ── ABOUT ── */
    #about { background: var(--white); }
    .about-inner {
      max-width: 1100px; margin: 0 auto;
      display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center;
    }
    .about-img {
      position: relative; border-radius: 3px; overflow: hidden;
      aspect-ratio: 4/5; box-shadow: 0 20px 60px var(--shadow-deep);
    }
    .about-img img { width: 100%; height: 100%; object-fit: cover; display: block; transition: transform 0.6s ease; }
    .about-img:hover img { transform: scale(1.03); }
    .about-img::before {
      content: ''; position: absolute; top: -12px; left: -12px; right: 12px; bottom: 12px;
      border: 1px solid var(--latte); border-radius: 3px; z-index: -1; opacity: 0.4;
    }
    .about-text p {
      font-size: 0.95rem; line-height: 1.9; color: var(--text-body);
      margin-bottom: 1rem; font-weight: 300;
    }
    .about-icons { display: flex; gap: 1.5rem; margin-top: 2rem; }
    .about-icon {
      display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
      font-size: 0.68rem; letter-spacing: 0.12em; text-transform: uppercase;
      color: var(--text-muted);
    }
    .about-icon .ico { font-size: 1.6rem; }

    /* ── MENU ── */
    #menu { background: var(--cream); }
    .menu-inner { max-width: 1100px; margin: 0 auto; }
    .menu-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1.5rem; margin-top: 3rem;
    }
    .menu-card {
      background: var(--white); border-radius: 4px;
      overflow: hidden; box-shadow: 0 4px 20px var(--shadow);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: default;
    }
    .menu-card:hover { transform: translateY(-6px); box-shadow: 0 14px 40px var(--shadow-deep); }
    .menu-card-img { aspect-ratio: 4/3; overflow: hidden; }
    .menu-card-img img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.5s ease; display: block; }
    .menu-card:hover .menu-card-img img { transform: scale(1.06); }
    .menu-card-body { padding: 1.2rem 1.3rem 1.4rem; }
    .menu-card-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.15rem; font-weight: 500; color: var(--dark-roast);
      margin-bottom: 0.3rem;
    }
    .menu-card-desc { font-size: 0.78rem; color: var(--text-muted); line-height: 1.6; margin-bottom: 0.9rem; }
    .menu-card-price { font-size: 0.8rem; letter-spacing: 0.1em; color: var(--latte); font-weight: 500; }

    /* ── HOURS ── */
    #hours { background: var(--dark-roast); }
    .hours-inner { max-width: 640px; margin: 0 auto; text-align: center; }
    #hours .section-title { color: var(--white); }
    #hours .section-label { color: var(--latte); }
    #hours .section-divider { margin: 0 auto 2rem; }
    .hours-status {
      display: inline-flex; align-items: center; gap: 0.5rem;
      background: rgba(74,175,74,0.15); border: 1px solid rgba(74,175,74,0.4);
      color: #7ec87e; padding: 0.4rem 1rem; border-radius: 20px;
      font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
      margin-bottom: 2.5rem;
    }
    .hours-status::before { content: ''; width: 7px; height: 7px; border-radius: 50%; background: #7ec87e; animation: pulse 2s infinite; }
    .hours-table { width: 100%; border-collapse: collapse; }
    .hours-table tr { border-bottom: 1px solid rgba(253,250,245,0.06); }
    .hours-table tr:last-child { border-bottom: none; }
    .hours-table td { padding: 0.85rem 0.5rem; font-size: 0.85rem; font-weight: 300; }
    .hours-table td:first-child { color: rgba(253,250,245,0.55); text-align: left; letter-spacing: 0.06em; }
    .hours-table td:last-child { color: var(--white); text-align: right; }
    .hours-table tr.closed td { color: rgba(253,250,245,0.3); }
    .hours-table tr.closed td:last-child { color: rgba(253,250,245,0.3); }

    /* ── LOCATION ── */
    #location { background: var(--white); }
    .location-inner { max-width: 1100px; margin: 0 auto; display: grid; grid-template-columns: 1.4fr 1fr; gap: 4rem; align-items: start; }
    .map-embed {
      border-radius: 4px; overflow: hidden;
      box-shadow: 0 10px 40px var(--shadow-deep);
      aspect-ratio: 4/3;
    }
    .map-embed iframe { width: 100%; height: 100%; border: 0; display: block; }
    .location-info { padding-top: 1rem; }
    .location-detail { display: flex; gap: 1rem; align-items: flex-start; margin-bottom: 1.5rem; }
    .location-icon { font-size: 1.1rem; margin-top: 0.1rem; flex-shrink: 0; }
    .location-detail-text { font-size: 0.88rem; line-height: 1.7; color: var(--text-body); }
    .location-detail-text strong { display: block; font-size: 0.7rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--text-muted); font-weight: 400; margin-bottom: 0.2rem; }
    .location-detail-text a { color: var(--espresso); text-decoration: none; }
    .location-detail-text a:hover { text-decoration: underline; }

    /* ── REVIEWS ── */
    #reviews { background: var(--parchment); }
    .reviews-inner { max-width: 1100px; margin: 0 auto; }
    .rating-hero { display: flex; align-items: center; gap: 1.2rem; margin-bottom: 3rem; }
    .rating-big {
      font-family: 'Cormorant Garamond', serif;
      font-size: 4.5rem; font-weight: 300; color: var(--dark-roast); line-height: 1;
    }
    .rating-meta { display: flex; flex-direction: column; gap: 0.3rem; }
    .rating-stars { color: var(--latte); font-size: 1.1rem; letter-spacing: 0.05em; }
    .rating-count { font-size: 0.78rem; color: var(--text-muted); letter-spacing: 0.06em; }
    .reviews-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem; }
    .review-card {
      background: var(--white); border-radius: 4px; padding: 1.8rem 1.6rem;
      box-shadow: 0 4px 20px var(--shadow); transition: transform 0.3s, box-shadow 0.3s;
    }
    .review-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px var(--shadow-deep); }
    .review-quote { font-size: 2rem; color: var(--latte); line-height: 1; margin-bottom: 0.5rem; font-family: 'Cormorant Garamond', serif; }
    .review-text { font-size: 0.88rem; line-height: 1.75; color: var(--text-body); margin-bottom: 1.2rem; font-weight: 300; font-style: italic; }
    .review-author { font-size: 0.75rem; letter-spacing: 0.1em; color: var(--latte); text-transform: uppercase; font-weight: 400; }
    .review-stars { color: var(--latte); font-size: 0.75rem; margin-bottom: 0.6rem; }

    /* ── FOOTER ── */
    footer { background: var(--soft-black); padding: 4rem 5% 2rem; }
    .footer-inner { max-width: 1100px; margin: 0 auto; }
    .footer-top { display: grid; grid-template-columns: 1.5fr 1fr 1fr; gap: 3rem; padding-bottom: 3rem; border-bottom: 1px solid rgba(253,250,245,0.08); margin-bottom: 2rem; }
    .footer-logo {
      font-family: 'Cormorant Garamond', serif; font-size: 1.5rem;
      font-weight: 400; color: var(--white); letter-spacing: 0.06em;
    }
    .footer-logo-jp { font-size: 0.75rem; color: var(--text-muted); letter-spacing: 0.15em; margin-top: 0.3rem; margin-bottom: 1rem; font-family: 'Jost', sans-serif; }
    .footer-tagline { font-size: 0.82rem; color: var(--text-muted); line-height: 1.7; max-width: 260px; }
    .footer-col h4 { font-size: 0.68rem; letter-spacing: 0.22em; text-transform: uppercase; color: var(--latte); margin-bottom: 1.2rem; font-weight: 400; }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 0.7rem; }
    .footer-col ul a { text-decoration: none; color: rgba(253,250,245,0.55); font-size: 0.82rem; transition: color 0.2s; }
    .footer-col ul a:hover { color: var(--white); }
    .social-icons { display: flex; gap: 0.8rem; margin-top: 0.5rem; }
    .social-icon {
      width: 36px; height: 36px; border: 1px solid rgba(253,250,245,0.15);
      border-radius: 2px; display: flex; align-items: center; justify-content: center;
      color: rgba(253,250,245,0.5); font-size: 0.8rem; text-decoration: none;
      transition: all 0.2s;
    }
    .social-icon:hover { border-color: var(--latte); color: var(--latte); }
    .footer-bottom { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; }
    .footer-copy { font-size: 0.72rem; color: rgba(253,250,245,0.25); letter-spacing: 0.06em; }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(28px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes bounce {
      0%, 100% { transform: translateX(-50%) translateY(0); }
      50% { transform: translateX(-50%) translateY(6px); }
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    .reveal {
      opacity: 0; transform: translateY(24px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-delay-1 { transition-delay: 0.1s; }
    .reveal-delay-2 { transition-delay: 0.2s; }
    .reveal-delay-3 { transition-delay: 0.3s; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .about-inner { grid-template-columns: 1fr; gap: 3rem; }
      .about-img { max-width: 480px; }
      .location-inner { grid-template-columns: 1fr; }
      .footer-top { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 640px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }
      section { padding: 4.5rem 5%; }
      .footer-top { grid-template-columns: 1fr; }
      .rating-big { font-size: 3.5rem; }
      .footer-bottom { flex-direction: column; text-align: center; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav id="navbar">
  <a href="#hero" class="nav-logo">
    Coffee Embassy
    <span>珈琲大使館 虎ノ門店</span>
  </a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#hours">Hours</a></li>
    <li><a href="#location">Location</a></li>
    <li><a href="#reviews">Reviews</a></li>
  </ul>
  <div class="hamburger" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </div>
</nav>

<div class="mobile-menu" id="mobileMenu">
  <a href="#about" onclick="closeMobile()">About</a>
  <a href="#menu" onclick="closeMobile()">Menu</a>
  <a href="#hours" onclick="closeMobile()">Hours</a>
  <a href="#location" onclick="closeMobile()">Location</a>
  <a href="#reviews" onclick="closeMobile()">Reviews</a>
</div>

<!-- HERO -->
<section id="hero">
  <div class="hero-content">
    <div class="hero-eyebrow">Toranomon, Tokyo</div>
    <h1 class="hero-title">Welcome to<br>Coffee Embassy</h1>
    <p class="hero-jp">珈琲大使館 虎ノ門店</p>
    <p class="hero-tagline">Where every cup represents craftsmanship and tradition.</p>
    <div class="hero-cta">
      <a href="#menu" class="btn-primary">View Menu</a>
      <a href="#location" class="btn-outline">Contact Us</a>
    </div>
  </div>
  <div class="scroll-hint">Scroll</div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-inner">
    <div class="about-img reveal">
      <img src="https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?w=800&q=80" alt="Coffee Embassy interior" loading="lazy" />
    </div>
    <div class="about-text reveal reveal-delay-1">
      <span class="section-label">Our Story</span>
      <h2 class="section-title">A sanctuary for<br>coffee devotees</h2>
      <div class="section-divider"></div>
      <p>Nestled in the quiet dignity of Toranomon, Coffee Embassy is more than a café — it is a living expression of Japan's devotion to precision and beauty. We honor the bean from origin to cup, guided by time-honored techniques and a restless pursuit of excellence.</p>
      <p>Each morning, the soft light of Minato filters through our windows as our baristas begin their careful rituals. From single-origin pour-overs to velvety espresso, every beverage is an act of intention.</p>
      <div class="about-icons">
        <div class="about-icon"><span class="ico">☕</span>Hand-crafted</div>
        <div class="about-icon"><span class="ico">🌿</span>Fresh daily</div>
        <div class="about-icon"><span class="ico">🇯🇵</span>Japanese craft</div>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-inner">
    <div class="reveal">
      <span class="section-label">Our Offerings</span>
      <h2 class="section-title">Menu highlights</h2>
      <div class="section-divider"></div>
    </div>
    <div class="menu-grid">
      <div class="menu-card reveal">
        <div class="menu-card-img">
          <img src="https://images.unsplash.com/photo-1510591509098-f4fdc6d0ff04?w=600&q=80" alt="Espresso" loading="lazy" />
        </div>
        <div class="menu-card-body">
          <div class="menu-card-name">Espresso</div>
          <div class="menu-card-desc">Intensely aromatic single-origin shot, extracted at precise pressure.</div>
          <div class="menu-card-price">¥ 450</div>
        </div>
      </div>
      <div class="menu-card reveal reveal-delay-1">
        <div class="menu-card-img">
          <img src="https://images.unsplash.com/photo-1534040385115-33dcb3acba5b?w=600&q=80" alt="Cappuccino" loading="lazy" />
        </div>
        <div class="menu-card-body">
          <div class="menu-card-name">Cappuccino</div>
          <div class="menu-card-desc">Velvety microfoam meets bold espresso in perfect balance.</div>
          <div class="menu-card-price">¥ 580</div>
        </div>
      </div>
      <div class="menu-card reveal reveal-delay-2">
        <div class="menu-card-img">
          <img src="https://images.unsplash.com/photo-1515823064-d6e0c04616a7?w=600&q=80" alt="Matcha Latte" loading="lazy" />
        </div>
        <div class="menu-card-body">
          <div class="menu-card-name">Matcha Latte</div>
          <div class="menu-card-desc">Ceremonial-grade matcha whisked with steamed oat milk.</div>
          <div class="menu-card-price">¥ 620</div>
        </div>
      </div>
      <div class="menu-card reveal reveal-delay-3">
        <div class="menu-card-img">
          <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=600&q=80" alt="Hand-Drip Coffee" loading="lazy" />
        </div>
        <div class="menu-card-body">
          <div class="menu-card-name">Hand-Drip Coffee</div>
          <div class="menu-card-desc">Patient, meditative pour-over using seasonal single origins.</div>
          <div class="menu-card-price">¥ 680</div>
        </div>
      </div>
      <div class="menu-card reveal reveal-delay-1">
        <div class="menu-card-img">
          <img src="https://images.unsplash.com/photo-1509440159596-0249088772ff?w=600&q=80" alt="Fresh Pastries" loading="lazy" />
        </div>
        <div class="menu-card-body">
          <div class="menu-card-name">Fresh Pastries</div>
          <div class="menu-card-desc">Baked each morning — croissants, scones, and seasonal tarts.</div>
          <div class="menu-card-price">¥ 380~</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- HOURS -->
<section id="hours">
  <div class="hours-inner reveal">
    <span class="section-label">Visit Us</span>
    <h2 class="section-title">Opening hours</h2>
    <div class="section-divider"></div>
    <div class="hours-status">Currently Open</div>
    <table class="hours-table">
      <tr><td>Monday</td><td>08:00 – 18:00</td></tr>
      <tr><td>Tuesday</td><td>08:00 – 18:00</td></tr>
      <tr><td>Wednesday</td><td>08:00 – 18:00</td></tr>
      <tr><td>Thursday</td><td>08:00 – 18:00</td></tr>
      <tr><td>Friday</td><td>08:00 – 18:00</td></tr>
      <tr class="closed"><td>Saturday</td><td>Closed</td></tr>
      <tr class="closed"><td>Sunday</td><td>Closed</td></tr>
    </table>
  </div>
</section>

<!-- LOCATION -->
<section id="location">
  <div class="location-inner">
    <div class="map-embed reveal">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3241.57!2d139.748!3d35.666!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188b9e92a6c1c5%3A0x1e8e3b1e8a3b4c2b!2s2-ch%C5%8Dme-4-1%20Toranomon%2C%20Minato%20City%2C%20Tokyo%20105-0001!5e0!3m2!1sen!2sjp!4v1"
        allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="Coffee Embassy map">
      </iframe>
    </div>
    <div class="location-info reveal reveal-delay-1">
      <span class="section-label">Find us</span>
      <h2 class="section-title">Coffee Embassy<br>Toranomon</h2>
      <div class="section-divider"></div>
      <div class="location-detail">
        <div class="location-icon">📍</div>
        <div class="location-detail-text">
          <strong>Address</strong>
          2 Chome-4-1 Toranomon, Minato City<br>Tokyo 105-0001, Japan
        </div>
      </div>
      <div class="location-detail">
        <div class="location-icon">📞</div>
        <div class="location-detail-text">
          <strong>Phone</strong>
          <a href="tel:+81335800209">+81 3-3580-0209</a>
        </div>
      </div>
      <div class="location-detail">
        <div class="location-icon">🕐</div>
        <div class="location-detail-text">
          <strong>Hours</strong>
          Monday – Friday: 08:00 – 18:00<br>Saturday & Sunday: Closed
        </div>
      </div>
      <div class="location-detail">
        <div class="location-icon">🚇</div>
        <div class="location-detail-text">
          <strong>Nearest Station</strong>
          Toranomon Station (Tokyo Metro Ginza Line)
        </div>
      </div>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section id="reviews">
  <div class="reviews-inner">
    <div class="reveal">
      <span class="section-label">Guest voices</span>
      <h2 class="section-title">What our guests say</h2>
      <div class="section-divider"></div>
      <div class="rating-hero">
        <div class="rating-big">3.9</div>
        <div class="rating-meta">
          <div class="rating-stars">★★★★☆</div>
          <div class="rating-count">Based on 210 reviews</div>
        </div>
      </div>
    </div>
    <div class="reviews-grid">
      <div class="review-card reveal">
        <div class="review-quote">"</div>
        <div class="review-stars">★★★★★</div>
        <p class="review-text">A truly serene coffee experience. The hand-drip coffee was extraordinary — complex, clean, and served with quiet care. I return every week without fail.</p>
        <div class="review-author">— Yuki T., Tokyo</div>
      </div>
      <div class="review-card reveal reveal-delay-1">
        <div class="review-quote">"</div>
        <div class="review-stars">★★★★☆</div>
        <p class="review-text">The matcha latte is unlike anything I've had in the city. The atmosphere is calm and unhurried — exactly what Toranomon mornings deserve.</p>
        <div class="review-author">— James H., London</div>
      </div>
      <div class="review-card reveal reveal-delay-2">
        <div class="review-quote">"</div>
        <div class="review-stars">★★★★★</div>
        <p class="review-text">Minimalist interior, exceptional coffee, knowledgeable staff. Coffee Embassy embodies everything I love about Japanese café culture. Simply wonderful.</p>
        <div class="review-author">— Mei L., Singapore</div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div>
        <div class="footer-logo">Coffee Embassy</div>
        <div class="footer-logo-jp">珈琲大使館 虎ノ門店</div>
        <p class="footer-tagline">Where every cup represents craftsmanship and tradition. Open Monday–Friday in the heart of Toranomon.</p>
      </div>
      <div class="footer-col">
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#hero">Home</a></li>
          <li><a href="#menu">Menu</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#hours">Hours</a></li>
          <li><a href="#location">Contact</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Follow Us</h4>
        <div class="social-icons">
          <a href="#" class="social-icon" aria-label="Instagram">ig</a>
          <a href="#" class="social-icon" aria-label="Twitter">tw</a>
          <a href="#" class="social-icon" aria-label="Facebook">fb</a>
        </div>
        <div style="margin-top:1.5rem">
          <h4>Contact</h4>
          <p style="font-size:0.82rem;color:rgba(253,250,245,0.45);line-height:1.7;margin-top:0.5rem">
            <a href="tel:+81335800209" style="color:rgba(253,250,245,0.45);text-decoration:none">+81 3-3580-0209</a><br>
            Toranomon, Minato City<br>Tokyo 105-0001
          </p>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="footer-copy">© 2025 Coffee Embassy 珈琲大使館. All rights reserved.</div>
      <div class="footer-copy">Crafted with care in Tokyo ☕</div>
    </div>
  </div>
</footer>

<script>
  // Sticky nav
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 40);
  });

  // Hamburger
  const hamburger = document.getElementById('hamburger');
  const mobileMenu = document.getElementById('mobileMenu');
  hamburger.addEventListener('click', () => {
    hamburger.classList.toggle('open');
    mobileMenu.classList.toggle('open');
  });
  function closeMobile() {
    hamburger.classList.remove('open');
    mobileMenu.classList.remove('open');
  }

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
