<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Masha Caribbean Food — Zoetermeer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400;1,600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --jungle: #1a3c1e;
  --jungle-mid: #2a5430;
  --palm: #3d7a47;
  --lime: #8bba4a;
  --sun: #f5c842;
  --mango: #f08c2a;
  --flame: #e04e2a;
  --sand: #faf3e0;
  --cream: #fff8ec;
  --bark: #3a2410;
  --text: #1e1208;
  --muted: #6b5040;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--cream);
  color: var(--text);
  overflow-x: hidden;
}

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 999;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 3rem;
  height: 68px;
  background: rgba(26, 60, 30, 0.94);
  backdrop-filter: blur(14px);
  border-bottom: 1px solid rgba(139,186,74,0.18);
}

.nav-brand {
  display: flex;
  align-items: center;
  gap: 10px;
  text-decoration: none;
  color: var(--sun);
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.45rem;
  font-weight: 600;
}

.nav-palm {
  font-size: 1.5rem;
  display: inline-block;
  animation: sway 3.5s ease-in-out infinite;
  transform-origin: bottom center;
}

@keyframes sway {
  0%,100%{transform:rotate(-4deg)}
  50%{transform:rotate(4deg)}
}

.nav-links {
  display: flex;
  gap: 2.2rem;
  list-style: none;
  align-items: center;
}

.nav-links a {
  color: rgba(255,255,255,0.75);
  text-decoration: none;
  font-size: 0.82rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  font-weight: 500;
  transition: color 0.2s;
  position: relative;
}

.nav-links a::after {
  content:'';
  position:absolute;
  bottom:-4px; left:0; right:0;
  height:1.5px;
  background:var(--sun);
  transform:scaleX(0);
  transition:transform 0.25s;
}

.nav-links a:hover { color: var(--sun); }
.nav-links a:hover::after { transform:scaleX(1); }

.nav-cta {
  background: var(--sun) !important;
  color: var(--bark) !important;
  padding: 8px 22px;
  border-radius: 30px;
  font-weight: 500 !important;
}
.nav-cta::after { display:none !important; }
.nav-cta:hover { background: var(--mango) !important; color:#fff !important; }

/* HERO */
.hero {
  min-height: 100vh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse at 20% 50%, rgba(42,84,48,0.75) 0%, transparent 55%),
    radial-gradient(ellipse at 80% 20%, rgba(240,140,42,0.22) 0%, transparent 50%),
    linear-gradient(155deg, #0d2410 0%, #1e4020 40%, #2a5430 70%, #1a2f18 100%);
  z-index: 0;
}

.hero-glow {
  position: absolute;
  border-radius: 50%;
  pointer-events: none;
  z-index: 1;
}

.hero-glow-1 {
  right: 5%; top: 10%;
  width: 500px; height: 500px;
  background: radial-gradient(circle, rgba(61,122,71,0.3) 0%, transparent 70%);
  animation: pulse1 7s ease-in-out infinite;
}

.hero-glow-2 {
  left: -5%; bottom: 10%;
  width: 380px; height: 380px;
  background: radial-gradient(circle, rgba(139,186,74,0.15) 0%, transparent 70%);
  animation: pulse1 9s ease-in-out infinite 2s;
}

@keyframes pulse1 {
  0%,100%{transform:scale(1);opacity:1}
  50%{transform:scale(1.1);opacity:0.7}
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  padding: 0 2rem;
  max-width: 820px;
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(245,200,66,0.1);
  border: 1px solid rgba(245,200,66,0.3);
  color: var(--sun);
  font-size: 0.72rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  font-weight: 500;
  padding: 7px 20px;
  border-radius: 30px;
  margin-bottom: 2rem;
  animation: fadeUp 0.8s ease both;
}

.hero-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(3.5rem, 9vw, 7.5rem);
  font-weight: 700;
  color: #fff;
  line-height: 0.92;
  margin-bottom: 0.5rem;
  animation: fadeUp 0.8s ease 0.12s both;
}

.hero-title em { font-style: italic; color: var(--sun); }

.hero-sub {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(1.2rem, 3vw, 1.9rem);
  color: rgba(255,255,255,0.5);
  font-style: italic;
  margin-bottom: 1.8rem;
  animation: fadeUp 0.8s ease 0.22s both;
}

