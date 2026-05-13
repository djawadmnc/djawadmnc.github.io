<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>CreativeStudio | Design & Web Development</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Space+Grotesk:wght@300;400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --black:#0a0a0f;
  --white:#f5f3ef;
  --accent:#ff5c1a;
  --accent2:#00e5ff;
  --muted:#999;
  --card-bg:#131318;
  --border:rgba(255,255,255,0.07);
}
html{scroll-behavior:smooth}
body{
  background:var(--black);
  color:var(--white);
  font-family:'Space Grotesk',sans-serif;
  overflow-x:hidden;
}

/* ── CANVAS BG ── */
#bg-canvas{
  position:fixed;top:0;left:0;width:100%;height:100%;
  z-index:0;pointer-events:none;opacity:0.55;
}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:1.2rem 5%;
  background:rgba(10,10,15,0.85);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);
}
.logo{
  font-family:'Bebas Neue',sans-serif;
  font-size:1.8rem;letter-spacing:2px;
  color:var(--white);
}
.logo span{color:var(--accent)}
.nav-links{display:flex;gap:2rem;list-style:none}
.nav-links a{
  color:var(--muted);font-size:.9rem;font-weight:500;
  text-decoration:none;letter-spacing:.5px;transition:color .3s;
}
.nav-links a:hover{color:var(--accent)}
.nav-cta{
  background:var(--accent);color:var(--white);
  padding:.6rem 1.4rem;border-radius:4px;
  font-size:.85rem;font-weight:600;letter-spacing:.5px;
  text-decoration:none;transition:opacity .3s;
}
.nav-cta:hover{opacity:.85}

/* ── SECTIONS ── */
section{position:relative;z-index:1}

/* ── HERO ── */
#hero{
  min-height:100vh;
  display:flex;flex-direction:column;
  align-items:center;justify-content:center;
  text-align:center;
  padding:8rem 5% 4rem;
}
.hero-badge{
  display:inline-block;
  background:rgba(255,92,26,0.12);
  border:1px solid rgba(255,92,26,0.3);
  color:var(--accent);
  font-size:.75rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;
  padding:.4rem 1rem;border-radius:20px;margin-bottom:2rem;
}
.hero-title{
  font-family:'Bebas Neue',sans-serif;
  font-size:clamp(4rem,10vw,9rem);
  line-height:.95;letter-spacing:1px;
  margin-bottom:1.5rem;
}
.hero-title .line2{
  color:transparent;
  -webkit-text-stroke:1px rgba(255,255,255,0.25);
}
.hero-title .accent{color:var(--accent)}
.hero-sub{
  max-width:560px;
  color:var(--muted);font-size:1.05rem;line-height:1.7;
  margin-bottom:3rem;
}
.hero-btns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap}
.btn-primary{
  background:var(--accent);color:#fff;
  padding:.85rem 2rem;border-radius:4px;
  font-size:.9rem;font-weight:700;letter-spacing:.5px;
  text-decoration:none;transition:all .3s;border:none;cursor:pointer;
}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 10px 30px rgba(255,92,26,.35)}
.btn-outline{
  background:transparent;color:var(--white);
  border:1px solid var(--border);
  padding:.85rem 2rem;border-radius:4px;
  font-size:.9rem;font-weight:600;letter-spacing:.5px;
  text-decoration:none;transition:all .3s;cursor:pointer;
}
.btn-outline:hover{border-color:var(--accent2);color:var(--accent2)}

.stats{
  display:flex;gap:3rem;margin-top:4rem;
  flex-wrap:wrap;justify-content:center;
}
.stat-item{text-align:center}
.stat-num{
  font-family:'Bebas Neue',sans-serif;
  font-size:2.5rem;color:var(--accent);letter-spacing:1px;
}
.stat-label{font-size:.8rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase}

/* ── SECTION HEADER ── */
.sec-header{text-align:center;margin-bottom:4rem}
.sec-label{
  font-size:.75rem;letter-spacing:3px;text-transform:uppercase;
  color:var(--accent);font-weight:600;margin-bottom:.8rem;
}
.sec-title{
  font-family:'Bebas Neue',sans-serif;
  font-size:clamp(2.5rem,5vw,4.5rem);
  letter-spacing:1px;line-height:1;
}
.sec-title span{color:var(--accent)}
.sec-sub{color:var(--muted);font-size:1rem;margin-top:.8rem;max-width:500px;margin-left:auto;margin-right:auto}

