<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IEPA — Institute for Educational Planning and Administration | UCC</title>
<meta name="description" content="Institute for Educational Planning and Administration, University of Cape Coast, Ghana — Postgraduate education, research and professional practice.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
  :root {
    --navy-900: #0a1628;
    --navy-800: #0f1f38;
    --navy-700: #16294a;
    --navy-600: #1e3a5f;
    --gold-400: #d4af37;
    --gold-500: #c9a227;
    --gold-300: #e6c869;
    --cream: #faf8f3;
    --cream-2: #f3efe6;
    --ink: #0a1628;
    --ink-soft: #4a5568;
    --line: rgba(10, 22, 40, 0.08);
    --white: #ffffff;
    --radius-lg: 24px;
    --radius-md: 16px;
    --radius-sm: 10px;
    --shadow-sm: 0 2px 8px rgba(10, 22, 40, 0.04);
    --shadow-md: 0 8px 30px rgba(10, 22, 40, 0.08);
    --shadow-lg: 0 24px 60px rgba(10, 22, 40, 0.14);
    --ease: cubic-bezier(0.22, 1, 0.36, 1);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }

  body {
    font-family: 'Plus Jakarta Sans', system-ui, sans-serif;
    background: var(--cream);
    color: var(--ink);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }

  h1, h2, h3, .serif { font-family: 'Instrument Serif', Georgia, serif; font-weight: 400; letter-spacing: -0.01em; }
  a { color: inherit; text-decoration: none; }
  img { max-width: 100%; display: block; }
  button { font-family: inherit; cursor: pointer; border: none; background: none; }

  /* ============ TOP BAR ============ */
  .topbar {
    background: var(--navy-900);
    color: rgba(255,255,255,0.7);
    font-size: 0.78rem;
    padding: 0.55rem 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }
  .topbar-inner {
    max-width: 1400px; margin: 0 auto; width: 100%;
    display: flex; justify-content: space-between; align-items: center;
    gap: 1rem; flex-wrap: wrap;
  }
  .topbar a { display: inline-flex; align-items: center; gap: 0.4rem; transition: color 0.25s; }
  .topbar a:hover { color: var(--gold-300); }
  .topbar .links { display: flex; gap: 1.25rem; align-items: center; }
  .topbar i { color: var(--gold-400); font-size: 0.85rem; }

  /* ============ HEADER ============ */
  header {
    position: sticky; top: 0; z-index: 1000;
    background: rgba(250, 248, 243, 0.85);
    backdrop-filter: blur(16px) saturate(180%);
    -webkit-backdrop-filter: blur(16px) saturate(180%);
    border-bottom: 1px solid var(--line);
    transition: all 0.35s var(--ease);
  }
  header.scrolled {
    background: rgba(250, 248, 243, 0.95);
    box-shadow: 0 4px 20px rgba(10,22,40,0.06);
  }
  nav {
    max-width: 1400px; margin: 0 auto;
    padding: 0.9rem 1.5rem;
    display: flex; align-items: center; justify-content: space-between;
    gap: 1.5rem;
  }
  .logo {
    display: flex; align-items: center; gap: 0.7rem;
    font-family: 'Instrument Serif', serif;
    font-size: 1.5rem; color: var(--navy-900);
    letter-spacing: -0.02em;
    z-index: 1100;
    white-space: nowrap;
  }
  .logo-mark {
    width: 42px; height: 42px;
    background: linear-gradient(135deg, var(--navy-800), var(--navy-600));
    border-radius: 12px;
    display: grid; place-items: center;
    color: var(--gold-400);
    font-size: 1.15rem;
    box-shadow: 0 4px 12px rgba(10,22,40,0.2), inset 0 1px 0 rgba(255,255,255,0.1);
  }
  .logo-text small {
    display: block; font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 0.62rem; letter-spacing: 2.5px; text-transform: uppercase;
    color: var(--ink-soft); font-weight: 600; margin-top: -2px;
  }

  .nav-links { display: flex; gap: 0.15rem; align-items: center; list-style: none; }
  .nav-links a {
    padding: 0.6rem 0.95rem;
    font-size: 0.88rem; font-weight: 500;
    color: var(--navy-800);
    border-radius: 10px;
    transition: all 0.25s var(--ease);
    position: relative;
  }
  .nav-links a:hover { background: rgba(10,22,40,0.05); }
  .nav-links a.active { color: var(--navy-900); font-weight: 600; }
  .nav-links a.active::after {
    content: ''; position: absolute; bottom: 4px; left: 50%;
    transform: translateX(-50%);
    width: 18px; height: 2px; background: var(--gold-500); border-radius: 2px;
  }

  .nav-actions { display: flex; align-items: center; gap: 0.6rem; }
  .btn-ghost {
    padding: 0.6rem 1rem; font-size: 0.85rem; font-weight: 600;
    color: var(--navy-800); border-radius: 10px;
    transition: background 0.25s;
    display: inline-flex; align-items: center; gap: 0.45rem;
  }
  .btn-ghost:hover { background: rgba(10,22,40,0.06); }
  .btn-gold {
    padding: 0.65rem 1.15rem; font-size: 0.85rem; font-weight: 700;
    background: linear-gradient(135deg, var(--gold-400), var(--gold-500));
    color: var(--navy-900);
    border-radius: 10px;
    display: inline-flex; align-items: center; gap: 0.45rem;
    transition: all 0.3s var(--ease);
    box-shadow: 0 4px 14px rgba(212, 175, 55, 0.35);
  }
  .btn-gold:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 22px rgba(212, 175, 55, 0.5);
  }

  /* Hamburger */
  .hamburger {
    display: none;
    width: 44px; height: 44px;
    border-radius: 10px;
    position: relative;
    z-index: 1100;
    transition: background 0.25s;
  }
  .hamburger:hover { background: rgba(10,22,40,0.06); }
  .hamburger span {
    position: absolute; left: 50%; width: 22px; height: 2px;
    background: var(--navy-900); border-radius: 2px;
    transform: translateX(-50%);
    transition: all 0.35s var(--ease);
  }
  .hamburger span:nth-child(1) { top: 15px; }
  .hamburger span:nth-child(2) { top: 21px; width: 16px; left: 12px; transform: none; }
  .hamburger span:nth-child(3) { top: 27px; }
  .hamburger.open span:nth-child(1) { top: 21px; transform: translateX(-50%) rotate(45deg); background: var(--gold-500); }
  .hamburger.open span:nth-child(2) { opacity: 0; transform: translateX(30px); }
  .hamburger.open span:nth-child(3) { top: 21px; transform: translateX(-50%) rotate(-45deg); background: var(--gold-500); }

  /* ============ DRAWER ============ */
  .drawer-overlay {
    position: fixed; inset: 0;
    background: rgba(10,22,40,0.5);
    backdrop-filter: blur(6px);
    opacity: 0; visibility: hidden;
    transition: all 0.35s var(--ease);
    z-index: 1050;
  }
  .drawer-overlay.open { opacity: 1; visibility: visible; }

  .drawer {
    position: fixed; top: 0; right: 0;
    height: 100dvh;
    width: min(88vw, 380px);
    background: linear-gradient(180deg, var(--navy-900) 0%, var(--navy-800) 100%);
    z-index: 1080;
    transform: translateX(100%);
    transition: transform 0.45s var(--ease);
    display: flex; flex-direction: column;
    padding: 1.5rem 1.5rem 1.5rem;
    overflow-y: auto;
    box-shadow: -20px 0 60px rgba(0,0,0,0.4);
  }
  .drawer.open { transform: translateX(0); }

  .drawer-top {
    display: flex; justify-content: space-between; align-items: center;
    margin-bottom: 2rem; padding-bottom: 1.25rem;
    border-bottom: 1px solid rgba(255,255,255,0.08);
  }
  .drawer-brand {
    display: flex; align-items: center; gap: 0.6rem;
    font-family: 'Instrument Serif', serif;
    font-size: 1.25rem; color: white;
  }
  .drawer-brand .logo-mark { width: 36px; height: 36px; font-size: 1rem; }
  .drawer-close {
    width: 38px; height: 38px; border-radius: 10px;
    color: rgba(255,255,255,0.7);
    display: grid; place-items: center;
    transition: all 0.25s;
  }
  .drawer-close:hover { background: rgba(255,255,255,0.08); color: var(--gold-400); }

  .drawer-nav { display: flex; flex-direction: column; gap: 0.2rem; }
  .drawer-nav a {
    color: rgba(255,255,255,0.85);
    display: flex; align-items: center; gap: 0.9rem;
    padding: 0.85rem 1rem;
    border-radius: 12px;
    font-size: 0.95rem; font-weight: 500;
    transition: all 0.25s var(--ease);
    border-left: 3px solid transparent;
  }
  .drawer-nav a i {
    width: 20px; color: var(--gold-400);
    font-size: 0.95rem; text-align: center;
    transition: transform 0.3s;
  }
  .drawer-nav a:hover, .drawer-nav a.active {
    background: rgba(255,255,255,0.06);
    color: white;
    border-left-color: var(--gold-400);
    padding-left: 1.25rem;
  }
  .drawer-nav a:hover i { transform: scale(1.15); }

  .drawer-divider { height: 1px; background: rgba(255,255,255,0.08); margin: 1.5rem 0; }

  .drawer-cta { display: flex; flex-direction: column; gap: 0.55rem; }
  .drawer-cta a {
    display: flex; align-items: center; justify-content: center;
    gap: 0.55rem;
    padding: 0.9rem 1rem; border-radius: 12px;
    font-size: 0.9rem; font-weight: 600;
    transition: all 0.3s var(--ease);
  }
  .drawer-cta a.primary {
    background: linear-gradient(135deg, var(--gold-400), var(--gold-500));
    color: var(--navy-900);
    box-shadow: 0 6px 20px rgba(212, 175, 55, 0.3);
  }
  .drawer-cta a.primary:hover { transform: translateY(-2px); box-shadow: 0 10px 26px rgba(212,175,55,0.45); }
  .drawer-cta a.outline {
    border: 1.5px solid rgba(255,255,255,0.15);
    color: rgba(255,255,255,0.9);
  }
  .drawer-cta a.outline:hover {
    background: rgba(255,255,255,0.06);
    border-color: var(--gold-400);
    color: var(--gold-300);
  }

  .drawer-footer {
    margin-top: auto; padding-top: 2rem;
    color: rgba(255,255,255,0.4);
    font-size: 0.78rem;
    text-align: center;
  }

  /* ============ HERO ============ */
  .hero {
    position: relative;
    min-height: 92vh;
    padding: 5rem 1.5rem 4rem;
    display: grid; place-items: center;
    overflow: hidden;
    background: var(--navy-900);
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 15% 20%, rgba(212,175,55,0.18), transparent 60%),
      radial-gradient(ellipse 50% 60% at 85% 80%, rgba(30,58,95,0.7), transparent 60%),
      radial-gradient(ellipse 80% 40% at 50% 100%, rgba(212,175,55,0.08), transparent 70%);
    animation: auroraMove 18s ease-in-out infinite alternate;
  }
  @keyframes auroraMove {
    0% { transform: scale(1) translate(0,0); }
    100% { transform: scale(1.15) translate(-3%, -2%); }
  }
  .hero-grid {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 70% 70% at 50% 40%, black, transparent);
    -webkit-mask-image: radial-gradient(ellipse 70% 70% at 50% 40%, black, transparent);
  }
  .hero-noise {
    position: absolute; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 400 400' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='3'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.5'/%3E%3C/svg%3E");
    opacity: 0.04; pointer-events: none;
  }

  .hero-content {
    position: relative; z-index: 2;
    max-width: 1100px; width: 100%;
    text-align: center;
    color: white;
  }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.55rem;
    padding: 0.5rem 1.15rem;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(212,175,55,0.3);
    border-radius: 100px;
    font-size: 0.78rem; font-weight: 500;
    letter-spacing: 0.5px;
    color: var(--gold-300);
    margin-bottom: 2rem;
    backdrop-filter: blur(10px);
    animation: fadeUp 0.9s var(--ease) both;
  }
  .hero-badge .pulse {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--gold-400);
    box-shadow: 0 0 0 0 rgba(212,175,55,0.7);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(212,175,55,0.7); }
    70% { box-shadow: 0 0 0 10px rgba(212,175,55,0); }
    100% { box-shadow: 0 0 0 0 rgba(212,175,55,0); }
  }

  .hero h1 {
    font-size: clamp(2.2rem, 6vw, 4.5rem);
    line-height: 1.05;
    margin-bottom: 1.5rem;
    font-weight: 400;
    letter-spacing: -0.02em;
    animation: fadeUp 0.9s 0.1s var(--ease) both;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--gold-300);
    position: relative;
  }
  .hero h1 em::after {
    content: '';
    position: absolute; left: 0; right: 0; bottom: 0.1em;
    height: 0.15em;
    background: linear-gradient(90deg, transparent, rgba(212,175,55,0.5), transparent);
    border-radius: 4px;
  }

  .hero-sub {
    font-size: clamp(1rem, 1.6vw, 1.15rem);
    color: rgba(255,255,255,0.7);
    max-width: 620px;
    margin: 0 auto 2.75rem;
    line-height: 1.65;
    animation: fadeUp 0.9s 0.2s var(--ease) both;
  }

  .hero-actions {
    display: flex; gap: 0.75rem; justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 4rem;
    animation: fadeUp 0.9s 0.3s var(--ease) both;
  }

  .btn {
    display: inline-flex; align-items: center; gap: 0.55rem;
    padding: 0.95rem 1.6rem;
    border-radius: 12px;
    font-size: 0.92rem; font-weight: 600;
    transition: all 0.3s var(--ease);
    border: 1.5px solid transparent;
    white-space: nowrap;
  }
  .btn i { transition: transform 0.3s var(--ease); }
  .btn:hover i.fa-arrow-right { transform: translateX(4px); }

  .btn-gold-lg {
    background: linear-gradient(135deg, var(--gold-400), var(--gold-500));
    color: var(--navy-900);
    box-shadow: 0 10px 30px rgba(212,175,55,0.35);
  }
  .btn-gold-lg:hover {
    transform: translateY(-3px);
    box-shadow: 0 16px 40px rgba(212,175,55,0.5);
  }

  .btn-glass {
    background: rgba(255,255,255,0.06);
    color: white;
    border-color: rgba(255,255,255,0.18);
    backdrop-filter: blur(10px);
  }
  .btn-glass:hover {
    background: rgba(255,255,255,0.12);
    border-color: rgba(255,255,255,0.35);
    transform: translateY(-3px);
  }

  /* Hero stats */
  .hero-stats {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 0;
    max-width: 800px;
    margin: 0 auto;
    padding: 1.75rem 0;
    border-top: 1px solid rgba(255,255,255,0.1);
    border-bottom: 1px solid rgba(255,255,255,0.1);
    animation: fadeUp 0.9s 0.4s var(--ease) both;
  }
  .hero-stat { padding: 0 1rem; position: relative; }
  .hero-stat + .hero-stat::before {
    content: ''; position: absolute; left: 0; top: 20%; bottom: 20%;
    width: 1px; background: rgba(255,255,255,0.1);
  }
  .hero-stat .num {
    font-family: 'Instrument Serif', serif;
    font-size: 2.25rem;
    color: var(--gold-300);
    line-height: 1;
    display: block;
    margin-bottom: 0.35rem;
  }
  .hero-stat .lbl {
    font-size: 0.78rem; letter-spacing: 1px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.55);
    font-weight: 500;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ============ TRUST STRIP ============ */
  .trust-strip {
    background: var(--navy-800);
    color: rgba(255,255,255,0.5);
    padding: 1rem 1.5rem;
    border-top: 1px solid rgba(255,255,255,0.06);
  }
  .trust-inner {
    max-width: 1400px; margin: 0 auto;
    display: flex; align-items: center; justify-content: center;
    gap: 2.5rem; flex-wrap: wrap;
    font-size: 0.82rem;
    letter-spacing: 0.3px;
  }
  .trust-inner span { display: inline-flex; align-items: center; gap: 0.5rem; }
  .trust-inner i { color: var(--gold-400); }

  /* ============ SECTION BASE ============ */
  section { padding: 6rem 1.5rem; }
  .container { max-width: 1300px; margin: 0 auto; }

  .section-head { margin-bottom: 3.5rem; max-width: 700px; }
  .section-head.center { margin-left: auto; margin-right: auto; text-align: center; }
  .eyebrow {
    display: inline-flex; align-items: center; gap: 0.5rem;
    font-size: 0.75rem; font-weight: 700;
    letter-spacing: 2.5px; text-transform: uppercase;
    color: var(--gold-500);
    margin-bottom: 1rem;
  }
  .eyebrow::before {
    content: ''; width: 24px; height: 1px; background: var(--gold-500);
  }
  .section-head.center .eyebrow::before { display: none; }
  .section-head.center .eyebrow::after { content: ''; width: 24px; height: 1px; background: var(--gold-500); }
  .section-head h2 {
    font-size: clamp(1.9rem, 4vw, 3rem);
    line-height: 1.1;
    color: var(--navy-900);
    margin-bottom: 1rem;
  }
  .section-head p {
    font-size: 1.02rem;
    color: var(--ink-soft);
    max-width: 560px;
  }
  .section-head.center p { margin: 0 auto; }

  /* ============ QUICK ACCESS BENTO ============ */
  .bento {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    gap: 1rem;
  }
  .bento-item {
    background: var(--white);
    border: 1px solid var(--line);
    border-radius: var(--radius-lg);
    padding: 1.75rem;
    position: relative;
    overflow: hidden;
    transition: all 0.4s var(--ease);
    display: flex; flex-direction: column;
    min-height: 200px;
  }
  .bento-item::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(212,175,55,0.06), transparent 60%);
    opacity: 0; transition: opacity 0.4s;
  }
  .bento-item:hover {
    transform: translateY(-4px);
    border-color: rgba(212,175,55,0.4);
    box-shadow: var(--shadow-lg);
  }
  .bento-item:hover::before { opacity: 1; }

  .bento-lg { grid-column: span 6; min-height: 260px; }
  .bento-md { grid-column: span 3; }
  .bento-sm { grid-column: span 4; }

  .bento-icon {
    width: 52px; height: 52px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--navy-800), var(--navy-600));
    color: var(--gold-400);
    display: grid; place-items: center;
    font-size: 1.25rem;
    margin-bottom: 1.5rem;
    transition: all 0.4s var(--ease);
    position: relative; z-index: 1;
  }
  .bento-item:hover .bento-icon {
    transform: translateY(-4px) rotate(-6deg) scale(1.08);
    box-shadow: 0 12px 30px rgba(10,22,40,0.25);
  }
  .bento-item h3 {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 1.05rem; font-weight: 700;
    color: var(--navy-900);
    margin-bottom: 0.5rem;
    position: relative; z-index: 1;
  }
  .bento-item p {
    font-size: 0.88rem;
    color: var(--ink-soft);
    line-height: 1.55;
    position: relative; z-index: 1;
  }
  .bento-arrow {
    margin-top: auto;
    color: var(--gold-500);
    font-size: 1rem;
    position: relative; z-index: 1;
    opacity: 0; transform: translateX(-8px);
    transition: all 0.4s var(--ease);
  }
  .bento-item:hover .bento-arrow { opacity: 1; transform: translateX(0); }

  .bento-featured {
    background: linear-gradient(135deg, var(--navy-900), var(--navy-700));
    color: white;
    border-color: transparent;
  }
  .bento-featured h3 { color: white; }
  .bento-featured p { color: rgba(255,255,255,0.7); }
  .bento-featured .bento-icon {
    background: rgba(212,175,55,0.15);
    border: 1px solid rgba(212,175,55,0.3);
  }

  /* ============ ANNOUNCEMENTS ============ */
  .announcements-section { background: var(--cream-2); }
  .ann-list { display: flex; flex-direction: column; gap: 1rem; }
  .ann {
    background: var(--white);
    border-radius: var(--radius-md);
    padding: 1.5rem 1.75rem;
    border: 1px solid var(--line);
    display: grid;
    grid-template-columns: auto 1fr auto;
    gap: 1.5rem;
    align-items: center;
    transition: all 0.35s var(--ease);
    position: relative;
    overflow: hidden;
  }
  .ann::before {
    content: ''; position: absolute; left: 0; top: 0; bottom: 0;
    width: 3px; background: var(--gold-400);
    transform: scaleY(0); transform-origin: top;
    transition: transform 0.4s var(--ease);
  }
  .ann:hover {
    transform: translateX(4px);
    box-shadow: var(--shadow-md);
    border-color: transparent;
  }
  .ann:hover::before { transform: scaleY(1); }

  .ann-date {
    text-align: center;
    min-width: 60px;
    padding: 0.6rem 0.5rem;
    background: var(--cream);
    border-radius: 12px;
    border: 1px solid var(--line);
  }
  .ann-date .day {
    font-family: 'Instrument Serif', serif;
    font-size: 1.7rem; line-height: 1;
    color: var(--navy-900);
    display: block;
  }
  .ann-date .mon {
    font-size: 0.7rem; font-weight: 700;
    letter-spacing: 1.5px; text-transform: uppercase;
    color: var(--gold-500);
  }

  .ann-body h4 {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 1.02rem; font-weight: 700;
    color: var(--navy-900);
    margin-bottom: 0.35rem;
  }
  .ann-body p {
    font-size: 0.9rem; color: var(--ink-soft);
    line-height: 1.55;
  }
  .ann-tag {
    display: inline-block;
    padding: 0.2rem 0.7rem;
    border-radius: 100px;
    font-size: 0.68rem; font-weight: 700;
    letter-spacing: 0.8px; text-transform: uppercase;
    background: rgba(212,175,55,0.15);
    color: #8a6d1f;
    margin-bottom: 0.55rem;
  }

  .ann-arrow {
    width: 42px; height: 42px;
    border-radius: 50%;
    background: var(--cream);
    color: var(--navy-800);
    display: grid; place-items: center;
    font-size: 0.85rem;
    transition: all 0.35s var(--ease);
    flex-shrink: 0;
  }
  .ann:hover .ann-arrow {
    background: var(--navy-900);
    color: var(--gold-400);
    transform: rotate(-45deg);
  }

  /* ============ PROGRAMMES ============ */
  .prog-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1.5rem;
  }
  .prog-card {
    background: var(--white);
    border-radius: var(--radius-lg);
    overflow: hidden;
    border: 1px solid var(--line);
    transition: all 0.45s var(--ease);
    display: flex; flex-direction: column;
    position: relative;
  }
  .prog-card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
  }
  .prog-visual {
    height: 160px;
    background: linear-gradient(135deg, var(--navy-900), var(--navy-600));
    position: relative;
    overflow: hidden;
    display: grid; place-items: center;
    color: var(--gold-400);
    font-size: 2.5rem;
  }
  .prog-visual::before {
    content: ''; position: absolute; inset: 0;
    background:
      radial-gradient(circle at 30% 30%, rgba(212,175,55,0.2), transparent 60%),
      radial-gradient(circle at 80% 70%, rgba(255,255,255,0.08), transparent 50%);
    transition: transform 0.6s var(--ease);
  }
  .prog-card:hover .prog-visual::before { transform: scale(1.2); }
  .prog-visual i { position: relative; z-index: 1; transition: transform 0.5s var(--ease); }
  .prog-card:hover .prog-visual i { transform: scale(1.15) rotate(-5deg); }

  .prog-body { padding: 1.75rem; flex: 1; display: flex; flex-direction: column; }
  .prog-level {
    display: inline-block;
    padding: 0.28rem 0.75rem;
    border-radius: 100px;
    font-size: 0.68rem; font-weight: 700;
    letter-spacing: 1px; text-transform: uppercase;
    background: rgba(10,22,40,0.06);
    color: var(--navy-800);
    margin-bottom: 1rem;
    align-self: flex-start;
  }
  .prog-level.phd { background: rgba(212,175,55,0.15); color: #8a6d1f; }

  .prog-body h3 {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 1.15rem; font-weight: 700;
    color: var(--navy-900);
    line-height: 1.35;
    margin-bottom: 0.7rem;
  }
  .prog-body p {
    font-size: 0.9rem; color: var(--ink-soft);
    line-height: 1.6;
    margin-bottom: 1.25rem;
  }
  .prog-facts {
    display: flex; gap: 1rem; flex-wrap: wrap;
    padding: 1rem 0;
    border-top: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
    margin-bottom: 1.25rem;
    font-size: 0.82rem; color: var(--ink-soft);
  }
  .prog-facts span { display: inline-flex; align-items: center; gap: 0.4rem; }
  .prog-facts i { color: var(--gold-500); }

  .prog-link {
    margin-top: auto;
    display: inline-flex; align-items: center; gap: 0.5rem;
    font-weight: 700; font-size: 0.88rem;
    color: var(--navy-900);
    transition: gap 0.3s var(--ease);
    align-self: flex-start;
  }
  .prog-link i { color: var(--gold-500); }
  .prog-link:hover { gap: 0.8rem; }

  /* ============ CTA BANNER ============ */
  .cta-banner {
    background: linear-gradient(135deg, var(--navy-900) 0%, var(--navy-700) 100%);
    border-radius: var(--radius-lg);
    padding: 3.5rem 3rem;
    position: relative;
    overflow: hidden;
    color: white;
    display: flex; align-items: center; justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
    margin: 0 auto;
    max-width: 1300px;
  }
  .cta-banner::before {
    content: ''; position: absolute;
    top: -50%; right: -10%;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(212,175,55,0.15), transparent 60%);
    border-radius: 50%;
  }
  .cta-banner::after {
    content: ''; position: absolute;
    bottom: -30%; left: -5%;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(30,58,95,0.5), transparent 60%);
    border-radius: 50%;
  }
  .cta-content { position: relative; z-index: 1; max-width: 640px; }
  .cta-content h2 {
    font-size: clamp(1.6rem, 3vw, 2.4rem);
    line-height: 1.15;
    margin-bottom: 0.75rem;
  }
  .cta-content h2 em { color: var(--gold-300); font-style: italic; }
  .cta-content p { color: rgba(255,255,255,0.7); font-size: 1rem; }
  .cta-actions { position: relative; z-index: 1; display: flex; gap: 0.75rem; flex-wrap: wrap; }

  /* ============ FOOTER ============ */
  footer {
    background: var(--navy-900);
    color: rgba(255,255,255,0.7);
    padding: 5rem 1.5rem 2rem;
    position: relative;
    overflow: hidden;
  }
  footer::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 1px;
    background: linear-gradient(90deg, transparent, rgba(212,175,55,0.4), transparent);
  }
  .footer-inner {
    max-width: 1300px; margin: 0 auto;
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr 1fr;
    gap: 3rem;
    margin-bottom: 3rem;
  }
  .footer-brand .logo { color: white; margin-bottom: 1.25rem; }
  .footer-brand .logo-mark { box-shadow: 0 6px 20px rgba(212,175,55,0.2); }
  .footer-brand p {
    font-size: 0.9rem;
    line-height: 1.7;
    color: rgba(255,255,255,0.55);
    max-width: 320px;
    margin-bottom: 1.5rem;
  }

  .socials { display: flex; gap: 0.55rem; }
  .socials a {
    width: 40px; height: 40px;
    border-radius: 12px;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.08);
    display: grid; place-items: center;
    color: rgba(255,255,255,0.7);
    font-size: 0.9rem;
    transition: all 0.3s var(--ease);
  }
  .socials a:hover {
    background: var(--gold-400);
    color: var(--navy-900);
    border-color: var(--gold-400);
    transform: translateY(-3px);
  }

  footer h4 {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 0.78rem; font-weight: 700;
    letter-spacing: 2px; text-transform: uppercase;
    color: var(--gold-300);
    margin-bottom: 1.25rem;
  }
  footer ul { list-style: none; display: flex; flex-direction: column; gap: 0.7rem; }
  footer ul a {
    font-size: 0.88rem;
    color: rgba(255,255,255,0.6);
    transition: all 0.25s var(--ease);
    display: inline-flex; align-items: center; gap: 0.5rem;
  }
  footer ul a:hover { color: var(--gold-300); transform: translateX(4px); }
  footer ul a i { font-size: 0.7rem; color: var(--gold-400); }

  .footer-bottom {
    max-width: 1300px; margin: 0 auto;
    padding-top: 2rem;
    border-top: 1px solid rgba(255,255,255,0.08);
    display: flex; justify-content: space-between; align-items: center;
    gap: 1rem; flex-wrap: wrap;
    font-size: 0.82rem;
    color: rgba(255,255,255,0.4);
  }
  .footer-bottom .links { display: flex; gap: 1.5rem; }
  .footer-bottom a:hover { color: var(--gold-300); }

  /* ============ BACK TO TOP ============ */
  .to-top {
    position: fixed; bottom: 1.75rem; right: 1.75rem;
    width: 48px; height: 48px;
    border-radius: 14px;
    background: var(--navy-900);
    color: var(--gold-400);
    display: grid; place-items: center;
    font-size: 1rem;
    box-shadow: 0 8px 24px rgba(10,22,40,0.3);
    opacity: 0; visibility: hidden;
    transform: translateY(20px);
    transition: all 0.4s var(--ease);
    z-index: 900;
  }
  .to-top.visible { opacity: 1; visibility: visible; transform: translateY(0); }
  .to-top:hover {
    background: var(--gold-400);
    color: var(--navy-900);
    transform: translateY(-4px);
    box-shadow: 0 12px 32px rgba(212,175,55,0.4);
  }

  /* ============ SCROLL REVEAL ============ */
  .reveal {
    opacity: 0;
    transform: translateY(36px);
    transition: opacity 0.8s var(--ease), transform 0.8s var(--ease);
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ============ RESPONSIVE ============ */
  @media (max-width: 1024px) {
    .bento-lg { grid-column: span 12; }
    .bento-md { grid-column: span 6; }
    .bento-sm { grid-column: span 6; }
  }

  @media (max-width: 900px) {
    .nav-links, .nav-actions { display: none; }
    .hamburger { display: block; }
    .footer-inner { grid-template-columns: 1fr 1fr; gap: 2.5rem; }
    section { padding: 4.5rem 1.25rem; }
    .ann { grid-template-columns: auto 1fr; padding: 1.25rem; }
    .ann-arrow { display: none; }
    .cta-banner { padding: 2.5rem 1.75rem; }
    .topbar .links { gap: 0.85rem; font-size: 0.72rem; }
    .topbar .links span:nth-child(n+3) { display: none; }
  }

  @media (max-width: 600px) {
    .topbar { font-size: 0.72rem; padding: 0.5rem 1rem; }
    .topbar .links a span { display: none; }
    nav { padding: 0.75rem 1rem; }
    .logo { font-size: 1.25rem; }
    .logo-mark { width: 36px; height: 36px; font-size: 1rem; }
    .hero { min-height: auto; padding: 3.5rem 1.25rem 3rem; }
    .hero h1 { font-size: 2.1rem; }
    .hero-stat .num { font-size: 1.75rem; }
    .hero-stats { grid-template-columns: repeat(2, 1fr); gap: 1.5rem 0; }
    .hero-stat:nth-child(3)::before { display: none; }
    .btn { padding: 0.85rem 1.3rem; font-size: 0.85rem; }
    .bento-lg, .bento-md, .bento-sm { grid-column: span 12; }
    .bento-item { min-height: 170px; padding: 1.5rem; }
    .footer-inner { grid-template-columns: 1fr; gap: 2rem; }
    .footer-bottom { flex-direction: column; text-align: center; }
    section { padding: 3.5rem 1rem; }
    .section-head h2 { font-size: 1.75rem; }
  }

  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      transition-duration: 0.01ms !important;
    }
  }
