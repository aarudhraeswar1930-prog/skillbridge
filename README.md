<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SkillBridge — Online Placement & Training Courses</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg:       #FAFAF7;
  --white:    #FFFFFF;
  --ink:      #1A1A18;
  --mid:      #6B6B60;
  --border:   #E4E4DC;
  --amber:    #D97706;
  --amber-lt: #FEF3C7;
  --teal:     #0D9488;
  --teal-lt:  #CCFBF1;
  --rose:     #E11D48;
}

html { scroll-behavior: smooth; }
body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--ink);
  overflow-x: hidden;
}

/* ── NAV ── */
nav {
  position: sticky; top: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 6%; height: 68px;
  background: var(--white);
  border-bottom: 1px solid var(--border);
}
.logo {
  font-family: 'DM Serif Display', serif;
  font-size: 1.55rem; color: var(--ink);
  text-decoration: none; letter-spacing: -.3px;
}
.logo span { color: var(--teal); }
.nav-links { display: flex; gap: 2rem; list-style: none; }
.nav-links a { font-size: .9rem; font-weight: 500; color: var(--mid); text-decoration: none; transition: color .2s; }
.nav-links a:hover { color: var(--ink); }
.nav-right { display: flex; gap: .75rem; align-items: center; }
.btn-outline {
  border: 1.5px solid var(--border); background: transparent;
  color: var(--ink); border-radius: 8px;
  padding: .5rem 1.1rem; font-size: .88rem; font-weight: 600;
  cursor: pointer; text-decoration: none; transition: border-color .2s;
}
.btn-outline:hover { border-color: var(--ink); }
.btn-teal {
  background: var(--teal); color: var(--white);
  border: none; border-radius: 8px;
  padding: .55rem 1.3rem; font-size: .88rem; font-weight: 600;
  cursor: pointer; text-decoration: none;
  transition: background .2s, transform .15s;
}
.btn-teal:hover { background: #0f766e; transform: translateY(-1px); }

/* ── HERO ── */
.hero {
  padding: 80px 6% 70px;
  display: grid; grid-template-columns: 1.1fr 1fr;
  gap: 5rem; align-items: center;
  max-width: 1280px; margin: 0 auto;
}
.hero-tag {
  display: inline-flex; align-items: center; gap: .5rem;
  background: var(--teal-lt); color: var(--teal);
  font-size: .75rem; font-weight: 700; letter-spacing: .08em; text-transform: uppercase;
  padding: .3rem .9rem; border-radius: 100px; margin-bottom: 1.4rem;
}
.hero h1 {
  font-family: 'DM Serif Display', serif;
  font-size: clamp(2.4rem, 4.5vw, 3.8rem);
  line-height: 1.1; letter-spacing: -.5px;
  color: var(--ink); margin-bottom: 1.4rem;
}
.hero h1 em { font-style: italic; color: var(--teal); }
.hero p { font-size: 1.05rem; line-height: 1.8; color: var(--mid); margin-bottom: 2rem; max-width: 480px; }
.hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }
.btn-hero {
  background: var(--ink); color: var(--white);
  border: none; border-radius: 10px;
  padding: .9rem 2rem; font-size: 1rem; font-weight: 600;
  cursor: pointer; text-decoration: none;
  transition: background .2s, transform .15s;
}
.btn-hero:hover { background: #333; transform: translateY(-2px); }
.btn-hero-ghost {
  background: transparent; color: var(--ink);
  border: 1.5px solid var(--border); border-radius: 10px;
  padding: .9rem 2rem; font-size: 1rem; font-weight: 500;
  cursor: pointer; text-decoration: none;
  transition: border-color .2s;
}
.btn-hero-ghost:hover { border-color: var(--ink); }

.hero-trust { display: flex; gap: 2rem; margin-top: 2.5rem; padding-top: 2rem; border-top: 1px solid var(--border); }
.trust-item { display: flex; flex-direction: column; }
.trust-val { font-family: 'DM Serif Display', serif; font-size: 1.8rem; color: var(--ink); line-height: 1; }
.trust-lbl { font-size: .78rem; color: var(--mid); margin-top: .25rem; }

/* Hero visual — course card preview */
.hero-visual { position: relative; }
.preview-card {
  background: var(--white); border: 1px solid var(--border);
  border-radius: 20px; overflow: hidden;
  box-shadow: 0 20px 60px #1A1A1815;
}
.preview-thumb {
  height: 160px; background: linear-gradient(135deg, #134e4a, #0d9488);
  display: flex; align-items: center; justify-content: center;
  font-size: 3.5rem;
}
.preview-body { padding: 1.5rem; }
.preview-cat { font-size: .72rem; font-weight: 700; text-transform: uppercase; letter-spacing: .08em; color: var(--teal); margin-bottom: .4rem; }
.preview-title { font-family: 'DM Serif Display', serif; font-size: 1.2rem; color: var(--ink); margin-bottom: 1rem; line-height: 1.3; }
.preview-instructor { display: flex; align-items: center; gap: .6rem; margin-bottom: 1rem; }
.avatar { width: 32px; height: 32px; border-radius: 50%; background: var(--teal); color: #fff; display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: .8rem; }
.preview-instructor span { font-size: .83rem; color: var(--mid); }
.preview-instructor strong { color: var(--ink); }
.rating-row { display: flex; align-items: center; gap: .5rem; margin-bottom: 1rem; }
.stars-filled { color: var(--amber); font-size: .9rem; }
.rating-num { font-weight: 700; font-size: .88rem; }
.rating-count { font-size: .78rem; color: var(--mid); }
.price-row { display: flex; align-items: center; gap: .8rem; }
.price-now { font-family: 'DM Serif Display', serif; font-size: 1.6rem; color: var(--ink); }
.price-was { font-size: .9rem; color: var(--mid); text-decoration: line-through; }
.price-badge { background: var(--amber-lt); color: var(--amber); font-size: .72rem; font-weight: 700; padding: .2rem .6rem; border-radius: 6px; }
.enroll-full {
  display: block; width: 100%; margin-top: 1.1rem;
  background: var(--teal); color: #fff;
  border: none; border-radius: 10px; padding: .8rem;
  font-size: .95rem; font-weight: 600; cursor: pointer;
  transition: background .2s;
}
.enroll-full:hover { background: #0f766e; }

.floating-pill {
  position: absolute; background: var(--white);
  border: 1px solid var(--border); border-radius: 12px;
  padding: .6rem 1rem; display: flex; align-items: center; gap: .6rem;
  box-shadow: 0 8px 24px #0001; font-size: .82rem; font-weight: 600;
  animation: float 3s ease-in-out infinite;
}
.floating-pill.top { top: -18px; right: 24px; animation-delay: 0s; }
.floating-pill.bot { bottom: -18px; left: 16px; animation-delay: 1.2s; }
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-7px)} }

/* ── TRUST BAR ── */
.trust-bar {
  background: var(--ink); padding: 22px 6%;
  display: flex; align-items: center; justify-content: center;
  gap: 3rem; flex-wrap: wrap;
}
.trust-bar-item { font-size: .82rem; color: #9CA3AF; font-weight: 500; display: flex; align-items: center; gap: .5rem; }
.trust-bar-item strong { color: var(--white); }

/* ── SHARED SECTION ── */
.sec { padding: 88px 6%; }
.sec-inner { max-width: 1200px; margin: 0 auto; }
.sec-label { font-size: .72rem; font-weight: 700; letter-spacing: .12em; text-transform: uppercase; color: var(--teal); margin-bottom: .7rem; }
.sec-title { font-family: 'DM Serif Display', serif; font-size: clamp(1.8rem, 3vw, 2.6rem); line-height: 1.15; margin-bottom: .8rem; }
.sec-sub { color: var(--mid); line-height: 1.8; max-width: 520px; }
.sec-header { margin-bottom: 3rem; }

/* ── WHAT YOU GET ── */
.gets-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(230px, 1fr)); gap: 1.5rem; }
.get-card {
  background: var(--white); border: 1px solid var(--border);
  border-radius: 16px; padding: 1.8rem;
  transition: box-shadow .3s, transform .3s;
}
.get-card:hover { box-shadow: 0 10px 36px #1A1A1810; transform: translateY(-3px); }
.get-icon { font-size: 2rem; margin-bottom: 1rem; }
.get-card h3 { font-family: 'DM Serif Display', serif; font-size: 1.1rem; margin-bottom: .5rem; }
.get-card p { font-size: .87rem; color: var(--mid); line-height: 1.7; }

/* ── COURSES ── */
.courses-bg { background: var(--white); }
.filter-row { display: flex; gap: .6rem; flex-wrap: wrap; margin-bottom: 2.5rem; }
.filter-btn {
  padding: .45rem 1.1rem; border-radius: 100px;
  border: 1.5px solid var(--border); background: transparent;
  font-size: .83rem; font-weight: 500; color: var(--mid);
  cursor: pointer; transition: all .2s;
}
.filter-btn.active, .filter-btn:hover { background: var(--ink); color: var(--white); border-color: var(--ink); }
.courses-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(290px, 1fr)); gap: 1.5rem; }
.course-card {
  background: var(--bg); border: 1px solid var(--border);
  border-radius: 16px; overflow: hidden;
  transition: box-shadow .3s, transform .3s; cursor: pointer;
}
.course-card:hover { box-shadow: 0 12px 40px #1A1A1814; transform: translateY(-4px); }
.c-thumb { height: 148px; display: flex; align-items: center; justify-content: center; font-size: 3rem; }
.c-body { padding: 1.3rem; }
.c-cat { font-size: .7rem; font-weight: 700; text-transform: uppercase; letter-spacing: .08em; color: var(--teal); margin-bottom: .35rem; }
.c-title { font-family: 'DM Serif Display', serif; font-size: 1.05rem; line-height: 1.3; margin-bottom: .5rem; color: var(--ink); }
.c-instructor { font-size: .78rem; color: var(--mid); margin-bottom: .7rem; }
.c-rating { display: flex; align-items: center; gap: .4rem; font-size: .78rem; margin-bottom: 1rem; }
.c-rating .s { color: var(--amber); }
.c-footer { display: flex; justify-content: space-between; align-items: center; padding-top: .9rem; border-top: 1px solid var(--border); }
.c-price { font-family: 'DM Serif Display', serif; font-size: 1.2rem; color: var(--ink); }
.c-price .was { font-family: 'DM Sans', sans-serif; font-size: .78rem; color: var(--mid); text-decoration: line-through; margin-left: .4rem; font-weight: 400; }
.c-enroll {
  background: var(--ink); color: var(--white);
  border: none; border-radius: 8px;
  padding: .4rem 1rem; font-size: .82rem; font-weight: 600;
  cursor: pointer; transition: background .2s;
}
.c-enroll:hover { background: #333; }

/* ── CURRICULUM ── */
.curriculum-bg { background: var(--bg); }
.curriculum-wrap { display: grid; grid-template-columns: 1fr 1.1fr; gap: 5rem; align-items: start; }
.module-list { display: flex; flex-direction: column; gap: .75rem; }
.module {
  background: var(--white); border: 1px solid var(--border);
  border-radius: 12px; padding: 1.1rem 1.3rem;
  display: flex; align-items: flex-start; gap: 1rem;
  cursor: pointer; transition: border-color .2s, box-shadow .2s;
}
.module:hover, .module.active { border-color: var(--teal); box-shadow: 0 4px 16px #0d948812; }
.module-num {
  width: 32px; height: 32px; min-width: 32px;
  border-radius: 8px; background: var(--teal-lt);
  color: var(--teal); font-weight: 700; font-size: .82rem;
  display: flex; align-items: center; justify-content: center;
}
.module-info h4 { font-weight: 600; font-size: .93rem; margin-bottom: .2rem; }
.module-info p { font-size: .78rem; color: var(--mid); }
.module-duration { margin-left: auto; font-size: .75rem; color: var(--mid); white-space: nowrap; }

.curriculum-cta { margin-top: 2rem; }
.curriculum-cta p { font-size: .87rem; color: var(--mid); margin-top: 1rem; }

/* ── INSTRUCTORS ── */
.instructors-bg { background: var(--white); }
.instructor-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 1.5rem; }
.instructor-card {
  border: 1px solid var(--border); border-radius: 16px; padding: 1.8rem; text-align: center;
  transition: box-shadow .3s, transform .3s;
}
.instructor-card:hover { box-shadow: 0 10px 36px #1A1A1810; transform: translateY(-3px); }
.i-avatar {
  width: 72px; height: 72px; border-radius: 50%; margin: 0 auto 1rem;
  display: flex; align-items: center; justify-content: center;
  font-family: 'DM Serif Display', serif; font-size: 1.6rem; color: #fff;
}
.i-name { font-family: 'DM Serif Display', serif; font-size: 1.1rem; margin-bottom: .25rem; }
.i-role { font-size: .8rem; color: var(--mid); margin-bottom: .8rem; }
.i-stats { display: flex; justify-content: center; gap: 1.5rem; font-size: .78rem; color: var(--mid); }
.i-stats strong { display: block; font-size: 1rem; color: var(--ink); font-weight: 700; }

/* ── PRICING ── */
.pricing-bg { background: var(--ink); }
.pricing-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; max-width: 960px; margin: 0 auto; }
.pricing-bg .sec-title { color: var(--white); }
.pricing-bg .sec-sub { color: #9CA3AF; }
.pricing-bg .sec-label { color: var(--amber); }
.plan {
  background: #252520; border: 1px solid #3A3A35;
  border-radius: 20px; padding: 2rem;
  transition: border-color .3s, transform .3s;
}
.plan:hover { border-color: var(--teal); transform: translateY(-4px); }
.plan.featured { background: var(--teal); border-color: var(--teal); }
.plan-tag {
  display: inline-block; font-size: .7rem; font-weight: 700;
  text-transform: uppercase; letter-spacing: .1em;
  background: #ffffff20; color: var(--white);
  padding: .2rem .7rem; border-radius: 100px; margin-bottom: 1.2rem;
}
.plan.featured .plan-tag { background: #ffffff30; }
.plan-name { font-family: 'DM Serif Display', serif; font-size: 1.4rem; color: var(--white); margin-bottom: .5rem; }
.plan-price { font-family: 'DM Serif Display', serif; font-size: 2.8rem; color: var(--white); line-height: 1; margin-bottom: .3rem; }
.plan-price sub { font-family: 'DM Sans', sans-serif; font-size: 1rem; font-weight: 400; }
.plan-desc { font-size: .83rem; color: rgba(255,255,255,.6); margin-bottom: 1.8rem; }
.plan-features { list-style: none; display: flex; flex-direction: column; gap: .75rem; margin-bottom: 2rem; }
.plan-features li { font-size: .87rem; color: rgba(255,255,255,.85); display: flex; align-items: center; gap: .6rem; }
.plan-features li::before { content: '✓'; color: var(--teal); font-weight: 700; min-width: 16px; }
.plan.featured .plan-features li::before { color: #fff; }
.plan-btn {
  display: block; width: 100%; text-align: center;
  background: var(--white); color: var(--ink);
  border: none; border-radius: 10px; padding: .8rem;
  font-size: .95rem; font-weight: 700; cursor: pointer;
  text-decoration: none; transition: background .2s, transform .15s;
}
.plan-btn:hover { background: #f0f0f0; transform: translateY(-1px); }
.plan.featured .plan-btn { background: var(--ink); color: var(--white); }
.plan.featured .plan-btn:hover { background: #333; }

/* ── TESTIMONIALS ── */
.test-bg { background: var(--bg); }
.test-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1.5rem; }
.test-card {
  background: var(--white); border: 1px solid var(--border);
  border-radius: 16px; padding: 1.8rem;
}
.test-stars { color: var(--amber); font-size: .9rem; margin-bottom: 1rem; letter-spacing: 2px; }
.test-quote { font-size: .9rem; line-height: 1.8; color: #374151; margin-bottom: 1.4rem; }
.test-foot { display: flex; align-items: center; gap: .8rem; }
.t-av { width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: .85rem; color: #fff; }
.t-name { font-weight: 600; font-size: .88rem; }
.t-role { font-size: .76rem; color: var(--mid); }
.t-placed { font-size: .74rem; font-weight: 600; color: var(--teal); margin-top: .15rem; }

/* ── FAQ ── */
.faq-bg { background: var(--white); }
.faq-list { max-width: 720px; display: flex; flex-direction: column; gap: .75rem; }
.faq-item {
  border: 1px solid var(--border); border-radius: 12px; overflow: hidden;
}
.faq-q {
  padding: 1.1rem 1.4rem; font-weight: 600; font-size: .93rem;
  cursor: pointer; display: flex; justify-content: space-between; align-items: center;
  user-select: none;
}
.faq-q::after { content: '+'; font-size: 1.2rem; color: var(--mid); transition: transform .2s; }
.faq-item.open .faq-q::after { transform: rotate(45deg); }
.faq-a { display: none; padding: 0 1.4rem 1.1rem; font-size: .88rem; color: var(--mid); line-height: 1.75; }
.faq-item.open .faq-a { display: block; }

/* ── CTA ── */
.cta-band {
  background: var(--teal);
  padding: 80px 6%; text-align: center;
}
.cta-band h2 { font-family: 'DM Serif Display', serif; font-size: clamp(1.8rem, 4vw, 2.8rem); color: var(--white); margin-bottom: .8rem; }
.cta-band p { color: rgba(255,255,255,.75); font-size: 1.05rem; margin-bottom: 2rem; }
.cta-band .btn-white {
  background: var(--white); color: var(--teal);
  border: none; border-radius: 10px; padding: .9rem 2.5rem;
  font-size: 1rem; font-weight: 700; cursor: pointer; text-decoration: none;
  transition: transform .15s, box-shadow .2s;
  box-shadow: 0 4px 20px #00000020;
  display: inline-block;
}
.cta-band .btn-white:hover { transform: translateY(-2px); box-shadow: 0 8px 28px #00000030; }

/* ── FOOTER ── */
footer { background: var(--ink); color: #6B6B60; padding: 60px 6% 28px; }
.footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem; max-width: 1200px; margin: 0 auto 2.5rem; }
.f-brand .logo { display: block; margin-bottom: .9rem; }
.f-brand p { font-size: .85rem; line-height: 1.7; max-width: 240px; }
.f-col h4 { font-weight: 700; font-size: .88rem; color: #9CA3AF; margin-bottom: 1rem; text-transform: uppercase; letter-spacing: .08em; }
.f-col ul { list-style: none; display: flex; flex-direction: column; gap: .55rem; }
.f-col a { color: #6B6B60; text-decoration: none; font-size: .85rem; transition: color .2s; }
.f-col a:hover { color: var(--white); }
.footer-bottom { max-width: 1200px; margin: 0 auto; padding-top: 1.5rem; border-top: 1px solid #2A2A28; display: flex; justify-content: space-between; font-size: .78rem; flex-wrap: wrap; gap: .5rem; }

/* ── RESPONSIVE ── */
@media (max-width: 960px) {
  .hero { grid-template-columns: 1fr; gap: 3rem; }
  .curriculum-wrap { grid-template-columns: 1fr; gap: 2.5rem; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 640px) {
  .nav-links { display: none; }
  .hero { padding: 50px 5% 50px; }
  .sec { padding: 60px 5%; }
  .trust-bar { gap: 1.5rem; flex-direction: column; align-items: flex-start; padding: 24px 5%; }
  .footer-grid { grid-template-columns: 1fr; }
  .hero-trust { flex-wrap: wrap; gap: 1.2rem; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="logo" href="#">Skill<span>Bridge</span></a>
  <ul class="nav-links">
    <li><a href="#courses">Courses</a></li>
    <li><a href="#curriculum">Curriculum</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#faq">FAQ</a></li>
  </ul>
  <div class="nav-right">
    <a class="btn-outline" href="#">Log in</a>
    <a class="btn-teal" href="#pricing">Enroll Now</a>
  </div>
</nav>

<!-- HERO -->
<div style="max-width:1280px;margin:0 auto;padding:0 6%;">
<div class="hero" style="padding-left:0;padding-right:0;">
  <div>
    <div class="hero-tag">🎓 Placement-Focused Training</div>
    <h1>Learn the skills.<br><em>Land the role.</em></h1>
    <p>Expert-led, industry-aligned online courses built specifically to get you placed. From fundamentals to job-ready in weeks, not years.</p>
    <div class="hero-actions">
      <a class="btn-hero" href="#courses">Browse Courses →</a>
      <a class="btn-hero-ghost" href="#curriculum">See Curriculum</a>
    </div>
    <div class="hero-trust">
      <div class="trust-item"><span class="trust-val">18K+</span><span class="trust-lbl">Students trained</span></div>
      <div class="trust-item"><span class="trust-val">94%</span><span class="trust-lbl">Placement rate</span></div>
      <div class="trust-item"><span class="trust-val">4.9★</span><span class="trust-lbl">Average rating</span></div>
    </div>
  </div>
  <div class="hero-visual">
    <div class="floating-pill top">🔥 482 enrolled this week</div>
    <div class="preview-card">
      <div class="preview-thumb">💻</div>
      <div class="preview-body">
        <div class="preview-cat">Full Stack Development</div>
        <div c