/* ── SERVICES ── */
#services{padding:7rem 5%}
.services-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:1.5rem;
}
.service-card{
  background:var(--card-bg);
  border:1px solid var(--border);
  border-radius:12px;
  padding:2.5rem 2rem;
  transition:all .4s;
  position:relative;overflow:hidden;
}
.service-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
  transform:scaleX(0);transform-origin:left;transition:transform .4s;
}
.service-card:hover{transform:translateY(-6px);border-color:rgba(255,92,26,.3)}
.service-card:hover::before{transform:scaleX(1)}
.service-icon{
  font-size:2rem;margin-bottom:1.2rem;
  width:56px;height:56px;
  background:rgba(255,92,26,0.1);
  border-radius:10px;display:flex;align-items:center;justify-content:center;
}
.service-title{font-size:1.2rem;font-weight:700;margin-bottom:.7rem}
.service-desc{color:var(--muted);font-size:.9rem;line-height:1.65}
.service-tools{
  display:flex;gap:.5rem;flex-wrap:wrap;margin-top:1.2rem;
}
.tool-tag{
  background:rgba(255,255,255,0.05);
  border:1px solid var(--border);
  color:var(--muted);font-size:.72rem;font-weight:500;
  padding:.25rem .7rem;border-radius:20px;letter-spacing:.3px;
}

/* ── PACKAGES ── */
#packages{padding:7rem 5%;background:rgba(255,255,255,0.015)}
.packages-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:1.5rem;max-width:1000px;margin:0 auto;
}
.pkg-card{
  background:var(--card-bg);
  border:1px solid var(--border);
  border-radius:16px;padding:2.5rem 2rem;
  position:relative;transition:all .3s;
}
.pkg-card.featured{
  border-color:var(--accent);
  background:rgba(255,92,26,0.05);
}
.pkg-badge{
  position:absolute;top:-12px;left:50%;transform:translateX(-50%);
  background:var(--accent);color:#fff;
  font-size:.7rem;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;
  padding:.3rem 1rem;border-radius:20px;
}
.pkg-name{
  font-size:.8rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;
  color:var(--muted);margin-bottom:.8rem;
}
.pkg-price{
  font-family:'Bebas Neue',sans-serif;
  font-size:3.5rem;letter-spacing:1px;line-height:1;
  margin-bottom:.3rem;
}
.pkg-price span{font-size:1.5rem;vertical-align:top;margin-top:.4rem;display:inline-block}
.pkg-price sub{font-size:1rem;font-family:'Space Grotesk',sans-serif;font-weight:400;color:var(--muted)}
.pkg-desc{color:var(--muted);font-size:.88rem;margin:.8rem 0 1.5rem;line-height:1.5}
.pkg-features{list-style:none;margin-bottom:2rem}
.pkg-features li{
  font-size:.88rem;color:var(--muted);
  padding:.45rem 0;border-bottom:1px solid var(--border);
  display:flex;align-items:center;gap:.7rem;
}
.pkg-features li::before{
  content:'✓';color:var(--accent);font-weight:700;font-size:.8rem;flex-shrink:0;
}
.pkg-btn{
  display:block;text-align:center;
  background:var(--accent);color:#fff;
  padding:.85rem;border-radius:6px;
  font-weight:700;font-size:.9rem;letter-spacing:.5px;
  text-decoration:none;transition:opacity .3s;
}
.pkg-btn:hover{opacity:.85}
.pkg-btn.outline{background:transparent;border:1px solid var(--border);color:var(--white)}
.pkg-btn.outline:hover{border-color:var(--accent);color:var(--accent);opacity:1}

/* ── PORTFOLIO ── */
#portfolio{padding:7rem 5%}
.portfolio-grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(300px,1fr));
  gap:1.5rem;
}
.portfolio-item{
  background:var(--card-bg);border-radius:12px;
  border:1px solid var(--border);
  overflow:hidden;transition:all .4s;cursor:pointer;
}
.portfolio-item:hover{transform:translateY(-5px);border-color:rgba(0,229,255,.25)}
.portfolio-thumb{
  height:200px;position:relative;overflow:hidden;
  display:flex;align-items:center;justify-content:center;
  font-size:3rem;
}
.portfolio-info{padding:1.4rem}
.portfolio-cat{
  font-size:.7rem;letter-spacing:2px;text-transform:uppercase;
  color:var(--accent2);font-weight:600;margin-bottom:.4rem;
}
.portfolio-name{font-size:1.05rem;font-weight:700;margin-bottom:.4rem}
.portfolio-tech{color:var(--muted);font-size:.82rem}