</style>
</head>
<body>

<!-- ============ TOP BAR ============ -->
<div class="topbar">
  <div class="topbar-inner">
    <div class="links">
      <a href="tel:+233332132400"><i class="fa-solid fa-phone"></i> <span>+233 33 213 2400</span></a>
      <a href="mailto:iepa@ucc.edu.gh"><i class="fa-solid fa-envelope"></i> <span>iepa@ucc.edu.gh</span></a>
      <span><i class="fa-solid fa-location-dot"></i> University of Cape Coast, Ghana</span>
    </div>
    <div class="links">
      <a href="#portal"><i class="fa-solid fa-user-graduate"></i> <span>Student Portal</span></a>
      <a href="#staff"><i class="fa-solid fa-chalkboard-user"></i> <span>Staff Portal</span></a>
    </div>
  </div>
</div>

<!-- ============ HEADER ============ -->
<header id="header">
  <nav>
    <a href="#home" class="logo">
      <div class="logo-mark"><i class="fa-solid fa-graduation-cap"></i></div>
      <div class="logo-text">
        IEPA
        <small>University of Cape Coast</small>
      </div>
    </a>

    <ul class="nav-links">
      <li><a href="#home" class="active">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#programmes">Programmes</a></li>
      <li><a href="#admissions">Admissions</a></li>
      <li><a href="#resources">Resources</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="nav-actions">
      <a href="#portal" class="btn-ghost">
        <i class="fa-solid fa-user-graduate"></i> Portal
      </a>
      <a href="#apply" class="btn-gold">
        <i class="fa-solid fa-arrow-right-to-bracket"></i> Apply Now
      </a>
    </div>

    <button class="hamburger" id="hamburger" aria-label="Menu" aria-expanded="false">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<!-- ============ DRAWER ============ -->