.hero-desc {
  color: rgba(255,255,255,0.6);
  font-size: 0.97rem;
  line-height: 1.8;
  max-width: 440px;
  margin: 0 auto 2.8rem;
  animation: fadeUp 0.8s ease 0.32s both;
}

.hero-btns {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  animation: fadeUp 0.8s ease 0.42s both;
}

@keyframes fadeUp {
  from{opacity:0;transform:translateY(22px)}
  to{opacity:1;transform:translateY(0)}
}

.btn {
  display: inline-block;
  padding: 15px 34px;
  border-radius: 50px;
  font-size: 0.87rem;
  font-weight: 500;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  text-decoration: none;
  border: none;
  cursor: pointer;
  transition: all 0.22s;
  font-family: 'DM Sans', sans-serif;
}

.btn-sun { background: var(--sun); color: var(--bark); }
.btn-sun:hover {
  background: var(--mango); color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(240,140,42,0.35);
}

.btn-ghost { background: transparent; color: #fff; border: 1.5px solid rgba(255,255,255,0.4); }
.btn-ghost:hover {
  background: rgba(255,255,255,0.1);
  border-color: rgba(255,255,255,0.7);
  transform: translateY(-2px);
}

.hero-scroll {
  position: absolute;
  bottom: 36px; left: 50%;
  transform: translateX(-50%);
  z-index: 2;
  display: flex; flex-direction: column; align-items: center; gap: 8px;
  color: rgba(255,255,255,0.35);
  font-size: 0.66rem; letter-spacing: 0.16em; text-transform: uppercase;
}

.scroll-line {
  width: 1px; height: 42px;
  background: linear-gradient(to bottom, rgba(255,255,255,0.4), transparent);
  animation: scrollPulse 2s ease-in-out infinite;
}

@keyframes scrollPulse {
  0%,100%{height:42px;opacity:1}
  50%{height:56px;opacity:0.4}
}

/* MARQUEE STRIP */
.strip {
  background: var(--jungle);
  padding: 1.1rem 0;
  overflow: hidden;
  position: relative;
  z-index: 2;
}

.strip-inner {
  display: flex;
  width: max-content;
  animation: marquee 22s linear infinite;
  gap: 2.5rem;
}

@keyframes marquee { from{transform:translateX(0)} to{transform:translateX(-50%)} }

.strip-item {
  display: flex; align-items: center; gap: 9px;
  color: rgba(255,255,255,0.65);
  font-size: 0.78rem; letter-spacing: 0.1em;
  text-transform: uppercase; white-space: nowrap; font-weight: 500;
}

.strip-dot { width: 4px; height: 4px; background: var(--sun); border-radius: 50%; flex-shrink: 0; }

/* SECTION HELPERS */
.section-tag {
  display: block;
  color: var(--palm);
  font-size: 0.72rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  font-weight: 500;
  margin-bottom: 0.7rem;
}

.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(2rem, 5vw, 3.2rem);
  font-weight: 700;
  line-height: 1.08;
  color: var(--jungle);
}

.section-title em { font-style: italic; color: var(--flame); }

.section-lead { color: var(--muted); line-height: 1.8; font-size: 0.94rem; }

.deco-line {
  height: 2px;
  width: 70px;
  background: linear-gradient(90deg, var(--jungle), var(--lime), transparent);
  margin: 1rem 0 1.5rem;
}

/* ABOUT */
.about { background: var(--sand); padding: 6rem 3rem; }

.about-inner {
  max-width: 1100px; margin: 0 auto;
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 5rem; align-items: center;
}

.about-card {
  background: var(--jungle);
  border-radius: 24px; padding: 3rem 2.5rem;
  position: relative; overflow: hidden;
}

.about-card::before {
  content:''; position:absolute;
  top:-60px; right:-60px; width:220px; height:220px;
  background: radial-gradient(circle, rgba(139,186,74,0.22) 0%, transparent 70%);
  border-radius: 50%;
}

.about-card::after {
  content:''; position:absolute;
  bottom:-50px; left:-50px; width:180px; height:180px;
  background: radial-gradient(circle, rgba(245,200,66,0.18) 0%, transparent 70%);
  border-radius: 50%;
}

.big-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 5.5rem; font-weight: 700;
  color: var(--sun); line-height: 1;
}

.big-num-label {
  font-size: 0.75rem; letter-spacing: 0.14em; text-transform: uppercase;
  color: rgba(255,255,255,0.45); margin-bottom: 2rem;
}