/* ── WHY ME ── */
#why{padding:7rem 5%;background:rgba(255,255,255,0.015)}
.why-grid{
  display:grid;grid-template-columns:1fr 1fr;gap:5rem;
  align-items:center;max-width:1100px;margin:0 auto;
}
.why-visual{
  background:var(--card-bg);border:1px solid var(--border);
  border-radius:16px;padding:3rem;
}
.skill-bar{margin-bottom:1.8rem}
.skill-label{
  display:flex;justify-content:space-between;
  font-size:.85rem;font-weight:600;margin-bottom:.6rem;
}
.skill-label span:last-child{color:var(--accent);font-family:'DM Mono',monospace}
.skill-track{
  height:4px;background:rgba(255,255,255,0.07);
  border-radius:4px;overflow:hidden;
}
.skill-fill{
  height:100%;border-radius:4px;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
  animation:fillbar 1.5s ease forwards;
  transform-origin:left;
}
@keyframes fillbar{from{width:0}to{width:var(--w)}}
.why-points{display:flex;flex-direction:column;gap:2rem}
.why-point{display:flex;gap:1.2rem;align-items:flex-start}
.why-num{
  font-family:'Bebas Neue',sans-serif;font-size:2rem;
  color:var(--accent);opacity:.4;flex-shrink:0;line-height:1;
}
.why-point h3{font-size:1.05rem;font-weight:700;margin-bottom:.4rem}
.why-point p{color:var(--muted);font-size:.88rem;line-height:1.6}

/* ── TESTIMONIALS ── */
#testimonials{padding:7rem 5%}
.testimonials-grid{
  display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:1.5rem;
}
.testimonial-card{
  background:var(--card-bg);border:1px solid var(--border);
  border-radius:12px;padding:2rem;
  transition:all .3s;
}
.testimonial-card:hover{border-color:rgba(255,92,26,.3)}
.t-stars{color:var(--accent);font-size:1rem;margin-bottom:1rem;letter-spacing:2px}
.t-text{color:#c5c3bf;font-size:.9rem;line-height:1.7;margin-bottom:1.5rem;font-style:italic}
.t-author{display:flex;align-items:center;gap:.8rem}
.t-avatar{
  width:40px;height:40px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-weight:700;font-size:.85rem;flex-shrink:0;
}
.t-name{font-size:.9rem;font-weight:600}
.t-country{font-size:.78rem;color:var(--muted)}

/* ── CONTACT ── */
#contact{padding:7rem 5%}
.contact-wrapper{
  display:grid;grid-template-columns:1fr 1.3fr;gap:5rem;
  max-width:1100px;margin:0 auto;align-items:start;
}
.contact-info h2{
  font-family:'Bebas Neue',sans-serif;
  font-size:clamp(2rem,4vw,3.5rem);margin-bottom:1.2rem;letter-spacing:1px;
}
.contact-info p{color:var(--muted);line-height:1.7;margin-bottom:2rem}
.contact-detail{display:flex;flex-direction:column;gap:1rem}
.c-item{display:flex;align-items:center;gap:1rem}
.c-icon{
  width:42px;height:42px;border-radius:8px;
  background:rgba(255,92,26,0.1);border:1px solid rgba(255,92,26,.2);
  display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0;
}
.c-text{font-size:.88rem;color:var(--muted)}
.c-text strong{color:var(--white);display:block;font-size:.9rem}
.contact-form{
  background:var(--card-bg);border:1px solid var(--border);
  border-radius:16px;padding:2.5rem;
}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1rem}
.form-group{margin-bottom:1rem}
.form-group label{
  display:block;font-size:.8rem;font-weight:600;
  letter-spacing:.5px;text-transform:uppercase;
  color:var(--muted);margin-bottom:.5rem;
}
.form-group input,
.form-group select,
.form-group textarea{
  width:100%;background:rgba(255,255,255,0.04);
  border:1px solid var(--border);border-radius:8px;
  color:var(--white);font-family:'Space Grotesk',sans-serif;
  font-size:.9rem;padding:.85rem 1rem;
  outline:none;transition:border-color .3s;
}
.form-group input:focus,
.form-group select,
.form-group textarea:focus{border-color:var(--accent)}
.form-group textarea{resize:vertical;min-height:120px}
.form-group select{cursor:pointer}
.form-group select option{background:#1a1a22;color:var(--white)}
.form-submit{
  width:100%;background:var(--accent);color:#fff;
  border:none;border-radius:8px;
  padding:1rem;font-family:'Space Grotesk',sans-serif;
  font-size:.95rem;font-weight:700;letter-spacing:.5px;
  cursor:pointer;transition:all .3s;
}
.form-submit:hover{transform:translateY(-2px);box-shadow:0 10px 30px rgba(255,92,26,.3)}
.form-note{text-align:center;color:var(--muted);font-size:.78rem;margin-top:.8rem}

/* ── FOOTER ── */
footer{
  border-top:1px solid var(--border);
  padding:3rem 5%;
  display:flex;align-items:center;justify-content:space-between;
  flex-wrap:wrap;gap:1rem;
}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:1.5rem;letter-spacing:2px}
.footer-logo span{color:var(--accent)}
.footer-copy{color:var(--muted);font-size:.82rem}
.footer-links{display:flex;gap:1.5rem}
.footer-links a{color:var(--muted);font-size:.82rem;text-decoration:none;transition:color .3s}
.footer-links a:hover{color:var(--accent)}

