@import url('https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Quicksand:wght@400;500;600;700&display=swap');

:root{
  --pink:#FBE4EC;
  --pink-soft:#FDF0F3;
  --pink-deep:#F3B8CE;
  --pink-line:#F5CBDA;
  --forest:#2F6B45;
  --forest-dark:#234F34;
  --forest-light:#4F8F63;
  --cream:#FFFBF9;
  --ink:#3D2E33;
  --muted:#6B5A61;
  --line:rgba(61,46,51,0.12);
  --max:1080px;
}

*{ box-sizing:border-box; }
html{ scroll-behavior:smooth; }
body{
  margin:0;
  background:var(--cream);
  color:var(--ink);
  font-family:'Quicksand', sans-serif;
  font-size:17px;
  line-height:1.65;
}
h1,h2,h3{
  font-family:'Baloo 2', sans-serif;
  font-weight:700;
  color:var(--forest);
  margin:0 0 14px;
}
h1{ font-size:clamp(2.1rem,4.5vw,3.1rem); line-height:1.1; }
h2{ font-size:clamp(1.6rem,3vw,2.1rem); }
h3{ font-size:1.25rem; margin-bottom:8px; }
a{ color:inherit; }
img{ max-width:100%; display:block; }
ul{ margin:0; padding:0; list-style:none; }
p{ color:var(--muted); margin:0 0 14px; }
.wrap{ max-width:var(--max); margin:0 auto; padding:0 28px; }

:focus-visible{ outline:2px solid var(--forest); outline-offset:3px; }

