<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="BT Brothers - Premium Unisex Salon. Expert haircuts, beard styling, grooming, facials & hair spa. Trained by Javed Habib. Book your appointment on WhatsApp." />
  <meta name="keywords" content="BT Brothers, unisex salon, haircut, beard styling, grooming, hair spa, facial, Javed Habib trained, Yash More, premium salon" />
  <meta name="author" content="BT Brothers Salon" />
  <meta property="og:title" content="BT Brothers | Premium Unisex Salon" />
  <meta property="og:description" content="Style that defines you. Expert grooming by Mr. Yash More, trained by Javed Habib." />
  <meta property="og:type" content="website" />
  <meta name="theme-color" content="#0a0a0a" />
  <title>BT Brothers | Premium Unisex Salon</title>

  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='12' fill='%230a0a0a'/><text y='.9em' font-size='80' x='10' fill='%23c9a84c'>✂</text></svg>" />

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;0,900;1,400;1,700&family=Poppins:wght@300;400;500;600;700&family=Cinzel:wght@400;600;700&display=swap" rel="stylesheet" />

  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />

  <style>
    /* ============================================================
       CSS CUSTOM PROPERTIES — DESIGN TOKENS
    ============================================================ */
    :root {
      --gold:        #c9a84c;
      --gold-light:  #e4c76b;
      --gold-dark:   #9a7a2e;
      --black:       #0a0a0a;
      --black-soft:  #111111;
      --black-card:  #161616;
      --black-border:#1e1e1e;
      --white:       #f5f5f0;
      --white-muted: #c2bfb5;
      --grey:        #888880;
      --font-display: 'Playfair Display', serif;
      --font-heading: 'Cinzel', serif;
      --font-body:    'Poppins', sans-serif;
      --transition:   0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      --shadow-gold:  0 0 40px rgba(201,168,76,0.15);
      --shadow-card:  0 8px 40px rgba(0,0,0,0.6);
      --radius:       4px;
      --radius-lg:    12px;
      --max-width:    1280px;
    }

    /* ============================================================
       RESET & BASE
    ============================================================ */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; font-size: 16px; }
    body {
      background-color: var(--black);
      color: var(--white);
      font-family: var(--font-body);
      font-weight: 400;
      line-height: 1.7;
      overflow-x: hidden;
    }
    img { display: block; max-width: 100%; height: auto; }
    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }
    button { border: none; background: none; cursor: pointer; font-family: var(--font-body); }
    ::selection { background: var(--gold); color: var(--black); }
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--black); }
    ::-webkit-scrollbar-thumb { background: var(--gold-dark); border-radius: 3px; }

    /* ============================================================
       LOADING SCREEN
    ============================================================ */
    #loader {
      position: fixed;
      inset: 0;
      background: var(--black);
      z-index: 9999;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 24px;
      transition: opacity 0.6s ease, visibility 0.6s ease;
    }
    #loader.hidden { opacity: 0; visibility: hidden; }
    .loader-logo {
      font-family: var(--font-heading);
      font-size: clamp(2rem, 5vw, 3.5rem);
      font-weight: 700;
      color: var(--gold);
      letter-spacing: 6px;
      animation: pulse-gold 1.5s ease-in-out infinite;
    }
    .loader-bar-wrap {
      width: 200px;
      height: 2px;
      background: var(--black-border);
      border-radius: 2px;
      overflow: hidden;
    }
    .loader-bar {
      height: 100%;
      width: 0%;
      background: linear-gradient(90deg, var(--gold-dark), var(--gold-light));
      border-radius: 2px;
      animation: loadBar 1.8s ease forwards;
    }
    @keyframes loadBar { to { width: 100%; } }
    @keyframes pulse-gold {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.5; }
    }

    /* ============================================================
       NAVBAR
    ============================================================ */
    #navbar {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 1000;
      padding: 0 5%;
      height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      transition: background var(--transition), box-shadow var(--transition), height var(--transition);
    }
    #navbar.scrolled {
      background: rgba(10,10,10,0.97);
      box-shadow: 0 2px 30px rgba(0,0,0,0.8);
      height: 66px;
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--black-border);
    }
    .nav-logo {
      font-family: var(--font-heading);
      font-size: 1.6rem;
      font-weight: 700;
      letter-spacing: 4px;
      color: var(--gold);
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .nav-logo span { color: var(--white); font-size: 0.85rem; letter-spacing: 2px; font-family: var(--font-body); font-weight: 300; }
    .nav-links {
      display: flex;
      align-items: center;
      gap: 36px;
    }
    .nav-links a {
      font-size: 0.78rem;
      font-weight: 500;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--white-muted);
      position: relative;
      transition: color var(--transition);
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0;
      width: 0; height: 1px;
      background: var(--gold);
      transition: width var(--transition);
    }
    .nav-links a:hover { color: var(--gold); }
    .nav-links a:hover::after { width: 100%; }
    .nav-cta {
      padding: 10px 24px;
      background: transparent;
      border: 1px solid var(--gold);
      color: var(--gold) !important;
      border-radius: var(--radius);
      font-size: 0.75rem !important;
      letter-spacing: 2px;
      transition: background var(--transition), color var(--transition) !important;
    }
    .nav-cta:hover { background: var(--gold) !important; color: var(--black) !important; }
    .nav-cta:hover::after { display: none; }

    /* Hamburger */
    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      padding: 4px;
      z-index: 1001;
    }
    .hamburger span {
      display: block;
      width: 26px; height: 2px;
      background: var(--gold);
      border-radius: 2px;
      transition: var(--transition);
    }
    .hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
    .hamburger.open span:nth-child(2) { opacity: 0; }
    .hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

    /* Mobile Menu */
    .mobile-menu {
      position: fixed;
      top: 0; right: -100%;
      width: min(320px, 85vw);
      height: 100vh;
      background: var(--black-soft);
      z-index: 999;
      padding: 100px 40px 40px;
      display: flex;
      flex-direction: column;
      gap: 32px;
      transition: right var(--transition);
      border-left: 1px solid var(--black-border);
    }
    .mobile-menu.open { right: 0; }
    .mobile-menu a {
      font-family: var(--font-display);
      font-size: 1.4rem;
      color: var(--white-muted);
      transition: color var(--transition);
      border-bottom: 1px solid var(--black-border);
      padding-bottom: 16px;
    }
    .mobile-menu a:hover { color: var(--gold); }
    .mobile-overlay {
      position: fixed; inset: 0;
      background: rgba(0,0,0,0.7);
      z-index: 998;
      display: none;
      backdrop-filter: blur(4px);
    }
    .mobile-overlay.show { display: block; }

    /* ============================================================
       UTILITY CLASSES
    ============================================================ */
    .container { max-width: var(--max-width); margin: 0 auto; padding: 0 5%; }
    .section { padding: 100px 0; }
    .section-label {
      font-size: 0.7rem;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 600;
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .section-label::before {
      content: '';
      display: block;
      width: 40px; height: 1px;
      background: var(--gold);
    }
    .section-title {
      font-family: var(--font-display);
      font-size: clamp(2rem, 4vw, 3.2rem);
      font-weight: 700;
      line-height: 1.2;
      color: var(--white);
      margin-bottom: 20px;
    }
    .section-title em { color: var(--gold); font-style: italic; }
    .section-sub {
      color: var(--white-muted);
      font-size: 1rem;
      max-width: 560px;
      line-height: 1.8;
    }
    .gold-line {
      width: 60px; height: 2px;
      background: linear-gradient(90deg, var(--gold), transparent);
      margin: 24px 0 40px;
    }
    .reveal {
      opacity: 0;
      transform: translateY(40px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    .reveal-left {
      opacity: 0;
      transform: translateX(-50px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal-left.visible { opacity: 1; transform: translateX(0); }
    .reveal-right {
      opacity: 0;
      transform: translateX(50px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .reveal-right.visible { opacity: 1; transform: translateX(0); }

    /* Gold Button */
    .btn-gold {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 14px 34px;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold), var(--gold-light));
      color: var(--black);
      font-family: var(--font-body);
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      border-radius: var(--radius);
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }
    .btn-gold::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, var(--gold-light), var(--gold), var(--gold-dark));
      opacity: 0;
      transition: opacity var(--transition);
    }
    .btn-gold:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,0.4); }
    .btn-gold:hover::before { opacity: 1; }
    .btn-gold span, .btn-gold i { position: relative; z-index: 1; }

    /* Outline Button */
    .btn-outline {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 13px 34px;
      background: transparent;
      color: var(--white);
      border: 1px solid rgba(255,255,255,0.3);
      font-family: var(--font-body);
      font-size: 0.8rem;
      font-weight: 600;
      letter-spacing: 2px;
      text-transform: uppercase;
      border-radius: var(--radius);
      transition: var(--transition);
    }
    .btn-outline:hover {
      border-color: var(--gold);
      color: var(--gold);
      transform: translateY(-2px);
    }

    /* ============================================================
       HERO SECTION
    ============================================================ */
    #hero {
      position: relative;
      height: 100vh;
      min-height: 650px;
      display: flex;
      align-items: center;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse at 20% 50%, rgba(201,168,76,0.06) 0%, transparent 60%),
        radial-gradient(ellipse at 80% 20%, rgba(201,168,76,0.04) 0%, transparent 50%),
        linear-gradient(135deg, #0a0a0a 0%, #0f0f0f 40%, #111008 100%);
    }
    /* Geometric decorative lines */
    .hero-lines {
      position: absolute;
      inset: 0;
      overflow: hidden;
      pointer-events: none;
    }
    .hero-lines::before {
      content: '';
      position: absolute;
      top: -50%; right: -10%;
      width: 600px; height: 600px;
      border: 1px solid rgba(201,168,76,0.08);
      border-radius: 50%;
      animation: rotateSlow 30s linear infinite;
    }
    .hero-lines::after {
      content: '';
      position: absolute;
      top: -30%; right: -5%;
      width: 400px; height: 400px;
      border: 1px solid rgba(201,168,76,0.05);
      border-radius: 50%;
      animation: rotateSlow 20s linear infinite reverse;
    }
    @keyframes rotateSlow { to { transform: rotate(360deg); } }

    /* Scissor decorative element */
    .hero-scissor-deco {
      position: absolute;
      right: 5%;
      top: 50%;
      transform: translateY(-50%);
      font-size: clamp(200px, 25vw, 380px);
      color: rgba(201,168,76,0.04);
      font-family: Arial, sans-serif;
      pointer-events: none;
      line-height: 1;
      user-select: none;
    }

    .hero-content {
      position: relative;
      z-index: 2;
      max-width: var(--max-width);
      margin: 0 auto;
      padding: 0 5%;
      width: 100%;
    }
    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 7px 18px;
      border: 1px solid rgba(201,168,76,0.3);
      border-radius: 50px;
      font-size: 0.7rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 28px;
      animation: fadeInDown 0.8s ease both;
      background: rgba(201,168,76,0.05);
      backdrop-filter: blur(8px);
    }
    .hero-badge i { font-size: 0.65rem; }
    .hero-title {
      font-family: var(--font-display);
      font-size: clamp(3rem, 7vw, 6.5rem);
      font-weight: 900;
      line-height: 1.05;
      margin-bottom: 10px;
      animation: fadeInUp 0.8s ease 0.2s both;
    }
    .hero-title-line2 {
      font-family: var(--font-display);
      font-size: clamp(3rem, 7vw, 6.5rem);
      font-weight: 400;
      font-style: italic;
      color: var(--gold);
      line-height: 1.05;
      margin-bottom: 28px;
      animation: fadeInUp 0.8s ease 0.35s both;
    }
    .hero-desc {
      font-size: 1rem;
      color: var(--white-muted);
      max-width: 480px;
      margin-bottom: 44px;
      line-height: 1.8;
      animation: fadeInUp 0.8s ease 0.5s both;
    }
    .hero-desc strong { color: var(--gold); font-weight: 600; }
    .hero-buttons {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
      animation: fadeInUp 0.8s ease 0.65s both;
    }
    .hero-stats {
      display: flex;
      gap: 48px;
      margin-top: 64px;
      padding-top: 40px;
      border-top: 1px solid var(--black-border);
      animation: fadeInUp 0.8s ease 0.8s both;
      flex-wrap: wrap;
    }
    .hero-stat-num {
      font-family: var(--font-display);
      font-size: 2.4rem;
      font-weight: 700;
      color: var(--gold);
      line-height: 1;
      margin-bottom: 6px;
    }
    .hero-stat-label {
      font-size: 0.72rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--grey);
    }
    .hero-scroll {
      position: absolute;
      bottom: 36px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      font-size: 0.65rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--grey);
      animation: fadeIn 1.2s ease 1.5s both;
    }
    .hero-scroll-line {
      width: 1px; height: 50px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      animation: scrollPulse 2s ease-in-out infinite;
    }
    @keyframes scrollPulse {
      0%, 100% { opacity: 1; transform: scaleY(1); }
      50% { opacity: 0.4; transform: scaleY(0.7); }
    }

    @keyframes fadeInDown { from { opacity:0; transform:translateY(-20px); } to { opacity:1; transform:translateY(0); } }
    @keyframes fadeInUp   { from { opacity:0; transform:translateY(30px); } to { opacity:1; transform:translateY(0); } }
    @keyframes fadeIn     { from { opacity:0; } to { opacity:1; } }

    /* ============================================================
       MARQUEE STRIP
    ============================================================ */
    .marquee-strip {
      background: var(--gold);
      padding: 14px 0;
      overflow: hidden;
      white-space: nowrap;
    }
    .marquee-inner {
      display: inline-flex;
      animation: marquee 25s linear infinite;
    }
    .marquee-inner span {
      font-family: var(--font-heading);
      font-size: 0.75rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--black);
      font-weight: 700;
      padding: 0 40px;
    }
    .marquee-inner i { color: rgba(0,0,0,0.4); font-size: 0.6rem; }
    @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }

    /* ============================================================
       ABOUT SECTION
    ============================================================ */
    #about { background: var(--black-soft); }
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }
    .about-image-wrap {
      position: relative;
    }
    .about-image-frame {
      position: relative;
      width: 100%;
      aspect-ratio: 3/4;
      background: var(--black-card);
      border-radius: var(--radius-lg);
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .about-image-inner {
      width: 100%;
      height: 100%;
      background:
        linear-gradient(160deg, rgba(201,168,76,0.12) 0%, rgba(0,0,0,0) 50%),
        var(--black-card);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 20px;
      padding: 40px;
    }
    .about-icon-large {
      font-size: 7rem;
      color: var(--gold);
      opacity: 0.6;
    }
    .about-image-frame::before {
      content: '';
      position: absolute;
      inset: -1px;
      border-radius: var(--radius-lg);
      background: linear-gradient(135deg, var(--gold), transparent, var(--gold-dark));
      z-index: -1;
      opacity: 0.3;
    }
    .about-badge-float {
      position: absolute;
      bottom: -20px;
      right: -20px;
      width: 130px; height: 130px;
      background: var(--gold);
      border-radius: 50%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 16px;
      box-shadow: 0 8px 40px rgba(201,168,76,0.4);
      animation: floatBadge 4s ease-in-out infinite;
    }
    .about-badge-float strong {
      font-family: var(--font-display);
      font-size: 1.8rem;
      font-weight: 900;
      color: var(--black);
      line-height: 1;
    }
    .about-badge-float span {
      font-size: 0.62rem;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: var(--black);
    }
    @keyframes floatBadge {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }
    .about-gold-line {
      width: 40px; height: 3px;
      background: var(--gold);
      border-radius: 2px;
      margin: 24px 0;
    }
    .about-text p {
      color: var(--white-muted);
      margin-bottom: 20px;
      line-height: 1.9;
    }
    .about-highlight {
      display: flex;
      align-items: flex-start;
      gap: 16px;
      padding: 24px;
      background: var(--black-card);
      border-radius: var(--radius);
      border-left: 3px solid var(--gold);
      margin: 32px 0;
    }
    .about-highlight i {
      font-size: 1.6rem;
      color: var(--gold);
      margin-top: 2px;
      flex-shrink: 0;
    }
    .about-highlight-text h4 {
      font-family: var(--font-display);
      font-size: 1.1rem;
      margin-bottom: 6px;
      color: var(--white);
    }
    .about-highlight-text p {
      font-size: 0.88rem;
      color: var(--white-muted);
      margin: 0;
    }
    .about-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 32px;
    }
    .about-tag {
      padding: 7px 16px;
      border: 1px solid var(--black-border);
      border-radius: 50px;
      font-size: 0.75rem;
      color: var(--white-muted);
      letter-spacing: 1px;
      transition: var(--transition);
    }
    .about-tag:hover { border-color: var(--gold); color: var(--gold); }

    /* ============================================================
       SERVICES SECTION
    ============================================================ */
    #services { background: var(--black); }
    .services-header { text-align: center; margin-bottom: 60px; }
    .services-header .section-label { justify-content: center; }
    .services-header .section-label::before { display: none; }
    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }
    .service-card {
      background: var(--black-card);
      border: 1px solid var(--black-border);
      border-radius: var(--radius-lg);
      padding: 36px 28px;
      transition: var(--transition);
      position: relative;
      overflow: hidden;
      cursor: default;
    }
    .service-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(201,168,76,0.06), transparent);
      opacity: 0;
      transition: opacity var(--transition);
    }
    .service-card::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      height: 2px; width: 0%;
      background: linear-gradient(90deg, var(--gold-dark), var(--gold-light));
      transition: width var(--transition);
    }
    .service-card:hover {
      border-color: rgba(201,168,76,0.3);
      transform: translateY(-6px);
      box-shadow: var(--shadow-card), var(--shadow-gold);
    }
    .service-card:hover::before { opacity: 1; }
    .service-card:hover::after { width: 100%; }
    .service-icon {
      width: 60px; height: 60px;
      background: rgba(201,168,76,0.1);
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      color: var(--gold);
      margin-bottom: 24px;
      transition: var(--transition);
    }
    .service-card:hover .service-icon {
      background: var(--gold);
      color: var(--black);
      transform: scale(1.1);
    }
    .service-card h3 {
      font-family: var(--font-display);
      font-size: 1.25rem;
      font-weight: 600;
      margin-bottom: 12px;
      color: var(--white);
    }
    .service-card p {
      font-size: 0.85rem;
      color: var(--white-muted);
      line-height: 1.75;
      margin-bottom: 24px;
    }
    .service-price {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .service-price-value {
      font-family: var(--font-display);
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--gold);
    }
    .service-price-label {
      font-size: 0.7rem;
      color: var(--grey);
      letter-spacing: 1px;
      text-transform: uppercase;
    }
    .service-book-link {
      font-size: 0.72rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--gold);
      display: flex;
      align-items: center;
      gap: 6px;
      transition: gap var(--transition);
    }
    .service-book-link:hover { gap: 10px; }

    /* ============================================================
       WHY CHOOSE US
    ============================================================ */
    #why {
      background: var(--black-soft);
      position: relative;
      overflow: hidden;
    }
    #why::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
    }
    .why-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }
    .why-items {
      display: grid;
      gap: 20px;
    }
    .why-item {
      display: flex;
      align-items: flex-start;
      gap: 20px;
      padding: 24px;
      background: var(--black-card);
      border-radius: var(--radius);
      border: 1px solid var(--black-border);
      transition: var(--transition);
    }
    .why-item:hover {
      border-color: rgba(201,168,76,0.2);
      transform: translateX(6px);
    }
    .why-item-icon {
      width: 48px; height: 48px;
      flex-shrink: 0;
      background: rgba(201,168,76,0.1);
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.1rem;
      color: var(--gold);
    }
    .why-item h4 {
      font-family: var(--font-display);
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 6px;
      color: var(--white);
    }
    .why-item p {
      font-size: 0.83rem;
      color: var(--white-muted);
      line-height: 1.7;
    }
    .why-visual {
      position: relative;
    }
    .why-visual-main {
      background: var(--black-card);
      border-radius: var(--radius-lg);
      border: 1px solid var(--black-border);
      padding: 48px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    .why-visual-main::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--gold-dark), var(--gold-light));
    }
    .why-big-number {
      font-family: var(--font-display);
      font-size: clamp(5rem, 10vw, 9rem);
      font-weight: 900;
      color: var(--gold);
      line-height: 1;
      margin-bottom: 16px;
      opacity: 0.9;
    }
    .why-big-text {
      font-family: var(--font-display);
      font-size: 1.4rem;
      font-style: italic;
      color: var(--white-muted);
      margin-bottom: 24px;
    }
    .why-cert {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 12px 20px;
      background: rgba(201,168,76,0.1);
      border: 1px solid rgba(201,168,76,0.2);
      border-radius: 50px;
      font-size: 0.78rem;
      color: var(--gold);
      letter-spacing: 1px;
    }

    /* ============================================================
       COUNTER SECTION
    ============================================================ */
    #counters {
      background: var(--gold);
      padding: 60px 0;
    }
    .counters-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 0;
    }
    .counter-item {
      text-align: center;
      padding: 24px 16px;
      border-right: 1px solid rgba(0,0,0,0.15);
    }
    .counter-item:last-child { border-right: none; }
    .counter-num {
      font-family: var(--font-display);
      font-size: clamp(2.5rem, 5vw, 3.8rem);
      font-weight: 900;
      color: var(--black);
      line-height: 1;
      margin-bottom: 8px;
    }
    .counter-label {
      font-size: 0.72rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: rgba(0,0,0,0.6);
      font-weight: 600;
    }

    /* ============================================================
       GALLERY SECTION
    ============================================================ */
    #gallery { background: var(--black); }
    .gallery-header { text-align: center; margin-bottom: 48px; }
    .gallery-header .section-label { justify-content: center; }
    .gallery-header .section-label::before { display: none; }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: auto;
      gap: 16px;
    }
    .gallery-item {
      position: relative;
      overflow: hidden;
      border-radius: var(--radius);
      background: var(--black-card);
      cursor: pointer;
    }
    .gallery-item:nth-child(1) { grid-row: span 2; }
    .gallery-item:nth-child(4) { grid-column: span 2; }
    .gallery-visual {
      width: 100%;
      height: 100%;
      min-height: 220px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 4rem;
      color: var(--gold);
      opacity: 0.3;
      transition: var(--transition);
    }
    .gallery-item:nth-child(1) .gallery-visual { min-height: 460px; }
    .gallery-item:nth-child(4) .gallery-visual { min-height: 220px; }
    /* Placeholder gradients to simulate styled images */
    .gallery-item:nth-child(1) { background: linear-gradient(135deg, #1a1508, #0f0e0a); }
    .gallery-item:nth-child(2) { background: linear-gradient(135deg, #0f0f0a, #1a1408); }
    .gallery-item:nth-child(3) { background: linear-gradient(135deg, #12100a, #1a1206); }
    .gallery-item:nth-child(4) { background: linear-gradient(135deg, #16130a, #0c0b07); }
    .gallery-item:nth-child(5) { background: linear-gradient(135deg, #111009, #1a1508); }
    .gallery-item:nth-child(6) { background: linear-gradient(135deg, #0e0d09, #16140a); }
    .gallery-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, transparent 60%);
      opacity: 0;
      transition: var(--transition);
      display: flex;
      align-items: flex-end;
      padding: 24px;
    }
    .gallery-item:hover .gallery-overlay { opacity: 1; }
    .gallery-item:hover .gallery-visual { opacity: 0.7; transform: scale(1.05); }
    .gallery-overlay-text {
      font-family: var(--font-display);
      font-size: 1rem;
      color: var(--gold);
      font-style: italic;
    }

    /* ============================================================
       BOOKING SECTION
    ============================================================ */
    #booking {
      background: var(--black-soft);
      position: relative;
      overflow: hidden;
    }
    #booking::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at center, rgba(201,168,76,0.06) 0%, transparent 70%);
    }
    .booking-inner {
      position: relative;
      text-align: center;
      max-width: 720px;
      margin: 0 auto;
    }
    .booking-icon {
      font-size: 4rem;
      color: var(--gold);
      margin-bottom: 24px;
      animation: pulse-gold 3s ease-in-out infinite;
    }
    .booking-inner .section-label { justify-content: center; }
    .booking-inner .section-label::before { display: none; }
    .booking-inner .section-title { margin-bottom: 16px; }
    .booking-inner .section-sub { margin: 0 auto 44px; }
    .booking-buttons {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 44px;
    }
    .btn-whatsapp {
      background: linear-gradient(135deg, #128c7e, #25d366);
      color: white;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 14px 34px;
      border-radius: var(--radius);
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      transition: var(--transition);
    }
    .btn-whatsapp:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(37,211,102,0.3);
    }
    .btn-instagram {
      background: linear-gradient(135deg, #833ab4, #fd1d1d, #fcb045);
      color: white;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 14px 34px;
      border-radius: var(--radius);
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      transition: var(--transition);
    }
    .btn-instagram:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(253,29,29,0.3);
    }
    .booking-info {
      display: flex;
      justify-content: center;
      gap: 40px;
      flex-wrap: wrap;
      padding-top: 40px;
      border-top: 1px solid var(--black-border);
    }
    .booking-info-item {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.85rem;
      color: var(--white-muted);
    }
    .booking-info-item i { color: var(--gold); font-size: 1.1rem; }
    .booking-info-item a { color: var(--white-muted); transition: color var(--transition); }
    .booking-info-item a:hover { color: var(--gold); }

    /* ============================================================
       TESTIMONIALS SECTION
    ============================================================ */
    #testimonials { background: var(--black); }
    .testimonials-header { text-align: center; margin-bottom: 60px; }
    .testimonials-header .section-label { justify-content: center; }
    .testimonials-header .section-label::before { display: none; }
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }
    .testimonial-card {
      background: var(--black-card);
      border: 1px solid var(--black-border);
      border-radius: var(--radius-lg);
      padding: 32px;
      transition: var(--transition);
      position: relative;
    }
    .testimonial-card::before {
      content: '\201C';
      position: absolute;
      top: 16px; right: 24px;
      font-family: var(--font-display);
      font-size: 6rem;
      color: var(--gold);
      opacity: 0.08;
      line-height: 1;
    }
    .testimonial-card:hover {
      border-color: rgba(201,168,76,0.2);
      transform: translateY(-4px);
      box-shadow: var(--shadow-card);
    }
    .testimonial-stars {
      display: flex;
      gap: 4px;
      margin-bottom: 20px;
    }
    .testimonial-stars i { color: var(--gold); font-size: 0.85rem; }
    .testimonial-text {
      font-size: 0.9rem;
      color: var(--white-muted);
      line-height: 1.85;
      font-style: italic;
      margin-bottom: 24px;
    }
    .testimonial-author {
      display: flex;
      align-items: center;
      gap: 14px;
    }
    .testimonial-avatar {
      width: 46px; height: 46px;
      border-radius: 50%;
      background: rgba(201,168,76,0.15);
      border: 2px solid var(--gold);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: var(--font-display);
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--gold);
      flex-shrink: 0;
    }
    .testimonial-author-name {
      font-weight: 600;
      font-size: 0.88rem;
      color: var(--white);
    }
    .testimonial-author-label {
      font-size: 0.72rem;
      color: var(--grey);
      letter-spacing: 1px;
    }

    /* ============================================================
       OWNER SECTION
    ============================================================ */
    #owner {
      background: var(--black-soft);
      position: relative;
      overflow: hidden;
    }
    .owner-grid {
      display: grid;
      grid-template-columns: 1fr 1.4fr;
      gap: 80px;
      align-items: center;
    }
    .owner-portrait {
      position: relative;
    }
    .owner-portrait-frame {
      width: 100%;
      aspect-ratio: 3/4;
      background: var(--black-card);
      border-radius: var(--radius-lg);
      overflow: hidden;
      border: 1px solid var(--black-border);
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      gap: 16px;
      position: relative;
    }
    .owner-portrait-frame::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--gold-dark), var(--gold-light));
    }
    .owner-portrait-icon {
      font-size: 8rem;
      color: var(--gold);
      opacity: 0.5;
    }
    .owner-portrait-name {
      font-family: var(--font-display);
      font-size: 1.1rem;
      color: var(--white-muted);
      font-style: italic;
    }
    .owner-name-badge {
      position: absolute;
      bottom: 24px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(10,10,10,0.9);
      border: 1px solid rgba(201,168,76,0.3);
      border-radius: var(--radius);
      padding: 10px 20px;
      text-align: center;
      backdrop-filter: blur(8px);
      white-space: nowrap;
    }
    .owner-name-badge strong {
      display: block;
      font-family: var(--font-display);
      font-size: 1rem;
      color: var(--gold);
      margin-bottom: 2px;
    }
    .owner-name-badge span {
      font-size: 0.7rem;
      color: var(--grey);
      letter-spacing: 1px;
      text-transform: uppercase;
    }
    .owner-credential {
      display: flex;
      align-items: flex-start;
      gap: 16px;
      padding: 24px;
      background: linear-gradient(135deg, rgba(201,168,76,0.08), rgba(201,168,76,0.02));
      border: 1px solid rgba(201,168,76,0.2);
      border-radius: var(--radius);
      margin: 32px 0;
    }
    .owner-credential i {
      font-size: 2rem;
      color: var(--gold);
      flex-shrink: 0;
      margin-top: 2px;
    }
    .owner-credential h4 {
      font-family: var(--font-display);
      font-size: 1.1rem;
      margin-bottom: 6px;
    }
    .owner-credential p {
      font-size: 0.85rem;
      color: var(--white-muted);
      line-height: 1.7;
    }
    .owner-skills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 28px;
    }
    .owner-skill-tag {
      padding: 8px 18px;
      background: var(--black-card);
      border: 1px solid var(--black-border);
      border-radius: 50px;
      font-size: 0.75rem;
      color: var(--white-muted);
      letter-spacing: 1px;
      transition: var(--transition);
    }
    .owner-skill-tag:hover { border-color: var(--gold); color: var(--gold); }

    /* ============================================================
       LOCATION SECTION
    ============================================================ */
    #location { background: var(--black); }
    .location-grid {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 60px;
      align-items: start;
    }
    .location-map {
      width: 100%;
      aspect-ratio: 4/3;
      background: var(--black-card);
      border-radius: var(--radius-lg);
      border: 1px solid var(--black-border);
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      gap: 16px;
      position: relative;
    }
    .location-map i { font-size: 4rem; color: var(--gold); opacity: 0.5; }
    .location-map p { font-size: 0.85rem; color: var(--grey); letter-spacing: 1px; }
    .location-map-placeholder-text {
      position: absolute;
      bottom: 20px;
      font-size: 0.7rem;
      color: var(--grey);
      text-align: center;
      padding: 0 20px;
    }
    .contact-items { display: grid; gap: 20px; margin-top: 8px; }
    .contact-item {
      display: flex;
      align-items: flex-start;
      gap: 18px;
      padding: 24px;
      background: var(--black-card);
      border-radius: var(--radius);
      border: 1px solid var(--black-border);
      transition: var(--transition);
    }
    .contact-item:hover { border-color: rgba(201,168,76,0.2); }
    .contact-icon {
      width: 44px; height: 44px;
      background: rgba(201,168,76,0.1);
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--gold);
      font-size: 1rem;
      flex-shrink: 0;
    }
    .contact-item h4 {
      font-size: 0.72rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--grey);
      margin-bottom: 6px;
    }
    .contact-item p, .contact-item a {
      font-size: 0.9rem;
      color: var(--white-muted);
      line-height: 1.6;
      transition: color var(--transition);
    }
    .contact-item a:hover { color: var(--gold); }
    .hours-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6px 20px; margin-top: 6px; }
    .hours-grid span { font-size: 0.8rem; color: var(--white-muted); }
    .hours-grid .today { color: var(--gold); font-weight: 600; }

    /* ============================================================
       FOOTER
    ============================================================ */
    #footer {
      background: var(--black-soft);
      border-top: 1px solid var(--black-border);
    }
    .footer-main {
      padding: 72px 0 48px;
    }
    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1.2fr;
      gap: 60px;
    }
    .footer-brand-logo {
      font-family: var(--font-heading);
      font-size: 2rem;
      font-weight: 700;
      color: var(--gold);
      letter-spacing: 4px;
      margin-bottom: 16px;
    }
    .footer-brand p {
      font-size: 0.85rem;
      color: var(--white-muted);
      line-height: 1.8;
      margin-bottom: 28px;
      max-width: 280px;
    }
    .footer-socials {
      display: flex;
      gap: 12px;
    }
    .footer-social-link {
      width: 40px; height: 40px;
      border: 1px solid var(--black-border);
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--white-muted);
      font-size: 0.9rem;
      transition: var(--transition);
    }
    .footer-social-link:hover {
      border-color: var(--gold);
      color: var(--gold);
      background: rgba(201,168,76,0.05);
    }
    .footer-col h4 {
      font-family: var(--font-heading);
      font-size: 0.72rem;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 24px;
      padding-bottom: 12px;
      border-bottom: 1px solid var(--black-border);
    }
    .footer-col ul { display: grid; gap: 12px; }
    .footer-col ul a {
      font-size: 0.85rem;
      color: var(--white-muted);
      transition: color var(--transition);
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .footer-col ul a:hover { color: var(--gold); }
    .footer-col ul a i { font-size: 0.6rem; color: var(--gold-dark); }
    .footer-contact-item {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      margin-bottom: 14px;
    }
    .footer-contact-item i {
      color: var(--gold);
      font-size: 0.9rem;
      margin-top: 2px;
      flex-shrink: 0;
    }
    .footer-contact-item span {
      font-size: 0.83rem;
      color: var(--white-muted);
      line-height: 1.6;
    }
    .footer-contact-item a { color: var(--white-muted); transition: color var(--transition); }
    .footer-contact-item a:hover { color: var(--gold); }
    .footer-bottom {
      border-top: 1px solid var(--black-border);
      padding: 20px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 12px;
    }
    .footer-bottom p {
      font-size: 0.78rem;
      color: var(--grey);
    }
    .footer-bottom span { color: var(--gold); }
    .footer-bottom-links {
      display: flex;
      gap: 24px;
    }
    .footer-bottom-links a {
      font-size: 0.75rem;
      color: var(--grey);
      transition: color var(--transition);
    }
    .footer-bottom-links a:hover { color: var(--gold); }

    /* ============================================================
       FLOATING ELEMENTS
    ============================================================ */
    /* WhatsApp Floating Button */
    .whatsapp-float {
      position: fixed;
      bottom: 28px;
      right: 28px;
      z-index: 900;
      width: 58px; height: 58px;
      background: linear-gradient(135deg, #128c7e, #25d366);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.6rem;
      color: white;
      box-shadow: 0 4px 20px rgba(37,211,102,0.4);
      transition: var(--transition);
      animation: float 3s ease-in-out infinite;
    }
    .whatsapp-float:hover {
      transform: scale(1.1) translateY(-4px);
      box-shadow: 0 8px 32px rgba(37,211,102,0.5);
    }
    .whatsapp-float .tooltip {
      position: absolute;
      right: 70px;
      background: var(--black-card);
      color: var(--white);
      padding: 8px 16px;
      border-radius: 6px;
      font-size: 0.78rem;
      white-space: nowrap;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease;
      border: 1px solid var(--black-border);
    }
    .whatsapp-float:hover .tooltip { opacity: 1; }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    /* Scroll to Top */
    #scrollTop {
      position: fixed;
      bottom: 100px;
      right: 28px;
      z-index: 900;
      width: 44px; height: 44px;
      background: var(--black-card);
      border: 1px solid var(--black-border);
      border-radius: var(--radius);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--gold);
      font-size: 0.9rem;
      cursor: pointer;
      opacity: 0;
      visibility: hidden;
      transition: var(--transition);
    }
    #scrollTop.show { opacity: 1; visibility: visible; }
    #scrollTop:hover {
      background: var(--gold);
      color: var(--black);
      border-color: var(--gold);
      transform: translateY(-2px);
    }

    /* ============================================================
       BOOKING MODAL
    ============================================================ */
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.85);
      z-index: 2000;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      opacity: 0;
      visibility: hidden;
      transition: var(--transition);
      backdrop-filter: blur(8px);
    }
    .modal-overlay.open { opacity: 1; visibility: visible; }
    .modal {
      background: var(--black-soft);
      border: 1px solid var(--black-border);
      border-radius: var(--radius-lg);
      padding: 48px;
      max-width: 480px;
      width: 100%;
      position: relative;
      transform: scale(0.9) translateY(20px);
      transition: var(--transition);
    }
    .modal-overlay.open .modal { transform: scale(1) translateY(0); }
    .modal::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--gold-dark), var(--gold-light));
      border-radius: var(--radius-lg) var(--radius-lg) 0 0;
    }
    .modal-close {
      position: absolute;
      top: 20px; right: 20px;
      width: 36px; height: 36px;
      border-radius: var(--radius);
      border: 1px solid var(--black-border);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--grey);
      cursor: pointer;
      transition: var(--transition);
      font-size: 0.85rem;
    }
    .modal-close:hover { border-color: var(--gold); color: var(--gold); }
    .modal h3 {
      font-family: var(--font-display);
      font-size: 1.8rem;
      margin-bottom: 8px;
    }
    .modal p { color: var(--white-muted); font-size: 0.88rem; margin-bottom: 32px; }
    .modal-options { display: grid; gap: 14px; }
    .modal-option {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 16px 20px;
      background: var(--black-card);
      border: 1px solid var(--black-border);
      border-radius: var(--radius);
      color: var(--white);
      font-size: 0.88rem;
      cursor: pointer;
      transition: var(--transition);
      text-decoration: none;
    }
    .modal-option i { font-size: 1.2rem; color: var(--gold); }
    .modal-option:hover { border-color: var(--gold); background: rgba(201,168,76,0.05); }

    /* ============================================================
       RESPONSIVE DESIGN
    ============================================================ */
    @media (max-width: 1100px) {
      .services-grid { grid-template-columns: repeat(2, 1fr); }
      .footer-grid { grid-template-columns: 1fr 1fr; gap: 40px; }
      .counters-grid { grid-template-columns: repeat(2, 1fr); }
      .counter-item:nth-child(2) { border-right: none; }
      .counter-item:nth-child(3) { border-right: 1px solid rgba(0,0,0,0.15); }
    }

    @media (max-width: 900px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }
      .about-grid { grid-template-columns: 1fr; gap: 48px; }
      .about-image-wrap { max-width: 400px; margin: 0 auto; }
      .why-grid { grid-template-columns: 1fr; gap: 48px; }
      .owner-grid { grid-template-columns: 1fr; gap: 48px; }
      .owner-portrait { max-width: 360px; margin: 0 auto; }
      .location-grid { grid-template-columns: 1fr; }
      .testimonials-grid { grid-template-columns: 1fr 1fr; }
      .gallery-grid { grid-template-columns: 1fr 1fr; }
      .gallery-item:nth-child(1) { grid-row: auto; }
      .gallery-item:nth-child(4) { grid-column: auto; }
    }

    @media (max-width: 640px) {
      .section { padding: 70px 0; }
      .services-grid { grid-template-columns: 1fr; }
      .testimonials-grid { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr; gap: 36px; }
      .counters-grid { grid-template-columns: repeat(2, 1fr); }
      .counter-item:nth-child(3) { border-right: none; }
      .gallery-grid { grid-template-columns: 1fr; }
      .hero-stats { gap: 28px; }
      .booking-info { flex-direction: column; align-items: center; gap: 20px; }
      .modal { padding: 32px 24px; }
      .hero-buttons { flex-direction: column; align-items: flex-start; }
      .about-badge-float { width: 100px; height: 100px; bottom: -12px; right: -12px; }
      .about-badge-float strong { font-size: 1.4rem; }
    }

    @media (max-width: 380px) {
      .hero-title, .hero-title-line2 { font-size: 2.4rem; }
    }
  </style>