/* ── SUCCESS MSG ── */
.success-msg{
  display:none;text-align:center;padding:2rem;
  color:var(--accent2);font-size:1rem;
}

/* ── SCROLL REVEAL ── */
.reveal{opacity:0;transform:translateY(30px);transition:all .7s ease}
.reveal.visible{opacity:1;transform:none}

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .why-grid,.contact-wrapper{grid-template-columns:1fr}
  .form-row{grid-template-columns:1fr}
  nav{padding:1rem 4%}
  .nav-links{display:none}
}
</style>
</head>
<body>

<canvas id="bg-canvas"></canvas>

<!-- NAV -->
<nav>
  <div class="logo">Creative<span>Studio</span></div>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#packages">Packages</a></li>
    <li><a href="#portfolio">Work</a></li>
    <li><a href="#why">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Hire Me →</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-badge">✦ Available for new projects on Fiverr</div>
  <h1 class="hero-title">
    <div>Designs That</div>
    <div class="line2">MAKE</div>
    <div>You Money<span class="accent">.</span></div>
  </h1>
  <p class="hero-sub">
    Logos, posters, brand identities, and high-converting websites — crafted in Photoshop, Illustrator, and pure code. Built to impress, optimised to convert.
  </p>
  <div class="hero-btns">
    <a href="#packages" class="btn-primary">View Packages</a>
    <a href="#portfolio" class="btn-outline">See My Work</a>
  </div>
  <div class="stats">
    <div class="stat-item">
      <div class="stat-num">120+</div>
      <div class="stat-label">Happy Clients</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">5.0</div>
      <div class="stat-label">Star Rating</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">48h</div>
      <div class="stat-label">Avg. Delivery</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">100%</div>
      <div class="stat-label">Satisfaction</div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="sec-header reveal">
    <div class="sec-label">What I Do</div>
    <h2 class="sec-title">My <span>Services</span></h2>
    <p class="sec-sub">Everything you need to build a powerful digital presence — from pixel to publish.</p>
  </div>
  <div class="services-grid">

    <div class="service-card reveal">
      <div class="service-icon">🎨</div>
      <div class="service-title">Poster & Print Design</div>
      <p class="service-desc">Eye-catching posters, flyers, banners, and event materials that grab attention and communicate your message at a glance. Print-ready files delivered.</p>
      <div class="service-tools">
        <span class="tool-tag">Photoshop</span>
        <span class="tool-tag">Illustrator</span>
        <span class="tool-tag">InDesign</span>
        <span class="tool-tag">Print-ready PDF</span>
      </div>
    </div>

    <div class="service-card reveal">
      <div class="service-icon">✏️</div>
      <div class="service-title">Logo & Brand Identity</div>
      <p class="service-desc">Custom logos and full brand kits — color palettes, typography guides, and usage rules — that make your business unforgettable.</p>
      <div class="service-tools">
        <span class="tool-tag">Illustrator</span>
        <span class="tool-tag">Vector files</span>
        <span class="tool-tag">Brand guide PDF</span>
      </div>
    </div>

    <div class="service-card reveal">
      <div class="service-icon">💻</div>
      <div class="service-title">Website Design & Dev</div>
      <p class="service-desc">Fast, modern, responsive websites coded from scratch. Pixel-perfect designs that load instantly and work beautifully on every device.</p>
      <div class="service-tools">
        <span class="tool-tag">HTML5</span>
        <span class="tool-tag">CSS3</span>
        <span class="tool-tag">JavaScript</span>
        <span class="tool-tag">Responsive</span>
      </div>
    </div>

    <div class="service-card reveal">
      <div class="service-icon">🖼️</div>
      <div class="service-title">Photo Editing & Retouching</div>
      <p class="service-desc">Professional photo retouching, background removal, colour grading, and composite editing. Product photos, portraits, real-estate — any image.</p>
      <div class="service-tools">
        <span class="tool-tag">Photoshop</span>
        <span class="tool-tag">Lightroom</span>
        <span class="tool-tag">High-res export</span>
      </div>
    </div>

    <div class="service-card reveal">
      <div class="service-icon">📱</div>
      <div class="service-title">Social Media Design</div>
      <p class="service-desc">Scroll-stopping Instagram posts, story templates, YouTube thumbnails, Facebook covers and full content packages for consistent brand presence.</p>
      <div class="service-tools">
        <span class="tool-tag">Photoshop</span>
        <span class="tool-tag">Illustrator</span>
        <span class="tool-tag">All platforms</span>
      </div>
    </div>

    <div class="service-card reveal">
      <div class="service-icon">⚡</div>
      <div class="service-title">Landing Page Conversion</div>
      <p class="service-desc">High-converting single-page sites designed around your goals — lead capture, product sales, event registration — with built-in contact forms.</p>
      <div class="service-tools">
        <span class="tool-tag">HTML/CSS</span>
        <span class="tool-tag">JavaScript</span>
        <span class="tool-tag">SEO-ready</span>
        <span class="tool-tag">Fast load</span>
      </div>
    </div>

  </div>