<div class="drawer-overlay" id="drawerOverlay"></div>
<aside class="drawer" id="drawer" aria-hidden="true">
  <div class="drawer-top">
    <div class="drawer-brand">
      <div class="logo-mark"><i class="fa-solid fa-graduation-cap"></i></div>
      IEPA
    </div>
    <button class="drawer-close" id="drawerClose" aria-label="Close">
      <i class="fa-solid fa-xmark"></i>
    </button>
  </div>

  <div class="drawer-nav">
    <a href="#home" class="active"><i class="fa-solid fa-house"></i> Home</a>
    <a href="#about"><i class="fa-solid fa-circle-info"></i> About IEPA</a>
    <a href="#programmes"><i class="fa-solid fa-book-open"></i> Programmes</a>
    <a href="#admissions"><i class="fa-solid fa-user-plus"></i> Admissions</a>
    <a href="#students"><i class="fa-solid fa-users"></i> Students</a>
    <a href="#lecturers"><i class="fa-solid fa-chalkboard-user"></i> Lecturers</a>
    <a href="#research"><i class="fa-solid fa-flask"></i> Research</a>
    <a href="#resources"><i class="fa-solid fa-folder-open"></i> Resources</a>
    <a href="#news"><i class="fa-solid fa-newspaper"></i> News &amp; Events</a>
    <a href="#support"><i class="fa-solid fa-headset"></i> Student Support</a>
    <a href="#contact"><i class="fa-solid fa-envelope"></i> Contact</a>
  </div>

  <div class="drawer-divider"></div>

  <div class="drawer-cta">
    <a href="#apply" class="primary"><i class="fa-solid fa-pen-to-square"></i> Apply Now</a>
    <a href="#portal" class="outline"><i class="fa-solid fa-user-graduate"></i> Student Portal</a>
    <a href="#staff" class="outline"><i class="fa-solid fa-chalkboard-user"></i> Lecturer Portal</a>
    <a href="#admin" class="outline"><i class="fa-solid fa-user-shield"></i> Admin Login</a>
  </div>

  <div class="drawer-footer">
    <i class="fa-solid fa-location-dot"></i> University of Cape Coast, Ghana
  </div>