.about-quote {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.35rem; font-style: italic;
  color: rgba(255,255,255,0.85); line-height: 1.5;
  border-left: 3px solid var(--lime); padding-left: 1.2rem;
  position: relative; z-index: 1;
}

.about-badges {
  display: flex; flex-wrap: wrap; gap: 0.6rem;
  margin-top: 1.5rem; position: relative; z-index: 1;
}

.badge {
  background: rgba(139,186,74,0.14);
  border: 1px solid rgba(139,186,74,0.28);
  color: var(--lime);
  font-size: 0.71rem; padding: 5px 14px; border-radius: 20px;
  letter-spacing: 0.08em; text-transform: uppercase; font-weight: 500;
}

.about-feats {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 1.2rem; margin-top: 2rem;
}

.feat {
  display: flex; align-items: flex-start; gap: 12px;
}

.feat-icon {
  width: 38px; height: 38px;
  background: var(--sun); border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem; flex-shrink: 0;
}

.feat h4 { font-size: 0.86rem; font-weight: 500; color: var(--jungle); margin-bottom: 2px; }
.feat p { font-size: 0.77rem; color: var(--muted); line-height: 1.5; }

/* MENU */
#menu { background: var(--cream); padding: 6rem 3rem; }

.menu-wrap { max-width: 1000px; margin: 0 auto; }

.menu-hd { margin-bottom: 3.5rem; }

.specials-row {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 1.2rem; margin-bottom: 4rem;
}

.special-card {
  background: var(--jungle); border-radius: 20px;
  padding: 1.8rem 1.6rem; position: relative;
  overflow: hidden; transition: transform 0.22s;
}

.special-card:hover { transform: translateY(-4px); }

.special-card::after {
  content:''; position:absolute;
  bottom:-30px; right:-30px; width:120px; height:120px;
  background: radial-gradient(circle, rgba(245,200,66,0.14) 0%, transparent 70%);
  border-radius: 50%;
}

.sc-icon { font-size: 1.6rem; margin-bottom: 0.7rem; }
.sc-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.22rem; font-weight: 600; color: var(--sun); margin-bottom: 0.3rem;
}
.sc-desc { font-size: 0.78rem; color: rgba(255,255,255,0.55); margin-bottom: 1rem; line-height: 1.5; }
.sc-price {
  font-family: 'Cormorant Garamond', serif;
  font-size: 2rem; font-weight: 700; color: #fff;
}

.menu-cat { margin-bottom: 3.5rem; }

.menu-cat-hd {
  display: flex; align-items: center; gap: 1rem;
  padding-bottom: 0.9rem; margin-bottom: 1rem;
  border-bottom: 2px solid rgba(0,0,0,0.07);
  position: relative;
}

.menu-cat-hd::after {
  content:''; position:absolute;
  bottom:-2px; left:0; width:56px; height:2px;
  background: var(--mango);
}

.cat-icon { font-size: 1.3rem; }

.cat-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.5rem; font-weight: 700; color: var(--jungle);
}

.cat-sub {
  font-size: 0.76rem; color: var(--muted);
  font-style: italic; margin-left: auto;
}

.menu-row {
  display: flex; justify-content: space-between;
  align-items: baseline; padding: 9px 4px;
  border-bottom: 1px dotted rgba(0,0,0,0.08);
  transition: background 0.15s; border-radius: 4px;
}
.menu-row:last-child { border-bottom: none; }
.menu-row:hover { background: rgba(245,200,66,0.05); }

.mr-name { font-size: 0.89rem; flex: 1; color: var(--text); }
.mr-dots { flex: 1; border-bottom: 1px dotted rgba(0,0,0,0.1); margin: 0 0.8rem; height: 12px; }
.mr-price { font-weight: 500; color: var(--flame); font-size: 0.89rem; white-space: nowrap; }

.two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem 4rem; }

/* RESERVATION */
#reservering {
  background: var(--jungle); padding: 6rem 3rem;
  position: relative; overflow: hidden;
}

#reservering::before {
  content:''; position:absolute;
  top:-100px; right:-100px; width:500px; height:500px;
  background: radial-gradient(circle, rgba(139,186,74,0.1) 0%, transparent 70%);
  border-radius: 50%; pointer-events: none;
}

.res-inner {
  max-width: 960px; margin: 0 auto;
  display: grid; grid-template-columns: 1fr 1.6fr;
  gap: 5rem; align-items: start;
  position: relative; z-index: 1;
}