</section>

<!-- PACKAGES -->
<section id="packages">
  <div class="sec-header reveal">
    <div class="sec-label">Pricing</div>
    <h2 class="sec-title">Simple <span>Packages</span></h2>
    <p class="sec-sub">Transparent pricing. No hidden fees. Everything you see is what you get.</p>
  </div>
  <div class="packages-grid">

    <div class="pkg-card reveal">
      <div class="pkg-name">Starter</div>
      <div class="pkg-price"><span>$</span>25<sub>/gig</sub></div>
      <p class="pkg-desc">Perfect for individuals and small projects that need clean, professional results fast.</p>
      <ul class="pkg-features">
        <li>1 design concept</li>
        <li>2 revisions included</li>
        <li>Source files (AI/PSD)</li>
        <li>48-hour delivery</li>
        <li>Print-ready export</li>
      </ul>
      <a href="#contact" class="pkg-btn outline">Get Started</a>
    </div>

    <div class="pkg-card featured reveal">
      <div class="pkg-badge">⭐ Most Popular</div>
      <div class="pkg-name">Professional</div>
      <div class="pkg-price"><span>$</span>75<sub>/gig</sub></div>
      <p class="pkg-desc">The complete package for growing brands. Multiple concepts, full source files, priority support.</p>
      <ul class="pkg-features">
        <li>3 design concepts</li>
        <li>Unlimited revisions</li>
        <li>All source files</li>
        <li>24-hour delivery</li>
        <li>Brand style guide</li>
        <li>Commercial license</li>
      </ul>
      <a href="#contact" class="pkg-btn">Order Now →</a>
    </div>

    <div class="pkg-card reveal">
      <div class="pkg-name">Premium</div>
      <div class="pkg-price"><span>$</span>150<sub>/gig</sub></div>
      <p class="pkg-desc">Full brand identity or complete website — for businesses serious about their digital presence.</p>
      <ul class="pkg-features">
        <li>5 design concepts</li>
        <li>Unlimited revisions</li>
        <li>Full website (5 pages)</li>
        <li>SEO optimised code</li>
        <li>Contact form included</li>
        <li>Priority support 7 days</li>
        <li>Commercial license</li>
      </ul>
      <a href="#contact" class="pkg-btn outline">Contact Me</a>
    </div>

  </div>
</section>