</aside>

<!-- ============ HERO ============ -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-noise"></div>

  <div class="hero-content">
    <div class="hero-badge">
      <span class="pulse"></span>
      Postgraduate Institute · University of Cape Coast
    </div>

    <h1>
      Shaping the future of <em>educational leadership</em> in Africa
    </h1>

    <p class="hero-sub">
      A centralised digital platform for IEPA students, lecturers and administrators — bringing information, resources and services into one seamless experience.
    </p>

    <div class="hero-actions">
      <a href="#programmes" class="btn btn-gold-lg">
        <i class="fa-solid fa-book-open"></i> Explore Programmes
        <i class="fa-solid fa-arrow-right"></i>
      </a>
      <a href="#portal" class="btn btn-glass">
        <i class="fa-solid fa-user-graduate"></i> Student Portal
      </a>
    </div>

    <div class="hero-stats">
      <div class="hero-stat">
        <span class="num">15+</span>
        <span class="lbl">Programmes</span>
      </div>
      <div class="hero-stat">
        <span class="num">500+</span>
        <span class="lbl">Students</span>
      </div>
      <div class="hero-stat">
        <span class="num">40+</span>
        <span class="lbl">Faculty</span>
      </div>
      <div class="hero-stat">
        <span class="num">25+</span>
        <span class="lbl">Years</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ TRUST STRIP ============ -->
