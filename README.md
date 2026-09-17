<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="theme-color" content="#0B5FFF">
<title>IEPA — Institute for Educational Planning and Administration | UCC</title>
<meta name="description" content="Postgraduate education, research and professional practice at the Institute for Educational Planning and Administration, University of Cape Coast.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
  :root {
    /* Modern palette — bright, friendly, professional */
    --blue-600: #0B5FFF;
    --blue-500: #2E7BFF;
    --blue-400: #5B96FF;
    --blue-50:  #EEF4FF;
    --ink-900:  #0A0E1A;
    --ink-700:  #2A3142;
    --ink-500:  #5B6478;
    --ink-400:  #8B94A7;
    --ink-200:  #E4E7EE;
    --ink-100:  #F1F3F8;
    --bg:       #FAFBFC;
    --white:    #FFFFFF;
    --success:  #10B981;
    --warn:     #F59E0B;
    --accent:   #FF6B35;

    --radius-sm: 10px;
    --radius:    16px;
    --radius-lg: 22px;
    --radius-xl: 28px;

    --shadow-xs: 0 1px 2px rgba(10,14,26,0.04);
    --shadow-sm: 0 2px 8px rgba(10,14,26,0.05);
    --shadow-md: 0 6px 20px rgba(10,14,26,0.08);
    --shadow-lg: 0 16px 40px rgba(10,14,26,0.12);

    --ease: cubic-bezier(0.32, 0.72, 0, 1);
    --header-h: 64px;
    --tabbar-h: 68px;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
  html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }

  body {
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
    background: var(--bg);
    color: var(--ink-900);
    line-height: 1.55;
    font-size: 15px;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
    padding-bottom: env(safe-area-inset-bottom);
  }

  h1, h2, h3, h4, .font-display {
    font-family: 'Outfit', system-ui, sans-serif;
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1.15;
  }

  a { color: inherit; text-decoration: none; }
  img { max-width: 100%; display: block; }
  button { font-family: inherit; cursor: pointer; border: none; background: none; color: inherit; }

  /* =====================================================
     HEADER  — app-style, sticky
     ===================================================== */
  .app-header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(255,255,255,0.85);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-bottom: 1px solid var(--ink-200);
  }
  .header-inner {
    max-width: 1200px;
    margin: 0 auto;
    height: var(--header-h);
    padding: 0 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
  }
  .brand {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Outfit', sans-serif;
    font-weight: 800;
    font-size: 1.15rem;
    letter-spacing: -0.03em;
    color: var(--ink-900);
    flex-shrink: 0;
  }
  .brand-mark {
    width: 36px;
    height: 36px;
    border-radius: 10px;
    background: linear-gradient(135deg, var(--blue-600), var(--blue-400));
    display: grid;
    place-items: center;
    color: white;
    font-size: 0.95rem;
    box-shadow: 0 4px 12px rgba(11,95,255,0.3);
  }
  .brand small {
    display: block;
    font-family: 'Inter', sans-serif;
    font-size: 0.62rem;
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--ink-400);
    margin-top: -1px;
  }

  /* Desktop nav */
  .desktop-nav {
    display: none;
    align-items: center;
    gap: 4px;
    list-style: none;
  }
  .desktop-nav a {
    padding: 8px 14px;
    border-radius: 10px;
    font-size: 0.9rem;
    font-weight: 500;
    color: var(--ink-700);
    transition: all 0.2s var(--ease);
  }
  .desktop-nav a:hover { background: var(--ink-100); color: var(--ink-900); }
  .desktop-nav a.active { color: var(--blue-600); background: var(--blue-50); font-weight: 600; }

  .header-actions { display: flex; align-items: center; gap: 6px; }

  .icon-btn {
    width: 42px;
    height: 42px;
    border-radius: 12px;
    display: grid;
    place-items: center;
    color: var(--ink-700);
    font-size: 1rem;
    transition: all 0.2s var(--ease);
    position: relative;
  }
  .icon-btn:hover { background: var(--ink-100); }
  .icon-btn:active { transform: scale(0.94); }

  .icon-btn .dot {
    position: absolute;
    top: 9px; right: 10px;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--accent);
    border: 2px solid var(--white);
  }

  .btn-primary {
    display: none;
    align-items: center;
    gap: 6px;
    padding: 10px 18px;
    border-radius: 12px;
    background: var(--blue-600);
    color: white;
    font-size: 0.88rem;
    font-weight: 600;
    transition: all 0.25s var(--ease);
    box-shadow: 0 4px 14px rgba(11,95,255,0.3);
  }
  .btn-primary:hover {
    background: #0A4FD9;
    transform: translateY(-1px);
    box-shadow: 0 8px 20px rgba(11,95,255,0.4);
  }
  .btn-primary:active { transform: translateY(0) scale(0.98); }

  /* =====================================================
     HERO — clean, bright, mobile-first
     ===================================================== */
  .hero {
    padding: 32px 20px 40px;
    background: linear-gradient(180deg, var(--blue-50) 0%, var(--bg) 100%);
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -100px; right: -100px;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(11,95,255,0.12), transparent 70%);
    pointer-events: none;
  }
  .hero-inner {
    max-width: 1200px;
    margin: 0 auto;
    position: relative;
  }
  .hero-chip {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 6px 12px;
    background: white;
    border: 1px solid var(--ink-200);
    border-radius: 100px;
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--ink-700);
    margin-bottom: 20px;
    box-shadow: var(--shadow-xs);
    animation: fadeUp 0.6s var(--ease) both;
  }
  .hero-chip .pulse {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--success);
    box-shadow: 0 0 0 0 rgba(16,185,129,0.5);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(16,185,129,0.5); }
    70% { box-shadow: 0 0 0 8px rgba(16,185,129,0); }
    100% { box-shadow: 0 0 0 0 rgba(16,185,129,0); }
  }

  .hero h1 {
    font-size: clamp(2rem, 8vw, 3.5rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.035em;
    margin-bottom: 16px;
    color: var(--ink-900);
    animation: fadeUp 0.6s 0.05s var(--ease) both;
  }
  .hero h1 .accent {
    background: linear-gradient(135deg, var(--blue-600), var(--blue-400));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  .hero p {
    font-size: 1rem;
    color: var(--ink-500);
    line-height: 1.6;
    max-width: 560px;
    margin-bottom: 28px;
    animation: fadeUp 0.6s 0.1s var(--ease) both;
  }

  .hero-cta {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
    animation: fadeUp 0.6s 0.15s var(--ease) both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 14px 22px;
    border-radius: 14px;
    font-size: 0.92rem;
    font-weight: 600;
    transition: all 0.25s var(--ease);
    min-height: 48px;
    white-space: nowrap;
  }
  .btn i { font-size: 0.9rem; transition: transform 0.3s var(--ease); }
  .btn:hover i.fa-arrow-right { transform: translateX(3px); }

  .btn-blue {
    background: var(--blue-600);
    color: white;
    box-shadow: 0 6px 18px rgba(11,95,255,0.3);
  }
  .btn-blue:hover { background: #0A4FD9; transform: translateY(-2px); box-shadow: 0 10px 24px rgba(11,95,255,0.4); }
  .btn-blue:active { transform: translateY(0) scale(0.98); }

  .btn-ghost {
    background: white;
    color: var(--ink-900);
    border: 1px solid var(--ink-200);
  }
  .btn-ghost:hover { border-color: var(--ink-400); background: var(--ink-100); }

  /* Hero stats — inline small */
  .hero-stats {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    margin-top: 36px;
    animation: fadeUp 0.6s 0.2s var(--ease) both;
  }
  .stat-card {
    background: white;
    border-radius: var(--radius);
    padding: 16px;
    border: 1px solid var(--ink-200);
    box-shadow: var(--shadow-xs);
  }
  .stat-card .num {
    font-family: 'Outfit', sans-serif;
    font-size: 1.75rem;
    font-weight: 800;
    color: var(--ink-900);
    line-height: 1;
    letter-spacing: -0.03em;
    margin-bottom: 4px;
    display: block;
  }
  .stat-card .num .plus { color: var(--blue-600); }
  .stat-card .lbl {
    font-size: 0.78rem;
    color: var(--ink-500);
    font-weight: 500;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* =====================================================
     SECTIONS
     ===================================================== */
  section { padding: 48px 20px; }
  .container { max-width: 1200px; margin: 0 auto; }

  .section-head { margin-bottom: 24px; }
  .section-head.center { text-align: center; }
  .section-head .eyebrow {
    display: inline-block;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--blue-600);
    margin-bottom: 8px;
  }
  .section-head h2 {
    font-size: clamp(1.5rem, 5vw, 2.25rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    color: var(--ink-900);
    margin-bottom: 8px;
  }
  .section-head p {
    color: var(--ink-500);
    font-size: 0.95rem;
    max-width: 560px;
  }
  .section-head.center p { margin: 0 auto; }

  .section-head .row {
    display: flex;
    align-items: end;
    justify-content: space-between;
    gap: 16px;
    flex-wrap: wrap;
  }
  .section-head .row h2 { margin-bottom: 0; }
  .see-all {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--blue-600);
    padding: 8px 12px;
    border-radius: 10px;
    transition: background 0.2s;
    white-space: nowrap;
  }
  .see-all:hover { background: var(--blue-50); }
  .see-all i { font-size: 0.75rem; }

  /* =====================================================
     QUICK ACCESS GRID — big thumb-friendly tiles
     ===================================================== */
  .quick-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
  }
  .quick-tile {
    background: white;
    border-radius: var(--radius);
    padding: 18px 16px;
    border: 1px solid var(--ink-200);
    box-shadow: var(--shadow-xs);
    transition: all 0.25s var(--ease);
    display: flex;
    flex-direction: column;
    min-height: 120px;
    position: relative;
    overflow: hidden;
  }
  .quick-tile:active { transform: scale(0.97); }
  .quick-tile:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-md);
    border-color: transparent;
  }
  .quick-tile .icon {
    width: 44px;
    height: 44px;
    border-radius: 12px;
    display: grid;
    place-items: center;
    font-size: 1.05rem;
    margin-bottom: 14px;
    transition: transform 0.3s var(--ease);
  }
  .quick-tile:hover .icon { transform: scale(1.1) rotate(-5deg); }

  .icon-blue { background: var(--blue-50); color: var(--blue-600); }
  .icon-green { background: #E7F8F1; color: var(--success); }
  .icon-orange { background: #FFF1EB; color: var(--accent); }
  .icon-purple { background: #F2EBFF; color: #7C3AED; }
  .icon-amber { background: #FEF6E7; color: var(--warn); }
  .icon-pink { background: #FDECF3; color: #EC4899; }
  .icon-teal { background: #E5F6F7; color: #0D9488; }
  .icon-indigo { background: #EBEEFF; color: #4F46E5; }

  .quick-tile h3 {
    font-family: 'Inter', sans-serif;
    font-size: 0.92rem;
    font-weight: 700;
    color: var(--ink-900);
    margin-bottom: 2px;
    letter-spacing: -0.01em;
  }
  .quick-tile p {
    font-size: 0.78rem;
    color: var(--ink-500);
    line-height: 1.45;
  }

  /* =====================================================
     ANNOUNCEMENTS — mobile card list
     ===================================================== */
  .ann-list { display: flex; flex-direction: column; gap: 10px; }
  .ann-card {
    background: white;
    border-radius: var(--radius);
    padding: 16px;
    border: 1px solid var(--ink-200);
    box-shadow: var(--shadow-xs);
    transition: all 0.25s var(--ease);
    display: flex;
    gap: 14px;
    align-items: flex-start;
    position: relative;
    overflow: hidden;
  }
  .ann-card:active { transform: scale(0.985); }
  .ann-card:hover {
    box-shadow: var(--shadow-md);
    border-color: transparent;
    transform: translateY(-2px);
  }

  .ann-date {
    flex-shrink: 0;
    width: 52px;
    height: 56px;
    border-radius: 12px;
    background: var(--blue-50);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: var(--blue-600);
  }
  .ann-date .d {
    font-family: 'Outfit', sans-serif;
    font-size: 1.35rem;
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
  }
  .ann-date .m {
    font-size: 0.62rem;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-top: 2px;
  }

  .ann-body { flex: 1; min-width: 0; }
  .ann-tag {
    display: inline-block;
    padding: 3px 9px;
    border-radius: 100px;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.6px;
    text-transform: uppercase;
    background: var(--blue-50);
    color: var(--blue-600);
    margin-bottom: 6px;
  }
  .ann-tag.green { background: #E7F8F1; color: var(--success); }
  .ann-tag.orange { background: #FFF1EB; color: var(--accent); }

  .ann-body h4 {
    font-family: 'Inter', sans-serif;
    font-size: 0.92rem;
    font-weight: 700;
    color: var(--ink-900);
    line-height: 1.35;
    margin-bottom: 4px;
    letter-spacing: -0.01em;
  }
  .ann-body p {
    font-size: 0.82rem;
    color: var(--ink-500);
    line-height: 1.5;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  /* =====================================================
     PROGRAMMES — horizontal scroll on mobile
     ===================================================== */
  .prog-scroll {
    display: flex;
    gap: 14px;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    padding: 4px 20px 20px;
    margin: 0 -20px;
    scrollbar-width: none;
    -webkit-overflow-scrolling: touch;
  }
  .prog-scroll::-webkit-scrollbar { display: none; }

  .prog-card {
    flex: 0 0 78%;
    scroll-snap-align: start;
    background: white;
    border-radius: var(--radius-lg);
    padding: 20px;
    border: 1px solid var(--ink-200);
    box-shadow: var(--shadow-sm);
    display: flex;
    flex-direction: column;
    min-height: 260px;
    transition: all 0.3s var(--ease);
    position: relative;
    overflow: hidden;
  }
  .prog-card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
  }
  .prog-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 6px;
    background: linear-gradient(90deg, var(--blue-600), var(--blue-400));
  }

  .prog-level {
    display: inline-block;
    padding: 4px 10px;
    border-radius: 100px;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.8px;
    text-transform: uppercase;
    background: var(--ink-100);
    color: var(--ink-700);
    margin-bottom: 14px;
    align-self: flex-start;
  }
  .prog-level.phd {
    background: linear-gradient(135deg, #FFF1EB, #FFE0D0);
    color: var(--accent);
  }

  .prog-card h3 {
    font-family: 'Outfit', sans-serif;
    font-size: 1.15rem;
    font-weight: 700;
    color: var(--ink-900);
    letter-spacing: -0.02em;
    line-height: 1.25;
    margin-bottom: 8px;
  }
  .prog-card .desc {
    font-size: 0.85rem;
    color: var(--ink-500);
    line-height: 1.5;
    margin-bottom: 16px;
    flex: 1;
  }
  .prog-facts {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 14px;
  }
  .prog-fact {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 5px 10px;
    background: var(--ink-100);
    border-radius: 8px;
    font-size: 0.72rem;
    font-weight: 600;
    color: var(--ink-700);
  }
  .prog-fact i { color: var(--blue-600); font-size: 0.75rem; }

  .prog-cta {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.85rem;
    font-weight: 700;
    color: var(--blue-600);
    align-self: flex-start;
  }
  .prog-cta i { transition: transform 0.25s var(--ease); }
  .prog-card:hover .prog-cta i { transform: translateX(4px); }

  /* =====================================================
     FEATURE BANNER (CTA)
     ===================================================== */
  .cta-banner {
    background: linear-gradient(135deg, var(--blue-600), #4F46E5);
    border-radius: var(--radius-xl);
    padding: 32px 24px;
    color: white;
    position: relative;
    overflow: hidden;
    text-align: center;
  }
  .cta-banner::before {
    content: '';
    position: absolute;
    top: -40%; right: -20%;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(255,255,255,0.15), transparent 70%);
  }
  .cta-banner::after {
    content: '';
    position: absolute;
    bottom: -40%; left: -20%;
    width: 240px; height: 240px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(255,255,255,0.08), transparent 70%);
  }
  .cta-banner > * { position: relative; z-index: 1; }
  .cta-banner h2 {
    font-size: clamp(1.4rem, 5vw, 2rem);
    font-weight: 800;
    letter-spacing: -0.03em;
    line-height: 1.15;
    margin-bottom: 10px;
  }
  .cta-banner p {
    font-size: 0.92rem;
    opacity: 0.9;
    margin-bottom: 22px;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
  }
  .cta-banner .btns {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }
  .btn-white {
    background: white;
    color: var(--blue-600);
    box-shadow: 0 6px 18px rgba(0,0,0,0.15);
  }
  .btn-white:hover { background: #F5F8FF; transform: translateY(-2px); }
  .btn-glass {
    background: rgba(255,255,255,0.15);
    color: white;
    border: 1px solid rgba(255,255,255,0.25);
    backdrop-filter: blur(10px);
  }
  .btn-glass:hover { background: rgba(255,255,255,0.25); }

  /* =====================================================
     FOOTER
     ===================================================== */
  footer {
    background: var(--ink-900);
    color: rgba(255,255,255,0.7);
    padding: 40px 20px 100px; /* bottom padding for tabbar */
    font-size: 0.88rem;
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
    color: white;
    font-family: 'Outfit', sans-serif;
    font-weight: 800;
    font-size: 1.2rem;
    letter-spacing: -0.03em;
    margin-bottom: 12px;
  }
  .footer-brand .brand-mark {
    box-shadow: 0 4px 12px rgba(11,95,255,0.4);
  }
  footer p.tagline { color: rgba(255,255,255,0.55); line-height: 1.6; max-width: 340px; margin-bottom: 20px; }

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
  .socials a:hover {
    background: var(--blue-600);
    color: white;
    border-color: transparent;
    transform: translateY(-3px);
  }

  footer h4 {
    font-family: 'Inter', sans-serif;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: white;
    margin-bottom: 14px;
  }
  footer ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
  footer ul a {
    color: rgba(255,255,255,0.55);
    font-size: 0.87rem;
    transition: color 0.2s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  footer ul a:hover { color: var(--blue-400); }
  footer ul a i { font-size: 0.75rem; color: var(--blue-500); }

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
    font-size: 0.78rem;
    color: rgba(255,255,255,0.4);
  }
  .footer-bottom .links { display: flex; gap: 20px; flex-wrap: wrap; justify-content: center; }
  .footer-bottom a:hover { color: var(--blue-400); }

  /* =====================================================
     BOTTOM TAB BAR (mobile only)
     ===================================================== */
  .tabbar {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    height: calc(var(--tabbar-h) + env(safe-area-inset-bottom));
    padding-bottom: env(safe-area-inset-bottom);
    background: rgba(255,255,255,0.92);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-top: 1px solid var(--ink-200);
    display: flex;
    justify-content: space-around;
    align-items: center;
    z-index: 200;
  }
  .tab {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 3px;
    padding: 8px 4px;
    color: var(--ink-400);
    font-size: 0.65rem;
    font-weight: 600;
    letter-spacing: 0.2px;
    transition: color 0.2s var(--ease);
    position: relative;
  }
  .tab i {
    font-size: 1.15rem;
    transition: transform 0.3s var(--ease);
  }
  .tab.active { color: var(--blue-600); }
  .tab.active i { transform: translateY(-1px) scale(1.05); }
  .tab.active::before {
    content: '';
    position: absolute;
    top: 4px;
    width: 22px;
    height: 3px;
    border-radius: 3px;
    background: var(--blue-600);
  }

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
     DESKTOP  (>= 768px)
     ===================================================== */
  @media (min-width: 768px) {
    body { font-size: 16px; }
    section { padding: 72px 40px; }

    .header-inner { padding: 0 32px; }
    .desktop-nav { display: flex; }
    .btn-primary { display: inline-flex; }
    .hero { padding: 72px 40px 80px; }
    .hero-stats { grid-template-columns: repeat(4, 1fr); gap: 16px; margin-top: 48px; }
    .quick-grid { grid-template-columns: repeat(4, 1fr); gap: 16px; }
    .quick-tile { min-height: 160px; padding: 22px; }

    .prog-scroll {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      overflow: visible;
      padding: 0;
      margin: 0;
    }
    .prog-card { flex: none; min-height: 300px; padding: 26px; }

    .cta-banner { padding: 56px 48px; }

    .footer-inner {
      grid-template-columns: 1.6fr 1fr 1fr 1fr;
      gap: 40px;
    }
    .footer-bottom { flex-direction: row; justify-content: space-between; text-align: left; }
    footer { padding: 64px 40px 40px; }

    .tabbar { display: none; }
    body { padding-bottom: 0; }
  }

  @media (min-width: 1024px) {
    .prog-card { flex: none; }
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

<!-- ============ HEADER ============ -->
<header class="app-header">
  <div class="header-inner">
    <a href="#home" class="brand">
      <div class="brand-mark"><i class="fa-solid fa-graduation-cap"></i></div>
      <div>
        IEPA
        <small>University of Cape Coast</small>
      </div>
    </a>

    <ul class="desktop-nav">
      <li><a href="#home" class="active">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#programmes">Programmes</a></li>
      <li><a href="#admissions">Admissions</a></li>
      <li><a href="#resources">Resources</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="header-actions">
      <button class="icon-btn" aria-label="Search">
        <i class="fa-solid fa-magnifying-glass"></i>
      </button>
      <button class="icon-btn" aria-label="Notifications">
        <i class="fa-regular fa-bell"></i>
        <span class="dot"></span>
      </button>
      <a href="#apply" class="btn-primary">
        Apply Now <i class="fa-solid fa-arrow-right"></i>
      </a>
    </div>
  </div>
</header>

<!-- ============ HERO ============ -->
<section class="hero" id="home">
  <div class="hero-inner">
    <div class="hero-chip">
      <span class="pulse"></span>
      Applications Open · 2026/2027
    </div>

    <h1>
      Advancing <span class="accent">educational leadership</span> through postgraduate study.
    </h1>

    <p>
      The Institute for Educational Planning and Administration at the University of Cape Coast — where scholars, planners and administrators shape the future of education in Africa.
    </p>

    <div class="hero-cta">
      <a href="#programmes" class="btn btn-blue">
        Explore Programmes <i class="fa-solid fa-arrow-right"></i>
      </a>
      <a href="#portal" class="btn btn-ghost">
        <i class="fa-solid fa-user-graduate"></i> Student Portal
      </a>
    </div>

    <div class="hero-stats">
      <div class="stat-card">
        <span class="num">15<span class="plus">+</span></span>
        <span class="lbl">Programmes</span>
      </div>
      <div class="stat-card">
        <span class="num">500<span class="plus">+</span></span>
        <span class="lbl">Students</span>
      </div>
      <div class="stat-card">
        <span class="num">40<span class="plus">+</span></span>
        <span class="lbl">Faculty</span>
      </div>
      <div class="stat-card">
        <span class="num">25<span class="plus">+</span></span>
        <span class="lbl">Years</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ QUICK ACCESS ============ -->
<section id="quick-access">
  <div class="container">
    <div class="section-head reveal">
      <span class="eyebrow">Quick Access</span>
      <h2>Find what you need</h2>
      <p>Direct links to the most used sections of the platform.</p>
    </div>

    <div class="quick-grid">
      <a href="#programmes" class="quick-tile reveal">
        <div class="icon icon-blue"><i class="fa-solid fa-book-open"></i></div>
        <h3>Programmes</h3>
        <p>Master's & PhD</p>
      </a>
      <a href="#admissions" class="quick-tile reveal">
        <div class="icon icon-green"><i class="fa-solid fa-user-plus"></i></div>
        <h3>Admissions</h3>
        <p>How to apply</p>
      </a>
      <a href="#calendar" class="quick-tile reveal">
        <div class="icon icon-orange"><i class="fa-regular fa-calendar-days"></i></div>
        <h3>Calendar</h3>
        <p>Key dates</p>
      </a>
      <a href="#portal" class="quick-tile reveal">
        <div class="icon icon-purple"><i class="fa-solid fa-user-graduate"></i></div>
        <h3>Portal</h3>
        <p>Student login</p>
      </a>
      <a href="#research" class="quick-tile reveal">
        <div class="icon icon-teal"><i class="fa-solid fa-flask"></i></div>
        <h3>Research</h3>
        <p>Guidelines & ethics</p>
      </a>
      <a href="#resources" class="quick-tile reveal">
        <div class="icon icon-amber"><i class="fa-solid fa-folder-open"></i></div>
        <h3>Resources</h3>
        <p>Forms & templates</p>
      </a>
      <a href="#forms" class="quick-tile reveal">
        <div class="icon icon-pink"><i class="fa-regular fa-file-lines"></i></div>
        <h3>Forms</h3>
        <p>Downloads</p>
      </a>
      <a href="#contact" class="quick-tile reveal">
        <div class="icon icon-indigo"><i class="fa-solid fa-address-book"></i></div>
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
      <a href="#" class="ann-card reveal">
        <div class="ann-date">
          <span class="d">15</span>
          <span class="m">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag">Registration</span>
          <h4>Course registration open for Semester 2</h4>
          <p>All continuing Master's and PhD students should complete registration by 31 January 2026.</p>
        </div>
      </a>

      <a href="#" class="ann-card reveal">
        <div class="ann-date">
          <span class="d">10</span>
          <span class="m">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag green">Research</span>
          <h4>Thesis proposal deadline extended</h4>
          <p>Final-year students now have until 15 February 2026 to submit proposals.</p>
        </div>
      </a>

      <a href="#" class="ann-card reveal">
        <div class="ann-date">
          <span class="d">05</span>
          <span class="m">Jan</span>
        </div>
        <div class="ann-body">
          <span class="ann-tag orange">Exams</span>
          <h4>Examination timetable released</h4>
          <p>Check the Student Centre for your personalised schedule.</p>
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

    <div class="prog-scroll">
      <article class="prog-card reveal">
        <span class="prog-level">Master's</span>
        <h3>MPhil in Educational Administration</h3>
        <p class="desc">Advanced study in educational leadership, policy analysis and institutional administration.</p>
        <div class="prog-facts">
          <span class="prog-fact"><i class="fa-regular fa-clock"></i> 2 years</span>
          <span class="prog-fact"><i class="fa-solid fa-laptop"></i> Full-time</span>
        </div>
        <a href="#" class="prog-cta">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>

      <article class="prog-card reveal">
        <span class="prog-level">Master's</span>
        <h3>MEd in Educational Planning</h3>
        <p class="desc">Preparation for planning and policy roles within national and institutional education systems.</p>
        <div class="prog-facts">
          <span class="prog-fact"><i class="fa-regular fa-clock"></i> 2 years</span>
          <span class="prog-fact"><i class="fa-solid fa-laptop"></i> Full / Part</span>
        </div>
        <a href="#" class="prog-cta">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>

      <article class="prog-card reveal">
        <span class="prog-level phd">Doctoral</span>
        <h3>PhD in Educational Administration</h3>
        <p class="desc">Research-intensive doctoral programme for senior education professionals and scholars.</p>
        <div class="prog-facts">
          <span class="prog-fact"><i class="fa-regular fa-clock"></i> 3–4 years</span>
          <span class="prog-fact"><i class="fa-solid fa-laptop"></i> Full-time</span>
        </div>
        <a href="#" class="prog-cta">Learn more <i class="fa-solid fa-arrow-right"></i></a>
      </article>
    </div>
  </div>
</section>

<!-- ============ CTA BANNER ============ -->
<section style="padding-top: 0;">
  <div class="container">
    <div class="cta-banner reveal">
      <h2>Ready to begin your postgraduate journey?</h2>
      <p>Applications for 2026/2027 are now open. Join a community of scholars shaping education across Africa.</p>
      <div class="btns">
        <a href="#apply" class="btn btn-white">
          <i class="fa-solid fa-pen-to-square"></i> Apply Now
        </a>
        <a href="#admissions" class="btn btn-glass">
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
        Institute for Educational Planning and Administration — University of Cape Coast, Ghana.
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

<!-- ============ BOTTOM TAB BAR (mobile only) ============ -->
<nav class="tabbar">
  <a href="#home" class="tab active">
    <i class="fa-solid fa-house"></i>
    Home
  </a>
  <a href="#programmes" class="tab">
    <i class="fa-solid fa-book-open"></i>
    Programmes
  </a>
  <a href="#portal" class="tab">
    <i class="fa-solid fa-user-graduate"></i>
    Portal
  </a>
  <a href="#announcements" class="tab">
    <i class="fa-regular fa-bell"></i>
    Alerts
  </a>
  <a href="#contact" class="tab">
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

  // Active state sync (nav + tabbar)
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.desktop-nav a, .tabbar .tab');
  const navIo = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.id;
        navLinks.forEach(l => l.classList.toggle('active', l.getAttribute('href') === '#' + id));
      }
    });
  }, { threshold: 0.35 });
  sections.forEach(s => navIo.observe(s));
</script>

</body>
</html>