<!-- PORTFOLIO -->
<section id="portfolio">
  <div class="sec-header reveal">
    <div class="sec-label">Recent Work</div>
    <h2 class="sec-title">Featured <span>Projects</span></h2>
    <p class="sec-sub">A selection of recent client work across design and development.</p>
  </div>
  <div class="portfolio-grid">

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#1a0a2e,#3d1a6e)">
        <div style="text-align:center">
          <div style="font-size:1.8rem;font-weight:900;letter-spacing:-1px;color:#a78bfa">NEXUS</div>
          <div style="font-size:.6rem;letter-spacing:6px;color:#6d4fc0;margin-top:4px">BRAND IDENTITY</div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Logo & Branding</div>
        <div class="portfolio-name">Nexus Tech — Full Brand Identity</div>
        <div class="portfolio-tech">Illustrator · Brand Guide · 5 logo variations</div>
      </div>
    </div>

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#0f1f0f,#1a3d1a)">
        <div style="text-align:center">
          <div style="font-size:3rem">🌿</div>
          <div style="font-size:.65rem;letter-spacing:4px;color:#4ade80;margin-top:6px">EVENT POSTER</div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Poster Design</div>
        <div class="portfolio-name">EcoFest 2024 Event Campaign</div>
        <div class="portfolio-tech">Photoshop · Print + Digital · A2 Format</div>
      </div>
    </div>

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#0a1628,#0d3060)">
        <div style="text-align:center;padding:1.5rem">
          <div style="background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.1);border-radius:8px;padding:.6rem 1rem;font-size:.75rem;color:#60a5fa;font-family:monospace">&lt;portfolio /&gt;</div>
          <div style="font-size:.6rem;color:#3b82f6;letter-spacing:2px;margin-top:.8rem">WEBSITE</div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Web Development</div>
        <div class="portfolio-name">Photography Portfolio Site</div>
        <div class="portfolio-tech">HTML · CSS · JS · Responsive · Contact Form</div>
      </div>
    </div>

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#1f0a0a,#4d1515)">
        <div style="text-align:center">
          <div style="font-size:.65rem;letter-spacing:6px;color:#f87171">SOCIAL MEDIA</div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:6px;margin-top:.8rem">
            <div style="background:rgba(255,100,100,0.2);border-radius:4px;width:48px;height:48px;margin:auto"></div>
            <div style="background:rgba(255,100,100,0.1);border-radius:4px;width:48px;height:48px;margin:auto"></div>
            <div style="background:rgba(255,100,100,0.1);border-radius:4px;width:48px;height:48px;margin:auto"></div>
            <div style="background:rgba(255,100,100,0.2);border-radius:4px;width:48px;height:48px;margin:auto"></div>
          </div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Social Media</div>
        <div class="portfolio-name">Café Brand — Instagram Content Pack</div>
        <div class="portfolio-tech">Photoshop · 30 templates · Editable PSD</div>
      </div>
    </div>

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#0f0f1a,#1a1a3d)">
        <div style="text-align:center">
          <div style="font-size:2.5rem">💎</div>
          <div style="font-size:.6rem;letter-spacing:4px;color:#818cf8;margin-top:6px">LUXURY BRAND</div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Logo Design</div>
        <div class="portfolio-name">Luxe Jewellery — Minimalist Logo</div>
        <div class="portfolio-tech">Illustrator · Vector · Multiple formats</div>
      </div>
    </div>

    <div class="portfolio-item reveal">
      <div class="portfolio-thumb" style="background:linear-gradient(135deg,#0a1a1f,#0d3d4d)">
        <div style="text-align:center;padding:1rem">
          <div style="border:1px solid rgba(0,229,255,0.3);border-radius:8px;padding:.8rem;font-size:.7rem;color:#00e5ff;font-family:monospace;text-align:left">
            <div style="opacity:.5">/* landing page */</div>
            <div>nav · hero</div>
            <div>services · cta</div>
            <div style="color:#ff5c1a">form.submit()</div>
          </div>
        </div>
      </div>
      <div class="portfolio-info">
        <div class="portfolio-cat">Web Development</div>
        <div class="portfolio-name">SaaS Product Landing Page</div>
        <div class="portfolio-tech">HTML/CSS/JS · Animations · Lead form</div>
      </div>
    </div>

  </div>
</section>