<div class="trust-strip">
  <div class="trust-inner">
    <span><i class="fa-solid fa-award"></i> Accredited by GTEC</span>
    <span><i class="fa-solid fa-certificate"></i> Affiliated with UCC</span>
    <span><i class="fa-solid fa-globe"></i> International Recognition</span>
    <span><i class="fa-solid fa-flask"></i> Research-Driven</span>
  </div>
</div>

<!-- ============ QUICK ACCESS ============ -->
<section id="quick-access">
  <div class="container">
    <div class="section-head reveal">
      <div class="eyebrow">Explore IEPA</div>
      <h2>Everything you need, in one place</h2>
      <p>Quick access to the most important sections of our digital platform.</p>
    </div>

    <div class="bento">
      <a href="#programmes" class="bento-item bento-lg bento-featured reveal">
        <div class="bento-icon"><i class="fa-solid fa-book-open"></i></div>
        <h3>Programmes</h3>
        <p>Discover our Master's and PhD programmes in educational planning, administration and leadership — designed for practising professionals and emerging scholars.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>

      <a href="#admissions" class="bento-item bento-md reveal">
        <div class="bento-icon"><i class="fa-solid fa-user-plus"></i></div>
        <h3>Admissions</h3>
        <p>Requirements, deadlines and the application process.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>

      <a href="#portal" class="bento-item bento-md reveal">
        <div class="bento-icon"><i class="fa-solid fa-user-graduate"></i></div>
        <h3>Student Portal</h3>
        <p>Access your dashboard, courses and resources.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>

      <a href="#calendar" class="bento-item bento-sm reveal">
        <div class="bento-icon"><i class="fa-solid fa-calendar-days"></i></div>
        <h3>Academic Calendar</h3>
        <p>Key dates for the current academic year.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>

      <a href="#research" class="bento-item bento-sm reveal">
        <div class="bento-icon"><i class="fa-solid fa-flask"></i></div>
        <h3>Research</h3>
        <p>Guidelines, ethics, templates and supervision.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>

      <a href="#resources" class="bento-item bento-sm reveal">
        <div class="bento-icon"><i class="fa-solid fa-folder-open"></i></div>
        <h3>Resources</h3>
        <p>Forms, handbooks, policies and templates.</p>
        <i class="fa-solid fa-arrow-right bento-arrow"></i>
      </a>
    </div>
  </div>