.res-info .section-tag { color: var(--lime); }

.res-details { margin-top: 2.5rem; display: flex; flex-direction: column; gap: 1.2rem; }

.res-detail { display: flex; align-items: center; gap: 14px; }

.rd-icon {
  width: 42px; height: 42px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 12px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1rem; flex-shrink: 0;
}

.rd-info h5 {
  font-size: 0.72rem; letter-spacing: 0.1em;
  text-transform: uppercase; color: rgba(255,255,255,0.38); margin-bottom: 2px;
}
.rd-info p { font-size: 0.88rem; color: rgba(255,255,255,0.82); }

.res-form {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 24px; padding: 2.5rem;
}

.fg { margin-bottom: 1.1rem; }

.fg label {
  display: block; font-size: 0.7rem;
  letter-spacing: 0.14em; text-transform: uppercase;
  color: rgba(255,255,255,0.45); font-weight: 500; margin-bottom: 7px;
}

.fg input, .fg select, .fg textarea {
  width: 100%; padding: 13px 16px;
  background: rgba(255,255,255,0.07);
  border: 1px solid rgba(255,255,255,0.13);
  border-radius: 12px; color: #fff;
  font-size: 0.9rem; font-family: 'DM Sans', sans-serif;
  outline: none; transition: border-color 0.2s, background 0.2s;
}

.fg input::placeholder, .fg textarea::placeholder { color: rgba(255,255,255,0.28); }

.fg input:focus, .fg select:focus, .fg textarea:focus {
  border-color: var(--sun);
  background: rgba(245,200,66,0.06);
}