<!-- WHY ME -->
<section id="why">
  <div style="max-width:1100px;margin:0 auto">
    <div class="sec-header reveal">
      <div class="sec-label">Why Choose Me</div>
      <h2 class="sec-title">Skills & <span>Experience</span></h2>
    </div>
    <div class="why-grid">
      <div class="why-visual reveal">
        <div class="skill-bar">
          <div class="skill-label"><span>Adobe Photoshop</span><span>95%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:95%"></div></div>
        </div>
        <div class="skill-bar">
          <div class="skill-label"><span>Adobe Illustrator</span><span>92%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:92%"></div></div>
        </div>
        <div class="skill-bar">
          <div class="skill-label"><span>HTML5 & CSS3</span><span>90%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:90%"></div></div>
        </div>
        <div class="skill-bar">
          <div class="skill-label"><span>JavaScript</span><span>80%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:80%"></div></div>
        </div>
        <div class="skill-bar">
          <div class="skill-label"><span>Branding & Identity</span><span>96%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:96%"></div></div>
        </div>
        <div class="skill-bar">
          <div class="skill-label"><span>Print Design</span><span>93%</span></div>
          <div class="skill-track"><div class="skill-fill" style="--w:93%"></div></div>
        </div>
        <div style="margin-top:2rem;padding-top:1.5rem;border-top:1px solid var(--border);display:flex;gap:2rem;flex-wrap:wrap">
          <div>
            <div style="font-family:'Bebas Neue',sans-serif;font-size:2.2rem;color:var(--accent)">4+</div>
            <div style="font-size:.75rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase">Years exp.</div>
          </div>
          <div>
            <div style="font-family:'Bebas Neue',sans-serif;font-size:2.2rem;color:var(--accent2)">120+</div>
            <div style="font-size:.75rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase">Projects done</div>
          </div>
          <div>
            <div style="font-family:'Bebas Neue',sans-serif;font-size:2.2rem;color:var(--accent)">48h</div>
            <div style="font-size:.75rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase">Max. delivery</div>
          </div>
        </div>
      </div>
      <div class="why-points reveal">
        <div class="why-point">
          <div class="why-num">01</div>
          <div>
            <h3>Pixel-perfect, every time</h3>
            <p>I obsess over alignment, spacing, and colour accuracy. Every file I deliver is clean, organised, and ready for print or web without extra editing.</p>
          </div>
        </div>
        <div class="why-point">
          <div class="why-num">02</div>
          <div>
            <h3>Fast turnaround, no excuses</h3>
            <p>Most projects ship within 24–48 hours. Urgent deadline? I offer express delivery so you never miss a launch date.</p>
          </div>
        </div>
        <div class="why-point">
          <div class="why-num">03</div>
          <div>
            <h3>Unlimited revisions until perfect</h3>
            <p>Your satisfaction is the only metric that matters. I revise until you're 100% happy — no passive-aggressive attitude, no extra charges.</p>
          </div>
        </div>
        <div class="why-point">
          <div class="why-num">04</div>
          <div>
            <h3>Clear communication, always</h3>
            <p>I respond within hours, ask the right questions upfront, and keep you updated so there are zero surprises at delivery.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials">
  <div class="sec-header reveal">
    <div class="sec-label">Client Reviews</div>
    <h2 class="sec-title">What Clients <span>Say</span></h2>
  </div>
  <div class="testimonials-grid">

    <div class="testimonial-card reveal">
      <div class="t-stars">★★★★★</div>
      <p class="t-text">"Absolutely incredible work. The logo he designed for our startup is exactly what we envisioned — clean, modern, and memorable. Delivered in under 24 hours with zero revisions needed."</p>
      <div class="t-author">
        <div class="t-avatar" style="background:rgba(255,92,26,.15);color:var(--accent)">JM</div>
        <div>
          <div class="t-name">James Mitchell</div>
          <div class="t-country">🇺🇸 United States · Logo Design</div>
        </div>
      </div>
    </div>

    <div class="testimonial-card reveal">
      <div class="t-stars">★★★★★</div>
      <p class="t-text">"My website looks and works better than I ever imagined. Responsive, fast, and the contact form works perfectly. I've already had 3 leads come through it this week. Highly recommend!"</p>
      <div class="t-author">
        <div class="t-avatar" style="background:rgba(0,229,255,.1);color:var(--accent2)">SB</div>
        <div>
          <div class="t-name">Sophie Beaumont</div>
          <div class="t-country">🇬🇧 United Kingdom · Web Development</div>
        </div>
      </div>
    </div>

    <div class="testimonial-card reveal">
      <div class="t-stars">★★★★★</div>
      <p class="t-text">"The event posters he created for our music festival were stunning. Everyone was asking who did them. Professional, creative, and a genuine pleasure to work with. Will order again."</p>
      <div class="t-author">
        <div class="t-avatar" style="background:rgba(255,92,26,.12);color:var(--accent)">KR</div>
        <div>
          <div class="t-name">Karim Rashed</div>
          <div class="t-country">🇦🇪 UAE · Poster Design</div>
        </div>
      </div>
    </div>

    <div class="testimonial-card reveal">
      <div class="t-stars">★★★★★</div>
      <p class="t-text">"I ordered a full Instagram content pack — 30 templates — and every single one was on-brand, beautifully designed, and easy to edit. Best investment I've made for my café this year."</p>
      <div class="t-author">
        <div class="t-avatar" style="background:rgba(0,229,255,.1);color:var(--accent2)">ML</div>
        <div>
          <div class="t-name">Marie Laurent</div>
          <div class="t-country">🇫🇷 France · Social Media Design</div>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrapper">
    <div class="contact-info reveal">
      <div class="sec-label">Get In Touch</div>
      <h2>Let's Build Something <span style="color:var(--accent)">Great</span></h2>
      <p>Ready to start your project? Fill in the form and I'll get back to you within a few hours with a quote and timeline.</p>
      <div class="contact-detail">
        <div class="c-item">
          <div class="c-icon">⚡</div>
          <div class="c-text"><strong>Response Time</strong>Usually within 2–4 hours</div>
        </div>
        <div class="c-item">
          <div class="c-icon">🌍</div>
          <div class="c-text"><strong>Available For</strong>Remote clients worldwide</div>
        </div>
        <div class="c-item">
          <div class="c-icon">🔒</div>
          <div class="c-text"><strong>100% Satisfaction</strong>Money-back guarantee on Fiverr</div>
        </div>
        <div class="c-item">
          <div class="c-icon">📦</div>
          <div class="c-text"><strong>Free Consultation</strong>Tell me your project before ordering</div>
        </div>
      </div>
    </div>
    <div class="contact-form reveal">
      <div id="form-container">
        <div class="form-row">
          <div class="form-group">
            <label>First Name</label>
            <input type="text" id="fname" placeholder="John"/>
          </div>
          <div class="form-group">
            <label>Last Name</label>
            <input type="text" id="lname" placeholder="Doe"/>
          </div>
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" id="email" placeholder="john@example.com"/>
        </div>
        <div class="form-group">
          <label>Service Needed</label>
          <select id="service">
            <option value="">— Select a service —</option>
            <option>Logo & Brand Identity</option>
            <option>Poster / Print Design</option>
            <option>Website Design & Development</option>
            <option>Social Media Design Pack</option>
            <option>Photo Editing & Retouching</option>
            <option>Landing Page</option>
            <option>Other / Custom Project</option>
          </select>
        </div>
        <div class="form-group">
          <label>Budget Range</label>
          <select id="budget">
            <option value="">— Select budget —</option>
            <option>$25 – $50 (Starter)</option>
            <option>$50 – $100 (Professional)</option>
            <option>$100 – $200 (Premium)</option>
            <option>$200+ (Enterprise)</option>
          </select>
        </div>
        <div class="form-group">
          <label>Project Details</label>
          <textarea id="message" placeholder="Tell me about your project — what you need, your deadline, any references or ideas you have..."></textarea>
        </div>
        <button class="form-submit" onclick="submitForm()">Send Message & Get Quote →</button>
        <p class="form-note">✓ No spam · ✓ Response within 4 hours · ✓ Free consultation</p>
      </div>
      <div class="success-msg" id="success-msg">
        <div style="font-size:2.5rem;margin-bottom:1rem">✅</div>
        <div style="font-size:1.2rem;font-weight:700;color:var(--white);margin-bottom:.5rem">Message Sent!</div>
        <p style="color:var(--muted);font-size:.9rem">Thanks for reaching out. I'll review your project and get back to you within a few hours with a personalised quote.</p>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Creative<span>Studio</span></div>
  <p class="footer-copy">© 2025 CreativeStudio. Available on Fiverr · All rights reserved.</p>
  <div class="footer-links">
    <a href="#services">Services</a>
    <a href="#portfolio">Portfolio</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<!-- SCRIPTS -->
