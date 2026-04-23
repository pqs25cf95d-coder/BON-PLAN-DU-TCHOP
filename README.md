<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Le Ngori & Bollet — Sandwichs & Salades à Dakar</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  /* ───── VARIABLES ───── */
  :root {
    --cream: #FDF6ED;
    --terracotta: #C4522A;
    --terra-light: #E8795A;
    --terra-dark: #8C3519;
    --green: #2A5C3F;
    --green-light: #3D7A56;
    --dark: #1A1208;
    --mid: #5C4A35;
    --sand: #E8D5B0;
    --sand-light: #F5EDDA;
    --white: #FFFDF9;
  }

  /* ───── BASE ───── */
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--dark);
    overflow-x: hidden;
  }

  h1, h2, h3 { font-family: 'Playfair Display', serif; }

  /* ───── NAV ───── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1rem 2rem;
    background: rgba(253,246,237,0.92);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--sand);
  }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 900;
    color: var(--terracotta);
    text-decoration: none;
    letter-spacing: -0.5px;
  }
  .nav-logo span { color: var(--green); }

  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    text-decoration: none; color: var(--mid);
    font-size: 0.9rem; font-weight: 500;
    letter-spacing: 0.03em;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--terracotta); }

  .nav-cta {
    background: var(--terracotta);
    color: white !important;
    padding: 0.5rem 1.2rem;
    border-radius: 2rem;
    transition: background 0.2s !important;
  }
  .nav-cta:hover { background: var(--terra-dark) !important; color: white !important; }

  /* ───── HERO ───── */
  #hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    padding-top: 70px;
    position: relative; overflow: hidden;
  }

  .hero-left {
    display: flex; flex-direction: column; justify-content: center;
    padding: 4rem 3rem 4rem 5rem;
  }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: var(--sand); color: var(--terracotta);
    font-size: 0.78rem; font-weight: 600; letter-spacing: 0.1em;
    text-transform: uppercase; padding: 0.4rem 1rem;
    border-radius: 2rem; margin-bottom: 1.5rem;
    width: fit-content;
  }

  .hero-title {
    font-size: clamp(2.8rem, 5vw, 4.5rem);
    line-height: 1.05;
    color: var(--dark);
    margin-bottom: 1.5rem;
  }
  .hero-title .accent { color: var(--terracotta); font-style: italic; }

  .hero-sub {
    font-size: 1.1rem; color: var(--mid);
    line-height: 1.7; max-width: 420px;
    margin-bottom: 2.5rem;
  }

  .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }

  .btn-primary {
    background: var(--terracotta); color: white;
    padding: 0.85rem 2rem; border-radius: 3rem;
    text-decoration: none; font-weight: 600; font-size: 0.95rem;
    transition: all 0.25s; border: 2px solid var(--terracotta);
    display: inline-flex; align-items: center; gap: 0.5rem;
  }
  .btn-primary:hover { background: var(--terra-dark); border-color: var(--terra-dark); transform: translateY(-2px); }

  .btn-outline {
    background: transparent; color: var(--green);
    padding: 0.85rem 2rem; border-radius: 3rem;
    text-decoration: none; font-weight: 600; font-size: 0.95rem;
    border: 2px solid var(--green);
    transition: all 0.25s;
    display: inline-flex; align-items: center; gap: 0.5rem;
  }
  .btn-outline:hover { background: var(--green); color: white; transform: translateY(-2px); }

  .hero-stats {
    display: flex; gap: 2rem; margin-top: 3rem;
    padding-top: 2rem; border-top: 1px solid var(--sand);
  }
  .hero-stat strong { display: block; font-size: 1.8rem; color: var(--terracotta); font-family: 'Playfair Display', serif; }
  .hero-stat span { font-size: 0.8rem; color: var(--mid); text-transform: uppercase; letter-spacing: 0.05em; }

  .hero-right {
    background: var(--green);
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }

  .hero-visual {
    position: relative; z-index: 2;
    text-align: center; color: white;
    padding: 3rem;
  }

  .hero-emoji-stack {
    font-size: 5rem; line-height: 1.2;
    display: block; margin-bottom: 1rem;
    animation: float 3s ease-in-out infinite;
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }

  .hero-visual h3 {
    font-family: 'Playfair Display', serif;
    font-size: 2rem; font-style: italic;
    color: var(--sand); margin-bottom: 0.5rem;
  }
  .hero-visual p { color: rgba(255,255,255,0.7); font-size: 0.9rem; }

  .hero-deco {
    position: absolute; border-radius: 50%;
    background: rgba(255,255,255,0.04);
  }
  .hero-deco-1 { width: 300px; height: 300px; top: -80px; right: -80px; }
  .hero-deco-2 { width: 200px; height: 200px; bottom: -50px; left: -50px; }

  /* ───── SECTIONS COMMUNES ───── */
  section { padding: 5rem 5rem; }

  .section-label {
    display: inline-block;
    font-size: 0.75rem; font-weight: 600; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--terracotta);
    margin-bottom: 0.75rem;
  }

  .section-title {
    font-size: clamp(2rem, 3.5vw, 3rem);
    color: var(--dark); line-height: 1.15;
    margin-bottom: 1rem;
  }

  .section-sub {
    color: var(--mid); font-size: 1rem;
    line-height: 1.7; max-width: 550px;
  }

  /* ───── À PROPOS ───── */
  #apropos {
    background: var(--sand-light);
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem;
    align-items: center;
  }

  .apropos-features { display: grid; gap: 1.5rem; margin-top: 2rem; }
  .feat {
    display: flex; gap: 1rem; align-items: flex-start;
    background: white; padding: 1.2rem 1.5rem;
    border-radius: 1rem; border: 1px solid var(--sand);
  }
  .feat-icon {
    font-size: 1.5rem; width: 2.5rem; height: 2.5rem;
    display: flex; align-items: center; justify-content: center;
    background: var(--sand); border-radius: 0.6rem; flex-shrink: 0;
  }
  .feat-text strong { display: block; font-size: 0.95rem; margin-bottom: 0.2rem; }
  .feat-text p { font-size: 0.85rem; color: var(--mid); line-height: 1.5; }

  .apropos-right {
    display: flex; flex-direction: column; gap: 1.5rem;
  }

  .quote-box {
    background: var(--green); color: white;
    padding: 2rem; border-radius: 1.5rem;
  }
  .quote-box p {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-style: italic;
    line-height: 1.5; margin-bottom: 1rem;
  }
  .quote-box cite { font-size: 0.85rem; opacity: 0.7; }

  .zones-box {
    background: var(--terracotta); color: white;
    padding: 1.5rem; border-radius: 1.5rem;
  }
  .zones-box h4 { font-size: 1rem; margin-bottom: 0.75rem; }
  .zones-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .zone-tag {
    background: rgba(255,255,255,0.2);
    padding: 0.3rem 0.8rem; border-radius: 1rem;
    font-size: 0.8rem; font-weight: 500;
  }

  /* ───── MENU ───── */
  #menu { background: var(--cream); }
  .menu-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; }
  .menu-tabs { display: flex; gap: 0.5rem; }
  .tab-btn {
    padding: 0.5rem 1.2rem; border-radius: 2rem;
    border: 2px solid var(--sand); background: transparent;
    color: var(--mid); font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem; font-weight: 500; cursor: pointer;
    transition: all 0.2s;
  }
  .tab-btn.active { background: var(--terracotta); color: white; border-color: var(--terracotta); }

  .menu-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
  .menu-grid.hidden { display: none; }

  .menu-card {
    background: white; border-radius: 1.2rem;
    border: 1px solid var(--sand); overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
    cursor: pointer; position: relative;
  }
  .menu-card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(26,18,8,0.1); }
  .menu-card.selected { border-color: var(--terracotta); box-shadow: 0 0 0 3px rgba(196,82,42,0.15); }
  .menu-card.selected::after {
    content: '✓'; position: absolute; top: 0.75rem; right: 0.75rem;
    background: var(--terracotta); color: white;
    width: 1.5rem; height: 1.5rem; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.8rem; font-weight: 700;
  }

  .card-emoji { font-size: 3.5rem; text-align: center; padding: 1.5rem 1rem 0.5rem; }
  .card-body { padding: 1rem 1.2rem 1.2rem; }
  .card-body h3 { font-family: 'Playfair Display', serif; font-size: 1.1rem; margin-bottom: 0.3rem; }
  .card-body p { font-size: 0.82rem; color: var(--mid); line-height: 1.5; margin-bottom: 0.75rem; }
  .card-footer { display: flex; justify-content: space-between; align-items: center; }
  .card-price { font-weight: 700; font-size: 1rem; color: var(--terracotta); }
  .card-add {
    width: 2rem; height: 2rem; border-radius: 50%;
    background: var(--sand); border: none; cursor: pointer;
    font-size: 1.2rem; display: flex; align-items: center; justify-content: center;
    transition: all 0.2s;
  }
  .card-add:hover { background: var(--terracotta); color: white; }

  /* ───── COMMANDE ───── */
  #commande {
    background: var(--dark); color: var(--cream);
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem;
    align-items: start;
  }

  #commande .section-title { color: var(--sand); }
  #commande .section-sub { color: rgba(253,246,237,0.6); }

  .order-form { display: flex; flex-direction: column; gap: 1rem; }

  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-group label { font-size: 0.85rem; color: rgba(253,246,237,0.7); font-weight: 500; }
  .form-group input, .form-group textarea, .form-group select {
    background: rgba(255,255,255,0.07);
    border: 1px solid rgba(255,255,255,0.12);
    color: var(--cream); font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem; padding: 0.75rem 1rem;
    border-radius: 0.75rem; outline: none;
    transition: border-color 0.2s;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
    border-color: var(--terra-light);
  }
  .form-group textarea { resize: vertical; min-height: 80px; }
  .form-group select option { background: var(--dark); }

  .selected-items-box {
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 0.75rem; padding: 1rem;
    min-height: 80px;
  }
  .selected-items-box p { font-size: 0.85rem; color: rgba(253,246,237,0.5); }
  .selected-tag {
    display: inline-flex; align-items: center; gap: 0.4rem;
    background: rgba(196,82,42,0.3); color: var(--terra-light);
    padding: 0.3rem 0.7rem; border-radius: 1rem;
    font-size: 0.82rem; margin: 0.2rem;
  }
  .remove-item { cursor: pointer; opacity: 0.7; }
  .remove-item:hover { opacity: 1; }

  .order-total {
    display: flex; justify-content: space-between; align-items: center;
    background: rgba(196,82,42,0.15); padding: 0.75rem 1rem;
    border-radius: 0.75rem; border: 1px solid rgba(196,82,42,0.3);
  }
  .order-total span { color: rgba(253,246,237,0.7); font-size: 0.9rem; }
  .order-total strong { color: var(--terra-light); font-size: 1.1rem; }

  .btn-whatsapp {
    background: #25D366; color: white;
    padding: 1rem 2rem; border-radius: 3rem;
    border: none; font-family: 'DM Sans', sans-serif;
    font-size: 1rem; font-weight: 600; cursor: pointer;
    display: flex; align-items: center; justify-content: center; gap: 0.75rem;
    transition: all 0.25s; width: 100%;
  }
  .btn-whatsapp:hover { background: #1da851; transform: translateY(-2px); }
  .btn-whatsapp:disabled { background: #555; cursor: not-allowed; transform: none; }

  .order-right { position: sticky; top: 100px; }
  .delivery-info {
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 1rem; padding: 1.5rem;
  }
  .delivery-info h4 { font-size: 1rem; margin-bottom: 1rem; color: var(--sand); }
  .delivery-info ul { list-style: none; display: flex; flex-direction: column; gap: 0.75rem; }
  .delivery-info li { font-size: 0.88rem; color: rgba(253,246,237,0.6); display: flex; align-items: center; gap: 0.5rem; }
  .delivery-info li::before { content: '→'; color: var(--terracotta); }

  /* ───── AVIS ───── */
  #avis { background: var(--sand-light); }
  .avis-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; }

  .avis-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-bottom: 3rem; }
  .avis-card {
    background: white; border-radius: 1.2rem;
    padding: 1.5rem; border: 1px solid var(--sand);
    animation: fadeIn 0.4s ease;
  }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: none; } }

  .avis-card .stars { color: #F5A623; font-size: 1rem; margin-bottom: 0.75rem; }
  .avis-card p { font-size: 0.9rem; color: var(--dark); line-height: 1.6; margin-bottom: 1rem; font-style: italic; }
  .avis-card .author { font-size: 0.8rem; color: var(--mid); font-weight: 600; }
  .avis-card .date { font-size: 0.75rem; color: #aaa; }

  .add-avis-panel {
    background: white; border-radius: 1.5rem;
    border: 2px solid var(--sand); padding: 2rem;
    max-width: 600px;
  }
  .add-avis-panel h3 { font-size: 1.4rem; margin-bottom: 1.5rem; }

  .star-select { display: flex; gap: 0.4rem; margin-bottom: 1rem; }
  .star-btn {
    font-size: 1.8rem; cursor: pointer;
    background: none; border: none;
    transition: transform 0.15s;
    line-height: 1;
  }
  .star-btn:hover { transform: scale(1.2); }

  .avis-form { display: flex; flex-direction: column; gap: 0.8rem; }
  .avis-form input, .avis-form textarea {
    border: 1.5px solid var(--sand);
    border-radius: 0.75rem; padding: 0.75rem 1rem;
    font-family: 'DM Sans', sans-serif; font-size: 0.92rem;
    outline: none; width: 100%;
    transition: border-color 0.2s;
  }
  .avis-form input:focus, .avis-form textarea:focus { border-color: var(--terracotta); }
  .avis-form textarea { resize: vertical; min-height: 90px; }
  .btn-submit-avis {
    background: var(--green); color: white;
    padding: 0.85rem 2rem; border-radius: 3rem;
    border: none; font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem; font-weight: 600; cursor: pointer;
    transition: all 0.2s; width: fit-content;
  }
  .btn-submit-avis:hover { background: var(--green-light); transform: translateY(-1px); }

  .no-avis { grid-column: 1/-1; text-align: center; padding: 3rem; color: var(--mid); font-style: italic; }

  /* ───── FOOTER ───── */
  footer {
    background: var(--dark); color: rgba(253,246,237,0.6);
    padding: 3rem 5rem;
    display: grid; grid-template-columns: 2fr 1fr 1fr;
    gap: 3rem;
  }
  .footer-brand .logo { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--cream); margin-bottom: 0.75rem; }
  .footer-brand .logo span { color: var(--terracotta); }
  .footer-brand p { font-size: 0.88rem; line-height: 1.6; }
  footer h4 { color: var(--cream); font-size: 0.9rem; margin-bottom: 1rem; }
  footer ul { list-style: none; display: flex; flex-direction: column; gap: 0.5rem; }
  footer ul li a { color: rgba(253,246,237,0.5); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
  footer ul li a:hover { color: var(--terracotta); }
  .footer-bottom {
    background: var(--dark); color: rgba(253,246,237,0.3);
    text-align: center; padding: 1rem 5rem;
    font-size: 0.78rem; border-top: 1px solid rgba(255,255,255,0.05);
  }

  /* ───── TOAST ───── */
  .toast {
    position: fixed; bottom: 2rem; right: 2rem;
    background: var(--green); color: white;
    padding: 0.85rem 1.5rem; border-radius: 0.75rem;
    font-size: 0.9rem; font-weight: 500;
    box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    transform: translateY(100px); opacity: 0;
    transition: all 0.3s; z-index: 999;
  }
  .toast.show { transform: translateY(0); opacity: 1; }

  /* ───── MOBILE ───── */
  .burger { display: none; background: none; border: none; font-size: 1.5rem; cursor: pointer; }
  
  @media (max-width: 900px) {
    .burger { display: block; }
    .nav-links { display: none; position: absolute; top: 100%; left: 0; right: 0; background: var(--cream); flex-direction: column; padding: 1rem 2rem; border-bottom: 1px solid var(--sand); }
    .nav-links.open { display: flex; }
    #hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 3rem 2rem; }
    .hero-right { min-height: 250px; }
    section { padding: 3rem 2rem; }
    #apropos, #commande { grid-template-columns: 1fr; gap: 2rem; }
    .menu-grid, .avis-grid { grid-template-columns: 1fr 1fr; }
    .menu-header { flex-direction: column; align-items: flex-start; gap: 1rem; }
    .avis-header { flex-direction: column; align-items: flex-start; gap: 1rem; }
    footer { grid-template-columns: 1fr; padding: 2rem; gap: 2rem; }
    .footer-bottom { padding: 1rem 2rem; }
  }

  @media (max-width: 600px) {
    .menu-grid, .avis-grid { grid-template-columns: 1fr; }
    .hero-stats { gap: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">Le Ngori <span>&</span> Bollet</a>
  <button class="burger" onclick="toggleMenu()">☰</button>
  <ul class="nav-links" id="navLinks">
    <li><a href="#apropos">À propos</a></li>
    <li><a href="#menu">Menu</a></li>
    <li><a href="#commande">Commander</a></li>
    <li><a href="#avis">Avis</a></li>
    <li><a href="#commande" class="nav-cta">🛵 Commander</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <span class="hero-badge">🌿 Livraison en bureau — Dakar</span>
    <h1 class="hero-title">
      Saveurs fraîches<br>
      <span class="accent">livrées</span> chez vous
    </h1>
    <p class="hero-sub">
      Sandwichs généreux et salades fraîches préparés avec amour,
      livrés directement dans vos bureaux à Dakar.
      Fait maison, vinaigrette maison, chaque jour.
    </p>
    <div class="hero-btns">
      <a href="#commande" class="btn-primary">🛵 Commander maintenant</a>
      <a href="#menu" class="btn-outline">📋 Voir le menu</a>
    </div>
    <div class="hero-stats">
      <div class="hero-stat"><strong>100%</strong><span>Fait maison</span></div>
      <div class="hero-stat"><strong>J+0</strong><span>Livraison jour même</span></div>
      <div class="hero-stat"><strong>★ 5/5</strong><span>Clients satisfaits</span></div>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-deco hero-deco-1"></div>
    <div class="hero-deco hero-deco-2"></div>
    <div class="hero-visual">
      <span class="hero-emoji-stack">🥖🥗🍋</span>
      <h3>Frais & Savoureux</h3>
      <p>Préparé chaque matin avec des ingrédients frais</p>
    </div>
  </div>
</section>

<!-- À PROPOS -->
<section id="apropos">
  <div>
    <span class="section-label">Notre histoire</span>
    <h2 class="section-title">Une cuisine sincère,<br>pour les travailleurs</h2>
    <p class="section-sub">
      Le Ngori & Bollet est né d'une idée simple : offrir aux professionnels de Dakar 
      une alternative saine, goûteuse et accessible à la pause déjeuner.
    </p>
    <div class="apropos-features">
      <div class="feat">
        <span class="feat-icon">🥬</span>
        <div class="feat-text">
          <strong>Ingrédients frais du marché</strong>
          <p>Approvisionnement local, chaque matin, pour garantir fraîcheur et qualité.</p>
        </div>
      </div>
      <div class="feat">
        <span class="feat-icon">🫙</span>
        <div class="feat-text">
          <strong>Vinaigrette maison</strong>
          <p>Notre sauce signature, préparée selon une recette exclusive.</p>
        </div>
      </div>
      <div class="feat">
        <span class="feat-icon">🛵</span>
        <div class="feat-text">
          <strong>Livraison rapide en bureau</strong>
          <p>Commandez avant 10h, recevez votre repas pour le déjeuner.</p>
        </div>
      </div>
    </div>
  </div>
  <div class="apropos-right">
    <div class="quote-box">
      <p>"On mange avec les yeux d'abord, puis avec le cœur."</p>
      <cite>— L'équipe Le Ngori & Bollet</cite>
    </div>
    <div class="zones-box">
      <h4>📍 Zones de livraison</h4>
      <div class="zones-tags">
        <span class="zone-tag">Plateau</span>
        <span class="zone-tag">Almadies</span>
        <span class="zone-tag">Point E</span>
        <span class="zone-tag">Mermoz</span>
        <span class="zone-tag">Sacré-Cœur</span>
        <span class="zone-tag">Fann</span>
        <span class="zone-tag">Dakar Centre</span>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-header">
    <div>
      <span class="section-label">Notre sélection</span>
      <h2 class="section-title">Le Menu du Jour</h2>
    </div>
    <div class="menu-tabs">
      <button class="tab-btn active" onclick="switchTab('sandwichs', this)">🥖 Sandwichs</button>
      <button class="tab-btn" onclick="switchTab('salades', this)">🥗 Salades</button>
      <button class="tab-btn" onclick="switchTab('boissons', this)">🥤 Boissons</button>
    </div>
  </div>

  <div class="menu-grid" id="grid-sandwichs">
    <div class="menu-card" onclick="toggleItem(this, 'Ngori Classic', 1500)">
      <div class="card-emoji">🥖</div>
      <div class="card-body">
        <h3>Ngori Classic</h3>
        <p>Poulet grillé, salade, tomate, oignon, vinaigrette maison</p>
        <div class="card-footer">
          <span class="card-price">1 500 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Bollet Thon', 1200)">
      <div class="card-emoji">🐟</div>
      <div class="card-body">
        <h3>Bollet Thon</h3>
        <p>Thon, œuf dur, cornichons, moutarde, salade verte</p>
        <div class="card-footer">
          <span class="card-price">1 200 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Bollet Avocat', 1300)">
      <div class="card-emoji">🥑</div>
      <div class="card-body">
        <h3>Bollet Avocat</h3>
        <p>Avocat frais, tomate, vinaigrette citronnée, herbes</p>
        <div class="card-footer">
          <span class="card-price">1 300 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Ngori Viande', 1800)">
      <div class="card-emoji">🥩</div>
      <div class="card-body">
        <h3>Ngori Viande</h3>
        <p>Bœuf mariné, sauce piment doux, oignon caramélisé</p>
        <div class="card-footer">
          <span class="card-price">1 800 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Bollet Végé', 1000)">
      <div class="card-emoji">🌿</div>
      <div class="card-body">
        <h3>Bollet Végé</h3>
        <p>Légumes grillés, houmous maison, poivrons, salade</p>
        <div class="card-footer">
          <span class="card-price">1 000 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Ngori Mixte', 2000)">
      <div class="card-emoji">🎉</div>
      <div class="card-body">
        <h3>Ngori Mixte</h3>
        <p>Poulet + crevettes, sauce cocktail, avocat, tomate</p>
        <div class="card-footer">
          <span class="card-price">2 000 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
  </div>

  <div class="menu-grid hidden" id="grid-salades">
    <div class="menu-card" onclick="toggleItem(this, 'Salade Verte Maison', 1000)">
      <div class="card-emoji">🥗</div>
      <div class="card-body">
        <h3>Salade Verte Maison</h3>
        <p>Laitue, concombre, tomate, vinaigrette maison</p>
        <div class="card-footer">
          <span class="card-price">1 000 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Salade Composée', 1500)">
      <div class="card-emoji">🥙</div>
      <div class="card-body">
        <h3>Salade Composée</h3>
        <p>Poulet, avocat, maïs, œuf, carottes râpées, laitue</p>
        <div class="card-footer">
          <span class="card-price">1 500 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Salade Thon', 1300)">
      <div class="card-emoji">🐠</div>
      <div class="card-body">
        <h3>Salade Thon</h3>
        <p>Thon, haricots verts, tomate, olive, sauce citron</p>
        <div class="card-footer">
          <span class="card-price">1 300 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
  </div>

  <div class="menu-grid hidden" id="grid-boissons">
    <div class="menu-card" onclick="toggleItem(this, 'Bissap Maison', 500)">
      <div class="card-emoji">🌺</div>
      <div class="card-body">
        <h3>Bissap Maison</h3>
        <p>Infusion de fleurs d'hibiscus fraîches, légèrement sucrée</p>
        <div class="card-footer">
          <span class="card-price">500 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Jus de Gingembre', 500)">
      <div class="card-emoji">🫚</div>
      <div class="card-body">
        <h3>Jus de Gingembre</h3>
        <p>Gingembre frais pressé, citron, miel naturel</p>
        <div class="card-footer">
          <span class="card-price">500 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
    <div class="menu-card" onclick="toggleItem(this, 'Eau minérale', 300)">
      <div class="card-emoji">💧</div>
      <div class="card-body">
        <h3>Eau minérale</h3>
        <p>Eau fraîche, bouteille 500ml</p>
        <div class="card-footer">
          <span class="card-price">300 FCFA</span>
          <button class="card-add">+</button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- COMMANDE -->
<section id="commande">
  <div>
    <span class="section-label" style="color:var(--terra-light)">Passer commande</span>
    <h2 class="section-title">Prêt à commander ?</h2>
    <p class="section-sub">
      Sélectionnez vos plats dans le menu ci-dessus, remplissez le formulaire
      et on vous contacte via WhatsApp pour confirmer la livraison.
    </p>

    <div class="order-form" style="margin-top:2rem">
      <div class="form-group">
        <label>Vos articles sélectionnés</label>
        <div class="selected-items-box" id="selectedItemsBox">
          <p id="emptyMsg">Aucun article sélectionné — choisissez dans le menu ↑</p>
        </div>
      </div>
      <div class="order-total" id="orderTotal" style="display:none">
        <span>Total estimé</span>
        <strong id="totalAmount">0 FCFA</strong>
      </div>
      <div class="form-group">
        <label>Votre prénom *</label>
        <input type="text" id="orderName" placeholder="Ex: Fatou">
      </div>
      <div class="form-group">
        <label>Bureau / Entreprise *</label>
        <input type="text" id="orderBureau" placeholder="Ex: Bureau 5ème étage, Immeuble XY">
      </div>
      <div class="form-group">
        <label>Heure souhaitée</label>
        <select id="orderHeure">
          <option value="12h00">12h00</option>
          <option value="12h30">12h30</option>
          <option value="13h00">13h00</option>
          <option value="13h30">13h30</option>
        </select>
      </div>
      <div class="form-group">
        <label>Note / Allergie (optionnel)</label>
        <textarea id="orderNote" placeholder="Ex: Sans oignon, allergie à la moutarde..."></textarea>
      </div>
      <button class="btn-whatsapp" onclick="sendOrder()" id="whatsappBtn">
        <span>💬</span> Envoyer la commande sur WhatsApp
      </button>
    </div>
  </div>

  <div class="order-right">
    <div class="delivery-info">
      <h4>📦 Infos livraison</h4>
      <ul>
        <li>Commandez avant <strong style="color:var(--terra-light)">10h30</strong> pour une livraison à midi</li>
        <li>Livraison gratuite dans un rayon de 2km</li>
        <li>Paiement à la livraison (cash ou Orange Money)</li>
        <li>Minimum de commande : 1 000 FCFA</li>
        <li>Disponible du lundi au vendredi</li>
        <li>Emballages propres et hygiéniques garantis</li>
      </ul>
    </div>

    <div style="background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.1);border-radius:1rem;padding:1.5rem;margin-top:1.5rem;">
      <h4 style="color:var(--sand);font-size:1rem;margin-bottom:1rem;">📅 Abonnements</h4>
      <p style="font-size:0.85rem;color:rgba(253,246,237,0.6);line-height:1.6;">
        Abonnez-vous à la semaine ou au mois et économisez jusqu'à 15% sur vos commandes. 
        Mentionnez-le dans votre note ou contactez-nous directement.
      </p>
    </div>
  </div>
</section>

<!-- AVIS -->
<section id="avis">
  <div class="avis-header">
    <div>
      <span class="section-label">Témoignages</span>
      <h2 class="section-title">Ce que disent nos clients</h2>
    </div>
  </div>

  <div class="avis-grid" id="avisGrid">
    <!-- Avis chargés depuis localStorage + avis par défaut -->
  </div>

  <div class="add-avis-panel">
    <h3>Laisser un avis 💬</h3>
    <div class="star-select" id="starSelect">
      <button class="star-btn" onclick="setStar(1)">☆</button>
      <button class="star-btn" onclick="setStar(2)">☆</button>
      <button class="star-btn" onclick="setStar(3)">☆</button>
      <button class="star-btn" onclick="setStar(4)">☆</button>
      <button class="star-btn" onclick="setStar(5)">☆</button>
    </div>
    <div class="avis-form">
      <input type="text" id="avisNom" placeholder="Votre prénom *">
      <input type="text" id="avisBureau" placeholder="Votre bureau (optionnel)">
      <textarea id="avisTexte" placeholder="Votre commentaire... *"></textarea>
      <button class="btn-submit-avis" onclick="submitAvis()">Publier mon avis ✓</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-brand">
    <div class="logo">Le Ngori <span>&</span> Bollet</div>
    <p>Sandwichs et salades frais, livrés dans vos bureaux à Dakar.<br>Fait maison, avec amour.</p>
  </div>
  <div>
    <h4>Navigation</h4>
    <ul>
      <li><a href="#apropos">À propos</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#commande">Commander</a></li>
      <li><a href="#avis">Avis clients</a></li>
    </ul>
  </div>
  <div>
    <h4>Contact</h4>
    <ul>
      <li><a href="#">📞 WhatsApp</a></li>
      <li><a href="#">📍 Dakar, Sénégal</a></li>
      <li><a href="#">🕐 Lun–Ven 8h–14h</a></li>
    </ul>
  </div>
</footer>
<div class="footer-bottom">
  © 2025 Le Ngori & Bollet — Fait avec ❤️ à Dakar
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
  // ─── CONFIG ───
  const WHATSAPP_NUMBER = "221XXXXXXXXX"; // ← Remplace par ton vrai numéro

  // ─── NAV ───
  function toggleMenu() {
    document.getElementById('navLinks').classList.toggle('open');
  }

  // ─── MENU TABS ───
  function switchTab(tab, btn) {
    document.querySelectorAll('.menu-grid').forEach(g => g.classList.add('hidden'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('grid-' + tab).classList.remove('hidden');
    btn.classList.add('active');
  }

  // ─── SÉLECTION D'ARTICLES ───
  let selectedItems = [];

  function toggleItem(card, name, price) {
    const idx = selectedItems.findIndex(i => i.name === name);
    if (idx > -1) {
      selectedItems.splice(idx, 1);
      card.classList.remove('selected');
    } else {
      selectedItems.push({ name, price });
      card.classList.add('selected');
    }
    renderSelected();
  }

  function renderSelected() {
    const box = document.getElementById('selectedItemsBox');
    const emptyMsg = document.getElementById('emptyMsg');
    const totalBox = document.getElementById('orderTotal');
    const totalAmt = document.getElementById('totalAmount');

    if (selectedItems.length === 0) {
      box.innerHTML = '<p id="emptyMsg">Aucun article sélectionné — choisissez dans le menu ↑</p>';
      totalBox.style.display = 'none';
    } else {
      box.innerHTML = selectedItems.map(i =>
        `<span class="selected-tag">${i.name} – ${i.price.toLocaleString()} FCFA 
          <span class="remove-item" onclick="removeItem('${i.name}')">✕</span>
        </span>`
      ).join('');
      totalBox.style.display = 'flex';
      const total = selectedItems.reduce((s, i) => s + i.price, 0);
      totalAmt.textContent = total.toLocaleString() + ' FCFA';
    }
  }

  function removeItem(name) {
    selectedItems = selectedItems.filter(i => i.name !== name);
    document.querySelectorAll('.menu-card').forEach(card => {
      const h3 = card.querySelector('h3');
      if (h3 && h3.textContent === name) card.classList.remove('selected');
    });
    renderSelected();
  }

  // ─── COMMANDE WHATSAPP ───
  function sendOrder() {
    const nom = document.getElementById('orderName').value.trim();
    const bureau = document.getElementById('orderBureau').value.trim();
    const heure = document.getElementById('orderHeure').value;
    const note = document.getElementById('orderNote').value.trim();

    if (!nom || !bureau) { showToast('⚠️ Merci de remplir votre prénom et bureau !'); return; }
    if (selectedItems.length === 0) { showToast('⚠️ Sélectionnez au moins un article dans le menu !'); return; }

    const total = selectedItems.reduce((s, i) => s + i.price, 0);
    const itemList = selectedItems.map(i => `• ${i.name} – ${i.price.toLocaleString()} FCFA`).join('\n');

    let msg = `🥖 *Nouvelle commande — Le Ngori & Bollet*\n\n`;
    msg += `👤 Nom : ${nom}\n`;
    msg += `🏢 Bureau : ${bureau}\n`;
    msg += `🕐 Heure souhaitée : ${heure}\n\n`;
    msg += `📋 *Articles :*\n${itemList}\n\n`;
    msg += `💰 *Total : ${total.toLocaleString()} FCFA*\n`;
    if (note) msg += `\n📝 Note : ${note}`;

    const url = `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(msg)}`;
    window.open(url, '_blank');
  }

  // ─── AVIS ───
  let currentStars = 0;
  const defaultAvis = [
    { nom: "Aminata S.", bureau: "Cabinet RH, Plateau", stars: 5, texte: "Le Ngori Classic est une tuerie ! La vinaigrette maison est incroyable. Je commande chaque vendredi.", date: "Janvier 2025" },
    { nom: "Moussa D.", bureau: "Banque Centrale", stars: 5, texte: "Livraison à l'heure, sandwich bien garni et frais. Exactement ce qu'il me faut pour la pause déj.", date: "Février 2025" },
    { nom: "Fatou N.", bureau: "5ème étage, Immeuble Alpha", stars: 5, texte: "La salade composée est parfaite pour ceux qui font attention à leur ligne. Je suis conquise !", date: "Mars 2025" },
  ];

  function loadAvis() {
    const saved = JSON.parse(localStorage.getItem('ngori_avis') || '[]');
    const all = [...defaultAvis, ...saved];
    const grid = document.getElementById('avisGrid');
    if (all.length === 0) {
      grid.innerHTML = '<div class="no-avis">Aucun avis pour le moment. Soyez le premier !</div>';
      return;
    }
    grid.innerHTML = all.map(a => `
      <div class="avis-card">
        <div class="stars">${'★'.repeat(a.stars)}${'☆'.repeat(5-a.stars)}</div>
        <p>"${a.texte}"</p>
        <div class="author">— ${a.nom}</div>
        <div class="date">${a.bureau ? a.bureau + ' · ' : ''}${a.date}</div>
      </div>
    `).join('');
  }

  function setStar(n) {
    currentStars = n;
    const btns = document.querySelectorAll('.star-btn');
    btns.forEach((b, i) => { b.textContent = i < n ? '★' : '☆'; });
  }

  function submitAvis() {
    const nom = document.getElementById('avisNom').value.trim();
    const bureau = document.getElementById('avisBureau').value.trim();
    const texte = document.getElementById('avisTexte').value.trim();

    if (!nom) { showToast('⚠️ Merci d\'indiquer votre prénom !'); return; }
    if (!texte) { showToast('⚠️ Veuillez écrire un commentaire !'); return; }
    if (currentStars === 0) { showToast('⚠️ Donnez une note en cliquant sur les étoiles !'); return; }

    const avis = {
      nom, bureau, stars: currentStars, texte,
      date: new Date().toLocaleDateString('fr-FR', { month: 'long', year: 'numeric' })
    };

    const saved = JSON.parse(localStorage.getItem('ngori_avis') || '[]');
    saved.push(avis);
    localStorage.setItem('ngori_avis', JSON.stringify(saved));

    document.getElementById('avisNom').value = '';
    document.getElementById('avisBureau').value = '';
    document.getElementById('avisTexte').value = '';
    setStar(0);

    loadAvis();
    showToast('✅ Merci pour votre avis !');
    document.getElementById('avisGrid').scrollIntoView({ behavior: 'smooth' });
  }

  // ─── TOAST ───
  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 3500);
  }

  // ─── INIT ───
  loadAvis();
</script>
</body>
</html>