</section>

<!-- ============ ANNOUNCEMENTS ============ -->
<section id="announcements" class="announcements-section">
  <div class="container">
    <div class="section-head reveal">
      <div class="eyebrow">Stay Informed</div>
      <h2>Latest Announcements</h2>
      <p>Important updates from the Institute for students, staff and applicants.</p>
    </div>

    <div class="ann-list">
      <a href="#" class="ann reveal">
        <div class="ann-date">
          <span class="day">15</span>
          <span class="mon">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag">Registration</span>
          <h4>Course Registration Now Open for Semester 2</h4>
          <p>All continuing Master's and PhD students should complete registration by 31 January 2026.</p>
        </div>
        <div class="ann-arrow"><i class="fa-solid fa-arrow-right"></i></div>
      </a>

      <a href="#" class="ann reveal">
        <div class="ann-date">
          <span class="day">10</span>
          <span class="mon">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag">Research</span>
          <h4>Thesis Proposal Submission Deadline Extended</h4>
          <p>Final-year students now have until 15 February 2026 to submit proposals to their supervisors.</p>
        </div>
        <div class="ann-arrow"><i class="fa-solid fa-arrow-right"></i></div>
      </a>

      <a href="#" class="ann reveal">
        <div class="ann-date">
          <span class="day">05</span>
          <span class="mon">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag">Examinations</span>
          <h4>End of Semester Examination Timetable Released</h4>
          <p>Check the Student Centre for your personalised examination schedule.</p>
        </div>
        <div class="ann-arrow"><i class="fa-solid fa-arrow-right"></i></div>
      </a>
    </div>
  </div>