<script>
// ── Animated particle background ──
const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize(){
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

class Particle{
  constructor(){this.reset()}
  reset(){
    this.x = Math.random()*W;
    this.y = Math.random()*H;
    this.size = Math.random()*1.5+.3;
    this.speedX = (Math.random()-.5)*.4;
    this.speedY = (Math.random()-.5)*.4;
    this.opacity = Math.random()*.5+.1;
    this.color = Math.random()>.6 ? '#ff5c1a' : Math.random()>.5 ? '#00e5ff' : '#ffffff';
  }
  update(){
    this.x+=this.speedX;
    this.y+=this.speedY;
    if(this.x<0||this.x>W||this.y<0||this.y>H) this.reset();
  }
  draw(){
    ctx.save();
    ctx.globalAlpha = this.opacity;
    ctx.fillStyle = this.color;
    ctx.beginPath();
    ctx.arc(this.x,this.y,this.size,0,Math.PI*2);
    ctx.fill();
    ctx.restore();
  }
}

for(let i=0;i<130;i++) particles.push(new Particle());

function drawConnections(){
  for(let i=0;i<particles.length;i++){
    for(let j=i+1;j<particles.length;j++){
      const dx=particles[i].x-particles[j].x;
      const dy=particles[i].y-particles[j].y;
      const dist=Math.sqrt(dx*dx+dy*dy);
      if(dist<100){
        ctx.save();
        ctx.globalAlpha=(1-dist/100)*0.06;
        ctx.strokeStyle='#ffffff';
        ctx.lineWidth=.5;
        ctx.beginPath();
        ctx.moveTo(particles[i].x,particles[i].y);
        ctx.lineTo(particles[j].x,particles[j].y);
        ctx.stroke();
        ctx.restore();
      }
    }
  }
}

function animate(){
  ctx.clearRect(0,0,W,H);
  drawConnections();
  particles.forEach(p=>{p.update();p.draw();});
  requestAnimationFrame(animate);
}
animate();

// ── Mouse-interactive particles ──
let mouse={x:W/2,y:H/2};
document.addEventListener('mousemove',e=>{mouse.x=e.clientX;mouse.y=e.clientY;});

// ── Scroll reveal ──
const reveals = document.querySelectorAll('.reveal');
const observer = new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting) e.target.classList.add('visible');});
},{threshold:.12});
reveals.forEach(r=>observer.observe(r));

// ── Form submit ──
function submitForm(){
  const fname=document.getElementById('fname').value.trim();
  const email=document.getElementById('email').value.trim();
  const service=document.getElementById('service').value;
  const message=document.getElementById('message').value.trim();
  if(!fname||!email||!service||!message){
    alert('Please fill in all required fields (Name, Email, Service, and Message).');
    return;
  }
  if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){
    alert('Please enter a valid email address.');
    return;
  }
  document.getElementById('form-container').style.display='none';
  const msg=document.getElementById('success-msg');
  msg.style.display='block';
  msg.style.animation='none';
  msg.offsetHeight;
  msg.style.animation='fadeIn .5s ease';
}

// Fade-in for success
const style=document.createElement('style');
style.textContent='@keyframes fadeIn{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:none}}';
document.head.appendChild(style);
</script>
</body>
</html>