</head>
<body>

  <!-- ============================================================
       LOADING SCREEN
  ============================================================ -->
  <div id="loader">
    <div class="loader-logo">BT BROTHERS</div>
    <div class="loader-bar-wrap">
      <div class="loader-bar"></div>
    </div>
  </div>

  <!-- ============================================================
       FLOATING WHATSAPP BUTTON
  ============================================================ -->
  <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank" rel="noopener" class="whatsapp-float" aria-label="Book on WhatsApp">
    <i class="fab fa-whatsapp"></i>
    <span class="tooltip">Book Appointment</span>
  </a>

  <!-- Scroll to Top -->
  <button id="scrollTop" aria-label="Scroll to top">
    <i class="fas fa-arrow-up"></i>
  </button>

  <!-- Mobile Menu Overlay -->
  <div class="mobile-overlay" id="mobileOverlay"></div>

  <!-- Mobile Menu -->
  <nav class="mobile-menu" id="mobileMenu">
    <a href="#hero" onclick="closeMobileMenu()">Home</a>
    <a href="#about" onclick="closeMobileMenu()">About</a>
    <a href="#services" onclick="closeMobileMenu()">Services</a>
    <a href="#gallery" onclick="closeMobileMenu()">Gallery</a>
    <a href="#booking" onclick="closeMobileMenu()">Book Now</a>
    <a href="#testimonials" onclick="closeMobileMenu()">Reviews</a>
    <a href="#owner" onclick="closeMobileMenu()">Our Expert</a>
    <a href="#location" onclick="closeMobileMenu()">Contact</a>
  </nav>

  <!-- ============================================================
       NAVBAR
  ============================================================ -->
  <header id="navbar">
    <a href="#hero" class="nav-logo">
      BT BROTHERS
      <span>Premium Salon</span>
    </a>
    <nav class="nav-links">
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#gallery">Gallery</a>
      <a href="#testimonials">Reviews</a>
      <a href="#owner">Our Expert</a>
      <a href="#booking" class="nav-cta">Book Now</a>
    </nav>
    <div class="hamburger" id="hamburger" onclick="toggleMobileMenu()" aria-label="Toggle menu">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>

  <!-- ============================================================
       HERO SECTION
  ============================================================ -->
  <section id="hero">
    <div class="hero-bg"></div>
    <div class="hero-lines"></div>
    <div class="hero-scissor-deco">✂</div>

    <div class="hero-content">
      <div class="hero-badge">
        <i class="fas fa-crown"></i>
        Premium Unisex Salon — Trained by Javed Habib
      </div>

      <h1 class="hero-title">Style That</h1>
      <p class="hero-title-line2">Defines You.</p>

      <p class="hero-desc">
        Where precision meets artistry. <strong>BT Brothers</strong> redefines grooming with expert cuts, beard mastery, and transformative styling — crafted for the modern man.
      </p>

      <div class="hero-buttons">
        <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank" rel="noopener" class="btn-gold">
          <i class="fab fa-whatsapp"></i>
          <span>Book on WhatsApp</span>
        </a>
        <a href="#services" class="btn-outline">
          <i class="fas fa-scissors"></i>
          View Services
        </a>
      </div>

      <div class="hero-stats">
        <div>
          <div class="hero-stat-num" data-count="500">0+</div>
          <div class="hero-stat-label">Happy Clients</div>
        </div>
        <div>
          <div class="hero-stat-num" data-count="6">0+</div>
          <div class="hero-stat-label">Expert Services</div>
        </div>
        <div>
          <div class="hero-stat-num">JH</div>
          <div class="hero-stat-label">Trained by Javed Habib</div>
        </div>
        <div>
          <div class="hero-stat-num">5★</div>
          <div class="hero-stat-label">Client Rating</div>
        </div>
      </div>
    </div>

    <div class="hero-scroll">
      <div class="hero-scroll-line"></div>
      Scroll
    </div>
  </section>

  <!-- ============================================================
       MARQUEE STRIP
  ============================================================ -->
  <div class="marquee-strip" aria-hidden="true">
    <div class="marquee-inner">
      <span>Premium Haircut</span>
      <i class="fas fa-diamond"></i>
      <span>Beard Styling</span>
      <i class="fas fa-diamond"></i>
      <span>Hair Spa</span>
      <i class="fas fa-diamond"></i>
      <span>Facial Treatment</span>
      <i class="fas fa-diamond"></i>
      <span>Grooming Packages</span>
      <i class="fas fa-diamond"></i>
      <span>Styling & Makeover</span>
      <i class="fas fa-diamond"></i>
      <span>Trained by Javed Habib</span>
      <i class="fas fa-diamond"></i>
      <span>BT Brothers Salon</span>
      <i class="fas fa-diamond"></i>
      <!-- Duplicate for seamless loop -->
      <span>Premium Haircut</span>
      <i class="fas fa-diamond"></i>
      <span>Beard Styling</span>
      <i class="fas fa-diamond"></i>
      <span>Hair Spa</span>
      <i class="fas fa-diamond"></i>
      <span>Facial Treatment</span>
      <i class="fas fa-diamond"></i>
      <span>Grooming Packages</span>
      <i class="fas fa-diamond"></i>
      <span>Styling & Makeover</span>
      <i class="fas fa-diamond"></i>
      <span>Trained by Javed Habib</span>
      <i class="fas fa-diamond"></i>
      <span>BT Brothers Salon</span>
      <i class="fas fa-diamond"></i>
    </div>
  </div>

  <!-- ============================================================
       ABOUT SECTION
  ============================================================ -->
  <section id="about" class="section">
    <div class="container">
      <div class="about-grid">

        <!-- Image -->
        <div class="about-image-wrap reveal-left">
          <div class="about-image-frame">
            <div class="about-image-inner">
              <i class="fas fa-store about-icon-large"></i>
              <span style="font-family: var(--font-display); font-size: 1.2rem; color: var(--white-muted); font-style: italic;">BT Brothers Salon</span>
            </div>
          </div>
          <div class="about-badge-float">
            <strong>5+</strong>
            <span>Years of Excellence</span>
          </div>
        </div>

        <!-- Text -->
        <div class="about-text reveal-right">
          <div class="section-label">Our Story</div>
          <h2 class="section-title">More Than a Salon,<br>It's a <em>Lifestyle</em></h2>
          <div class="about-gold-line"></div>

          <p>BT Brothers is a premium unisex grooming destination built on a philosophy that every client deserves the finest experience — from the moment they walk through our doors to the final look in the mirror.</p>

          <p>Rooted in passion and precision, we blend modern trends with timeless barbering techniques to deliver looks that not only turn heads but build confidence. Our commitment to hygiene, quality products, and attentive service sets us apart from the ordinary.</p>

          <div class="about-highlight">
            <i class="fas fa-award"></i>
            <div class="about-highlight-text">
              <h4>Trained by the Best — Javed Habib</h4>
              <p>Our head barber Mr. Yash More has been professionally trained under the legendary Javed Habib, India's most renowned hair and grooming expert. This elite training ensures world-class skill in every service we deliver.</p>
            </div>
          </div>

          <p>Whether you're in for a sharp fade, a sculpted beard, or a rejuvenating facial — BT Brothers is your trusted grooming partner.</p>

          <div class="about-tags">
            <span class="about-tag"><i class="fas fa-check" style="color:var(--gold);margin-right:6px;font-size:0.6rem;"></i>Premium Products</span>
            <span class="about-tag"><i class="fas fa-check" style="color:var(--gold);margin-right:6px;font-size:0.6rem;"></i>Expert Barbers</span>
            <span class="about-tag"><i class="fas fa-check" style="color:var(--gold);margin-right:6px;font-size:0.6rem;"></i>Hygienic Environment</span>
            <span class="about-tag"><i class="fas fa-check" style="color:var(--gold);margin-right:6px;font-size:0.6rem;"></i>Unisex Services</span>
            <span class="about-tag"><i class="fas fa-check" style="color:var(--gold);margin-right:6px;font-size:0.6rem;"></i>JH Certified</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ============================================================
       SERVICES SECTION
  ============================================================ -->
  <section id="services" class="section">
    <div class="container">
      <div class="services-header">
        <div class="section-label">What We Offer</div>
        <h2 class="section-title">Our <em>Premium</em> Services</h2>
        <p class="section-sub" style="margin: 0 auto;">Every service is delivered with precision, premium products, and a passion for perfection.</p>
      </div>

      <div class="services-grid">

        <!-- Haircut -->
        <div class="service-card reveal">
          <div class="service-icon"><i class="fas fa-cut"></i></div>
          <h3>Precision Haircut</h3>
          <p>Classic to contemporary — every cut is tailored to your face shape, hair texture, and personal style. Sharp, clean, and always on point.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹200+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20a%20Haircut" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

        <!-- Beard Styling -->
        <div class="service-card reveal" style="transition-delay:0.1s">
          <div class="service-icon"><i class="fas fa-user-tie"></i></div>
          <h3>Beard Styling</h3>
          <p>Shape and define your beard with expert precision. From subtle trims to bold styles, we sculpt your beard to frame your face perfectly.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹150+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20Beard%20Styling" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

        <!-- Hair Spa -->
        <div class="service-card reveal" style="transition-delay:0.2s">
          <div class="service-icon"><i class="fas fa-spa"></i></div>
          <h3>Hair Spa</h3>
          <p>Deeply nourishing treatment that revives dull, damaged hair. Restore moisture, reduce frizz, and bring back your hair's natural shine and strength.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹500+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20Hair%20Spa" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

        <!-- Facial -->
        <div class="service-card reveal" style="transition-delay:0.3s">
          <div class="service-icon"><i class="fas fa-face-smile"></i></div>
          <h3>Facial Treatment</h3>
          <p>Refresh and revitalize your skin with our customized facial treatments. Deep cleanse, exfoliate, and moisturize for a clear, confident complexion.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹400+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20a%20Facial" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

        <!-- Grooming Packages -->
        <div class="service-card reveal" style="transition-delay:0.4s">
          <div class="service-icon"><i class="fas fa-box-open"></i></div>
          <h3>Grooming Packages</h3>
          <p>The full BT Brothers experience — haircut + beard + facial + wash. Bundled for the man who takes grooming seriously. Best value deal.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹699+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20know%20about%20Grooming%20Packages" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

        <!-- Styling & Makeover -->
        <div class="service-card reveal" style="transition-delay:0.5s">
          <div class="service-icon"><i class="fas fa-magic"></i></div>
          <h3>Styling & Makeover</h3>
          <p>Complete transformation from head to toe. Event-ready looks, professional styling, and makeovers for weddings, shoots, or any special occasion.</p>
          <div class="service-price">
            <div>
              <div class="service-price-value">₹800+</div>
              <div class="service-price-label">Starting from</div>
            </div>
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20Styling%20and%20Makeover" target="_blank" class="service-book-link">
              Book <i class="fas fa-arrow-right" style="font-size:0.65rem;"></i>
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ============================================================
       WHY CHOOSE US
  ============================================================ -->
  <section id="why" class="section">
    <div class="container">
      <div class="why-grid">

        <div class="why-items">
          <div class="section-label reveal">Why BT Brothers</div>
          <h2 class="section-title reveal" style="margin-bottom:36px;">The <em>BT</em> Difference</h2>

          <div class="why-item reveal" style="transition-delay:0.1s">
            <div class="why-item-icon"><i class="fas fa-certificate"></i></div>
            <div>
              <h4>Javed Habib Trained Expertise</h4>
              <p>Our head barber is certified and trained by India's top grooming authority — Javed Habib. Every cut reflects that world-class standard.</p>
            </div>
          </div>

          <div class="why-item reveal" style="transition-delay:0.2s">
            <div class="why-item-icon"><i class="fas fa-shield-alt"></i></div>
            <div>
              <h4>Strict Hygiene Standards</h4>
              <p>We follow professional sterilization protocols. Fresh blades, sanitized tools, and clean linen for every single client — always.</p>
            </div>
          </div>

          <div class="why-item reveal" style="transition-delay:0.3s">
            <div class="why-item-icon"><i class="fas fa-flask"></i></div>
            <div>
              <h4>Premium Product Range</h4>
              <p>We exclusively use professional-grade, salon-quality products — from styling gels to facial kits — to ensure the best results for your hair and skin.</p>
            </div>
          </div>

          <div class="why-item reveal" style="transition-delay:0.4s">
            <div class="why-item-icon"><i class="fas fa-heart"></i></div>
            <div>
              <h4>Client-First Philosophy</h4>
              <p>We listen, understand, and deliver. No rush, no compromise. Your satisfaction is our measurement of success at every visit.</p>
            </div>
          </div>

          <div class="why-item reveal" style="transition-delay:0.5s">
            <div class="why-item-icon"><i class="fas fa-clock"></i></div>
            <div>
              <h4>Punctual & Efficient</h4>
              <p>We respect your time. WhatsApp booking ensures zero waiting — arrive for your slot and leave looking like a million bucks, on schedule.</p>
            </div>
          </div>
        </div>

        <div class="why-visual reveal-right">
          <div class="why-visual-main">
            <div class="why-big-number" id="satisfiedCounter">500</div>
            <div class="why-big-text">Satisfied Clients</div>
            <p style="color:var(--white-muted);font-size:0.85rem;line-height:1.8;margin-bottom:28px;">Every number represents a transformation, a confidence boost, and a returning customer who trusts BT Brothers with their look.</p>
            <div class="why-cert">
              <i class="fas fa-award"></i>
              Certified by Javed Habib Institute
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ============================================================
       COUNTERS SECTION
  ============================================================ -->
  <section id="counters">
    <div class="container">
      <div class="counters-grid">
        <div class="counter-item">
          <div class="counter-num"><span class="counter" data-target="500">0</span>+</div>
          <div class="counter-label">Happy Clients</div>
        </div>
        <div class="counter-item">
          <div class="counter-num"><span class="counter" data-target="6">0</span></div>
          <div class="counter-label">Expert Services</div>
        </div>
        <div class="counter-item">
          <div class="counter-num"><span class="counter" data-target="5">0</span>★</div>
          <div class="counter-label">Average Rating</div>
        </div>
        <div class="counter-item">
          <div class="counter-num"><span class="counter" data-target="1">0</span></div>
          <div class="counter-label">JH Trained Expert</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ============================================================
       GALLERY SECTION
  ============================================================ -->
  <section id="gallery" class="section">
    <div class="container">
      <div class="gallery-header">
        <div class="section-label">Our Work</div>
        <h2 class="section-title">The <em>Art</em> of Grooming</h2>
        <p class="section-sub" style="margin: 0 auto;">Every client that sits in our chair leaves with a story to tell — and a look to show for it.</p>
      </div>

      <div class="gallery-grid">

        <div class="gallery-item reveal-left">
          <div class="gallery-visual" style="font-size:6rem;">✂</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Classic Fade Cut</span>
          </div>
        </div>

        <div class="gallery-item reveal" style="transition-delay:0.1s">
          <div class="gallery-visual">💈</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Beard Sculpt</span>
          </div>
        </div>

        <div class="gallery-item reveal" style="transition-delay:0.2s">
          <div class="gallery-visual">🧴</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Hair Spa Treatment</span>
          </div>
        </div>

        <div class="gallery-item reveal" style="transition-delay:0.3s">
          <div class="gallery-visual" style="font-size:5rem;">🪒</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Premium Grooming</span>
          </div>
        </div>

        <div class="gallery-item reveal" style="transition-delay:0.35s">
          <div class="gallery-visual">✨</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Facial Glow</span>
          </div>
        </div>

        <div class="gallery-item reveal-right" style="transition-delay:0.4s">
          <div class="gallery-visual">👑</div>
          <div class="gallery-overlay">
            <span class="gallery-overlay-text">Style Makeover</span>
          </div>
        </div>

      </div>

      <div style="text-align:center;margin-top:40px;" class="reveal">
        <a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank" rel="noopener" class="btn-instagram">
          <i class="fab fa-instagram"></i>
          View More on Instagram
        </a>
      </div>
    </div>
  </section>

  <!-- ============================================================
       BOOKING SECTION
  ============================================================ -->
  <section id="booking" class="section">
    <div class="container">
      <div class="booking-inner">
        <div class="booking-icon">
          <i class="fas fa-calendar-check"></i>
        </div>
        <div class="section-label">Easy Booking</div>
        <h2 class="section-title">Ready for Your<br><em>Transformation?</em></h2>
        <p class="section-sub">Book your appointment in seconds via WhatsApp. No apps, no hassle — just a quick message and your slot is confirmed.</p>

        <div class="booking-buttons">
          <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank" rel="noopener" class="btn-whatsapp">
            <i class="fab fa-whatsapp" style="font-size:1.1rem;"></i>
            Book on WhatsApp
          </a>
          <a href="tel:+919511220814" class="btn-gold">
            <i class="fas fa-phone"></i>
            <span>Call Us Now</span>
          </a>
          <a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank" rel="noopener" class="btn-instagram">
            <i class="fab fa-instagram"></i>
            Instagram
          </a>
        </div>

        <div class="booking-info">
          <div class="booking-info-item">
            <i class="fas fa-phone"></i>
            <a href="tel:+919511220814">+91 95112 20814</a>
          </div>
          <div class="booking-info-item">
            <i class="fab fa-whatsapp"></i>
            <a href="https://wa.me/919511220814" target="_blank">WhatsApp Booking</a>
          </div>
          <div class="booking-info-item">
            <i class="fab fa-instagram"></i>
            <a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank">@b.t.brothers_hair_beauty</a>
          </div>
          <div class="booking-info-item">
            <i class="fas fa-clock"></i>
            <span>Open Daily: 9 AM – 9 PM</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ============================================================
       TESTIMONIALS SECTION
  ============================================================ -->
  <section id="testimonials" class="section" style="background:var(--black-soft);">
    <div class="container">
      <div class="testimonials-header">
        <div class="section-label">Client Stories</div>
        <h2 class="section-title">What Our <em>Clients</em> Say</h2>
        <p class="section-sub" style="margin: 0 auto;">Our work speaks through our clients. Here's what they have to say about the BT Brothers experience.</p>
      </div>

      <div class="testimonials-grid">

        <div class="testimonial-card reveal" style="transition-delay:0s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testimonial-text">"Absolute top-tier service! Yash bhai gave me the cleanest fade I've ever had. The atmosphere is premium, the tools are sterilized, and the results speak for themselves. BT Brothers is my go-to now."</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">R</div>
            <div>
              <div class="testimonial-author-name">Rahul Sharma</div>
              <div class="testimonial-author-label">Regular Client</div>
            </div>
          </div>
        </div>

        <div class="testimonial-card reveal" style="transition-delay:0.15s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testimonial-text">"Got the grooming package before my wedding — haircut, beard, and facial. I looked the best I ever have. Mr. Yash's training from Javed Habib is very evident. Professional skill at every step."</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">A</div>
            <div>
              <div class="testimonial-author-name">Aman Deshmukh</div>
              <div class="testimonial-author-label">Wedding Client</div>
            </div>
          </div>
        </div>

        <div class="testimonial-card reveal" style="transition-delay:0.3s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testimonial-text">"The hair spa here is genuinely amazing — my hair felt so soft and healthy after. The salon has a luxurious vibe and the team is very professional. Highly recommend to anyone who takes their grooming seriously."</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">P</div>
            <div>
              <div class="testimonial-author-name">Priya Patil</div>
              <div class="testimonial-author-label">Hair Spa Client</div>
            </div>
          </div>
        </div>

        <div class="testimonial-card reveal" style="transition-delay:0.1s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i>
          </div>
          <p class="testimonial-text">"Been coming here for over a year. Yash bhai knows exactly what style suits me — sometimes better than I do! The beard trims are precise and the conversations are great too. Highly loyal client."</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">V</div>
            <div>
              <div class="testimonial-author-name">Vikram Kulkarni</div>
              <div class="testimonial-author-label">Loyal Client, 1+ Year</div>
            </div>
          </div>
        </div>

        <div class="testimonial-card reveal" style="transition-delay:0.25s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testimonial-text">"The makeover styling for my photoshoot was done perfectly. Yash sir is a real artist — he understood my look, styled my hair and beard just right. I got so many compliments on the photos. Highly skilled!"</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">S</div>
            <div>
              <div class="testimonial-author-name">Sameer Joshi</div>
              <div class="testimonial-author-label">Photoshoot Client</div>
            </div>
          </div>
        </div>

        <div class="testimonial-card reveal" style="transition-delay:0.4s">
          <div class="testimonial-stars">
            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
          </div>
          <p class="testimonial-text">"Brought my teenage son here and he was thrilled with the result! Clean, friendly environment. The WhatsApp booking is super convenient. We're now regulars. Such a well-run salon — top marks for everything."</p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">N</div>
            <div>
              <div class="testimonial-author-name">Neha More</div>
              <div class="testimonial-author-label">Client & Parent</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ============================================================
       OWNER SECTION
  ============================================================ -->
  <section id="owner" class="section">
    <div class="container">
      <div class="owner-grid">

        <div class="owner-portrait reveal-left">
          <div class="owner-portrait-frame">
            <i class="fas fa-user-circle owner-portrait-icon"></i>
            <span class="owner-portrait-name">Mr. Yash More</span>
            <div class="owner-name-badge">
              <strong>Mr. Yash More</strong>
              <span>Founder & Head Barber</span>
            </div>
          </div>
        </div>

        <div class="reveal-right">
          <div class="section-label">Meet Our Expert</div>
          <h2 class="section-title">Driven by <em>Passion,</em><br>Crafted by Skill</h2>
          <div class="gold-line"></div>

          <p style="color:var(--white-muted);line-height:1.9;margin-bottom:20px;">
            Behind every exceptional haircut at BT Brothers is one man's relentless pursuit of perfection — <strong style="color:var(--white);">Mr. Yash More</strong>. With deep roots in the art of grooming and an unwavering commitment to craft, Yash has dedicated himself to elevating what a salon experience can be.
          </p>

          <p style="color:var(--white-muted);line-height:1.9;margin-bottom:32px;">
            From mastering technical precision to understanding individual style — Yash brings a unique blend of artistry and professionalism to every client who sits in his chair. His vision gave rise to BT Brothers — a space where grooming meets luxury.
          </p>

          <div class="owner-credential">
            <i class="fas fa-graduation-cap"></i>
            <div>
              <h4>Professionally Trained by Javed Habib</h4>
              <p>Javed Habib is India's most celebrated hair expert, known globally for revolutionizing the grooming industry. Mr. Yash More's training under this legend has equipped him with techniques, skills, and industry insight that elevate BT Brothers above the rest.</p>
            </div>
          </div>

          <h4 style="font-family:var(--font-heading);font-size:0.72rem;letter-spacing:3px;text-transform:uppercase;color:var(--gold);margin-bottom:16px;">Areas of Expertise</h4>
          <div class="owner-skills">
            <span class="owner-skill-tag">Precision Haircuts</span>
            <span class="owner-skill-tag">Beard Architecture</span>
            <span class="owner-skill-tag">Hair Spa Treatments</span>
            <span class="owner-skill-tag">Skin Facials</span>
            <span class="owner-skill-tag">Event Makeovers</span>
            <span class="owner-skill-tag">Color & Highlights</span>
            <span class="owner-skill-tag">Scalp Treatments</span>
            <span class="owner-skill-tag">Grooming Consultation</span>
          </div>

          <div style="margin-top:36px;">
            <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment%20with%20Mr.%20Yash" target="_blank" class="btn-gold">
              <i class="fab fa-whatsapp"></i>
              <span>Book with Yash</span>
            </a>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ============================================================
       LOCATION SECTION
  ============================================================ -->
  <section id="location" class="section" style="background:var(--black-soft);">
    <div class="container">
      <div class="section-label reveal">Find Us</div>
      <h2 class="section-title reveal">Visit <em>BT Brothers</em></h2>
      <div class="gold-line reveal"></div>

      <div class="location-grid">

        <!-- Map -->
        <div class="location-map reveal-left">
          <i class="fas fa-map-marker-alt"></i>
          <p>Google Maps</p>
          <div class="location-map-placeholder-text">
            <!-- Replace this div with a real Google Maps iframe embed when location is finalized -->
            Add your Google Maps embed here — iframe with your salon address
          </div>
        </div>

        <!-- Contact Details -->
        <div class="contact-items reveal-right">

          <div class="contact-item">
            <div class="contact-icon"><i class="fas fa-map-marker-alt"></i></div>
            <div>
              <h4>Address</h4>
              <p>BT Brothers Salon<br>[Your Full Street Address]<br>[City, State – PIN Code]</p>
            </div>
          </div>

          <div class="contact-item">
            <div class="contact-icon"><i class="fas fa-phone"></i></div>
            <div>
              <h4>Phone / WhatsApp</h4>
              <p><a href="tel:+919511220814">+91 95112 20814</a><br>
                 <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank">WhatsApp Booking Available</a></p>
            </div>
          </div>

          <div class="contact-item">
            <div class="contact-icon"><i class="fab fa-instagram"></i></div>
            <div>
              <h4>Instagram</h4>
              <p><a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank" rel="noopener">@b.t.brothers_hair_beauty</a></p>
            </div>
          </div>

          <div class="contact-item">
            <div class="contact-icon"><i class="fas fa-clock"></i></div>
            <div>
              <h4>Working Hours</h4>
              <div class="hours-grid">
                <span class="today">Monday – Friday</span>
                <span class="today">9:00 AM – 9:00 PM</span>
                <span>Saturday</span>
                <span>9:00 AM – 9:00 PM</span>
                <span>Sunday</span>
                <span>10:00 AM – 7:00 PM</span>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>

  <!-- ============================================================
       FOOTER
  ============================================================ -->
  <footer id="footer">
    <div class="footer-main">
      <div class="container">
        <div class="footer-grid">

          <!-- Brand -->
          <div class="footer-brand">
            <div class="footer-brand-logo">BT BROTHERS</div>
            <p>Premium unisex grooming by Mr. Yash More — trained by Javed Habib. Where every visit is an experience, and every look is a masterpiece.</p>
            <div class="footer-socials">
              <a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank" class="footer-social-link" aria-label="Instagram">
                <i class="fab fa-instagram"></i>
              </a>
              <a href="https://wa.me/919511220814" target="_blank" class="footer-social-link" aria-label="WhatsApp">
                <i class="fab fa-whatsapp"></i>
              </a>
              <a href="tel:+919511220814" class="footer-social-link" aria-label="Phone">
                <i class="fas fa-phone"></i>
              </a>
            </div>
          </div>

          <!-- Quick Links -->
          <div class="footer-col">
            <h4>Quick Links</h4>
            <ul>
              <li><a href="#hero"><i class="fas fa-chevron-right"></i> Home</a></li>
              <li><a href="#about"><i class="fas fa-chevron-right"></i> About Us</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Services</a></li>
              <li><a href="#gallery"><i class="fas fa-chevron-right"></i> Gallery</a></li>
              <li><a href="#testimonials"><i class="fas fa-chevron-right"></i> Reviews</a></li>
              <li><a href="#owner"><i class="fas fa-chevron-right"></i> Our Expert</a></li>
            </ul>
          </div>

          <!-- Services -->
          <div class="footer-col">
            <h4>Our Services</h4>
            <ul>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Precision Haircut</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Beard Styling</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Hair Spa</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Facial Treatment</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Grooming Package</a></li>
              <li><a href="#services"><i class="fas fa-chevron-right"></i> Styling & Makeover</a></li>
            </ul>
          </div>

          <!-- Contact -->
          <div class="footer-col">
            <h4>Contact Us</h4>
            <div class="footer-contact-item">
              <i class="fas fa-map-marker-alt"></i>
              <span>[Your Salon Address]<br>[City, State – PIN]</span>
            </div>
            <div class="footer-contact-item">
              <i class="fas fa-phone"></i>
              <span><a href="tel:+919511220814">+91 95112 20814</a></span>
            </div>
            <div class="footer-contact-item">
              <i class="fab fa-whatsapp"></i>
              <span><a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank">Book on WhatsApp</a></span>
            </div>
            <div class="footer-contact-item">
              <i class="fab fa-instagram"></i>
              <span><a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank">@b.t.brothers_hair_beauty</a></span>
            </div>
            <div class="footer-contact-item">
              <i class="fas fa-clock"></i>
              <span>Mon–Fri: 9AM–9PM<br>Sat–Sun: 10AM–7PM</span>
            </div>
          </div>

        </div>
      </div>
    </div>

    <div class="container">
      <div class="footer-bottom">
        <p>© 2025 <span>BT Brothers</span>. All rights reserved. Owned by <span>Mr. Yash More</span>.</p>
        <div class="footer-bottom-links">
          <a href="#">Privacy Policy</a>
          <a href="#">Terms of Service</a>
        </div>
      </div>
    </div>
  </footer>

  <!-- ============================================================
       BOOKING MODAL (optional quick-booking popup)
  ============================================================ -->
  <div class="modal-overlay" id="bookingModal">
    <div class="modal">
      <button class="modal-close" onclick="closeModal()" aria-label="Close modal">
        <i class="fas fa-times"></i>
      </button>
      <h3>Book Your Appointment</h3>
      <p>Choose how you'd like to connect with BT Brothers and lock in your slot.</p>
      <div class="modal-options">
        <a href="https://wa.me/919511220814?text=I%20want%20to%20book%20an%20appointment" target="_blank" class="modal-option">
          <i class="fab fa-whatsapp"></i>
          <span>Book via WhatsApp — Instant Confirmation</span>
        </a>
        <a href="tel:+919511220814" class="modal-option">
          <i class="fas fa-phone"></i>
          <span>Call Us Directly — +91 95112 20814</span>
        </a>
        <a href="https://instagram.com/b.t.brothers_hair_beauty" target="_blank" class="modal-option">
          <i class="fab fa-instagram"></i>
          <span>DM on Instagram — @b.t.brothers_hair_beauty</span>
        </a>
      </div>
    </div>
  </div>

  <!-- ============================================================
       JAVASCRIPT
  ============================================================ -->
  <script>
    /* =============================================
       LOADER
    ============================================= */
    window.addEventListener('load', function () {
      setTimeout(function () {
        const loader = document.getElementById('loader');
        if (loader) loader.classList.add('hidden');
      }, 2000);
    });

    /* =============================================
       NAVBAR SCROLL
    ============================================= */
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', function () {
      if (window.scrollY > 60) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    }, { passive: true });

    /* =============================================
       MOBILE MENU
    ============================================= */
    function toggleMobileMenu() {
      const menu = document.getElementById('mobileMenu');
      const overlay = document.getElementById('mobileOverlay');
      const hamburger = document.getElementById('hamburger');
      const isOpen = menu.classList.contains('open');
      if (isOpen) {
        menu.classList.remove('open');
        overlay.classList.remove('show');
        hamburger.classList.remove('open');
        document.body.style.overflow = '';
      } else {
        menu.classList.add('open');
        overlay.classList.add('show');
        hamburger.classList.add('open');
        document.body.style.overflow = 'hidden';
      }
    }
    function closeMobileMenu() {
      document.getElementById('mobileMenu').classList.remove('open');
      document.getElementById('mobileOverlay').classList.remove('show');
      document.getElementById('hamburger').classList.remove('open');
      document.body.style.overflow = '';
    }
    document.getElementById('mobileOverlay').addEventListener('click', closeMobileMenu);

    /* =============================================
       SCROLL TO TOP
    ============================================= */
    const scrollTopBtn = document.getElementById('scrollTop');
    window.addEventListener('scroll', function () {
      if (window.scrollY > 400) {
        scrollTopBtn.classList.add('show');
      } else {
        scrollTopBtn.classList.remove('show');
      }
    }, { passive: true });
    scrollTopBtn.addEventListener('click', function () {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    /* =============================================
       REVEAL ON SCROLL
    ============================================= */
    const revealElements = document.querySelectorAll('.reveal, .reveal-left, .reveal-right');
    const revealObserver = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry) {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          revealObserver.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });

    revealElements.forEach(function (el) {
      revealObserver.observe(el);
    });

    /* =============================================
       ANIMATED COUNTERS
    ============================================= */
    function animateCounter(el, target, duration) {
      let start = 0;
      const step = target / (duration / 16);
      const timer = setInterval(function () {
        start += step;
        if (start >= target) {
          el.textContent = target;
          clearInterval(timer);
        } else {
          el.textContent = Math.floor(start);
        }
      }, 16);
    }

    const counterSection = document.getElementById('counters');
    let countersStarted = false;
    const counterObserver = new IntersectionObserver(function (entries) {
      if (entries[0].isIntersecting && !countersStarted) {
        countersStarted = true;
        document.querySelectorAll('.counter').forEach(function (counter) {
          const target = parseInt(counter.getAttribute('data-target'));
          animateCounter(counter, target, 1600);
        });
      }
    }, { threshold: 0.3 });
    if (counterSection) counterObserver.observe(counterSection);

    /* =============================================
       BOOKING MODAL
    ============================================= */
    function openModal() {
      document.getElementById('bookingModal').classList.add('open');
      document.body.style.overflow = 'hidden';
    }
    function closeModal() {
      document.getElementById('bookingModal').classList.remove('open');
      document.body.style.overflow = '';
    }
    document.getElementById('bookingModal').addEventListener('click', function (e) {
      if (e.target === this) closeModal();
    });
    document.addEventListener('keydown', function (e) {
      if (e.key === 'Escape') closeModal();
    });

    /* =============================================
       SMOOTH SCROLL FOR NAV LINKS
    ============================================= */
    document.querySelectorAll('a[href^="#"]').forEach(function (anchor) {
      anchor.addEventListener('click', function (e) {
        const href = this.getAttribute('href');
        if (href === '#') return;
        const target = document.querySelector(href);
        if (target) {
          e.preventDefault();
          const offset = 76;
          const top = target.getBoundingClientRect().top + window.pageYOffset - offset;
          window.scrollTo({ top: top, behavior: 'smooth' });
        }
      });
    });

    /* =============================================
       ACTIVE NAV HIGHLIGHT ON SCROLL
    ============================================= */
    const sections = document.querySelectorAll('section[id]');
    const navLinks = document.querySelectorAll('.nav-links a');
    window.addEventListener('scroll', function () {
      let current = '';
      sections.forEach(function (section) {
        const sectionTop = section.offsetTop - 100;
        if (window.pageYOffset >= sectionTop) {
          current = section.getAttribute('id');
        }
      });
      navLinks.forEach(function (link) {
        link.style.color = '';
        if (link.getAttribute('href') === '#' + current) {
          link.style.color = 'var(--gold)';
        }
      });
    }, { passive: true });
  </script>

</body>
</html>