</section>

<!-- ============ PROGRAMMES ============ -->
<section id="programmes">
  <div class="container">
    <div class="section-head reveal">
      <div class="eyebrow">Study With Us</div>
      <h2>Featured Programmes</h2>
      <p>Postgraduate degrees designed for educational leaders, planners and researchers.</p>
    </div>

    <div class="prog-grid">
      <a href="#" class="prog-card reveal">
        <div class="prog-visual"><i class="fa-solid fa-graduation-cap"></i></div>
        <div class="prog-body">
          <span class="prog-level">Master's</span>
          <h3>MPhil in Educational Administration</h3>
          <p>Advanced study in educational leadership, policy analysis and institutional administration.</p>
          <div class="prog-facts">
            <span><i class="fa-regular fa-clock"></i> 2 years</span>
            <span><i class="fa-solid fa-laptop"></i> Full-time</span>
          </div>
          <span class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></span>
        </div>
      </a>

      <a href="#" class="prog-card reveal">
        <div class="prog-visual"><i class="fa-solid fa-compass-drafting"></i></div>
        <div class="prog-body">
          <span class="prog-level">Master's</span>
          <h3>MEd in Educational Planning</h3>
          <p>Preparation for planning and policy roles within national and institutional education systems.</p>
          <div class="prog-facts">
            <span><i class="fa-regular fa-clock"></i> 2 years</span>
            <span><i class="fa-solid fa-laptop"></i> Full / Part</span>
          </div>
          <span class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></span>
        </div>
      </a>

      <a href="#" class="prog-card reveal">
        <div class="prog-visual"><i class="fa-solid fa-microscope"></i></div>
        <div class="prog-body">
          <span class="prog-level phd">Doctoral</span>
          <h3>PhD in Educational Administration</h3>
          <p>Research-intensive doctoral programme for senior education professionals and scholars.</p>
          <div class="prog-facts">
            <span><i class="fa-regular fa-clock"></i> 3–4 years</span>
            <span><i class="fa-solid fa-laptop"></i> Full-time</span>
          </div>
          <span class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></span>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- ============ CTA BANNER ============ -->
