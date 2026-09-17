<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="theme-color" content="#0F172A">
<title>IEPA — Institute for Educational Planning and Administration | UCC</title>
<meta name="description" content="Postgraduate education, research and professional practice at the Institute for Educational Planning and Administration, University of Cape Coast, Ghana.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=DM+Sans:ital,opsz,wght@0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
  :root {
    /* Deep academic palette — slate + copper accent */
    --slate-950: #0B1120;
    --slate-900: #0F172A;
    --slate-800: #1E293B;
    --slate-700: #334155;
    --slate-500: #64748B;
    --slate-400: #94A3B8;
    --slate-300: #CBD5E1;
    --slate-200: #E2E8F0;
    --slate-100: #F1F5F9;
    --slate-50:  #F8FAFC;

    --copper-500: #C2703E;
    --copper-400: #D98555;
    --copper-300: #E8A87C;
    --copper-50:  #FDF5EF;

    --teal-500: #0D9488;
    --teal-50:  #F0FDFA;

    --white: #FFFFFF;
    --bg: #F8FAFC;

    --radius-sm: 10px;
    --radius: 16px;
    --radius-lg: 22px;
    --radius-xl: 28px;

    --shadow-sm: 0 1px 3px rgba(15,23,42,0.06);
    --shadow-md: 0 4px 16px rgba(15,23,42,0.08);
    --shadow-lg: 0 12px 40px rgba(15,23,42,0.12);

    --ease: cubic-bezier(0.22, 1, 0.36, 1);
    --dock-h: 72px;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
  html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }

  body {
    font-family: 'DM Sans', system-ui, -apple-system, sans-serif;
    background: var(--bg);
    color: var(--slate-900);
    line-height: 1.6;
    font-size: 15px;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
    padding-bottom: calc(var(--dock-h) + env(safe-area-inset-bottom) + 16px);
  }

  h1, h2, h3, h4, .font-display {
    font-family: 'Space Grotesk', system-ui, sans-serif;
    font-weight: 700;
    letter-spacing: -0.03em;
    line-height: 1.1;
  }

  a { color: inherit; text-decoration: none; }
  img { max-width: 100%; display: block; }
  button { font-family: inherit; cursor: pointer; border: none; background: none; color: inherit; }

  /* =====================================================
     TOP HEADER — minimal, app-like
     ===================================================== */
  .top-header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(248,250,252,0.9);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-bottom: 1px solid var(--slate-200);
  }
  .top-inner {
    max-width: 1200px;
    margin: 0 auto;
    padding: 12px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    min-height: 60px;
  }

  .brand {
    display: flex;
    align-items: center;
    gap: 10px;
    flex-shrink: 0;
  }
  .brand-mark {
    width: 38px;
    height: 38px;
    border-radius: 11px;
    background: var(--slate-900);
    display: grid;
    place-items: center;
    color: var(--copper-300);
    font-size: 0.95rem;
    box-shadow: 0 4px 12px rgba(15,23,42,0.25);
  }
  .brand-text {
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 700;
    font-size: 1.05rem;
    letter-spacing: -0.04em;
    color: var(--slate-900);
    line-height: 1.1;
  }
  .brand-text small {
    display: block;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.58rem;
    font-weight: 600;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--slate-400);
    margin-top: 1px;
  }

  .header-right {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .icon-btn {
    width: 42px;
    height: 42px;
    border-radius: 12px;
    display: grid;
    place-items: center;
    color: var(--slate-700);
    font-size: 1.05rem;
    transition: all 0.2s var(--ease);
    position: relative;
  }
  .icon-btn:active { transform: scale(0.94); background: var(--slate-100); }

  .icon-btn .badge-dot {
    position: absolute;
    top: 9px;
    right: 10px;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--copper-500);
    border: 2px solid var(--slate-50);
  }

  .btn-desktop {
    display: none;
  }

  /* =====================================================
     HERO — bold, mobile-first
     ===================================================== */
  .hero {
    padding: 40px 20px 32px;
    background: linear-gradient(180deg, var(--white) 0%, var(--bg) 100%);
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -80px;
    right: -80px;
    width: 260px;
    height: 260px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(194,112,62,0.10), transparent 70%);
    pointer-events: none;
  }
  .hero-inner {
    max-width: 1200px;
    margin: 0 auto;
    position: relative;
  }

  .hero-eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 7px 14px;
    background: var(--white);
    border: 1px solid var(--slate-200);
    border-radius: 100px;
    font-size: 0.72rem;
    font-weight: 600;
    color: var(--slate-700);
    margin-bottom: 20px;
    box-shadow: var(--shadow-sm);
    animation: fadeUp 0.6s var(--ease) both;
  }
  .hero-eyebrow .live-dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: var(--teal-500);
    box-shadow: 0 0 0 0 rgba(13,148,136,0.5);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(13,148,136,0.5); }
    70% { box-shadow: 0 0 0 8px rgba(13,148,136,0); }
    100% { box-shadow: 0 0 0 0 rgba(13,148,136,0); }
  }

  .hero h1 {
    font-size: clamp(1.9rem, 8vw, 3.4rem);
    font-weight: 700;
    line-height: 1.05;
    letter-spacing: -0.04em;
    margin-bottom: 18px;
    color: var(--slate-900);
    animation: fadeUp 0.6s 0.05s var(--ease) both;
  }
  .hero h1 .accent {
    color: var(--copper-500);
    position: relative;
    display: inline-block;
  }
  .hero h1 .accent::after {
    content: '';
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0.08em;
    height: 0.18em;
    background: linear-gradient(90deg, rgba(194,112,62,0.25), rgba(194,112,62,0.05));
    border-radius: 3px;
    z-index: -1;
  }

  .hero-lead {
    font-size: 1rem;
    color: var(--slate-500);
    line-height: 1.65;
    max-width: 580px;
    margin-bottom: 28px;
    animation: fadeUp 0.6s 0.1s var(--ease) both;
  }

  .hero-cta {
    display: flex;
    flex-direction: column;
    gap: 10px;
    animation: fadeUp 0.6s 0.15s var(--ease) both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    padding: 15px 24px;
    border-radius: 14px;
    font-size: 0.95rem;
    font-weight: 600;
    transition: all 0.25s var(--ease);
    min-height: 52px;
    white-space: nowrap;
    font-family: inherit;
  }
  .btn i { font-size: 0.9rem; transition: transform 0.3s var(--ease); }
  .btn:active { transform: scale(0.97); }
  .btn:hover i.fa-arrow-right { transform: translateX(3px); }

  .btn-dark {
    background: var(--slate-900);
    color: var(--white);
    box-shadow: 0 6px 20px rgba(15,23,42,0.25);
  }
  .btn-dark:hover { background: var(--slate-800); transform: translateY(-2px); box-shadow: 0 10px 28px rgba(15,23,42,0.35); }

  .btn-outline {
    background: var(--white);
    color: var(--slate-900);
    border: 1.5px solid var(--slate-200);
  }
  .btn-outline:hover { border-color: var(--slate-400); background: var(--slate-50); }

  /* Hero facts strip */
  .hero-facts {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    margin-top: 32px;
    animation: fadeUp 0.6s 0.2s var(--ease) both;
  }
  .fact-tile {
    background: var(--white);
    border: 1px solid var(--slate-200);
    border-radius: var(--radius);
    padding: 16px;
    box-shadow: var(--shadow-sm);
  }
  .fact-tile .number {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 1.6rem;
    font-weight: 700;
    letter-spacing: -0.04em;
    color: var(--slate-900);
    line-height: 1;
    display: block;
    margin-bottom: 4px;
  }
  .fact-tile .number span { color: var(--copper-500); }
  .fact-tile .label {
    font-size: 0.72rem;
    font-weight: 600;
    color: var(--slate-500);
    letter-spacing: 0.3px;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* =====================================================
     SECTIONS
     ===================================================== */
  section { padding: 44px 20px; }
  .container { max-width: 1200px; margin: 0 auto; }

  .section-head { margin-bottom: 24px; }
  .section-head .eyebrow {
    display: inline-block;
    font-size: 0.68rem;
    font-weight: 700;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--copper-500);
    margin-bottom: 8px;
  }
  .section-head h2 {
    font-size: clamp(1.5rem, 5.5vw, 2.2rem);
    font-weight: 700;
    letter-spacing: -0.035em;
    color: var(--slate-900);
    margin-bottom: 8px;
  }
  .section-head p {
    color: var(--slate-500);
    font-size: 0.95rem;
    max-width: 560px;
  }
  .section-head .row {
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 16px;
    flex-wrap: wrap;
  }
  .section-head .row h2 { margin-bottom: 0; }

  .see-all {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--slate-700);
    padding: 8px 12px;
    border-radius: 10px;
    transition: background 0.2s;
    white-space: nowrap;
    min-height: 40px;
  }
  .see-all:active { background: var(--slate-100); }
  .see-all i { font-size: 0.72rem; color: var(--copper-500); }

  /* =====================================================
     SERVICE GRID — 2 cols on mobile, big tap targets
     ===================================================== */
  .service-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }
  .service-card {
    background: var(--white);
    border: 1px solid var(--slate-200);
    border-radius: var(--radius);
    padding: 20px 16px;
    box-shadow: var(--shadow-sm);
    transition: all 0.25s var(--ease);
    display: flex;
    flex-direction: column;
    min-height: 140px;
    position: relative;
    overflow: hidden;
  }
  .service-card:active { transform: scale(0.97); }
  .service-card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
  }
  .service-card .icon-wrap {
    width: 46px;
    height: 46px;
    border-radius: 13px;
    display: grid;
    place-items: center;
    font-size: 1.15rem;
    margin-bottom: 14px;
    transition: transform 0.3s var(--ease);
  }
  .service-card:hover .icon-wrap { transform: scale(1.1) rotate(-4deg); }

  .ic-copper { background: var(--copper-50); color: var(--copper-500); }
  .ic-slate  { background: var(--slate-100); color: var(--slate-800); }
  .ic-teal   { background: var(--teal-50); color: var(--teal-500); }
  .ic-amber  { background: #FEF6E7; color: #B45309; }
  .ic-indigo { background: #EEF2FF; color: #4F46E5; }
  .ic-rose   { background: #FFF1F2; color: #E11D48; }
  .ic-emerald{ background: #ECFDF5; color: #059669; }
  .ic-violet { background: #F5F3FF; color: #7C3AED; }

  .service-card h3 {
    font-family: 'DM Sans', sans-serif;
    font-size: 0.92rem;
    font-weight: 700;
    color: var(--slate-900);
    margin-bottom: 3px;
    letter-spacing: -0.01em;
    line-height: 1.25;
  }
  .service-card p {
    font-size: 0.76rem;
    color: var(--slate-500);
    line-height: 1.45;
    margin-top: auto;
  }

  /* =====================================================
     ANNOUNCEMENTS — card list
     ===================================================== */
  .ann-list { display: flex; flex-direction: column; gap: 10px; }
  .ann-row {
    background: var(--white);
    border: 1px solid var(--slate-200);
    border-radius: var(--radius);
    padding: 16px;
    box-shadow: var(--shadow-sm);
    display: flex;
    gap: 14px;
    align-items: flex-start;
    transition: all 0.25s var(--ease);
    position: relative;
    overflow: hidden;
  }
  .ann-row:active { transform: scale(0.985); }
  .ann-row:hover {
    box-shadow: var(--shadow-md);
    border-color: transparent;
    transform: translateY(-2px);
  }

  .ann-date-block {
    flex-shrink: 0;
    width: 54px;
    height: 58px;
    border-radius: 13px;
    background: var(--slate-900);
    color: var(--white);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .ann-date-block .day {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 1.35rem;
    font-weight: 700;
    line-height: 1;
    letter-spacing: -0.04em;
  }
  .ann-date-block .month {
    font-size: 0.58rem;
    font-weight: 700;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    opacity: 0.7;
    margin-top: 3px;
  }

  .ann-content { flex: 1; min-width: 0; }
  .ann-chip {
    display: inline-block;
    padding: 3px 9px;
    border-radius: 100px;
    font-size: 0.63rem;
    font-weight: 700;
    letter-spacing: 0.7px;
    text-transform: uppercase;
    background: var(--copper-50);
    color: var(--copper-500);
    margin-bottom: 6px;
  }
  .ann-chip.teal { background: var(--teal-50); color: var(--teal-500); }
  .ann-chip.amber { background: #FEF6E7; color: #B45309; }

  .ann-content h4 {
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--slate-900);
    line-height: 1.35;
    margin-bottom: 4px;
    letter-spacing: -0.01em;
  }
  .ann-content p {
    font-size: 0.8rem;
    color: var(--slate-500);
    line-height: 1.5;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  /* =====================================================
     PROGRAMMES — horizontal swipe
     ===================================================== */
  .prog-scroller {
    display: flex;
    gap: 14px;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    padding: 4px 20px 22px;
    margin: 0 -20px;
    scrollbar-width: none;
    -webkit-overflow-scrolling: touch;
  }
  .prog-scroller::-webkit-scrollbar { display: none; }

  .prog-item {
    flex: 0 0 80%;
    scroll-snap-align: start;
    background: var(--white);
    border: 1px solid var(--slate-200);
    border-radius: var(--radius-lg);
    padding: 22px;
    box-shadow: var(--shadow-sm);
    display: flex;
    flex-direction: column;
    min-height: 280px;
    transition: all 0.3s var(--ease);
    position: relative;
    overflow: hidden;
  }
  .prog-item:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
  }
  .prog-item::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 5px;
    background: linear-gradient(90deg, var(--slate-900), var(--copper-400));
  }

  .prog-badge {
    display: inline-block;
    padding: 4px 10px;
    border-radius: 100px;
    font-size: 0.63rem;
    font-weight: 700;
    letter-spacing: 0.8px;
    text-transform: uppercase;
    background: var(--slate-100);
    color: var(--slate-700);
    margin-bottom: 14px;
    align-self: flex-start;
  }
  .prog-badge.phd {
    background: linear-gradient(135deg, #FEF6E7, #FDE8CC);
    color: #B45309;
  }

  .prog-item h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--slate-900);
    letter-spacing: -0.03em;
    line-height: 1.25;
    margin-bottom: 8px;
  }
  .prog-item .prog-desc {
    font-size: 0.83rem;
    color: var(--slate-500);
    line-height: 1.55;
    margin-bottom: 16px;
    flex: 1;
  }

  .prog-chips {
    display: flex;
    gap: 7px;
    flex-wrap: wrap;
    margin-bottom: 16px;
  }
  .prog-chip {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 5px 10px;
    background: var(--slate-100);
    border-radius: 8px;
    font-size: 0.7rem;
    font-weight: 600;
    color: var(--slate-700);
  }
  .prog-chip i { color: var(--copper-500); font-size: 0.72rem; }

  .prog-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.83rem;
    font-weight: 700;
    color: var(--slate-900);
    align-self: flex-start;
  }
  .prog-link i { color: var(--copper-500); transition: transform 0.25s var(--ease); }
  .prog-item:hover .prog-link i { transform: translateX(4px); }

  /* =====================================================
     BANNER
     ===================================================== */
  .banner {
    background: linear-gradient(135deg, var(--slate-900), var(--slate-800));
    border-radius: var(--radius-xl);
    padding: 32px 24px;
    color: var(--white);
    position: relative;
    overflow: hidden;
    text-align: center;
  }
  .banner::before {
    content: '';
    position: absolute;
    top: -40%;
    right: -20%;
    width: 280px;
    height: 280px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(194,112,62,0.25), transparent 70%);
  }
  .banner > * { position: relative; z-index: 1; }
  .banner h2 {
    font-size: clamp(1.3rem, 5vw, 1.9rem);
    font-weight: 700;
    letter-spacing: -0.035em;
    line-height: 1.15;
    margin-bottom: 10px;
  }
  .banner p {
    font-size: 0.9rem;
    opacity: 0.8;
    margin-bottom: 22px;
    max-width: 460px;
    margin-left: auto;
    margin-right: auto;
  }
  .banner-btns {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }
  .btn-light {
    background: var(--white);
    color: var(--slate-900);
    box-shadow: 0 6px 18px rgba(0,0,0,0.2);
  }
  .btn-light:hover { background: var(--slate-100); transform: translateY(-2px); }
  .btn-ghost-white {
    background: rgba(255,255,255,0.1);
    color: var(--white);
    border: 1px solid rgba(255,255,255,0.2);
  }
  .btn-ghost-white:hover { background: rgba(255,255,255,0.2); }

  /* =====================================================
     FOOTER
     ===================================================== */
  footer {
    background: var(--slate-950);
    color: rgba(255,255,255,0.65);
    padding: 40px 20px calc(var(--dock-h) + env(safe-area-inset-bottom) + 40px);
    font-size: 0.87rem;
  }
  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr;
    gap: 28px;
  }
  .footer-brand {
    display: flex;
    align-items: center;
    gap: 10px;
    color: var(--white);
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 700;
    font-size: 1.1rem;
    letter-spacing: -0.04em;
    margin-bottom: 12px;
  }
  .footer-brand .brand-mark {
    background: var(--slate-800);
    color: var(--copper-300);
    box-shadow: none;
  }
  footer .tagline {
    color: rgba(255,255,255,0.5);
    line-height: 1.65;
    max-width: 340px;
    margin-bottom: 20px;
  }

  .socials { display: flex; gap: 10px; }
  .socials a {
    width: 40px;
    height: 40px;
    border-radius: 12px;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.08);
    display: grid;
    place-items: center;
    color: rgba(255,255,255,0.7);
    transition: all 0.25s var(--ease);
  }
  .socials a:hover { background: var(--copper-500); color: var(--white); border-color: transparent; transform: translateY(-3px); }

  footer h4 {
    font-family: 'DM Sans', sans-serif;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 14px;
  }
  footer ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  footer ul a {
    color: rgba(255,255,255,0.55);
    font-size: 0.85rem;
    transition: color 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  footer ul a:hover { color: var(--copper-300); }
  footer ul a i { font-size: 0.7rem; color: var(--copper-500); }

  .footer-bottom {
    max-width: 1200px;
    margin: 32px auto 0;
    padding-top: 22px;
    border-top: 1px solid rgba(255,255,255,0.08);
    display: flex;
    flex-direction: column;
    gap: 14px;
    align-items: center;
    text-align: center;
    font-size: 0.76rem;
    color: rgba(255,255,255,0.4);
  }
  .footer-bottom .links { display: flex; gap: 20px; flex-wrap: wrap; justify-content: center; }
  .footer-bottom a:hover { color: var(--copper-300); }

  /* =====================================================
     FLOATING BOTTOM DOCK — the star of mobile UX
     ===================================================== */
  .dock {
    position: fixed;
    bottom: calc(12px + env(safe-area-inset-bottom));
    left: 16px;
    right: 16px;
    max-width: 500px;
    margin: 0 auto;
    height: 62px;
    background: rgba(15,23,42,0.94);
    backdrop-filter: saturate(180%) blur(24px);
    -webkit-backdrop-filter: saturate(180%) blur(24px);
    border-radius: 22px;
    display: flex;
    align-items: center;
    justify-content: space-around;
    padding: 0 6px;
    z-index: 300;
    box-shadow: 0 12px 40px rgba(15,23,42,0.35), 0 2px 8px rgba(0,0,0,0.2);
    border: 1px solid rgba(255,255,255,0.08);
  }

  .dock-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 2px;
    padding: 8px 4px;
    border-radius: 16px;
    color: rgba(255,255,255,0.5);
    font-size: 0.6rem;
    font-weight: 600;
    letter-spacing: 0.2px;
    transition: all 0.25s var(--ease);
    position: relative;
    min-height: 50px;
  }
  .dock-item i {
    font-size: 1.1rem;
    transition: transform 0.3s var(--ease);
  }
  .dock-item.active {
    color: var(--white);
  }
  .dock-item.active i {
    color: var(--copper-300);
    transform: translateY(-1px) scale(1.08);
  }
  .dock-item.active::before {
    content: '';
    position: absolute;
    top: 4px;
    width: 20px;
    height: 3px;
    border-radius: 3px;
    background: var(--copper-400);
  }
  .dock-item:active { transform: scale(0.94); }

  /* =====================================================
     SCROLL REVEAL
     ===================================================== */
  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s var(--ease), transform 0.7s var(--ease);
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* =====================================================
     DESKTOP (>= 768px)
     ===================================================== */
  @media (min-width: 768px) {
    body { font-size: 16px; padding-bottom: 0; }

    .top-inner { padding: 16px 40px; min-height: 72px; }
    .brand-mark { width: 42px; height: 42px; font-size: 1.05rem; }
    .brand-text { font-size: 1.15rem; }

    .btn-desktop {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 11px 20px;
      border-radius: 12px;
      background: var(--slate-900);
      color: var(--white);
      font-size: 0.88rem;
      font-weight: 600;
      transition: all 0.25s var(--ease);
      box-shadow: 0 4px 14px rgba(15,23,42,0.2);
      margin-left: 8px;
    }
    .btn-desktop:hover { background: var(--slate-800); transform: translateY(-2px); box-shadow: 0 8px 22px rgba(15,23,42,0.3); }

    .hero { padding: 72px 40px 56px; }
    .hero h1 { font-size: 3.4rem; }
    .hero-cta { flex-direction: row; }
    .hero-facts { grid-template-columns: repeat(4, 1fr); gap: 14px; margin-top: 48px; }

    section { padding: 72px 40px; }
    .service-grid { grid-template-columns: repeat(4, 1fr); gap: 16px; }
    .service-card { min-height: 170px; padding: 24px; }

    .prog-scroller {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      overflow: visible;
      padding: 0;
      margin: 0;
    }
    .prog-item { flex: none; min-height: 320px; padding: 26px; }

    .banner { padding: 56px 48px; }

    .footer-inner { grid-template-columns: 1.6fr 1fr 1fr 1fr; gap: 40px; }
    .footer-bottom { flex-direction: row; justify-content: space-between; text-align: left; }
    footer { padding: 64px 40px 40px; }

    .dock { display: none; }
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

<!-- ============ TOP HEADER ============ -->
<header class="top-header">
  <div class="top-inner">
    <a href="#home" class="brand">
      <div class="brand-mark"><i class="fa-solid fa-graduation-cap"></i></div>
      <div class="brand-text">
        IEPA
        <small>University of Cape Coast</small>
      </div>
    </a>

    <div class="header-right">
      <button class="icon-btn" aria-label="Search">
        <i class="fa-solid fa-magnifying-glass"></i>
      </button>
      <button class="icon-btn" aria-label="Notifications">
        <i class="fa-regular fa-bell"></i>
        <span class="badge-dot"></span>
      </button>
      <a href="#apply" class="btn-desktop">
        Apply Now <i class="fa-solid fa-arrow-right"></i>
      </a>
    </div>
  </div>
</header>

<!-- ============ HERO ============ -->
<section class="hero" id="home">
  <div class="hero-inner">
    <div class="hero-eyebrow">
      <span class="live-dot"></span>
      UNESCO Category II Centre of Excellence · Applications Open 2026/2027
    </div>

    <h1>
      Shaping <span class="accent">educational leaders</span> for Africa's future.
    </h1>

    <p class="hero-lead">
      The Institute for Educational Planning and Administration at the University of Cape Coast — a postgraduate institute dedicated to research, policy and professional practice in education.
    </p>

    <div class="hero-cta">
      <a href="#programmes" class="btn btn-dark">
        Explore Programmes <i class="fa-solid fa-arrow-right"></i>
      </a>
      <a href="#portal" class="btn btn-outline">
        <i class="fa-solid fa-user-graduate"></i> Student Portal
      </a>
    </div>

    <div class="hero-facts">
      <div class="fact-tile">
        <span class="number">15<span>+</span></span>
        <span class="label">Programmes</span>
      </div>
      <div class="fact-tile">
        <span class="number">500<span>+</span></span>
        <span class="label">Students</span>
      </div>
      <div class="fact-tile">
        <span class="number">40<span>+</span></span>
        <span class="label">Faculty</span>
      </div>
      <div class="fact-tile">
        <span class="number">50<span>+</span></span>
        <span class="label">Years of Impact</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ SERVICE GRID ============ -->
<section id="quick-access">
  <div class="container">
    <div class="section-head reveal">
      <span class="eyebrow">Quick Access</span>
      <h2>Everything in one place</h2>
      <p>Direct links to the most used sections of the platform.</p>
    </div>

    <div class="service-grid">
      <a href="#programmes" class="service-card reveal">
        <div class="icon-wrap ic-slate"><i class="fa-solid fa-book-open"></i></div>
        <h3>Programmes</h3>
        <p>MPhil, MEd & PhD</p>
      </a>
      <a href="#admissions" class="service-card reveal">
        <div class="icon-wrap ic-copper"><i class="fa-solid fa-user-plus"></i></div>
        <h3>Admissions</h3>
        <p>How to apply</p>
      </a>
      <a href="#calendar" class="service-card reveal">
        <div class="icon-wrap ic-amber"><i class="fa-regular fa-calendar-days"></i></div>
        <h3>Calendar</h3>
        <p>Key dates</p>
      </a>
      <a href="#portal" class="service-card reveal">
        <div class="icon-wrap ic-indigo"><i class="fa-solid fa-user-graduate"></i></div>
        <h3>Portal</h3>
        <p>Student login</p>
      </a>
      <a href="#research" class="service-card reveal">
        <div class="icon-wrap ic-teal"><i class="fa-solid fa-flask"></i></div>
        <h3>Research</h3>
        <p>Guidelines & ethics</p>
      </a>
      <a href="#resources" class="service-card reveal">
        <div class="icon-wrap ic-rose"><i class="fa-solid fa-folder-open"></i></div>
        <h3>Resources</h3>
        <p>Forms & templates</p>
      </a>
      <a href="#forms" class="service-card reveal">
        <div class="icon-wrap ic-emerald"><i class="fa-regular fa-file-lines"></i></div>
        <h3>Forms</h3>
        <p>Downloads</p>
      </a>
      <a href="#contact" class="service-card reveal">
        <div class="icon-wrap ic-violet"><i class="fa-solid fa-address-book"></i></div>
        <h3>Contact</h3>
        <p>Directory</p>
      </a>
    </div>
  </div>
</section>

<!-- ============ ANNOUNCEMENTS ============ -->
<section id="announcements">
  <div class="container">
    <div class="section-head">
      <div class="row">
        <div>
          <span class="eyebrow">Latest</span>
          <h2>Announcements</h2>
        </div>
        <a href="#" class="see-all">
          See all <i class="fa-solid fa-arrow-right"></i>
        </a>
      </div>
    </div>

    <div class="ann-list">
      <a href="#" class="ann-row reveal">
        <div class="ann-date-block">
          <span class="day">15</span>
          <span class="month">Jan</span>
        </div>
        <div class="ann-content">
          <span class="ann-chip">Registration</span>
          <h4>Course registration open for Semester 2</h4>
          <p>All continuing Master's and PhD students should complete registration by 31 January 2026.</p>
        </div>
      </a>

      <a href="#" class="ann-row reveal">
        <div class="ann-date-block">
          <span class="day">10</span>
          <span class="month">Jan</span>
        </div>
        <div class="ann-content">
          <span class="ann-chip teal">Research</span>
          <h4>Thesis proposal deadline extended</h4>
          <p>Final-year students now have until 15 February 2026 to submit proposals to their supervisors.</p>
        </div>
      </a>

      <a href="#" class="ann-row reveal">
        <div class="ann-date-block">
          <span class="day">05</span>
          <span class="month">Jan</span>
        </div>
        <div class="ann-content">
          <span class="ann-chip amber">Exams</span>
          <h4>Examination timetable released</h4>
          <p>Check the Student Centre for your personalised examination schedule.</p>
        </div>
      </a>
    </div>
  </div>
</section>

<!-- ============ PROGRAMMES ============ -->
<section id="programmes">
  <div class="container">
    <div class="section-head">
      <div class="row">
        <div>
          <span class="eyebrow">Study With Us</span>
          <h2>Featured Programmes</h2>
        </div>
        <a href="#" class="see-all">
          All <i class="fa-solid fa-arrow-right"></i>
        </a>
      </div>
    </div>

    <div class="prog-scroller">
      <article class="prog-item reveal">
        <span class="prog-badge">Master's</span>
        <h3>MPhil in Educational Planning</h3>
        <p class="prog-desc">Blended-format programme for appraising and diagnosing educational challenges — formulating, implementing and evaluating plans and policies.</p>
        <div class="prog-chips">
          <span class="prog-chip"><i class="fa-regular fa-clock"></i> 2 years</span>
          <span class="prog-chip"><i class="fa-solid fa-laptop"></i> Blended</span>
        </div>
        <a href="#" class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>

      <article class="prog-item reveal">
        <span class="prog-badge">Master's</span>
        <h3>MEd in Educational Planning</h3>
        <p class="prog-desc">Part-time, professional-oriented programme for skilled educational planners — aligned with SDG 4 and the Education 2030 Agenda.</p>
        <div class="prog-chips">
          <span class="prog-chip"><i class="fa-regular fa-clock"></i> 2 years</span>
          <span class="prog-chip"><i class="fa-solid fa-laptop"></i> Part-time</span>
        </div>
        <a href="#" class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>

      <article class="prog-item reveal">
        <span class="prog-badge phd">Doctoral</span>
        <h3>PhD in Educational Administration</h3>
        <p class="prog-desc">Research-intensive doctoral programme for senior education professionals and scholars. Progression requires successful defence of research proposal.</p>
        <div class="prog-chips">
          <span class="prog-chip"><i class="fa-regular fa-clock"></i> 3–4 years</span>
          <span class="prog-chip"><i class="fa-solid fa-laptop"></i> Full-time</span>
        </div>
        <a href="#" class="prog-link">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>
    </div>
  </div>
</section>

<!-- ============ BANNER ============ -->
<section style="padding-top: 0;">
  <div class="container">
    <div class="banner reveal">
      <h2>Begin your postgraduate journey at IEPA</h2>
      <p>Applications for 2026/2027 are now open. Join a community of scholars and practitioners shaping education across West Africa.</p>
      <div class="banner-btns">
        <a href="#apply" class="btn btn-light">
          <i class="fa-solid fa-pen-to-square"></i> Apply Now
        </a>
        <a href="#admissions" class="btn btn-ghost-white">
          Learn More
        </a>
      </div>
    </div>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer id="contact">
  <div class="footer-inner">
    <div>
      <div class="footer-brand">
        <div class="brand-mark"><i class="fa-solid fa-graduation-cap"></i></div>
        IEPA
      </div>
      <p class="tagline">
        Institute for Educational Planning and Administration — a UNESCO Category II Centre of Excellence at the University of Cape Coast, Ghana.
      </p>
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
    <span>© 2026 IEPA · University of Cape Coast</span>
    <div class="links">
      <a href="#privacy">Privacy</a>
      <a href="#terms">Terms</a>
      <a href="#accessibility">Accessibility</a>
    </div>
  </div>
</footer>

<!-- ============ FLOATING BOTTOM DOCK ============ -->
<nav class="dock" aria-label="Primary navigation">
  <a href="#home" class="dock-item active">
    <i class="fa-solid fa-house"></i>
    Home
  </a>
  <a href="#programmes" class="dock-item">
    <i class="fa-solid fa-book-open"></i>
    Programmes
  </a>
  <a href="#portal" class="dock-item">
    <i class="fa-solid fa-user-graduate"></i>
    Portal
  </a>
  <a href="#announcements" class="dock-item">
    <i class="fa-regular fa-bell"></i>
    Alerts
  </a>
  <a href="#contact" class="dock-item">
    <i class="fa-regular fa-user"></i>
    Contact
  </a>
</nav>

<script>
  // Scroll reveal
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), (i % 4) * 70);
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
  revealEls.forEach(el => io.observe(el));

  // Sync active state between sections and dock
  const sections = document.querySelectorAll('section[id]');
  const dockItems = document.querySelectorAll('.dock-item');
  const navIo = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.id;
        dockItems.forEach(item => {
          item.classList.toggle('active', item.getAttribute('href') === '#' + id);
        });
      }
    });
  }, { threshold: 0.4 });
  sections.forEach(s => navIo.observe(s));
</script>

</body>
</html>
