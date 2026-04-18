<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Esteem Laundry Services</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy: #ddeef2;
      --deep: #edf6f9;
      --cream: #1e3c45;
      --gold: #2e8b84;
      --gold-light: #45aaa2;
      --white: #ffffff;
      --muted: #5c8a94;
      --bubble: #c8e8ed;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--deep);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ── NOISE TEXTURE OVERLAY ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
      opacity: 0.4;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.4rem 5%;
      background: rgba(237,246,249,0.92);
      backdrop-filter: blur(18px);
      border-bottom: 1px solid rgba(46,139,132,0.2);
    }

    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem;
      font-weight: 700;
      color: var(--gold);
      letter-spacing: 0.5px;
    }

    .nav-logo span { color: var(--cream); font-style: italic; }

    .nav-links {
      display: flex;
      gap: 2.2rem;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--muted);
      font-size: 0.85rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      transition: color 0.3s;
    }

    .nav-links a:hover { color: var(--gold); }

    .nav-cta {
      background: var(--gold);
      color: var(--navy) !important;
      padding: 0.55rem 1.4rem;
      border-radius: 2px;
      font-weight: 500 !important;
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: grid;
      place-items: center;
      position: relative;
      padding: 7rem 5% 4rem;
      overflow: hidden;
    }

    .hero-bg-circle {
      position: absolute;
      border-radius: 50%;
      filter: blur(80px);
      pointer-events: none;
    }

    .hero-bg-circle:nth-child(1) {
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(46,139,132,0.12) 0%, transparent 70%);
      top: -100px; right: -150px;
      animation: floatA 8s ease-in-out infinite;
    }

    .hero-bg-circle:nth-child(2) {
      width: 400px; height: 400px;
      background: radial-gradient(circle, rgba(100,200,210,0.08) 0%, transparent 70%);
      bottom: 50px; left: -100px;
      animation: floatB 10s ease-in-out infinite;
    }

    @keyframes floatA { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-30px)} }
    @keyframes floatB { 0%,100%{transform:translateY(0)} 50%{transform:translateY(20px)} }

    .hero-content {
      text-align: center;
      position: relative;
      z-index: 1;
      max-width: 860px;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      border: 1px solid rgba(200,168,75,0.4);
      padding: 0.4rem 1.1rem;
      border-radius: 100px;
      font-size: 0.78rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 2rem;
      animation: fadeUp 0.8s ease both;
    }

    .hero-badge::before {
      content: '';
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--gold);
      animation: pulse 2s ease infinite;
    }

    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 8vw, 5.5rem);
      line-height: 1.08;
      font-weight: 900;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.9s 0.1s ease both;
    }

    .hero h1 em {
      font-style: italic;
      color: var(--gold);
      display: block;
    }

    .hero p {
      font-size: 1.05rem;
      color: var(--muted);
      max-width: 520px;
      margin: 0 auto 2.5rem;
      line-height: 1.75;
      animation: fadeUp 1s 0.2s ease both;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeUp 1.1s 0.3s ease both;
    }

    .btn-primary {
      background: var(--gold);
      color: var(--navy);
      padding: 0.9rem 2.2rem;
      border-radius: 3px;
      font-weight: 500;
      font-size: 0.9rem;
      letter-spacing: 0.5px;
      text-decoration: none;
      transition: background 0.3s, transform 0.2s;
    }

    .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); }

    .btn-outline {
      border: 1px solid rgba(200,168,75,0.4);
      color: var(--gold);
      padding: 0.9rem 2.2rem;
      border-radius: 3px;
      font-size: 0.9rem;
      text-decoration: none;
      transition: border-color 0.3s, color 0.3s, transform 0.2s;
    }

    .btn-outline:hover { border-color: var(--gold); color: var(--gold-light); transform: translateY(-2px); }

    .hero-scroll {
      position: absolute;
      bottom: 2.5rem;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.4rem;
      font-size: 0.72rem;
      letter-spacing: 2px;
      color: var(--muted);
      text-transform: uppercase;
      animation: fadeUp 1.2s 0.5s ease both;
    }

    .scroll-line {
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      animation: scrollDrop 2s ease infinite;
    }

    @keyframes scrollDrop { 0%{opacity:0;transform:scaleY(0);transform-origin:top} 50%{opacity:1} 100%{opacity:0;transform:scaleY(1);transform-origin:top} }

    @keyframes fadeUp { from{opacity:0;transform:translateY(24px)} to{opacity:1;transform:translateY(0)} }

    /* ── STATS STRIP ── */
    .stats {
      background: var(--gold);
      padding: 1.6rem 5%;
      display: flex;
      justify-content: center;
      gap: 4rem;
      flex-wrap: wrap;
    }

    .stat {
      text-align: center;
      color: var(--navy);
    }

    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2rem;
      font-weight: 900;
    }

    .stat-label {
      font-size: 0.78rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      opacity: 0.75;
      margin-top: 0.1rem;
    }

    /* ── SECTION SHARED ── */
    section { position: relative; z-index: 1; }

    .section-label {
      font-size: 0.75rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.8rem;
    }

    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      line-height: 1.2;
      font-weight: 700;
    }

    .section-title em { font-style: italic; color: var(--gold); }

    /* ── SERVICES ── */
    .services {
      padding: 7rem 5%;
    }

    .services-header {
      max-width: 500px;
      margin-bottom: 4rem;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.5px;
      background: rgba(46,139,132,0.08);
      border: 1px solid rgba(46,139,132,0.15);
    }

    .service-card {
      background: var(--navy);
      padding: 2.5rem 2rem;
      transition: background 0.3s;
      cursor: default;
      position: relative;
      overflow: hidden;
    }

    .service-card::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      height: 2px;
      width: 0;
      background: var(--gold);
      transition: width 0.4s ease;
    }

    .service-card:hover { background: #112035; }
    .service-card:hover::after { width: 100%; }

    .service-icon {
      font-size: 2.2rem;
      margin-bottom: 1.2rem;
      display: block;
    }

    .service-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 0.7rem;
      color: var(--cream);
    }

    .service-desc {
      font-size: 0.88rem;
      color: var(--muted);
      line-height: 1.7;
    }

    /* ── WHY US ── */
    .why {
      padding: 7rem 5%;
      background: var(--navy);
    }

    .why-inner {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
      max-width: 1100px;
      margin: 0 auto;
    }

    .why-visual {
      position: relative;
    }

    .why-box {
      background: var(--deep);
      border: 1px solid rgba(46,139,132,0.2);
      padding: 3rem 2.5rem;
      border-radius: 4px;
      position: relative;
    }

    .why-box-accent {
      position: absolute;
      top: -1px; left: 2.5rem;
      width: 60px; height: 2px;
      background: var(--gold);
    }

    .why-quote {
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem;
      font-style: italic;
      line-height: 1.55;
      color: var(--cream);
      margin-bottom: 1.5rem;
    }

    .why-author {
      font-size: 0.82rem;
      letter-spacing: 1px;
      color: var(--gold);
      text-transform: uppercase;
    }

    .floating-tag {
      position: absolute;
      bottom: -1.5rem;
      right: -1.5rem;
      background: var(--gold);
      color: var(--navy);
      padding: 0.8rem 1.4rem;
      font-size: 0.82rem;
      font-weight: 500;
      letter-spacing: 1px;
      text-transform: uppercase;
      border-radius: 2px;
    }

    .why-points {
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }

    .why-point {
      display: flex;
      gap: 1.2rem;
      align-items: flex-start;
    }

    .why-num {
      font-family: 'Playfair Display', serif;
      font-size: 2rem;
      font-weight: 900;
      color: rgba(46,139,132,0.25);
      line-height: 1;
      flex-shrink: 0;
    }

    .why-point h3 {
      font-weight: 500;
      font-size: 1rem;
      color: var(--cream);
      margin-bottom: 0.3rem;
    }

    .why-point p {
      font-size: 0.87rem;
      color: var(--muted);
      line-height: 1.65;
    }

    /* ── PROCESS ── */
    .process {
      padding: 7rem 5%;
      text-align: center;
    }

    .process-header { margin-bottom: 4rem; }

    .process-steps {
      display: flex;
      gap: 0;
      max-width: 900px;
      margin: 0 auto;
      position: relative;
    }

    .process-steps::before {
      content: '';
      position: absolute;
      top: 2rem;
      left: 10%;
      right: 10%;
      height: 1px;
      background: linear-gradient(to right, transparent, rgba(46,139,132,0.3), transparent);
    }

    .process-step {
      flex: 1;
      padding: 0 1rem;
      position: relative;
    }

    .step-num {
      width: 4rem; height: 4rem;
      border-radius: 50%;
      background: var(--navy);
      border: 1px solid rgba(46,139,132,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem;
      font-weight: 700;
      color: var(--gold);
      margin: 0 auto 1.5rem;
      position: relative;
      z-index: 1;
      transition: background 0.3s, border-color 0.3s;
    }

    .process-step:hover .step-num {
      background: var(--gold);
      color: var(--navy);
      border-color: var(--gold);
    }

    .step-title {
      font-family: 'Playfair Display', serif;
      font-size: 1.05rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      color: var(--cream);
    }

    .step-desc {
      font-size: 0.85rem;
      color: var(--muted);
      line-height: 1.65;
    }

    /* ── LOCATION ── */
    .location {
      padding: 7rem 5%;
      background: var(--navy);
    }

    .location-inner {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
      max-width: 1100px;
      margin: 0 auto;
    }

    .location-details {
      display: flex;
      flex-direction: column;
      gap: 1.8rem;
      margin-top: 2.5rem;
    }

    .loc-item {
      display: flex;
      gap: 1rem;
      align-items: flex-start;
    }

    .loc-icon {
      width: 2.5rem; height: 2.5rem;
      background: rgba(200,168,75,0.12);
      border-radius: 3px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.1rem;
      flex-shrink: 0;
    }

    .loc-item h4 {
      font-size: 0.78rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.3rem;
    }

    .loc-item p {
      font-size: 0.9rem;
      color: var(--muted);
      line-height: 1.6;
    }

    .map-container {
      position: relative;
      border-radius: 4px;
      overflow: hidden;
      border: 1px solid rgba(46,139,132,0.2);
    }

    .map-container iframe {
      width: 100%;
      height: 380px;
      display: block;
      filter: grayscale(30%) contrast(1.1);
    }

    .map-label {
      position: absolute;
      top: 1rem; left: 1rem;
      background: var(--gold);
      color: var(--navy);
      padding: 0.4rem 0.9rem;
      font-size: 0.78rem;
      font-weight: 500;
      letter-spacing: 1px;
      text-transform: uppercase;
      border-radius: 2px;
    }

    /* ── CTA ── */
    .cta-section {
      padding: 7rem 5%;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .cta-bg {
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at center, rgba(46,139,132,0.07) 0%, transparent 70%);
    }

    .cta-section h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 3.5rem);
      font-weight: 900;
      margin-bottom: 1.2rem;
      position: relative;
      z-index: 1;
    }

    .cta-section h2 em { font-style: italic; color: var(--gold); }

    .cta-section p {
      color: var(--muted);
      max-width: 500px;
      margin: 0 auto 2.5rem;
      line-height: 1.7;
      position: relative;
      z-index: 1;
    }

    .cta-section .hero-actions { position: relative; z-index: 1; }

    /* ── FOOTER ── */
    footer {
      background: var(--deep);
      border-top: 1px solid rgba(200,168,75,0.1);
      padding: 3rem 5%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1.5rem;
    }

    .footer-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--gold);
    }

    .footer-logo span { color: var(--muted); font-style: italic; }

    footer p {
      font-size: 0.82rem;
      color: var(--muted);
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      .nav-links { display: none; }
      .why-inner, .location-inner { grid-template-columns: 1fr; gap: 3rem; }
      .floating-tag { display: none; }
      .process-steps { flex-direction: column; gap: 2rem; }
      .process-steps::before { display: none; }
      .stats { gap: 2rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">Esteem <span>Laundry</span></div>
    <ul class="nav-links">
      <li><a href="#services">Services</a></li>
      <li><a href="#why">Why Us</a></li>
      <li><a href="#process">How It Works</a></li>
      <li><a href="#location">Find Us</a></li>
      <li><a href="#contact" class="nav-cta">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg-circle"></div>
    <div class="hero-bg-circle"></div>
    <div class="hero-content">
      <div class="hero-badge">Mile 11 · Trusted Since Day One</div>
      <h1>
        Fresh, Clean &<em>Beautifully Pressed.</em>
      </h1>
      <p>Professional laundry and dry-cleaning services that care for your clothes like we care for our customers — with esteem.</p>
      <div class="hero-actions">
        <a href="#services" class="btn-primary">Explore Services</a>
        <a href="#location" class="btn-outline">Find Our Location</a>
      </div>
    </div>
    <div class="hero-scroll">
      Scroll <div class="scroll-line"></div>
    </div>
  </section>

  <!-- STATS -->
  <div class="stats">
    <div class="stat"><div class="stat-num">500+</div><div class="stat-label">Happy Customers</div></div>
    <div class="stat"><div class="stat-num">24h</div><div class="stat-label">Turnaround Time</div></div>
    <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Satisfaction Rate</div></div>
    <div class="stat"><div class="stat-num">5★</div><div class="stat-label">Rated Service</div></div>
  </div>

  <!-- SERVICES -->
  <section class="services" id="services">
    <div class="services-header">
      <p class="section-label">What We Offer</p>
      <h2 class="section-title">Our <em>Services</em></h2>
    </div>
    <div class="services-grid">
      <div class="service-card">
        <span class="service-icon">👔</span>
        <div class="service-name">Wash & Iron</div>
        <p class="service-desc">Full-cycle washing and precision ironing for everyday wear. Returned crisp, fresh, and ready to wear.</p>
      </div>
      <div class="service-card">
        <span class="service-icon">🧥</span>
        <div class="service-name">Dry Cleaning</div>
        <p class="service-desc">Gentle solvent-based cleaning for suits, coats, and delicate fabrics that need extra care.</p>
      </div>
      <div class="service-card">
        <span class="service-icon">🛏️</span>
        <div class="service-name">Bedding & Linen</div>
        <p class="service-desc">Deep-clean and freshening of duvets, bed sheets, pillowcases, and household linens.</p>
      </div>
      <div class="service-card">
        <span class="service-icon">👗</span>
        <div class="service-name">Delicate Fabrics</div>
        <p class="service-desc">Specialised handling of silk, chiffon, lace, and other fragile garments with expert care.</p>
      </div>
      <div class="service-card">
        <span class="service-icon">🚗</span>
        <div class="service-name">Pickup & Delivery</div>
        <p class="service-desc">Convenient door-to-door laundry collection and delivery within the Mile 11 area.</p>
      </div>

    </div>
  </section>

  <!-- WHY US -->
  <section class="why" id="why">
    <div class="why-inner">
      <div class="why-visual">
        <div class="why-box">
          <div class="why-box-accent"></div>
          <p class="why-quote">"We treat every garment as if it were our own — because your clothes tell your story."</p>
          <p class="why-author">— Esteem Laundry Services, Mile 11</p>
        </div>
        <div class="floating-tag">⭐ Trusted by Mile 11</div>
      </div>
      <div>
        <p class="section-label">Why Choose Us</p>
        <h2 class="section-title" style="margin-bottom:2.5rem">The <em>Esteem</em> Difference</h2>
        <div class="why-points">
          <div class="why-point">
            <div class="why-num">01</div>
            <div>
              <h3>Premium Products Only</h3>
              <p>We use high-quality, fabric-safe detergents that clean deeply without damaging fibres or colours.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-num">02</div>
            <div>
              <h3>Fast 24-Hour Turnaround</h3>
              <p>Most orders are ready within 24 hours. Express same-day service available on request.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-num">03</div>
            <div>
              <h3>Experienced & Careful Hands</h3>
              <p>Our team knows fabrics. From silk to denim, we treat every item with the right technique.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-num">04</div>
            <div>
              <h3>Affordable, Transparent Pricing</h3>
              <p>No surprises. Clear pricing for every service, with discounts for bulk and regular customers.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROCESS -->
  <section class="process" id="process">
    <div class="process-header">
      <p class="section-label">Simple Steps</p>
      <h2 class="section-title">How It <em>Works</em></h2>
    </div>
    <div class="process-steps">
      <div class="process-step">
        <div class="step-num">1</div>
        <div class="step-title">Drop Off or Request Pickup</div>
        <p class="step-desc">Bring your items to us at Mile 11 or call to schedule a pickup from your location.</p>
      </div>
      <div class="process-step">
        <div class="step-num">2</div>
        <div class="step-title">We Clean & Care</div>
        <p class="step-desc">Your garments are sorted, treated, washed, dried, and pressed with professional care.</p>
      </div>
      <div class="process-step">
        <div class="step-num">3</div>
        <div class="step-title">Collect or Get Delivered</div>
        <p class="step-desc">Pick up your fresh laundry or have it delivered right to your doorstep, hassle-free.</p>
      </div>
    </div>
  </section>

  <!-- LOCATION -->
  <section class="location" id="location">
    <div class="location-inner">
      <div>
        <p class="section-label">Find Us</p>
        <h2 class="section-title">We're at <em>Mile 11</em></h2>
        <div class="location-details">
          <div class="loc-item">
            <div class="loc-icon">📍</div>
            <div>
              <h4>Address</h4>
              <p>HM2C+CC3, Mile 11<br>Esteem Laundry Services</p>
            </div>
          </div>
          <div class="loc-item">
            <div class="loc-icon">🕐</div>
            <div>
              <h4>Opening Hours</h4>
              <p>Monday – Saturday: 7:00 AM – 7:00 PM<br>Sunday: Closed</p>
            </div>
          </div>
          <div class="loc-item">
            <div class="loc-icon">📞</div>
            <div>
              <h4>Get In Touch</h4>
              <p><a href="tel:0247262646" style="color:var(--gold);text-decoration:none;font-size:1rem;font-weight:500;">0247 262 646</a><br>Call or WhatsApp us for enquiries,<br>pickup requests, or pricing.</p>
            </div>
          </div>
        </div>
      </div>
      <div class="map-container">
        <div class="map-label">📍 Our Location</div>
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d996.4!2d9.2!3d4.1!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xfdfbd9b606705e5%3A0x59e7d3b9fa42a661!2sEsteem%20Laundry%20Services!5e0!3m2!1sen!2s!4v1700000000000!5m2!1sen!2s"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
          title="Esteem Laundry Services Location">
        </iframe>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section class="cta-section" id="contact">
    <div class="cta-bg"></div>
    <h2>Ready for <em>Fresh Laundry?</em></h2>
    <p>Visit us at Mile 11 today or reach out to schedule your first pickup. Your clothes deserve the best.</p>
    <div class="hero-actions">
      <a href="https://maps.app.goo.gl/Mn3iXMPrsPVtXdqcA" target="_blank" class="btn-primary">Get Directions</a>
      <a href="tel:0247262646" class="btn-outline">Call Us Now</a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-logo">Esteem <span>Laundry Services</span></div>
    <p>Mile 11 · Professional Laundry & Dry Cleaning</p>
    <p style="font-size:0.78rem">© 2025 Esteem Laundry Services. All rights reserved.</p>
  </footer>

</body>
</html>