<section style="padding-top: 0;">
  <div class="cta-banner reveal">
    <div class="cta-content">
      <h2>Ready to take the next step in your <em>academic journey?</em></h2>
      <p>Applications for the 2026/2027 academic year are now open. Join a community of scholars shaping education across Africa.</p>
    </div>
    <div class="cta-actions">
      <a href="#apply" class="btn btn-gold-lg">
        <i class="fa-solid fa-pen-to-square"></i> Apply Now
      </a>
      <a href="#admissions" class="btn btn-glass">
        <i class="fa-solid fa-circle-info"></i> Learn More
      </a>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer id="contact">
  <div class="footer-inner">
    <div class="footer-brand">
      <div class="logo">
        <div class="logo-mark"><i class="fa-solid fa-graduation-cap"></i></div>
        <div class="logo-text">IEPA<small style="color: rgba(255,255,255,0.5);">University of Cape Coast</small></div>
      </div>
      <p>The Institute for Educational Planning and Administration — advancing postgraduate education, research and professional practice in Ghana and across Africa.</p>
      <div class="socials">
        <a href="#" aria-label="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
        <a href="#" aria-label="X"><i class="fa-brands fa-x-twitter"></i></a>
        <a href="#" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
        <a href="#" aria-label="YouTube"><i class="fa-brands fa-youtube"></i></a>
      </div>
    </div>

    <div>
      <h4>Explore</h4>
      <ul>
        <li><a href="#programmes"><i class="fa-solid fa-chevron-right"></i> Programmes</a></li>
        <li><a href="#admissions"><i class="fa-solid fa-chevron-right"></i> Admissions</a></li>
        <li><a href="#resources"><i class="fa-solid fa-chevron-right"></i> Resources</a></li>
        <li><a href="#research"><i class="fa-solid fa-chevron-right"></i> Research</a></li>
      </ul>
    </div>

    <div>
      <h4>Portals</h4>
      <ul>
        <li><a href="#portal"><i class="fa-solid fa-chevron-right"></i> Student Portal</a></li>
        <li><a href="#staff"><i class="fa-solid fa-chevron-right"></i> Lecturer Portal</a></li>
        <li><a href="#admin"><i class="fa-solid fa-chevron-right"></i> Admin Login</a></li>
        <li><a href="#helpdesk"><i class="fa-solid fa-chevron-right"></i> Help Desk</a></li>
      </ul>
    </div>

    <div>
      <h4>Contact</h4>
      <ul>
        <li><a href="mailto:iepa@ucc.edu.gh"><i class="fa-solid fa-envelope"></i> iepa@ucc.edu.gh</a></li>
        <li><a href="tel:+233332132400"><i class="fa-solid fa-phone"></i> +233 33 213 2400</a></li>
        <li><a href="https://ucc.edu.gh" target="_blank" rel="noopener"><i class="fa-solid fa-globe"></i> ucc.edu.gh</a></li>
      </ul>
    </div>
  </div>

  <div class="footer-bottom">
    <span>© 2026 Institute for Educational Planning and Administration · UCC</span>
    <div class="links">
      <a href="#privacy">Privacy Policy</a>
      <a href="#terms">Terms of Use</a>
      <a href="#accessibility">Accessibility</a>
    </div>
  </div>
</footer>

<button class="to-top" id="toTop" aria-label="Back to top">
  <i class="fa-solid fa-arrow-up"></i>
</button>

<script>
  // ===== Drawer =====
  const hamburger = document.getElementById('hamburger');
  const drawer = document.getElementById('drawer');
  const overlay = document.getElementById('drawerOverlay');
  const closeBtn = document.getElementById('drawerClose');
  const drawerLinks = drawer.querySelectorAll('a');

  const openDrawer = () => {
    drawer.classList.add('open');
    overlay.classList.add('open');
    hamburger.classList.add('open');
    hamburger.setAttribute('aria-expanded','true');
    drawer.setAttribute('aria-hidden','false');
    document.body.style.overflow = 'hidden';
  };
  const closeDrawer = () => {
    drawer.classList.remove('open');
    overlay.classList.remove('open');
    hamburger.classList.remove('open');
    hamburger.setAttribute('aria-expanded','false');
    drawer.setAttribute('aria-hidden','true');
    document.body.style.overflow = '';
  };

  hamburger.addEventListener('click', () => drawer.classList.contains('open') ? closeDrawer() : openDrawer());
  closeBtn.addEventListener('click', closeDrawer);
  overlay.addEventListener('click', closeDrawer);
  drawerLinks.forEach(l => l.addEventListener('click', closeDrawer));
  document.addEventListener('keydown', e => e.key === 'Escape' && closeDrawer());

  // ===== Scroll behaviours =====
  const header = document.getElementById('header');
  const toTop = document.getElementById('toTop');

  window.addEventListener('scroll', () => {
    const y = window.scrollY;
    header.classList.toggle('scrolled', y > 20);
    toTop.classList.toggle('visible', y > 600);
  });

  toTop.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

  // ===== Scroll reveal =====
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), (i % 4) * 80);
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12, rootMargin: '0px 0px -60px 0px' });
  revealEls.forEach(el => io.observe(el));

  // ===== Active nav link =====
  const sections = document.querySelectorAll('section[id]');
  const allNavLinks = document.querySelectorAll('.nav-links a, .drawer-nav a');
  const navIo = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.id;
        allNavLinks.forEach(l => {
          l.classList.toggle('active', l.getAttribute('href') === `#${id}`);
        });
      }
    });
  }, { threshold: 0.4 });
  sections.forEach(s => navIo.observe(s));
</script>

</body>
</html>
Redesign UI