/* ---- Nav ---- */
header{
  position:sticky; top:0; z-index:30;
  background:rgba(255,251,249,0.94);
  backdrop-filter:blur(6px);
  border-bottom:1px solid var(--pink-line);
}
.nav{
  display:flex; align-items:center; justify-content:space-between;
  padding:12px 28px; max-width:var(--max); margin:0 auto;
}
.brand{ display:flex; align-items:center; gap:12px; text-decoration:none; }
.brand img{ width:48px; height:48px; border-radius:50%; object-fit:cover; }
.brand span{
  font-family:'Baloo 2', sans-serif; font-weight:700;
  font-size:1.4rem; color:var(--forest);
}
.nav-links{ display:flex; gap:6px; align-items:center; }
.nav-links a{
  text-decoration:none; font-weight:700; font-size:0.96rem;
  color:var(--ink); padding:10px 16px; border-radius:999px;
  transition:background .18s ease, color .18s ease;
}
.nav-links a:hover{ background:var(--pink); }
.nav-links a.active{ background:var(--forest); color:#fff; }
.nav-toggle{ display:none; }

@media (max-width:760px){
  .nav-links{
    position:absolute; top:100%; left:0; right:0; flex-direction:column;
    align-items:stretch; background:var(--cream); border-bottom:1px solid var(--pink-line);
    max-height:0; overflow:hidden; gap:0; padding:0;
  }
  .nav-links a{ border-radius:0; padding:14px 28px; border-bottom:1px solid var(--pink-line); }
  .nav-toggle{ display:block; background:none; border:none; cursor:pointer; width:30px; height:22px; position:relative; }
  .nav-toggle span,.nav-toggle::before,.nav-toggle::after{ content:''; position:absolute; left:0; right:0; height:2px; background:var(--forest); }
  .nav-toggle::before{ top:1px; } .nav-toggle span{ top:10px; } .nav-toggle::after{ top:19px; }
  #nav-check{ display:none; }
  #nav-check:checked ~ .nav-links{ max-height:500px; }
}

/* ---- Hero ---- */
.hero{
  background:var(--pink);
  padding:56px 0;
  border-bottom:1px solid var(--pink-line);
}
.hero .wrap{ display:grid; grid-template-columns:1.1fr 0.9fr; gap:44px; align-items:center; }
.hero.no-media .wrap{ grid-template-columns:1fr; }
.hero .tagline{
  font-family:'Baloo 2', sans-serif; font-weight:700;
  color:var(--forest); font-size:clamp(1.6rem,3.5vw,2.4rem);
  margin-bottom:16px;
}
.hero p.lead{ font-size:1.05rem; color:var(--muted); }
.hero-media img{
  border-radius:22px; border:6px solid #fff;
  box-shadow:0 8px 0 var(--pink-deep);
  aspect-ratio:4/3; object-fit:cover; width:100%;
}
@media (max-width:800px){ .hero .wrap{ grid-template-columns:1fr; } .hero-media{ order:-1; } }

/* ---- Buttons ---- */
.btn{
  display:inline-block; padding:13px 28px; border-radius:999px;
  font-weight:700; text-decoration:none; font-size:0.98rem;
  transition:transform .15s ease, background .2s ease;
}
.btn:hover{ transform:translateY(-1px); }
.btn-primary{ background:var(--forest); color:#fff; }
.btn-primary:hover{ background:var(--forest-light); }
.btn-outline{ border:1.5px solid var(--forest); color:var(--forest); }
.btn-outline:hover{ background:var(--forest); color:#fff; }

/* ---- Sections ---- */
section{ padding:56px 0; }
section.alt{ background:var(--pink-soft); }
.section-badge{
  display:inline-block; background:var(--forest); color:#fff;
  font-size:0.82rem; font-weight:700; padding:5px 14px; border-radius:999px;
  margin-bottom:14px;
}

/* ---- Bullet / stat lists ---- */
.stat-list li{ padding:16px 0; border-bottom:1px solid var(--line); }
.stat-list li:last-child{ border-bottom:none; }
.stat-list strong{ color:var(--forest); display:block; font-size:1.05rem; margin-bottom:2px; }

/* ---- Project / what-we-do cards ---- */
.card-grid{ display:grid; grid-template-columns:repeat(2,1fr); gap:24px; }
@media (max-width:760px){ .card-grid{ grid-template-columns:1fr; } }
.card{
  background:#fff; border:1px solid var(--pink-line); border-radius:20px;
  padding:0; overflow:hidden; box-shadow:0 3px 0 var(--pink-line);
}
.card .card-photo{ width:100%; aspect-ratio:16/9; object-fit:cover; }
.card .card-body{ padding:24px; }
.card svg{ width:42px; height:42px; margin-bottom:12px; }
.card ul{ margin-top:10px; }
.card li{ position:relative; padding-left:20px; margin-bottom:8px; color:var(--muted); }
.card li::before{ content:''; position:absolute; left:0; top:9px; width:6px; height:6px; background:var(--pink-deep); border-radius:50%; }

/* ---- Team ---- */
.team-photo-banner{ border-radius:22px; overflow:hidden; margin-bottom:36px; border:6px solid #fff; box-shadow:0 8px 0 var(--pink-deep); }
.team-photo-banner img{ width:100%; max-height:420px; object-fit:cover; }
.team-photo-banner .caption{ background:var(--forest); color:#fff; padding:12px 20px; font-size:0.92rem; font-weight:600; }
.team-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:22px; }
@media (max-width:860px){ .team-grid{ grid-template-columns:repeat(2,1fr); } }
@media (max-width:560px){ .team-grid{ grid-template-columns:1fr; } }
.team-card{ background:#fff; border:1px solid var(--pink-line); border-radius:16px; padding:24px; text-align:left; }
.team-avatar{
  width:56px; height:56px; border-radius:50%; background:var(--pink);
  display:flex; align-items:center; justify-content:center;
  font-family:'Baloo 2',sans-serif; font-weight:700; color:var(--forest);
  font-size:1.2rem; margin-bottom:14px;
}
.team-card h3{ margin-bottom:2px; font-size:1.1rem; }
.team-card .role{ color:var(--pink-deep); font-weight:700; font-size:0.88rem; }

/* ---- Blog ---- */
.post-grid{ display:grid; grid-template-columns:repeat(3,1fr); gap:22px; }
@media (max-width:860px){ .post-grid{ grid-template-columns:1fr; } }
.post-card{ background:#fff; border:1px solid var(--pink-line); border-radius:16px; overflow:hidden; box-shadow:0 3px 0 var(--pink-line); }
.post-card .thumb{ height:160px; background:var(--pink); display:flex; align-items:center; justify-content:center; overflow:hidden; }
.post-card .thumb img{ width:100%; height:100%; object-fit:cover; }
.post-card .body{ padding:20px; }
.post-card .date{ color:var(--pink-deep); font-weight:700; font-size:0.85rem; margin-bottom:6px; display:block; }

/* ---- Inline photo blocks ---- */
.photo-row{ display:grid; grid-template-columns:1fr 1fr; gap:24px; align-items:center; margin-top:32px; }
@media (max-width:760px){ .photo-row{ grid-template-columns:1fr; } }
.photo-row img{ border-radius:18px; border:5px solid #fff; box-shadow:0 6px 0 var(--pink-deep); width:100%; object-fit:cover; aspect-ratio:4/3; }
.photo-row p{ margin:0; }

/* ---- Form ---- */
.form-box{ background:#fff; border:1px solid var(--pink-line); border-radius:18px; padding:32px; max-width:640px; }
.form-row{ margin-bottom:18px; }
.form-row label{ display:block; font-weight:700; margin-bottom:6px; color:var(--forest); font-size:0.95rem; }
.form-row input, .form-row select, .form-row textarea{
  width:100%; padding:12px 14px; border:1.5px solid var(--pink-line); border-radius:10px;
  font-family:'Quicksand',sans-serif; font-size:1rem; background:var(--cream); color:var(--ink);
}
.form-row textarea{ min-height:110px; resize:vertical; }
.form-note{ font-size:0.88rem; color:var(--muted); font-style:italic; margin-top:14px; }

/* ---- Footer ---- */
footer{ background:var(--forest-dark); color:#F3E6EC; padding:32px 0; }
footer .wrap{ display:flex; justify-content:space-between; flex-wrap:wrap; gap:16px; align-items:center; }
footer a{ color:#F3E6EC; text-decoration:none; margin-left:18px; font-size:0.92rem; }
footer a:hover{ text-decoration:underline; }
footer .fine{ color:#CFE0D4; font-size:0.85rem; }
