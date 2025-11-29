:root{
  --bg: #f7f8fb;
  --card: #ffffff;
  --accent: #0f62fe; /* main color */
  --accent-2: #ff6b6b; /* secondary */
  --muted: #6b7280;
  --radius: 1rem;
  --max-width: 1100px;
  font-size: 16px;
  --gutter: 1rem;
}

*{box-sizing:border-box}
html,body{height:100%}
body{
  margin:0;
  font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  background:var(--bg);
  color:#111827;
  line-height:1.4;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  font-size:100%;
}

/* container */
.container{
  width: min(92%, var(--max-width));
  margin: 0 auto;
  padding: 2rem 0;
}

/* Header */
.site-header{
  background:linear-gradient(90deg,var(--accent),#045ed1);
  color:#fff;
  position:sticky;
  top:0;
  z-index:40;
}
.header-inner{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:1rem;
  padding:0.5rem 0;
}
.logo{font-weight:800; font-size:1.25rem}
.nav{
  display:flex;
  gap:1rem;
}
.nav a{
  color:#fff;
  text-decoration:none;
  font-weight:600;
  padding:0.5rem 0.6rem;
  border-radius:0.5rem;
  transition:transform .18s ease, background .18s ease;
}
.nav a:hover{ transform: translateY(-3px); background: rgba(255,255,255,0.08)}
.menu-btn{display:none; background:transparent; border:0; color:#fff; font-size:1.2rem}

/* Hero (flexbox layout) */
.hero-inner{
  display:flex;
  gap:1.5rem;
  align-items:center;
  justify-content:space-between;
  padding:2.5rem 0;
}
.hero-text{flex:1 1 420px}
.hero-image{flex:0 0 160px; display:flex; align-items:center; justify-content:center}
.avatar{
  width:9rem; height:9rem; border-radius:50%;
  background:linear-gradient(180deg,var(--accent),var(--accent-2));
  display:flex; align-items:center; justify-content:center;
  color:#fff; font-weight:700; font-size:2.5rem;
  box-shadow:0 8px 30px rgba(12,40,80,0.12);
  transform: translateY(0);
  transition:transform .3s ease;
}
.avatar:hover{ transform: translateY(-6px) rotate(-3deg)}

/* Animated title (keyframe color change) */
.animated-title{
  font-size:1.6rem;
  margin:0.25rem 0;
  font-weight:800;
  animation: colorPulse 4s linear infinite;
}
@keyframes colorPulse{
  0%{ color:var(--accent) }
  50%{ color:var(--accent-2) }
  100%{ color:var(--accent) }
}

h1{font-size:1.4rem; margin:0 0 0.25rem}
.lead{color:var(--muted); margin-top:0.5rem}

/* Buttons */
.btn{
  display:inline-block;
  background:var(--accent);
  color:#fff;
  padding:0.6rem 1rem;
  border-radius:0.6rem;
  text-decoration:none;
  font-weight:700;
  transition: transform .18s ease, box-shadow .18s ease;
  border:0;
}
.btn:hover{ transform: translateY(-4px); box-shadow: 0 10px 30px rgba(15,98,254,0.18) }
.btn.ghost{ background:transparent; color:var(--accent); border:2px solid rgba(15,98,254,0.12)}

/* Sections */
.section{ padding: 1.5rem 0; }
.section h3{ margin:0 0 0.8rem; font-size:1.1rem; color:#111827}

/* Skills grid */
.skills-grid{
  display:grid;
  gap:0.8rem;
  grid-template-columns: repeat(2,1fr);
}
.skill-card{
  background:var(--card);
  padding:1rem;
  border-radius:0.8rem;
  box-shadow:0 6px 18px rgba(12,40,80,0.06);
  display:flex; justify-content:space-between; align-items:center;
  transition: transform .18s ease, box-shadow .18s ease;
  cursor:default;
}
.skill-card:hover{ transform: translateY(-6px); box-shadow:0 14px 30px rgba(12,40,80,0.08) }
.skill-card .level{ color:var(--muted); font-size:0.85rem }

/* Projects grid (CSS Grid) */
.projects-grid{
  display:grid;
  gap:1rem;
  grid-template-columns: 1fr;
}
.project-card{
  background:var(--card);
  padding:1rem;
  border-radius:0.8rem;
  box-shadow: 0 8px 28px rgba(12,40,80,0.05);
  transition: transform .18s ease;
}
.project-card:hover{ transform: translateY(-8px) }
.card-link{ display:inline-block; margin-top:0.6rem; color:var(--accent); font-weight:700; text-decoration:none; }

/* Contact form */
.contact-form{
  max-width:640px;
  display:flex;
  flex-direction:column;
  gap:0.8rem;
}
.contact-form label{ display:flex; flex-direction:column; gap:0.4rem; }
.contact-form input, .contact-form textarea{
  padding:0.6rem; border-radius:0.5rem; border:1px solid #e6e9ef; background:#fff; font-size:1rem;
  transition: box-shadow .12s ease, transform .12s ease;
}
.contact-form input:focus, .contact-form textarea:focus{
  outline:none; box-shadow: 0 6px 24px rgba(15,98,254,0.08); transform: translateY(-2px);
}

/* Footer */
.site-footer{ background:#063a84; color:#fff; padding:0.8rem 0 }
.footer-inner{ display:flex; justify-content:space-between; align-items:center; gap:1rem; width:min(92%,var(--max-width)); margin:0 auto; }

/* Responsive / mobile-first breakpoints */
@media (min-width: 600px){
  .skills-grid{ grid-template-columns: repeat(3,1fr);}
  .projects-grid{ grid-template-columns: repeat(2, 1fr); }
}
@media (min-width: 900px){
  .hero-inner{ padding:3rem 0; }
  .projects-grid{ grid-template-columns: repeat(3, 1fr); }
  .nav a{ padding:0.5rem 0.8rem }
}

/* Desktop wide */
@media (min-width: 1100px){
  .hero-inner{ gap:3rem; align-items:center }
  .hero-text h1{ font-size:2rem }
  .animated-title{ font-size:2.2rem }
}

/* small screens specifics */
@media (max-width:599px){
  .hero-inner{ flex-direction:column; text-align:center; gap:1rem }
  .hero-image{ order:-1 }
  .nav{ display:none }
  .menu-btn{ display:inline-block }
  .nav.open{ display:flex; position:absolute; top:64px; right:12px; background:rgba(255,255,255,0.95); padding:8px; border-radius:8px; box-shadow:0 8px 20px rgba(0,0,0,0.08); flex-direction:column; }
  .skills-grid{ grid-template-columns: repeat(2,1fr) }
  .projects-grid{ grid-template-columns: 1fr }
}

/* use relative units for spacing & text size - demonstrated below */
h1,h2,h3{ line-height:1.1; }