[index.html](https://github.com/user-attachments/files/32313068/index.html)
# iepa-website
IEPA digital pla<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IEPA — Institute for Educational Planning and Administration | UCC</title>
<meta name="description" content="Institute for Educational Planning and Administration, University of Cape Coast, Ghana — Postgraduate education, research and professional practice.">

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Playfair+Display:wght@600;700;800&display=swap" rel="stylesheet">

<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
  :root {
    --primary: #003366;
    --primary-dark: #001f3f;
    --primary-light: #005599;
    --accent: #C8A951;
    --accent-light: #e0c479;
    --bg: #f8f9fb;
    --surface: #ffffff;
    --text: #1a1a1a;
    --text-muted: #666;
    --border: #e5e8ed;
    --shadow-sm: 0 1px 3px rgba(0,0,0,0.06);
    --shadow-md: 0 4px 16px rgba(0,0,0,0.08);
    --shadow-lg: 0 12px 32px rgba(0,0,0,0.12);
    --radius: 12px;
    --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
    color: var(--text);
    background: var(--bg);
    line-height: 1.65;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }

  h1, h2, h3, h4 { font-family: 'Playfair Display', Georgia, serif; line-height: 1.2; }

  a { color: inherit; }
  img { max-width: 100%; display: block; }

  /* ============ HEADER / NAV ============ */
  header {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 1000;
    background: rgba(0, 51, 102, 0.85);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(255,255,255,0.08);
    transition: all var(--transition);
  }
  header.scrolled {
    background: rgba(0, 31, 63, 0.95);
    box-shadow: var(--shadow-md);
  }
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1280px;
    margin: 0 auto;
    padding: 1rem 1.5rem;
  }
  .logo {
    display: flex; align-items: center; gap: 0.6rem;
    font-family: 'Playfair Display', serif;
    font-weight: 700; font-size: 1.35rem;
    color: white; text-decoration: none;
    letter-spacing: 0.5px;
    z-index: 1100;
  }
  .logo i { color: var(--accent); font-size: 1.4rem; }
  .logo span { color: var(--accent); font-weight: 600; }

  /* Desktop nav */
  .nav-links {
    display: flex; list-style: none; gap: 0.4rem; align-items: center;
  }
  .nav-links a {
    color: rgba(255,255,255,0.9);
    text-decoration: none;
    font-weight: 500;
    font-size: 0.92rem;
    padding: 0.5rem 0.9rem;
    border-radius: 8px;
    position: relative;
    transition: all var(--transition);
  }
  .nav-links a:hover {
    color: var(--accent);
    background: rgba(255,255,255,0.06);
  }
  .nav-links a.active { color: var(--accent); }
  .nav-links a.active::after {
    content: '';
    position: absolute;
    bottom: 2px; left: 50%;
    transform: translateX(-50%);
    width: 20px; height: 2px;
    background: var(--accent);
    border-radius: 2px;
  }

  /* Portal buttons in nav */
  .nav-cta {
    display: flex; gap: 0.5rem; align-items: center;
  }
  .nav-cta .btn-portal {
    background: var(--accent);
    color: var(--primary-dark) !important;
    font-weight: 600;
    padding: 0.55rem 1.1rem;
    border-radius: 8px;
    font-size: 0.88rem;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    transition: all var(--transition);
  }
  .nav-cta .btn-portal:hover {
    background: var(--accent-light);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(200,169,81,0.35);
  }

  /* Hamburger */
  .hamburger {
    display: none;
    background: transparent;
    border: none;
    cursor: pointer;
    width: 44px; height: 44px;
    position: relative;
    z-index: 1100;
    border-radius: 8px;
    transition: background var(--transition);
  }
  .hamburger:hover { background: rgba(255,255,255,0.08); }
  .hamburger span {
    position: absolute;
    left: 50%; transform: translateX(-50%);
    width: 24px; height: 2px;
    background: white;
    border-radius: 2px;
    transition: all var(--transition);
  }
  .hamburger span:nth-child(1) { top: 14px; }
  .hamburger span:nth-child(2) { top: 21px; }
  .hamburger span:nth-child(3) { top: 28px; }
  .hamburger.open span:nth-child(1) { top: 21px; transform: translateX(-50%) rotate(45deg); background: var(--accent); }
  .hamburger.open span:nth-child(2) { opacity: 0; transform: translateX(-50%) scaleX(0); }
  .hamburger.open span:nth-child(3) { top: 21px; transform: translateX(-50%) rotate(-45deg); background: var(--accent); }

  /* Mobile side drawer */
  .drawer-overlay {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.5);
    opacity: 0;
    visibility: hidden;
    transition: all var(--transition);
    z-index: 1050;
    backdrop-filter: blur(4px);
  }
  .drawer-overlay.open { opacity: 1; visibility: visible; }

  .drawer {
    position: fixed;
    top: 0; right: 0;
    height: 100vh;
    width: min(85vw, 340px);
    background: linear-gradient(180deg, var(--primary-dark) 0%, var(--primary) 100%);
    z-index: 1080;
    transform: translateX(100%);
    transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    display: flex;
    flex-direction: column;
    padding: 5rem 1.5rem 2rem;
    overflow-y: auto;
    box-shadow: -8px 0 40px rgba(0,0,0,0.3);
  }
  .drawer.open { transform: translateX(0); }

  .drawer-header {
    position: absolute;
    top: 1.25rem; left: 1.5rem;
    color: white;
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    font-size: 1.15rem;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .drawer-header i { color: var(--accent); }

  .drawer nav ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }
  .drawer nav a {
    color: rgba(255,255,255,0.9);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 0.85rem;
    padding: 0.85rem 1rem;
    border-radius: 10px;
    font-weight: 500;
    font-size: 0.98rem;
    transition: all var(--transition);
    border-left: 3px solid transparent;
  }
  .drawer nav a i {
    width: 22px;
    color: var(--accent);
    font-size: 1rem;
    text-align: center;
  }
  .drawer nav a:hover,
  .drawer nav a.active {
    background: rgba(255,255,255,0.08);
    border-left-color: var(--accent);
    color: white;
    padding-left: 1.25rem;
  }

  .drawer-divider {
    height: 1px;
    background: rgba(255,255,255,0.12);
    margin: 1.25rem 0;
  }

  .drawer-cta {
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }
  .drawer-cta a {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.6rem;
    padding: 0.85rem 1rem;
    border-radius: 10px;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.95rem;
    transition: all var(--transition);
  }
  .drawer-cta a.primary {
    background: var(--accent);
    color: var(--primary-dark);
  }
  .drawer-cta a.primary:hover {
    background: var(--accent-light);
    transform: translateY(-2px);
  }
  .drawer-cta a.outline {
    border: 1.5px solid rgba(255,255,255,0.3);
    color: white;
  }
  .drawer-cta a.outline:hover {
    background: rgba(255,255,255,0.08);
    border-color: var(--accent);
    color: var(--accent);
  }

  .drawer-footer {
    margin-top: auto;
    padding-top: 2rem;
    color: rgba(255,255,255,0.5);
    font-size: 0.8rem;
    text-align: center;
  }

  /* ============ HERO ============ */
  .hero {
    min-height: 100vh;
    padding: 8rem 1.5rem 5rem;
    background: linear-gradient(135deg, #001f3f 0%, #003366 50%, #004a8f 100%);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(circle at 20% 30%, rgba(200,169,81,0.15) 0%, transparent 50%),
      radial-gradient(circle at 80% 70%, rgba(0,120,200,0.25) 0%, transparent 50%);
    animation: heroGlow 12s ease-in-out infinite alternate;
  }
  @keyframes heroGlow {
    0% { transform: scale(1) rotate(0deg); opacity: 1; }
    100% { transform: scale(1.15) rotate(3deg); opacity: 0.85; }
  }
  /* Floating shapes */
  .hero::after {
    content: '';
    position: absolute;
    width: 500px; height: 500px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(200,169,81,0.12), transparent 70%);
    top: -100px; right: -100px;
    animation: floatShape 15s ease-in-out infinite;
  }
  @keyframes floatShape {
    0%, 100% { transform: translate(0,0); }
    50% { transform: translate(-40px, 40px); }
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 900px;
    text-align: center;
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: rgba(200,169,81,0.15);
    border: 1px solid rgba(200,169,81,0.4);
    color: var(--accent-light);
    padding: 0.5rem 1.1rem;
    border-radius: 50px;
    font-size: 0.82rem;
    font-weight: 500;
    margin-bottom: 1.75rem;
    letter-spacing: 0.5px;
    animation: fadeUp 0.8s ease both;
  }
  .hero-badge i { font-size: 0.8rem; }

  .hero h1 {
    font-size: clamp(1.75rem, 5vw, 3.4rem);
    margin-bottom: 1.5rem;
    line-height: 1.15;
    animation: fadeUp 0.8s 0.15s ease both;
  }
  .hero h1 .highlight {
    color: var(--accent);
    position: relative;
    display: inline-block;
  }
  .hero h1 .highlight::after {
    content: '';
    position: absolute;
    bottom: 4px; left: 0; right: 0;
    height: 6px;
    background: rgba(200,169,81,0.25);
    border-radius: 3px;
    z-index: -1;
  }

  .hero p.lead {
    font-size: clamp(1rem, 2vw, 1.15rem);
    color: rgba(255,255,255,0.85);
    max-width: 640px;
    margin: 0 auto 2.5rem;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .hero .btn-group {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeUp 0.8s 0.45s ease both;
  }

  .btn {
    padding: 0.95rem 1.9rem;
    border-radius: 10px;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.95rem;
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    transition: all var(--transition);
    border: 2px solid transparent;
    cursor: pointer;
    font-family: inherit;
  }
  .btn i { font-size: 0.9rem; transition: transform var(--transition); }
  .btn:hover i { transform: translateX(3px); }

  .btn-primary {
    background: var(--accent);
    color: var(--primary-dark);
  }
  .btn-primary:hover {
    background: var(--accent-light);
    transform: translateY(-3px);
    box-shadow: 0 12px 28px rgba(200,169,81,0.4);
  }

  .btn-outline {
    background: rgba(255,255,255,0.08);
    color: white;
    border-color: rgba(255,255,255,0.35);
    backdrop-filter: blur(8px);
  }
  .btn-outline:hover {
    background: white;
    color: var(--primary);
    border-color: white;
    transform: translateY(-3px);
  }

  /* Scroll indicator */
  .scroll-indicator {
    position: absolute;
    bottom: 2rem; left: 50%;
    transform: translateX(-50%);
    color: rgba(255,255,255,0.6);
    font-size: 1.5rem;
    animation: bounce 2s infinite;
    cursor: pointer;
    z-index: 3;
  }
  @keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translate(-50%, 0); }
    40% { transform: translate(-50%, -10px); }
    60% { transform: translate(-50%, -5px); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ============ SECTIONS ============ */
  section {
    padding: 5rem 1.5rem;
    max-width: 1280px;
    margin: 0 auto;
  }
  .section-header { margin-bottom: 3rem; text-align: center; }
  .section-label {
    display: inline-block;
    color: var(--accent);
    font-size: 0.82rem;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
  }
  .section-header h2 {
    color: var(--primary);
    font-size: clamp(1.6rem, 3.5vw, 2.2rem);
    margin-bottom: 0.75rem;
  }
  .section-header p {
    color: var(--text-muted);
    max-width: 600px;
    margin: 0 auto;
    font-size: 1rem;
  }

  /* Scroll reveal */
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.7s ease, transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ============ GRID / CARDS ============ */
  .grid {
    display: grid;
    gap: 1.5rem;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  }
  .card {
    background: var(--surface);
    padding: 2rem 1.75rem;
    border-radius: var(--radius);
    box-shadow: var(--shadow-sm);
    transition: all var(--transition);
    border: 1px solid var(--border);
    text-decoration: none;
    color: inherit;
    display: block;
    position: relative;
    overflow: hidden;
  }
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 4px;
    background: linear-gradient(90deg, var(--accent), var(--primary-light));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .card:hover::before { transform: scaleX(1); }
  .card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
  }
  .card-icon {
    width: 54px; height: 54px;
    border-radius: 12px;
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
    color: var(--accent);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.35rem;
    margin-bottom: 1.25rem;
    transition: all var(--transition);
  }
  .card:hover .card-icon {
    transform: rotate(-6deg) scale(1.08);
    box-shadow: 0 10px 24px rgba(0,51,102,0.25);
  }
  .card h3 {
    color: var(--primary);
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
    font-family: 'Inter', sans-serif;
    font-weight: 700;
  }
  .card p {
    font-size: 0.92rem;
    color: var(--text-muted);
    line-height: 1.55;
  }
  .card-arrow {
    position: absolute;
    bottom: 1.5rem; right: 1.5rem;
    color: var(--accent);
    font-size: 0.9rem;
    opacity: 0;
    transform: translateX(-8px);
    transition: all var(--transition);
  }
  .card:hover .card-arrow {
    opacity: 1;
    transform: translateX(0);
  }

  /* ============ ANNOUNCEMENTS ============ */
  .announcement-list { display: flex; flex-direction: column; gap: 1rem; }
  .announcement {
    background: var(--surface);
    padding: 1.5rem 1.75rem;
    border-radius: var(--radius);
    border-left: 4px solid var(--accent);
    box-shadow: var(--shadow-sm);
    transition: all var(--transition);
    position: relative;
    overflow: hidden;
  }
  .announcement:hover {
    transform: translateX(6px);
    box-shadow: var(--shadow-md);
  }
  .announcement .meta {
    font-size: 0.82rem;
    color: var(--text-muted);
    margin-bottom: 0.5rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    flex-wrap: wrap;
  }
  .announcement .meta i { color: var(--accent); }
  .tag {
    background: rgba(0,51,102,0.08);
    color: var(--primary);
    padding: 0.15rem 0.65rem;
    border-radius: 20px;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .announcement strong {
    display: block;
    color: var(--primary);
    font-size: 1.05rem;
    margin-bottom: 0.4rem;
    font-weight: 700;
  }
  .announcement p {
    color: var(--text-muted);
    font-size: 0.94rem;
  }
  .read-more {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    color: var(--primary);
    font-weight: 600;
    font-size: 0.86rem;
    text-decoration: none;
    margin-top: 0.75rem;
    transition: gap var(--transition);
  }
  .read-more:hover { gap: 0.7rem; color: var(--accent); }

  /* ============ PROGRAMME CARDS ============ */
  .programme-card {
    background: var(--surface);
    border-radius: var(--radius);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
    transition: all var(--transition);
    border: 1px solid var(--border);
    display: flex;
    flex-direction: column;
  }
  .programme-card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-lg);
  }
  .programme-banner {
    height: 8px;
    background: linear-gradient(90deg, var(--accent), var(--primary-light));
  }
  .programme-body { padding: 1.75rem; flex: 1; display: flex; flex-direction: column; }
  .programme-badge {
    display: inline-block;
    background: rgba(200,169,81,0.15);
    color: #8a6d1f;
    padding: 0.25rem 0.75rem;
    border-radius: 20px;
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-bottom: 0.85rem;
    align-self: flex-start;
  }
  .programme-card h3 {
    color: var(--primary);
    font-size: 1.15rem;
    margin-bottom: 0.75rem;
    font-family: 'Inter', sans-serif;
    font-weight: 700;
    line-height: 1.35;
  }
  .programme-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin: 1rem 0;
    padding: 1rem 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    font-size: 0.85rem;
    color: var(--text-muted);
  }
  .programme-meta span { display: flex; align-items: center; gap: 0.4rem; }
  .programme-meta i { color: var(--accent); }
  .programme-card .btn-apply {
    margin-top: auto;
    align-self: flex-start;
    padding: 0.65rem 1.25rem;
    background: var(--primary);
    color: white;
    border-radius: 8px;
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 600;
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    transition: all var(--transition);
  }
  .programme-card .btn-apply:hover {
    background: var(--accent);
    color: var(--primary-dark);
    transform: translateY(-2px);
  }

  /* ============ FOOTER ============ */
  footer {
    background: linear-gradient(180deg, #001a33 0%, #00111f 100%);
    color: #b8c4d1;
    padding: 4rem 1.5rem 1.5rem;
    margin-top: 4rem;
  }
  .footer-inner {
    max-width: 1280px;
    margin: 0 auto;
    display: grid;
    gap: 2.5rem;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  footer h4 {
    color: var(--accent);
    margin-bottom: 1.25rem;
    font-family: 'Inter', sans-serif;
    font-size: 0.95rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-transform: uppercase;
  }
  footer p { font-size: 0.9rem; line-height: 1.7; }
  footer a {
    color: #b8c4d1;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 0.7rem;
    font-size: 0.9rem;
    transition: all var(--transition);
  }
  footer a i { font-size: 0.75rem; color: var(--accent); }
  footer a:hover { color: var(--accent); transform: translateX(4px); }

  .social-links { display: flex; gap: 0.6rem; margin-top: 1rem; }
  .social-links a {
    width: 38px; height: 38px;
    border-radius: 50%;
    background: rgba(255,255,255,0.06);
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0;
    transition: all var(--transition);
  }
  .social-links a i { font-size: 0.9rem; color: #b8c4d1; }
  .social-links a:hover {
    background: var(--accent);
    transform: translateY(-3px) !important;
  }
  .social-links a:hover i { color: var(--primary-dark); }

  .copyright {
    text-align: center;
    margin-top: 3rem;
    padding-top: 1.75rem;
    border-top: 1px solid rgba(255,255,255,0.08);
    font-size: 0.85rem;
    color: #7a8a9a;
  }

  /* ============ BACK TO TOP ============ */
  .back-to-top {
    position: fixed;
    bottom: 2rem; right: 2rem;
    width: 48px; height: 48px;
    border-radius: 50%;
    background: var(--primary);
    color: white;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    opacity: 0;
    visibility: hidden;
    transform: translateY(20px);
    transition: all var(--transition);
    z-index: 900;
    box-shadow: var(--shadow-lg);
  }
  .back-to-top.visible {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
  }
  .back-to-top:hover {
    background: var(--accent);
    color: var(--primary-dark);
    transform: translateY(-4px);
  }

  /* ============ RESPONSIVE ============ */
  @media (max-width: 900px) {
    .nav-links { display: none; }
    .nav-cta { display: none; }
    .hamburger { display: block; }
    section { padding: 4rem 1.25rem; }
    .hero { padding: 7rem 1.25rem 4rem; min-height: auto; }
  }

  @media (max-width: 600px) {
    .drawer { width: 100vw; max-width: 340px; }
    .hero .btn { padding: 0.85rem 1.5rem; font-size: 0.9rem; }
    .card { padding: 1.5rem 1.25rem; }
    .announcement { padding: 1.25rem; }
    .back-to-top { bottom: 1.25rem; right: 1.25rem; width: 44px; height: 44px; }
  }

  /* Reduced motion */
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
<header id="header">
  <nav>
    <a href="#home" class="logo">
      <i class="fa-solid fa-graduation-cap"></i>
      IEPA <span>| UCC</span>
    </a>

    <ul class="nav-links">
      <li><a href="#home" class="active">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#programmes">Programmes</a></li>
      <li><a href="#admissions">Admissions</a></li>
      <li><a href="#resources">Resources</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="nav-cta">
      <a href="#portal" class="btn-portal">
        <i class="fa-solid fa-user-graduate"></i> Portal
      </a>
    </div>

    <button class="hamburger" id="hamburger" aria-label="Toggle menu" aria-expanded="false">
      <span></span>
      <span></span>
      <span></span>
    </button>
  </nav>
</header>

<!-- ============ MOBILE DRAWER ============ -->
<div class="drawer-overlay" id="drawerOverlay"></div>

<aside class="drawer" id="drawer" aria-hidden="true">
  <div class="drawer-header">
    <i class="fa-solid fa-graduation-cap"></i> IEPA
  </div>

  <nav>
    <ul>
      <li><a href="#home" class="active"><i class="fa-solid fa-house"></i> Home</a></li>
      <li><a href="#about"><i class="fa-solid fa-circle-info"></i> About IEPA</a></li>
      <li><a href="#programmes"><i class="fa-solid fa-book-open"></i> Programmes</a></li>
      <li><a href="#admissions"><i class="fa-solid fa-user-plus"></i> Admissions</a></li>
      <li><a href="#students"><i class="fa-solid fa-users"></i> Students</a></li>
      <li><a href="#lecturers"><i class="fa-solid fa-chalkboard-user"></i> Lecturers</a></li>
      <li><a href="#research"><i class="fa-solid fa-flask"></i> Research</a></li>
      <li><a href="#resources"><i class="fa-solid fa-folder-open"></i> Resources</a></li>
      <li><a href="#news"><i class="fa-solid fa-newspaper"></i> News &amp; Events</a></li>
      <li><a href="#support"><i class="fa-solid fa-headset"></i> Student Support</a></li>
      <li><a href="#contact"><i class="fa-solid fa-envelope"></i> Contact</a></li>
    </ul>
  </nav>

  <div class="drawer-divider"></div>

  <div class="drawer-cta">
    <a href="#apply" class="primary">
      <i class="fa-solid fa-pen-to-square"></i> Apply Now
    </a>
    <a href="#portal" class="outline">
      <i class="fa-solid fa-user-graduate"></i> Student Portal
    </a>
    <a href="#lecturer-portal" class="outline">
      <i class="fa-solid fa-chalkboard-user"></i> Lecturer Portal
    </a>
    <a href="#admin" class="outline">
      <i class="fa-solid fa-user-shield"></i> Admin Login
    </a>
  </div>

  <div class="drawer-footer">
    <i class="fa-solid fa-location-dot"></i> University of Cape Coast, Ghana
  </div>
</aside>

<!-- ============ HERO ============ -->
<section class="hero" id="home">
  <div class="hero-content">
    <div class="hero-badge">
      <i class="fa-solid fa-award"></i> Postgraduate Institute · University of Cape Coast
    </div>

    <h1>
      Advancing <span class="highlight">Educational Planning</span> and Administration Through Postgraduate Education, Research and Professional Practice
    </h1>

    <p class="lead">
      A centralised digital platform for IEPA students, lecturers, administrators and prospective applicants — bringing information, resources and services together in one place.
    </p>

    <div class="btn-group">
      <a href="#programmes" class="btn btn-primary">
        <i class="fa-solid fa-book-open"></i> Explore Programmes
      </a>
      <a href="#admissions" class="btn btn-outline">
        <i class="fa-solid fa-pen-to-square"></i> Apply Now
      </a>
      <a href="#portal" class="btn btn-outline">
        <i class="fa-solid fa-user-graduate"></i> Student Portal
      </a>
    </div>
  </div>

  <a href="#quick-access" class="scroll-indicator" aria-label="Scroll down">
    <i class="fa-solid fa-chevron-down"></i>
  </a>
</section>

<!-- ============ QUICK ACCESS ============ -->
<section id="quick-access">
  <div class="section-header reveal">
    <span class="section-label">Explore</span>
    <h2>Quick Access</h2>
    <p>Everything you need, one click away</p>
  </div>

  <div class="grid">
    <a href="#programmes" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-book-open"></i></div>
      <h3>Programmes</h3>
      <p>Master's and PhD programmes offered at IEPA.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#admissions" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-user-plus"></i></div>
      <h3>Admissions</h3>
      <p>Requirements, deadlines and application process.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#calendar" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-calendar-days"></i></div>
      <h3>Academic Calendar</h3>
      <p>Key dates for the current academic year.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#portal" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-user-graduate"></i></div>
      <h3>Student Portal</h3>
      <p>Access your dashboard, courses and resources.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#research" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-flask"></i></div>
      <h3>Research</h3>
      <p>Guidelines, ethics, templates and supervision.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#resources" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-folder-open"></i></div>
      <h3>Resources</h3>
      <p>Forms, handbooks, policies and templates.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#forms" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-file-lines"></i></div>
      <h3>Forms</h3>
      <p>Academic, research and administrative forms.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
    <a href="#contact" class="card reveal">
      <div class="card-icon"><i class="fa-solid fa-address-book"></i></div>
      <h3>Contact IEPA</h3>
      <p>Directory of offices, staff and services.</p>
      <i class="fa-solid fa-arrow-right card-arrow"></i>
    </a>
  </div>
</section>

<!-- ============ ANNOUNCEMENTS ============ -->
<section id="announcements">
  <div class="section-header reveal">
    <span class="section-label">Stay Informed</span>
    <h2>Latest Announcements</h2>
    <p>Important updates from the Institute</p>
  </div>

  <div class="announcement-list">
    <div class="announcement reveal">
      <div class="meta">
        <span><i class="fa-regular fa-calendar"></i> 15 January 2026</span>
        <span class="tag">Registration</span>
      </div>
      <strong>Course Registration Now Open for Semester 2</strong>
      <p>All continuing Master's and PhD students should complete registration by 31 January 2026.</p>
      <a href="#" class="read-more">Read more <i class="fa-solid fa-arrow-right"></i></a>
    </div>

    <div class="announcement reveal">
      <div class="meta">
        <span><i class="fa-regular fa-calendar"></i> 10 January 2026</span>
        <span class="tag">Research</span>
      </div>
      <strong>Thesis Proposal Submission Deadline Extended</strong>
      <p>Final-year students now have until 15 February 2026 to submit proposals to their supervisors.</p>
      <a href="#" class="read-more">Read more <i class="fa-solid fa-arrow-right"></i></a>
    </div>

    <div class="announcement reveal">
      <div class="meta">
        <span><i class="fa-regular fa-calendar"></i> 5 January 2026</span>
        <span class="tag">Examinations</span>
      </div>
      <strong>End of Semester Examination Timetable Released</strong>
      <p>Check the Student Centre for your personalised examination schedule.</p>
      <a href="#" class="read-more">Read more <i class="fa-solid fa-arrow-right"></i></a>
    </div>
  </div>
</section>

<!-- ============ PROGRAMMES ============ -->
<section id="programmes">
  <div class="section-header reveal">
    <span class="section-label">Study With Us</span>
    <h2>Featured Programmes</h2>
    <p>Postgraduate degrees in educational planning and administration</p>
  </div>

  <div class="grid">
    <article class="programme-card reveal">
      <div class="programme-banner"></div>
      <div class="programme-body">
        <span class="programme-badge">Master's</span>
        <h3>MPhil in Educational Administration</h3>
        <p style="color: var(--text-muted); font-size: 0.92rem;">Advanced study in educational leadership, policy analysis and institutional administration.</p>
        <div class="programme-meta">
          <span><i class="fa-regular fa-clock"></i> 2 years</span>
          <span><i class="fa-solid fa-laptop"></i> Full-time</span>
        </div>
        <a href="#" class="btn-apply">
          Learn more <i class="fa-solid fa-arrow-right"></i>
        </a>
      </div>
    </article>

    <article class="programme-card reveal">
      <div class="programme-banner"></div>
      <div class="programme-body">
        <span class="programme-badge">Master's</span>
        <h3>MEd in Educational Planning</h3>
        <p style="color: var(--text-muted); font-size: 0.92rem;">Preparation for planning and policy roles within national and institutional education systems.</p>
        <div class="programme-meta">
          <span><i class="fa-regular fa-clock"></i> 2 years</span>
          <span><i class="fa-solid fa-laptop"></i> Full / Part-time</span>
        </div>
        <a href="#" class="btn-apply">
          Learn more <i class="fa-solid fa-arrow-right"></i>
        </a>
      </div>
    </article>

    <article class="programme-card reveal">
      <div class="programme-banner"></div>
      <div class="programme-body">
        <span class="programme-badge">Doctoral</span>
        <h3>PhD in Educational Administration</h3>
        <p style="color: var(--text-muted); font-size: 0.92rem;">Research-intensive doctoral programme for senior education professionals and scholars.</p>
        <div class="programme-meta">
          <span><i class="fa-regular fa-clock"></i> 3–4 years</span>
          <span><i class="fa-solid fa-laptop"></i> Full-time</span>
        </div>
        <a href="#" class="btn-apply">
          Learn more <i class="fa-solid fa-arrow-right"></i>
        </a>
      </div>
    </article>
  </div>
</section>

<!-- ============ FOOTER ============ -->
<footer id="contact">
  <div class="footer-inner">
    <div>
      <h4><i class="fa-solid fa-graduation-cap"></i> IEPA</h4>
      <p>Institute for Educational Planning and Administration<br>University of Cape Coast, Ghana</p>
      <div class="social-links">
        <a href="#" aria-label="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
        <a href="#" aria-label="Twitter / X"><i class="fa-brands fa-x-twitter"></i></a>
        <a href="#" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
        <a href="#" aria-label="YouTube"><i class="fa-brands fa-youtube"></i></a>
      </div>
    </div>

    <div>
      <h4>Quick Links</h4>
      <a href="#programmes"><i class="fa-solid fa-chevron-right"></i> Programmes</a>
      <a href="#admissions"><i class="fa-solid fa-chevron-right"></i> Admissions</a>
      <a href="#resources"><i class="fa-solid fa-chevron-right"></i> Resources</a>
      <a href="#portal"><i class="fa-solid fa-chevron-right"></i> Student Portal</a>
    </div>

    <div>
      <h4>Contact</h4>
      <a href="mailto:iepa@ucc.edu.gh"><i class="fa-solid fa-envelope"></i> iepa@ucc.edu.gh</a>
      <a href="tel:+233332132400"><i class="fa-solid fa-phone"></i> +233 33 213 2400</a>
      <a href="https://ucc.edu.gh" target="_blank" rel="noopener"><i class="fa-solid fa-globe"></i> University of Cape Coast</a>
    </div>

    <div>
      <h4>Legal</h4>
      <a href="#privacy"><i class="fa-solid fa-shield-halved"></i> Privacy Policy</a>
      <a href="#terms"><i class="fa-solid fa-file-contract"></i> Terms of Use</a>
    </div>
  </div>

  <div class="copyright">
    © 2026 Institute for Educational Planning and Administration, University of Cape Coast. All rights reserved.
  </div>
</footer>

<!-- ============ BACK TO TOP ============ -->
<button class="back-to-top" id="backToTop" aria-label="Back to top">
  <i class="fa-solid fa-arrow-up"></i>
</button>

<script>
  // ===== Mobile drawer =====
  const hamburger = document.getElementById('hamburger');
  const drawer = document.getElementById('drawer');
  const overlay = document.getElementById('drawerOverlay');
  const drawerLinks = drawer.querySelectorAll('a');

  function openDrawer() {
    drawer.classList.add('open');
    overlay.classList.add('open');
    hamburger.classList.add('open');
    hamburger.setAttribute('aria-expanded', 'true');
    drawer.setAttribute('aria-hidden', 'false');
    document.body.style.overflow = 'hidden';
  }

  function closeDrawer() {
    drawer.classList.remove('open');
    overlay.classList.remove('open');
    hamburger.classList.remove('open');
    hamburger.setAttribute('aria-expanded', 'false');
    drawer.setAttribute('aria-hidden', 'true');
    document.body.style.overflow = '';
  }

  hamburger.addEventListener('click', () => {
    drawer.classList.contains('open') ? closeDrawer() : openDrawer();
  });
  overlay.addEventListener('click', closeDrawer);
  drawerLinks.forEach(link => link.addEventListener('click', closeDrawer));

  // Close drawer on Escape
  document.addEventListener('keydown', e => {
    if (e.key === 'Escape') closeDrawer();
  });

  // ===== Header shrink on scroll =====
  const header = document.getElementById('header');
  const backToTop = document.getElementById('backToTop');

  window.addEventListener('scroll', () => {
    const y = window.scrollY;
    header.classList.toggle('scrolled', y > 40);
    backToTop.classList.toggle('visible', y > 500);
  });

  // ===== Scroll reveal =====
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        // stagger
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12, rootMargin: '0px 0px -50px 0px' });

  revealEls.forEach(el => io.observe(el));

  // ===== Active nav link on scroll =====
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a, .drawer nav a');

  const navObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.id;
        navLinks.forEach(link => {
          link.classList.toggle('active', link.getAttribute('href') === `#${id}`);
        });
      }
    });
  }, { threshold: 0.4 });

  sections.forEach(section => navObserver.observe(section));

  // ===== Back to top =====
  backToTop.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });
</script>

</body>
</html>tform