.fg select { cursor: pointer; }
.fg select option { background: #1e4020; color: #fff; }
.fg textarea { resize: vertical; min-height: 90px; }

.fr2 { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

.form-btn {
  width: 100%; margin-top: 0.5rem; padding: 16px;
  background: var(--sun); color: var(--bark);
  border: none; border-radius: 50px;
  font-size: 0.87rem; font-weight: 500;
  letter-spacing: 0.08em; text-transform: uppercase;
  font-family: 'DM Sans', sans-serif;
  cursor: pointer; transition: all 0.22s;
}

.form-btn:hover {
  background: var(--mango); color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(240,140,42,0.35);
}

.form-note {
  font-size: 0.72rem; color: rgba(255,255,255,0.28);
  text-align: center; margin-top: 1rem; line-height: 1.6;
}

.success-box {
  display: none; margin-top: 1.2rem;
  background: rgba(139,186,74,0.1);
  border: 1px solid rgba(139,186,74,0.3);
  border-radius: 14px; padding: 1.8rem; text-align: center;
}
.success-box.show { display: block; }
.success-box .si { font-size: 2rem; margin-bottom: 0.5rem; }
.success-box h4 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.4rem; color: var(--lime); margin-bottom: 0.3rem;
}
.success-box p { font-size: 0.83rem; color: rgba(255,255,255,0.5); line-height: 1.6; }

/* FOOTER */
footer { background: #0d1e0f; padding: 5rem 3rem 2.5rem; }

.ft { max-width: 1000px; margin: 0 auto; }

.ft-top {
  display: grid; grid-template-columns: 1.5fr 1fr 1fr 1fr;
  gap: 3rem; padding-bottom: 3rem;
  border-bottom: 1px solid rgba(255,255,255,0.07);
  margin-bottom: 2rem;
}

.ft-brand-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 1.6rem; color: var(--sun); font-weight: 700;
  margin-bottom: 0.8rem; display: flex; align-items: center; gap: 8px;
}

.ft-brand-desc { font-size: 0.84rem; line-height: 1.8; color: rgba(255,255,255,0.4); max-width: 240px; }

.ft-col h5 {
  font-size: 0.68rem; letter-spacing: 0.18em; text-transform: uppercase;
  color: var(--lime); margin-bottom: 1.2rem; font-weight: 500;
}

.ft-col a, .ft-col p {
  display: block; font-size: 0.84rem; line-height: 2.1;
  color: rgba(255,255,255,0.45); text-decoration: none; transition: color 0.2s;
}

.ft-col a:hover { color: var(--sun); }

.ft-bottom {
  display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 0.8rem;
  font-size: 0.73rem; color: rgba(255,255,255,0.22);
}

.ft-heart { color: var(--sun); }

/* RESPONSIVE */
@media (max-width: 900px) {
  nav { padding: 0 1.5rem; }
  .nav-links { gap: 1rem; }
  .about-inner { grid-template-columns: 1fr; gap: 2.5rem; }
  .specials-row { grid-template-columns: 1fr; }
  .two-col { grid-template-columns: 1fr; gap: 0; }
  .res-inner { grid-template-columns: 1fr; gap: 3rem; }
  .ft-top { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 600px) {
  nav { padding: 0 1.2rem; }
  .nav-links { display: none; }
  #menu, #reservering, .about { padding: 4rem 1.5rem; }
  .ft-top { grid-template-columns: 1fr; }
  .fr2 { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#home" class="nav-brand">
    <span class="nav-palm">🌴</span>
    Masha Caribbean
  </a>
  <ul class="nav-links">
    <li><a href="#menu">Menu</a></li>
    <li><a href="#reservering">Reserveren</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="tel:0793602116" class="nav-cta">📞 Bel ons</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-glow hero-glow-1"></div>
  <div class="hero-glow hero-glow-2"></div>

  <div class="hero-content">
    <div class="hero-eyebrow">Website Preview gemaakt door Jace Len</div>
    <h1 class="hero-title">Masha<br><em>Caribbean</em><br>Food</h1>
    <p class="hero-sub"></p>
    <p class="hero-desc">Verse Surinaamse en Caribische gerechten, bereid met de smaken en tradities van het eiland. Een maaltijd vol liefde.</p>
    <div class="hero-btns">
      <a href="#menu" class="btn btn-sun">Ontdek het menu</a>
      <a href="#reservering" class="btn btn-ghost">Reserveer een tafel</a>
    </div>
  </div>

  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>scroll</span>
  </div>
</section>

<!-- STRIP -->
<div class="strip">
  <div class="strip-inner">
    <div class="strip-item"><div class="strip-dot"></div>Vers bereid dagelijks</div>
    <div class="strip-item"><div class="strip-dot"></div>Surinaamse gerechten</div>
    <div class="strip-item"><div class="strip-dot"></div>Caribische smaken</div>
    <div class="strip-item"><div class="strip-dot"></div>Afhalen & bezorgen</div>
    <div class="strip-item"><div class="strip-dot"></div>Dorpsstraat 108 Zoetermeer</div>
    <div class="strip-item"><div class="strip-dot"></div>079 360 2116</div>
    <div class="strip-item"><div class="strip-dot"></div>Verse ingrediënten</div>
    <div class="strip-item"><div class="strip-dot"></div>Familie restaurant</div>
    <div class="strip-item"><div class="strip-dot"></div>Vers bereid dagelijks</div>
    <div class="strip-item"><div class="strip-dot"></div>Surinaamse gerechten</div>
    <div class="strip-item"><div class="strip-dot"></div>Caribische smaken</div>
    <div class="strip-item"><div class="strip-dot"></div>Afhalen & bezorgen</div>
    <div class="strip-item"><div class="strip-dot"></div>Dorpsstraat 108 Zoetermeer</div>
    <div class="strip-item"><div class="strip-dot"></div>079 360 2116</div>
    <div class="strip-item"><div class="strip-dot"></div>Verse ingrediënten</div>
    <div class="strip-item"><div class="strip-dot"></div>Familie restaurant</div>
  </div>
</div>

<!-- ABOUT -->
<section class="about">
  <div class="about-inner">
    <div>
      <div class="about-card">
        <div class="big-num">100%</div>
        <div class="big-num-label"></div>
        <div class="about-quote">"Koken met liefde en de smaken van thuis — elke dag opnieuw."</div>
        <div class="about-badges">
          <span class="badge">🌶️ Pittig op verzoek</span>
          <span class="badge">🌿 Verse kruiden</span>
          <span class="badge">🍋 Zelfgemaakt</span>
        </div>
      </div>
    </div>
    <div>
      <span class="section-tag">Over Masha</span>
      <h2 class="section-title">Het hart van<br><em>het Caribisch</em><br>gebied in Zoetermeer</h2>
      <div class="deco-line"></div>
      <p class="section-lead">Bij Masha Caribbean draait alles om authenticiteit. Van onze Surinaamse stoba tot de krokante truki pan — elk gerecht is een reis naar de smaken van het eiland, bereid met liefde en vakmanschap.</p>
      <div class="about-feats">
        <div class="feat"><div class="feat-icon">🍛</div><div><h4>Traditionele recepten</h4><p>Generaties van smaak en vakmanschap</p></div></div>
        <div class="feat"><div class="feat-icon">🌿</div><div><h4>Verse bereiding</h4><p>Dagelijks vers bereid voor jou</p></div></div>
      </div>
    </div>
  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="menu-wrap">
    <div class="menu-hd">
      <span class="section-tag">Onze gerechten</span>
      <h2 class="section-title">Menu <em>Kaart</em></h2>
      <div class="deco-line"></div>
      <p style="font-size:0.8rem;color:var(--muted)">Alle prijzen zijn inclusief btw. Prijswijzigingen voorbehouden.</p>
    </div>

    <div class="specials-row">
      <div class="special-card">
        <div class="sc-icon"></div>
        <div class="sc-name">Kinder Menu</div>
        <div class="sc-desc">Friet inclusief mix snacks</div>
        <div class="sc-price">€9,99</div>
      </div>
      <div class="special-card">
        <div class="sc-icon"></div>
        <div class="sc-name">Masha Box</div>
        <div class="sc-desc">Gebakken funchi, friet, kip, sla &amp; kaas</div>
        <div class="sc-price">€9,99</div>
      </div>
      <div class="special-card">
        <div class="sc-icon"></div>
        <div class="sc-name">Johnny Cake</div>
        <div class="sc-desc">Kaas €4,50 · Kip €7,50 · Plain €3,50</div>
        <div class="sc-price">v.a. €3,50</div>
      </div>
    </div>

    <!-- Voorgerechten -->
    <div class="menu-cat">
      <div class="menu-cat-hd">
        <span class="cat-icon">🥗</span>
        <span class="cat-title">Voorgerechten</span>
      </div>
      <div class="menu-row"><span class="mr-name">Kaasbal</span><div class="mr-dots"></div><span class="mr-price">€4,99</span></div>
      <div class="menu-row"><span class="mr-name">Pikibari</span><div class="mr-dots"></div><span class="mr-price">€4,99</span></div>
      <div class="menu-row"><span class="mr-name">Sososhi rol</span><div class="mr-dots"></div><span class="mr-price">€2,50</span></div>
      <div class="menu-row"><span class="mr-name">Kroket</span><div class="mr-dots"></div><span class="mr-price">€3,99</span></div>
      <div class="menu-row"><span class="mr-name">Sopi di karai</span><div class="mr-dots"></div><span class="mr-price">€8,99</span></div>
    </div>

    <!-- Hoofdgerechten -->
    <div class="menu-cat">
      <div class="menu-cat-hd">
        <span class="cat-icon">🍽️</span>
        <span class="cat-title">Hoofdgerechten</span>
        <span class="cat-sub">incl. rijst of friet &amp; macaroni salade</span>
      </div>
      <div class="menu-row"><span class="mr-name">Stoba di Galina (Gestoofd kip)</span><div class="mr-dots"></div><span class="mr-price">€19,95</span></div>
      <div class="menu-row"><span class="mr-name">Stoba di Karni (Gestoofd rundvlees)</span><div class="mr-dots"></div><span class="mr-price">€24,95</span></div>
      <div class="menu-row"><span class="mr-name">Piska (Vis)</span><div class="mr-dots"></div><span class="mr-price">€24,95</span></div>
      <div class="menu-row"><span class="mr-name">Mixed Grill (kip, spareribs, karbonade)</span><div class="mr-dots"></div><span class="mr-price">€27,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Galina — kip klein</span><div class="mr-dots"></div><span class="mr-price">€11,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Galina — kip groot</span><div class="mr-dots"></div><span class="mr-price">€23,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Spareribs — klein</span><div class="mr-dots"></div><span class="mr-price">€13,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Spareribs — 500g</span><div class="mr-dots"></div><span class="mr-price">€25,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Spareribs — 1000g (+€6,95)</span><div class="mr-dots"></div><span class="mr-price">€25,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Shrimp — garnalen klein</span><div class="mr-dots"></div><span class="mr-price">€17,95</span></div>
      <div class="menu-row"><span class="mr-name">Truki Pan Shrimp — garnalen groot</span><div class="mr-dots"></div><span class="mr-price">€25,95</span></div>
    </div>

    <div class="two-col">
      <div class="menu-cat">
        <div class="menu-cat-hd">
          <span class="cat-icon">🫕</span>
          <span class="cat-title">Surinaamse Gerechten</span>
        </div>
        <div class="menu-row"><span class="mr-name">Nasi met kip</span><div class="mr-dots"></div><span class="mr-price">€17,95</span></div>
        <div class="menu-row"><span class="mr-name">Bami met kip</span><div class="mr-dots"></div><span class="mr-price">€17,95</span></div>
        <div class="menu-row"><span class="mr-name">Kip kerrie</span><div class="mr-dots"></div><span class="mr-price">€5,50</span></div>
      </div>
      <div class="menu-cat">
        <div class="menu-cat-hd">
          <span class="cat-icon">🥪</span>
          <span class="cat-title">Surinaamse Broodjes</span>
        </div>
        <div class="menu-row"><span class="mr-name">Kip cashew</span><div class="mr-dots"></div><span class="mr-price">€5,50</span></div>
        <div class="menu-row"><span class="mr-name">Kip ketjap</span><div class="mr-dots"></div><span class="mr-price">€5,50</span></div>
        <div class="menu-row"><span class="mr-name">Karbonade</span><div class="mr-dots"></div><span class="mr-price">€6,50</span></div>
        <div class="menu-row"><span class="mr-name">Kabbeljauuw</span><div class="mr-dots"></div><span class="mr-price">€6,50</span></div>
        <div class="menu-row"><span class="mr-name">Garnalen</span><div class="mr-dots"></div><span class="mr-price">€6,50</span></div>
      </div>
    </div>

    <div class="two-col">
      <div class="menu-cat">
        <div class="menu-cat-hd">
          <span class="cat-icon">🥟</span>
          <span class="cat-title">Pastechi</span>
        </div>
        <div class="menu-row"><span class="mr-name">Kaas</span><div class="mr-dots"></div><span class="mr-price">€3,75</span></div>
        <div class="menu-row"><span class="mr-name">Kip</span><div class="mr-dots"></div><span class="mr-price">€3,75</span></div>
        <div class="menu-row"><span class="mr-name">Gehakt</span><div class="mr-dots"></div><span class="mr-price">€3,75</span></div>
        <div class="menu-row"><span class="mr-name">Kabbeljauuw</span><div class="mr-dots"></div><span class="mr-price">€4,30</span></div>
      </div>
      <div class="menu-cat">
        <div class="menu-cat-hd">
          <span class="cat-icon">🍌</span>
          <span class="cat-title">Bijgerechten</span>
        </div>
        <div class="menu-row"><span class="mr-name">Funchi</span><div class="mr-dots"></div><span class="mr-price">€3,95</span></div>
        <div class="menu-row"><span class="mr-name">Bana Hasi (Gebakken banaan)</span><div class="mr-dots"></div><span class="mr-price">€3,95</span></div>
        <div class="menu-row"><span class="mr-name">Funchi Hasi (Gebakken funchi)</span><div class="mr-dots"></div><span class="mr-price">€3,95</span></div>
        <div class="menu-row"><span class="mr-name">Arros Blanco (Witte rijst)</span><div class="mr-dots"></div><span class="mr-price">€4,50</span></div>
        <div class="menu-row"><span class="mr-name">Nasi</span><div class="mr-dots"></div><span class="mr-price">€6,50</span></div>
      </div>
    </div>
  </div>
</section>

<!-- RESERVERING -->
<section id="reservering">
  <div class="res-inner">
    <div class="res-info">
      <span class="section-tag">Reserveer nu</span>
      <h2 class="section-title" style="color:#fff">Boek jouw<br><em style="color:var(--sun)">Caribische</em><br>tafel</h2>
      <div class="deco-line"></div>
      <p class="section-lead" style="color:rgba(255,255,255,0.58)">Reserveer online en wij zorgen voor een onvergetelijke avond vol Caribische smaken en warmte.</p>
      <div class="res-details">
        <div class="res-detail">
          <div class="rd-icon">📍</div>
          <div class="rd-info"><h5>Adres</h5><p>Dorpsstraat 108, 2712 AN Zoetermeer</p></div>
        </div>
        <div class="res-detail">
          <div class="rd-icon">📞</div>
          <div class="rd-info"><h5>Telefoon</h5><p>079 360 2116</p></div>
        </div>
        <div class="res-detail">
          <div class="rd-icon">🕐</div>
          <div class="rd-info"><h5>Openingstijden</h5><p>Ma–Vr 11:00–21:00 · Za 11:00–21:30 · Zo 12:00–20:00</p></div>
        </div>
      </div>
    </div>

    <div class="res-form">
      <div class="fr2">
        <div class="fg"><label>Voornaam</label><input type="text" id="fn" placeholder="Jouw naam"></div>
        <div class="fg"><label>Achternaam</label><input type="text" id="ln" placeholder="Achternaam"></div>
      </div>
      <div class="fr2">
        <div class="fg"><label>Email</label><input type="email" id="em" placeholder="jouw@email.nl"></div>
        <div class="fg"><label>Telefoon</label><input type="tel" id="ph" placeholder="06 ···"></div>
      </div>
      <div class="fr2">
        <div class="fg"><label>Datum</label><input type="date" id="dt"></div>
        <div class="fg">
          <label>Tijdstip</label>
          <select id="ti">
            <option value="">Kies tijd</option>
            <option>12:00</option><option>12:30</option><option>13:00</option>
            <option>17:00</option><option>17:30</option><option>18:00</option>
            <option>18:30</option><option>19:00</option><option>19:30</option>
            <option>20:00</option><option>20:30</option>
          </select>
        </div>
      </div>
      <div class="fg">
        <label>Aantal personen</label>
        <select id="gu">
          <option value="">Selecteer</option>
          <option>1 persoon</option><option>2 personen</option><option>3 personen</option>
          <option>4 personen</option><option>5 personen</option><option>6 personen</option>
          <option>7 of meer — bel ons</option>
        </select>
      </div>
      <div class="fg">
        <label>Bijzonderheden</label>
        <textarea id="no" placeholder="Allergieën, dieetwensen, speciale gelegenheid..."></textarea>
      </div>
      <button class="form-btn" onclick="bookTable()">Bevestig reservering 🌴</button>
      <p class="form-note">U ontvangt een bevestiging via e-mail of telefoon.</p>
      <div class="success-box" id="sb">
        <div class="si">🎉</div>
        <h4>Reservering ontvangen!</h4>
        <p>Bedankt! We nemen snel contact op ter bevestiging.<br>Tot snel bij Masha Caribbean!</p>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer id="contact">
  <div class="ft">
    <div class="ft-top">
      <div>
        <div class="ft-brand-name">🌴 Masha Caribbean</div>
        <p class="ft-brand-desc">Authentiek Caribisch en Surinaams eten in Zoetermeer. Bereid met liefde, tradities en de smaken van het eiland.</p>
      </div>
      <div class="ft-col">
        <h5>Contact</h5>
        <p>📍 Dorpsstraat 108</p>
        <p>2712 AN Zoetermeer</p>
        <a href="tel:0793602116">📞 079 360 2116</a>
      </div>
      <div class="ft-col">
        <h5>Openingstijden</h5>
        <p>Ma – Vr: 11:00 – 21:00</p>
        <p>Zaterdag: 11:00 – 21:30</p>
        <p>Zondag: 12:00 – 20:00</p>
      </div>
      <div class="ft-col">
        <h5>Navigatie</h5>
        <a href="#home">Home</a>
        <a href="#menu">Menu</a>
        <a href="#reservering">Reserveren</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
    <div class="ft-bottom">
      <span>© 2025 Masha Caribbean Food · Zoetermeer</span>
      <span>Gemaakt met <span class="ft-heart">♥</span> voor authentiek Caribisch eten</span>
    </div>
  </div>
</footer>

<script>
document.getElementById('dt').min = new Date().toISOString().split('T')[0];

function bookTable() {
  const fn = document.getElementById('fn').value.trim();
  const em = document.getElementById('em').value.trim();
  const dt = document.getElementById('dt').value;
  const ti = document.getElementById('ti').value;
  const gu = document.getElementById('gu').value;

  if (!fn || !em || !dt || !ti || !gu) {
    alert('Vul alle verplichte velden in om te reserveren.');
    return;
  }

  document.getElementById('sb').classList.add('show');
  const btn = document.querySelector('.form-btn');
  btn.disabled = true;
  btn.style.opacity = '0.4';
  btn.style.cursor = 'default';

  ['fn','ln','em','ph','dt','no'].forEach(id => document.getElementById(id).value = '');
  ['ti','gu'].forEach(id => document.getElementById(id).selectedIndex = 0);
}
</script>
</body>
</html>
