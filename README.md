<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DesignThink — One Idea Can Change The Future</title>
<meta name="description" content="An immersive Design Thinking platform — transform any real-world problem through all 5 stages into a human-centred innovation roadmap. One idea can change the future.">
<meta property="og:title" content="DesignThink — One Idea Can Change The Future">
<meta property="og:description" content="Enter any real-world challenge. Watch Design Thinking transform it through Empathise, Define, Ideate, Prototype and Test into an actionable innovation roadmap.">
<meta property="og:type" content="website">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="DesignThink — One Idea Can Change The Future">
<meta name="twitter:description" content="Transform any problem through Design Thinking. AI-powered. Human-centred. Built for innovators.">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#080810;--surface:#0f0f1c;--surface2:#171724;
  --border:rgba(255,255,255,0.09);--border2:rgba(255,255,255,0.15);
  --text:#f0ede8;--muted:rgba(240,237,232,0.55);--muted2:rgba(240,237,232,0.30);
  --orange:#e8521a;--orange2:#e07838;--blue:#2d6fd4;--green:#0db86a;
  --purple:#8b42d4;--yellow:#d4a017;--pink:#c45a9a;--teal:#0f9688;--amber:#f59e0b;
}
html{scroll-behavior:smooth;overflow-x:hidden}
body{font-family:'Plus Jakarta Sans',sans-serif;background:var(--bg);color:var(--text);overflow-x:hidden}
#cur,#cur-ring,#cur-label{display:none}
@media(pointer:fine){body{cursor:none}#cur{display:block}#cur-ring{display:block}#cur-label{display:block}}

/* CURSOR */
#cur{position:fixed;width:10px;height:10px;background:var(--orange);border-radius:50%;pointer-events:none;z-index:99999;transform:translate(-50%,-50%);will-change:transform;transition:width .3s,height .3s,background .3s,border-radius .3s,opacity .3s}
#cur-ring{position:fixed;width:36px;height:36px;border:1.5px solid rgba(255,92,26,.5);border-radius:50%;pointer-events:none;z-index:99998;transform:translate(-50%,-50%);will-change:transform;transition:width .4s,height .4s,border-color .3s,opacity .3s}
#cur-label{position:fixed;pointer-events:none;z-index:99997;font-size:.65rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--orange);opacity:0;transform:translate(-50%,-50%);white-space:nowrap;transition:opacity .3s}
body.hovering-card #cur{width:60px;height:60px;background:rgba(255,92,26,.15);border-radius:8px}
body.hovering-card #cur-ring{width:80px;height:80px;opacity:.3}
body.hovering-card #cur-label{opacity:1}

/* LOADER */
#loader{position:fixed;inset:0;z-index:9999;background:var(--bg);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:2rem;transition:opacity .8s,transform .8s}
.ld-logo{font-family:'Bebas Neue',sans-serif;font-size:clamp(3rem,8vw,6rem);letter-spacing:.08em;overflow:hidden}
.ld-logo span{display:inline-block;animation:ldSlide .8s cubic-bezier(.76,0,.24,1) both}
.ld-logo span:nth-child(1){animation-delay:.1s}.ld-logo span:nth-child(2){animation-delay:.18s}
.ld-logo span:nth-child(3){animation-delay:.26s}.ld-logo span:nth-child(4){animation-delay:.34s}
.ld-logo span:nth-child(5){animation-delay:.42s}.ld-logo span:nth-child(6){animation-delay:.5s}
.ld-logo span:nth-child(7){animation-delay:.58s}.ld-logo span:nth-child(8){animation-delay:.66s}
.ld-logo span:nth-child(9){animation-delay:.74s}.ld-logo span:nth-child(10){animation-delay:.82s}
.ld-logo span:nth-child(11){animation-delay:.9s}
@keyframes ldSlide{from{transform:translateY(100%);opacity:0}to{transform:translateY(0);opacity:1}}
.ld-bar-wrap{width:280px;height:1.5px;background:rgba(255,255,255,.08)}
.ld-bar-fill{height:100%;background:var(--orange);animation:ldFill 2s ease forwards .5s;width:0}
@keyframes ldFill{to{width:100%}}
.ld-pct{font-size:.7rem;letter-spacing:.15em;text-transform:uppercase;color:var(--muted)}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;transition:padding .4s,background .4s}
nav.tall{padding:1.4rem 4rem}
nav.short{padding:.8rem 4rem;background:rgba(8,8,16,.92)}
.nav-inner{display:flex;align-items:center;justify-content:space-between;backdrop-filter:blur(24px);border-bottom:1px solid var(--border)}
.nav-logo{font-family:'Bebas Neue',sans-serif;font-size:1.8rem;letter-spacing:.1em;color:var(--orange);text-decoration:none;transition:font-size .4s}
nav.short .nav-logo{font-size:1.4rem}
.nav-links{display:flex;gap:3rem;list-style:none;position:relative}
.nav-pill{position:absolute;bottom:-1px;height:2px;background:var(--orange);border-radius:2px;transition:left .35s cubic-bezier(.76,0,.24,1),width .35s cubic-bezier(.76,0,.24,1);pointer-events:none}
.nav-links a{font-size:.75rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;text-decoration:none;color:var(--muted);transition:color .2s;padding:.3rem 0;cursor:none}
.nav-links a:hover,.nav-links a.active{color:var(--text)}
.nav-cta{background:var(--orange);color:#fff;font-size:.75rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;padding:10px 22px;border-radius:5px;border:none;cursor:none;text-decoration:none;transition:background .2s,transform .2s}
.nav-cta:hover{background:var(--orange2);transform:translateY(-1px)}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:none;z-index:201}
.hamburger span{width:24px;height:1.5px;background:var(--text);transition:all .3s}
.mob-menu{display:none;position:fixed;inset:0;background:var(--bg);z-index:210;flex-direction:column;align-items:center;justify-content:center;gap:3rem}
.mob-menu.open{display:flex}
.mob-menu a{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.5rem,8vw,5rem);letter-spacing:.05em;color:var(--text);text-decoration:none;opacity:0;transform:translateY(40px);transition:opacity .4s,transform .4s,color .2s}
.mob-menu.open a{opacity:1;transform:translateY(0)}
.mob-menu.open a:nth-child(1){transition-delay:.1s}
.mob-menu.open a:nth-child(2){transition-delay:.18s}
.mob-menu.open a:nth-child(3){transition-delay:.26s}
.mob-menu.open a:nth-child(4){transition-delay:.34s}
.mob-menu.open a:nth-child(5){transition-delay:.42s}
.mob-close{position:absolute;top:2rem;right:2rem;font-size:1.5rem;cursor:none;color:var(--muted)}

/* HERO */
.hero{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:10rem 2rem 6rem;position:relative;overflow:hidden}
#webgl-canvas{position:absolute;inset:0;z-index:0}
.hero-ghost{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-family:'Bebas Neue',sans-serif;font-size:clamp(8rem,22vw,20rem);letter-spacing:.05em;color:var(--text);opacity:.025;pointer-events:none;z-index:1;white-space:nowrap;will-change:transform}
.hero-content{position:relative;z-index:3;max-width:1100px}
.hero-tag{display:inline-flex;align-items:center;gap:10px;padding:8px 20px;border:1px solid var(--border2);border-radius:100px;font-size:.7rem;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);margin-bottom:2.5rem;backdrop-filter:blur(12px);background:rgba(255,255,255,.03);opacity:0;transform:translateY(-20px)}
.hero-tag .dot{width:7px;height:7px;border-radius:50%;background:var(--green);box-shadow:0 0 10px var(--green);animation:gPulse 2s infinite}
@keyframes gPulse{0%,100%{box-shadow:0 0 4px var(--green)}50%{box-shadow:0 0 10px var(--green)}}
.hero-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(4.5rem,13vw,12rem);line-height:.88;letter-spacing:.02em;margin-bottom:2rem}
.hero-title .t1{display:block;color:var(--text);overflow:hidden}
.hero-title .t2{display:block;-webkit-text-stroke:2px var(--orange);color:transparent;overflow:hidden}
.hero-title .t3{display:block;background:linear-gradient(135deg,var(--orange),var(--orange2),var(--yellow));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;overflow:hidden}
.hero-sub{font-size:clamp(.95rem,1.4vw,1.1rem);font-weight:300;line-height:1.85;color:var(--muted);max-width:560px;margin:0 auto 3rem;opacity:0}
.hero-btns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;opacity:0}
.btn-fire{background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;font-size:.85rem;font-weight:700;padding:14px 32px;border-radius:7px;border:none;cursor:none;text-decoration:none;display:inline-flex;align-items:center;gap:10px;transition:transform .25s,box-shadow .25s;letter-spacing:.03em}
.btn-fire:hover{transform:translateY(-3px);box-shadow:0 8px 24px rgba(232,82,26,.25)}
.btn-ghost{background:transparent;color:var(--text);font-size:.85rem;font-weight:600;padding:14px 32px;border-radius:7px;border:1.5px solid var(--border2);cursor:none;text-decoration:none;display:inline-flex;align-items:center;gap:10px;transition:border-color .2s,background .2s}
.btn-ghost:hover{border-color:rgba(255,255,255,.3);background:rgba(255,255,255,.04)}
.hero-counter{position:absolute;bottom:3rem;right:4rem;z-index:3;text-align:right;opacity:0}
.hc-num{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.5rem,5vw,4rem);color:var(--orange);line-height:1;display:block}
.hc-label{font-size:.68rem;letter-spacing:.12em;text-transform:uppercase;color:var(--muted)}
.hero-scroll{position:absolute;bottom:3rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;z-index:3;opacity:0}
.hero-scroll span{font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;color:var(--muted2)}
.scroll-line{width:1px;height:48px;background:linear-gradient(to bottom,var(--orange),transparent);animation:sLine 2.2s ease-in-out infinite}
@keyframes sLine{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform:scaleY(1);transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

/* GLASSMORPHISM FLOATS */
.hero-float{position:absolute;padding:12px 18px;border-radius:12px;border:1px solid rgba(255,255,255,.12);background:rgba(255,255,255,.06);backdrop-filter:blur(14px);font-size:.75rem;font-weight:600;color:var(--text);pointer-events:none;z-index:3;opacity:0;white-space:nowrap}
.hf1{top:22%;left:4%}.hf2{top:30%;right:4%}.hf3{bottom:28%;left:6%}.hf4{bottom:22%;right:5%}

/* HORIZONTAL STAGES SCROLL */
#stages-scroll{height:500vh;position:relative}
#stages-sticky{position:sticky;top:0;height:100vh;overflow:hidden;display:flex;align-items:stretch}
.stages-track{display:flex;width:500vw;height:100%}
.stage-slide{width:100vw;flex-shrink:0;display:grid;grid-template-columns:1fr 1fr;height:100%;position:relative;overflow:hidden}
.stage-slide-bg{position:absolute;inset:0;font-family:'Bebas Neue',sans-serif;font-size:clamp(12rem,28vw,26rem);letter-spacing:.02em;color:rgba(255,255,255,.025);display:flex;align-items:center;justify-content:flex-end;padding-right:2rem;pointer-events:none;z-index:0;line-height:.85}
.stage-img-side{overflow:hidden;position:relative;z-index:1}
.stage-img-side img{width:100%;height:100%;object-fit:cover;filter:saturate(.65) brightness(.7);transition:transform .6s}
.stage-img-overlay{position:absolute;inset:0}
.stage-content-side{padding:clamp(2rem,4vw,5rem);display:flex;flex-direction:column;justify-content:center;background:var(--surface);position:relative;z-index:1}
.ss-num{font-family:'Bebas Neue',sans-serif;font-size:.85rem;letter-spacing:.2em;margin-bottom:1rem}
.ss-name{font-family:'Bebas Neue',sans-serif;font-size:clamp(3rem,6vw,5.5rem);line-height:.9;margin-bottom:1.5rem}
.ss-desc{font-size:clamp(.82rem,1.1vw,.95rem);line-height:1.85;color:var(--muted);margin-bottom:2rem;max-width:460px}
.ss-tools{display:flex;flex-wrap:wrap;gap:8px}
.ss-tool{font-size:.7rem;padding:5px 13px;border-radius:4px}
.ss-quote{margin-top:2rem;padding:1.2rem 1.5rem;border-left:2px solid;font-family:'Instrument Serif',serif;font-style:italic;font-size:clamp(.88rem,1.1vw,1rem);line-height:1.7;color:var(--muted)}
.stages-progress{position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);display:flex;gap:12px;z-index:10}
.sp-dot{width:8px;height:8px;border-radius:50%;background:rgba(255,255,255,.2);transition:all .3s;cursor:none}
.sp-dot.active{background:var(--orange);width:24px;border-radius:4px}

/* SECTION COMMON */
section{padding:clamp(4rem,8vw,8rem) clamp(1.5rem,5vw,5rem);position:relative;overflow:hidden}
.sec-eyebrow{font-size:.68rem;font-weight:700;letter-spacing:.2em;text-transform:uppercase;color:var(--orange);margin-bottom:1rem;display:flex;align-items:center;gap:12px}
.sec-eyebrow::before{content:'';width:24px;height:1.5px;background:var(--orange)}
.sec-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.2rem,5vw,4.5rem);letter-spacing:.02em;line-height:.92;margin-bottom:1.2rem}
.sec-desc{font-size:clamp(.88rem,1.1vw,1rem);font-weight:300;line-height:1.85;color:var(--muted);max-width:560px}

/* PROBLEM LAB */
#lab{background:var(--bg);padding:0;min-height:100vh;display:flex;flex-direction:column;justify-content:center}
.lab-header{padding:clamp(3rem,6vw,5rem) clamp(1.5rem,5vw,5rem) 2rem}
.lab-split{display:grid;grid-template-columns:1fr 1fr;flex:1;min-height:70vh}
.lab-left{background:var(--surface);padding:clamp(2rem,4vw,4rem);display:flex;flex-direction:column;border-right:1px solid var(--border)}
.lab-right{background:var(--surface2);padding:clamp(2rem,4vw,4rem);display:flex;flex-direction:column;position:relative;overflow:hidden}
.lab-lbl{font-size:.67rem;font-weight:700;letter-spacing:.18em;text-transform:uppercase;color:var(--orange);margin-bottom:.9rem;display:flex;align-items:center;gap:10px}
.lab-lbl::before{content:'';width:18px;height:1.5px;background:var(--orange)}
.lab-ta-wrap{position:relative;flex:0 0 auto}
.lab-ta{width:100%;min-height:180px;background:rgba(255,255,255,.03);border:1.5px solid var(--border2);border-radius:10px;padding:1.2rem 1.5rem;font-family:'Plus Jakarta Sans',sans-serif;font-size:.92rem;color:var(--text);resize:vertical;line-height:1.75;outline:none;transition:border-color .3s;cursor:text}
.lab-ta:focus{border-color:var(--orange)}
.lab-ta::placeholder{color:var(--muted2)}
.scan-line{position:absolute;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,rgba(255,92,26,.6),transparent);top:0;transform:translateY(-4px);opacity:0;pointer-events:none;border-radius:10px}
.lab-ta-wrap.scanning .scan-line{opacity:1;animation:scanAnim 1.5s linear infinite}
@keyframes scanAnim{from{top:0}to{top:100%}}
.lab-chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:1.2rem}
.lab-chip{font-size:.72rem;padding:6px 14px;border-radius:100px;border:1px solid var(--border2);color:var(--muted);cursor:none;transition:all .25s;background:transparent;font-family:'Plus Jakarta Sans',sans-serif}
.lab-chip:hover{border-color:var(--orange);color:var(--orange);background:rgba(255,92,26,.06)}
.lab-chip.sel{border-color:var(--orange);color:var(--orange)}
.lab-go{margin-top:1.5rem;width:100%;background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;font-family:'Plus Jakarta Sans',sans-serif;font-size:.9rem;font-weight:700;padding:14px;border-radius:10px;border:none;cursor:none;display:flex;align-items:center;justify-content:center;gap:12px;transition:transform .2s,box-shadow .2s;letter-spacing:.03em;position:relative;overflow:hidden}
.lab-go:not(:disabled):hover{transform:translateY(-2px);box-shadow:0 8px 20px rgba(232,82,26,.2)}
.lab-go:disabled{opacity:.55}
.lab-go .shim{position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,.15),transparent);transform:translateX(-200%);animation:shimA 2.5s infinite}
@keyframes shimA{to{transform:translateX(200%)}}
.lab-actions{display:flex;gap:8px;margin-top:1rem}
.lab-act-btn{flex:1;padding:9px;border-radius:7px;border:1px solid var(--border2);background:transparent;color:var(--muted);font-family:'Plus Jakarta Sans',sans-serif;font-size:.75rem;font-weight:600;cursor:none;transition:all .2s}
.lab-act-btn:hover{border-color:rgba(255,255,255,.25);color:var(--text);background:rgba(255,255,255,.04)}

/* OUTPUT */
.lab-out-header{display:flex;align-items:center;gap:10px;margin-bottom:1.5rem;flex-shrink:0}
.out-indicator{width:8px;height:8px;border-radius:50%;background:var(--green);box-shadow:0 0 4px var(--green);animation:gPulse 2s infinite}
.out-status{font-size:.72rem;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);font-weight:600}
.lab-placeholder{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1.5rem;text-align:center;position:relative}
.pl-orb{width:100px;height:100px;border-radius:50%;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:2rem;position:relative;animation:plSpin 8s linear infinite}
.pl-orb::before{content:'';position:absolute;width:75px;height:75px;border-radius:50%;border:1px dashed rgba(255,92,26,.25);animation:plSpin 5s linear infinite reverse}
.pl-orb::after{content:'';position:absolute;width:50px;height:50px;border-radius:50%;border:1px solid rgba(255,92,26,.1);animation:plSpin 3s linear infinite}
@keyframes plSpin{to{transform:rotate(360deg)}}
.pl-text{font-size:.85rem;color:var(--muted2);line-height:1.7}
.lab-output{flex:1;overflow-y:auto;display:none;scrollbar-width:thin;scrollbar-color:var(--border) transparent}
.lab-output::-webkit-scrollbar{width:3px}
.lab-output::-webkit-scrollbar-thumb{background:var(--border2);border-radius:3px}

/* DT BLOCKS */
.dt-block{border-radius:12px;padding:1.4rem;margin-bottom:1rem;transform:translateX(30px);opacity:0;transition:transform .5s cubic-bezier(.34,1.56,.64,1),opacity .4s}
.dt-block.in{transform:translateX(0);opacity:1}
.dt-block.refined{background:rgba(16,217,124,.06);border:1px solid rgba(16,217,124,.2)}
.dt-block.empathise{background:rgba(168,85,247,.06);border:1px solid rgba(168,85,247,.2)}
.dt-block.define{background:rgba(59,130,246,.06);border:1px solid rgba(59,130,246,.2)}
.dt-block.ideate{background:rgba(251,191,36,.06);border:1px solid rgba(251,191,36,.2)}
.dt-block.prototype{background:rgba(255,92,26,.06);border:1px solid rgba(255,92,26,.2)}
.dt-block.test{background:rgba(16,217,124,.06);border:1px solid rgba(16,217,124,.2)}
.dt-blabel{font-size:.63rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;margin-bottom:.7rem}
.dt-block.refined .dt-blabel{color:var(--green)}
.dt-block.empathise .dt-blabel{color:var(--purple)}
.dt-block.define .dt-blabel{color:var(--blue)}
.dt-block.ideate .dt-blabel{color:var(--yellow)}
.dt-block.prototype .dt-blabel{color:var(--orange2)}
.dt-block.test .dt-blabel{color:var(--green)}
.dt-bcontent{font-size:.83rem;line-height:1.8;color:rgba(240,237,232,.78)}

/* FRAMEWORKS */
#frameworks{background:var(--surface)}
.fw-header{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:end;margin-bottom:3.5rem}
.fw-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5px;background:var(--border);border:1px solid var(--border);border-radius:18px;overflow:hidden}
.fw-card{background:var(--surface2);overflow:hidden;cursor:none;transition:background .3s}
.fw-card:hover{background:var(--bg)}
.fw-img{height:190px;overflow:hidden;position:relative}
.fw-img img{width:100%;height:100%;object-fit:cover;transition:transform .6s,filter .4s;filter:saturate(.6) brightness(.75)}
.fw-card:hover .fw-img img{transform:scale(1.06);filter:saturate(.9) brightness(.85)}
.fw-img-ov{position:absolute;inset:0;background:linear-gradient(to bottom,transparent 40%,var(--surface2) 100%)}
.fw-body{padding:1.6rem}
.fw-num{font-size:.65rem;font-weight:700;letter-spacing:.15em;color:var(--orange);margin-bottom:.5rem;display:flex;align-items:center;gap:8px;text-transform:uppercase}
.fw-num::after{content:'';flex:1;height:1px;background:rgba(255,92,26,.2)}
.fw-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:1rem;font-weight:700;margin-bottom:.55rem;line-height:1.3}
.fw-desc{font-size:.8rem;line-height:1.72;color:var(--muted);margin-bottom:.9rem}
.fw-tags{display:flex;gap:6px;flex-wrap:wrap}
.fw-tag{font-size:.66rem;padding:3px 9px;border-radius:4px;background:rgba(255,255,255,.05);border:1px solid var(--border2);color:var(--muted);transition:all .25s}
.fw-card:hover .fw-tag{border-color:rgba(255,92,26,.25);color:var(--orange2)}

/* CANVAS */
#canvas-section{background:var(--bg)}
.canvas-hdr{display:grid;grid-template-columns:1fr auto;gap:4rem;align-items:end;margin-bottom:3.5rem}
.canvas-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:2px;background:var(--border);border:1px solid var(--border);border-radius:18px;overflow:hidden}
.c-cell{padding:1.8rem 1.6rem;background:var(--surface);cursor:none;transition:background .3s;position:relative;overflow:hidden}
.c-cell::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;opacity:0;transition:opacity .3s}
.c-cell:hover{background:var(--surface2)}.c-cell:hover::after{opacity:1}
.c-cell.span2{grid-column:span 2}
.c-cell.cp::after{background:var(--purple)}.c-cell.cb::after{background:var(--blue)}
.c-cell.co::after{background:var(--orange)}.c-cell.cg::after{background:var(--green)}
.c-cell.cy::after{background:var(--yellow)}.c-cell.cpk::after{background:var(--pink)}
.c-ico{font-size:1.4rem;margin-bottom:.9rem}
.c-lbl{font-size:.63rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;margin-bottom:.55rem}
.c-cell.cp .c-lbl{color:var(--purple)}.c-cell.cb .c-lbl{color:var(--blue)}
.c-cell.co .c-lbl{color:var(--orange)}.c-cell.cg .c-lbl{color:var(--green)}
.c-cell.cy .c-lbl{color:var(--yellow)}.c-cell.cpk .c-lbl{color:var(--pink)}
.c-ttl{font-size:.92rem;font-weight:700;margin-bottom:.45rem}
.c-dsc{font-size:.76rem;line-height:1.65;color:var(--muted)}

/* CASE STUDIES BENTO */
#cases{background:var(--surface)}
.cases-hdr{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:end;margin-bottom:3rem}
.bento{display:grid;grid-template-columns:repeat(3,1fr);grid-template-rows:auto auto;gap:2px;background:var(--border);border:1px solid var(--border);border-radius:18px;overflow:hidden}
.bcase{overflow:hidden;cursor:none;position:relative;transition:transform .3s,box-shadow .3s}
.bcase:hover{transform:translateY(-6px);box-shadow:0 20px 60px rgba(0,0,0,.5);z-index:2}
.bcase.big{grid-column:span 2;grid-row:span 2}
.bcase-img{width:100%;object-fit:cover;display:block;transition:transform .6s,filter .4s;filter:saturate(.55) brightness(.7)}
.bcase.big .bcase-img{height:520px}
.bcase:not(.big) .bcase-img{height:260px}
.bcase:hover .bcase-img{transform:scale(1.04);filter:saturate(.85) brightness(.8)}
.bcase-ov{position:absolute;inset:0;transition:opacity .3s}
.bcase-content{position:absolute;bottom:0;left:0;right:0;padding:1.8rem}
.bcase-tag{display:inline-flex;align-items:center;gap:6px;font-size:.62rem;font-weight:700;letter-spacing:.12em;text-transform:uppercase;padding:4px 12px;border-radius:100px;margin-bottom:.7rem}
.bcase-slide{position:absolute;bottom:0;left:0;right:0;padding:.8rem 1.8rem;display:flex;align-items:center;justify-content:space-between;transform:translateY(100%);transition:transform .3s cubic-bezier(.34,1.56,.64,1);background:linear-gradient(to top,rgba(4,4,10,.95),transparent)}
.bcase:hover .bcase-slide{transform:translateY(0)}
.bcase-slide span{font-size:.75rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--orange)}
.bcase-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:clamp(.95rem,1.3vw,1.1rem);font-weight:800;line-height:1.3;margin-bottom:.5rem}
.bcase.big .bcase-title{font-size:clamp(1.1rem,1.6vw,1.4rem)}
.bcase-desc{font-size:.78rem;line-height:1.65;color:rgba(240,237,232,.6);margin-bottom:.9rem}
.bcase-stats{display:flex;gap:1.5rem;flex-wrap:wrap}
.bcs-num{font-family:'Bebas Neue',sans-serif;font-size:1.3rem;color:var(--orange);display:block;line-height:1}
.bcs-lbl{font-size:.62rem;color:rgba(240,237,232,.4);letter-spacing:.07em}

/* PROCESS */
#process{background:var(--bg)}
.process-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:0;margin-top:3.5rem;position:relative}
.process-grid::before{content:'';position:absolute;top:48px;left:10%;right:10%;height:1px;background:linear-gradient(90deg,transparent,var(--orange),var(--orange2),var(--orange),transparent);animation:trkGlow 3s ease-in-out infinite}
@keyframes trkGlow{0%,100%{opacity:.25}50%{opacity:.9}}
.pstep{text-align:center;padding:2.5rem 1.2rem;cursor:none;transition:all .3s}
.pstep:hover{background:rgba(255,92,26,.04)}
.pstep-n{font-family:'Bebas Neue',sans-serif;font-size:.72rem;letter-spacing:.18em;color:var(--orange);margin-bottom:.6rem}
.pstep-b{width:56px;height:56px;border-radius:50%;background:var(--surface);border:1px solid var(--border2);display:flex;align-items:center;justify-content:center;margin:0 auto 1.1rem;font-size:1.4rem;transition:all .35s;position:relative;z-index:2}
.pstep:hover .pstep-b,.pstep.act .pstep-b{background:linear-gradient(135deg,var(--orange),var(--orange2));border-color:var(--orange);box-shadow:0 0 16px rgba(232,82,26,.25);transform:scale(1.15)}
.pstep-t{font-weight:700;font-size:.88rem;margin-bottom:.35rem;transition:color .3s}
.pstep:hover .pstep-t,.pstep.act .pstep-t{color:var(--orange)}
.pstep-d{font-size:.73rem;line-height:1.6;color:var(--muted)}

/* QUIZ */
#quiz{background:var(--surface)}
.quiz-inner{max-width:680px;margin:0 auto;margin-top:3.5rem}
.qpbar{height:2px;background:rgba(255,255,255,.08);border-radius:2px;margin-bottom:3rem;overflow:hidden}
.qpfill{height:100%;background:linear-gradient(90deg,var(--orange),var(--orange2));border-radius:2px;transition:width .4s ease}
.qnum{font-size:.7rem;letter-spacing:.15em;text-transform:uppercase;color:var(--orange);font-weight:700;display:block;margin-bottom:.9rem}
.qtext{font-size:clamp(1rem,1.6vw,1.18rem);font-weight:700;line-height:1.5;margin-bottom:2rem}
.qopts{display:grid;gap:.8rem}
.qopt{background:rgba(255,255,255,.03);border:1.5px solid var(--border);border-radius:11px;padding:1rem 1.4rem;font-size:.87rem;cursor:none;transition:all .2s;text-align:left;color:var(--text);font-family:'Plus Jakarta Sans',sans-serif;display:flex;align-items:center;gap:12px}
.qopt::before{content:'';width:18px;height:18px;border-radius:50%;border:2px solid var(--border2);flex-shrink:0;transition:all .2s}
.qopt:hover:not(:disabled){border-color:var(--orange2);background:rgba(255,92,26,.06)}
.qopt:hover:not(:disabled)::before{border-color:var(--orange)}
.qopt.correct{border-color:var(--green);background:rgba(16,217,124,.08)}
.qopt.correct::before{background:var(--green);border-color:var(--green)}
.qopt.wrong{border-color:#ef4444;background:rgba(239,68,68,.08)}
.qopt.wrong::before{background:#ef4444;border-color:#ef4444}
.qnav{margin-top:1.5rem;display:flex;justify-content:flex-end}
.qres{text-align:center;padding:4rem 2rem;display:none}
.qscore{font-family:'Bebas Neue',sans-serif;font-size:clamp(4rem,10vw,7rem);background:linear-gradient(135deg,var(--orange),var(--orange2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1}
.qmsg{font-size:1rem;color:var(--muted);margin-top:1rem;margin-bottom:2rem}

/* FOOTER */
footer{background:var(--bg);border-top:1px solid var(--border);padding:clamp(3rem,6vw,5rem) clamp(1.5rem,5vw,5rem) clamp(2rem,4vw,3rem);display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:clamp(2rem,4vw,4rem)}
.ft-brand{font-family:'Bebas Neue',sans-serif;font-size:2rem;color:var(--orange);letter-spacing:.1em;margin-bottom:1rem}
.ft-tagline{font-family:'Instrument Serif',serif;font-style:italic;font-size:1.05rem;color:var(--muted);line-height:1.6;margin-bottom:1rem}
.ft-desc{font-size:.82rem;line-height:1.75;color:var(--muted2)}
.ft-col h4{font-size:.65rem;font-weight:700;letter-spacing:.18em;text-transform:uppercase;color:var(--muted2);margin-bottom:1.2rem}
.ft-col a{display:block;font-size:.82rem;color:var(--muted);text-decoration:none;margin-bottom:.65rem;transition:color .2s}
.ft-col a:hover{color:var(--text)}
.ft-bottom{border-top:1px solid var(--border);padding-top:2rem;margin-top:2rem;display:flex;justify-content:space-between;font-size:.76rem;color:var(--muted2);grid-column:1/-1}

/* REVEAL */
.rev{opacity:0;transform:translateY(36px);transition:opacity .8s ease,transform .8s ease}
.rev.vis{opacity:1;transform:translateY(0)}

/* THINKING ANIM */
.think-dots{display:inline-flex;gap:5px;align-items:center}
.think-dots span{width:5px;height:5px;border-radius:50%;background:var(--orange);animation:tdot 1.4s infinite ease-in-out}
.think-dots span:nth-child(2){animation-delay:.2s}
.think-dots span:nth-child(3){animation-delay:.4s}
@keyframes tdot{0%,80%,100%{transform:scale(.5);opacity:.4}40%{transform:scale(1);opacity:1}}

/* RESPONSIVE */
@media(max-width:1024px){
  nav.tall,nav.short{padding:1rem 2rem}
  .fw-grid{grid-template-columns:1fr 1fr}
  .canvas-grid{grid-template-columns:1fr 1fr}
  .bento{grid-template-columns:1fr 1fr}
  .bcase.big{grid-column:span 2;grid-row:span 1}
  .bcase.big .bcase-img{height:300px}
  footer{grid-template-columns:1fr 1fr;gap:2rem}
}
@media(max-width:768px){
  .nav-links,.nav-cta{display:none}
  .hamburger{display:flex}
  .stage-slide{grid-template-columns:1fr}
  .stage-img-side{height:260px;min-height:200px}
  .lab-split{grid-template-columns:1fr}
  .fw-grid{grid-template-columns:1fr}
  .canvas-grid{grid-template-columns:1fr}
  .bento{grid-template-columns:1fr}
  .bcase.big{grid-column:span 1}
  .process-grid{grid-template-columns:1fr 1fr}
  footer{grid-template-columns:1fr}
  .fw-header,.cases-hdr,.canvas-hdr{grid-template-columns:1fr}
}

@media(prefers-reduced-motion:reduce){
  .hero-float{animation:none!important}
  .scroll-line{animation:none!important}
  .stages-ring{animation:none!important}
  .pl-orb{animation:none!important}
  .out-indicator{animation:none!important}
  .ld-logo span{animation:none!important}
}

.hero-philosophy{font-family:'Instrument Serif',serif;font-style:italic;font-size:clamp(1rem,2vw,1.4rem);color:var(--muted);margin-bottom:1.5rem;opacity:0;letter-spacing:.02em}

#stages-scroll{margin-bottom:0}
#lab{margin-top:0}
.section-bridge{display:flex;align-items:center;justify-content:center;gap:2rem;padding:3rem clamp(1.5rem,5vw,5rem);background:var(--bg)}
.bridge-line{flex:1;height:1px;background:linear-gradient(90deg,transparent,rgba(232,82,26,0.25),transparent)}
.bridge-label{font-size:.7rem;font-weight:700;letter-spacing:.2em;text-transform:uppercase;color:rgba(232,82,26,0.5)}

.hero-vignette{position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 40%,rgba(255,255,255,0.018) 0%,transparent 70%);pointer-events:none;z-index:2}

#frameworks,#cases,#quiz{border-top:1px solid var(--border)}
</style>
</head>
<body>
<!-- CURSOR -->
<div id="cur"></div>
<div id="cur-ring"></div>
<div id="cur-label">EXPLORE →</div>

<!-- LOADER -->
<div id="loader">
  <div class="ld-logo">
    <span>D</span><span>E</span><span>S</span><span>I</span><span>G</span><span>N</span><span style="display:inline-block;width:.4em"></span><span>T</span><span>H</span><span>I</span><span>N</span><span>K</span>
  </div>
  <div class="ld-bar-wrap"><div class="ld-bar-fill"></div></div>
  <p class="ld-pct" id="ldPct">Loading 0%</p>
</div>

<!-- MOBILE MENU -->
<div class="mob-menu" id="mobMenu">
  <span class="mob-close" onclick="closeMob()">✕</span>
  <a href="#home" onclick="closeMob()">Home</a>
  <a href="#stages-scroll" onclick="closeMob()">5 Stages</a>
  <a href="#lab" onclick="closeMob()">Problem Lab</a>
  <a href="#cases" onclick="closeMob()">Case Studies</a>
  <a href="#quiz" onclick="closeMob()">Quiz</a>
</div>

<!-- NAV -->
<nav id="mainNav" class="tall">
  <div class="nav-inner">
    <a href="#home" class="nav-logo">DT</a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#stages-scroll" class="nav-link">Stages</a></li>
      <li><a href="#lab" class="nav-link">Problem Lab</a></li>
      <li><a href="#frameworks" class="nav-link">Frameworks</a></li>
      <li><a href="#cases" class="nav-link">Cases</a></li>
      <li><a href="#quiz" class="nav-link">Quiz</a></li>
      <div class="nav-pill" id="navPill"></div>
    </ul>
    <a href="#lab" class="nav-cta">Try the Lab</a>
    <div class="hamburger" id="hamburger" onclick="openMob()">
      <span></span><span></span><span></span>
    </div>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <canvas id="webgl-canvas"></canvas>
  <div class="hero-vignette"></div>
  <div class="hero-ghost" id="heroGhost">INNOVATION</div>
  <div class="hero-float hf1" id="hf1">🔍 Empathise First</div>
  <div class="hero-float hf2" id="hf2">💡 100 Ideas/Hour</div>
  <div class="hero-float hf3" id="hf3">🚀 Prototype in 48hrs</div>
  <div class="hero-float hf4" id="hf4">✅ Test. Iterate. Launch.</div>
  <div class="hero-content">
    <div class="hero-tag" id="heroTag"><span class="dot"></span>Entrepreneurship & Innovation Management</div>
    <div class="hero-philosophy" id="heroPhil">One idea can change the future.</div>
    <h1 class="hero-title" id="heroTitle">
      <span class="t1" id="scramble1">REAL PROBLEMS</span>
      <span class="t2" id="scramble2">BOLD IDEAS</span>
      <span class="t3" id="scramble3">FUTURE BUILT.</span>
    </h1>
    <p class="hero-sub" id="heroSub">Enter any real-world challenge. Watch Design Thinking transform it — structured through all 5 stages into a human-centred innovation roadmap that actually works.</p>
    <div class="hero-btns" id="heroBtns">
      <a href="#lab" class="btn-fire">Enter the Problem Lab →</a>
      <a href="#stages-scroll" class="btn-ghost">Explore 5 Stages</a>
    </div>
  </div>
  <div class="hero-counter" id="heroCounter">
    <span class="hc-num" id="counterNum">0</span>
    <span class="hc-label">problems solved today</span>
  </div>
  <div class="hero-scroll" id="heroScroll">
    <span>Scroll to Explore</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- HORIZONTAL STAGES SCROLL -->
<div id="stages-scroll">
  <div id="stages-sticky">
    <div class="stages-track" id="stagesTrack">

      <!-- Stage 1: Empathise -->
      <div class="stage-slide" id="ss0">
        <div class="stage-slide-bg">EMPATHISE</div>
        <div class="stage-img-side">
          <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=900&q=80" alt="Empathise">
          <div class="stage-img-overlay" style="background:linear-gradient(135deg,rgba(168,85,247,.22),rgba(4,4,10,.5))"></div>
        </div>
        <div class="stage-content-side">
          <div class="ss-num" style="color:var(--purple)">01 / 05</div>
          <div class="ss-name" style="color:var(--purple)">Empathise</div>
          <p class="ss-desc">Step into your user's world. Observe without judgement. Listen beyond words. The goal is to uncover latent needs — the ones people can't articulate — through immersive research, shadowing and deep conversation.</p>
          <div class="ss-tools">
            <span class="ss-tool" style="background:rgba(168,85,247,.1);border:1px solid rgba(168,85,247,.25);color:#c084fc">User Interviews</span>
            <span class="ss-tool" style="background:rgba(168,85,247,.1);border:1px solid rgba(168,85,247,.25);color:#c084fc">Empathy Maps</span>
            <span class="ss-tool" style="background:rgba(168,85,247,.1);border:1px solid rgba(168,85,247,.25);color:#c084fc">Shadowing</span>
            <span class="ss-tool" style="background:rgba(168,85,247,.1);border:1px solid rgba(168,85,247,.25);color:#c084fc">Diary Studies</span>
          </div>
          <div class="ss-quote" style="border-color:var(--purple);background:rgba(168,85,247,.05)"><p>"You cannot solve a problem you don't truly understand. Empathy is not sympathy — it is living the problem."</p></div>
        </div>
      </div>

      <!-- Stage 2: Define -->
      <div class="stage-slide" id="ss1">
        <div class="stage-slide-bg">DEFINE</div>
        <div class="stage-content-side" style="order:-1">
          <div class="ss-num" style="color:var(--blue)">02 / 05</div>
          <div class="ss-name" style="color:var(--blue)">Define</div>
          <p class="ss-desc">Transform scattered observations into a razor-sharp problem statement — the Point of View (POV). A great POV captures the human need, the insight, and the context, framing it as an exciting challenge to solve.</p>
          <div class="ss-tools">
            <span class="ss-tool" style="background:rgba(59,130,246,.1);border:1px solid rgba(59,130,246,.25);color:#93c5fd">POV Statement</span>
            <span class="ss-tool" style="background:rgba(59,130,246,.1);border:1px solid rgba(59,130,246,.25);color:#93c5fd">How Might We</span>
            <span class="ss-tool" style="background:rgba(59,130,246,.1);border:1px solid rgba(59,130,246,.25);color:#93c5fd">Affinity Mapping</span>
            <span class="ss-tool" style="background:rgba(59,130,246,.1);border:1px solid rgba(59,130,246,.25);color:#93c5fd">5 Whys</span>
          </div>
          <div class="ss-quote" style="border-color:var(--blue);background:rgba(59,130,246,.05)"><p>"A problem well-defined is a problem half solved. The POV is your compass — it directs every decision downstream."</p></div>
        </div>
        <div class="stage-img-side">
          <img src="https://images.unsplash.com/photo-1542744173-8e7e53415bb0?w=900&q=80" alt="Define">
          <div class="stage-img-overlay" style="background:linear-gradient(135deg,rgba(59,130,246,.2),rgba(4,4,10,.5))"></div>
        </div>
      </div>

      <!-- Stage 3: Ideate -->
      <div class="stage-slide" id="ss2">
        <div class="stage-slide-bg">IDEATE</div>
        <div class="stage-img-side">
          <img src="https://images.unsplash.com/photo-1531538606174-0f90ff5dce83?w=900&q=80" alt="Ideate">
          <div class="stage-img-overlay" style="background:linear-gradient(135deg,rgba(251,191,36,.16),rgba(4,4,10,.5))"></div>
        </div>
        <div class="stage-content-side">
          <div class="ss-num" style="color:var(--yellow)">03 / 05</div>
          <div class="ss-name" style="color:var(--yellow)">Ideate</div>
          <p class="ss-desc">Diverge wildly before converging. Generate 100 ideas without judging any. Quantity is the strategy — the best solutions are born from collision of seemingly absurd concepts. Use structured techniques to unlock deep creativity.</p>
          <div class="ss-tools">
            <span class="ss-tool" style="background:rgba(251,191,36,.1);border:1px solid rgba(251,191,36,.25);color:#fde68a">Brainwriting 6-3-5</span>
            <span class="ss-tool" style="background:rgba(251,191,36,.1);border:1px solid rgba(251,191,36,.25);color:#fde68a">SCAMPER</span>
            <span class="ss-tool" style="background:rgba(251,191,36,.1);border:1px solid rgba(251,191,36,.25);color:#fde68a">Crazy 8s</span>
            <span class="ss-tool" style="background:rgba(251,191,36,.1);border:1px solid rgba(251,191,36,.25);color:#fde68a">Mind Mapping</span>
          </div>
          <div class="ss-quote" style="border-color:var(--yellow);background:rgba(251,191,36,.05)"><p>"Creativity is not a gift — it is a skill. And like all skills, it can be activated with the right technique."</p></div>
        </div>
      </div>

      <!-- Stage 4: Prototype -->
      <div class="stage-slide" id="ss3">
        <div class="stage-slide-bg">PROTOTYPE</div>
        <div class="stage-content-side" style="order:-1">
          <div class="ss-num" style="color:var(--orange)">04 / 05</div>
          <div class="ss-name" style="color:var(--orange)">Prototype</div>
          <p class="ss-desc">Make ideas tangible immediately. A prototype is anything that communicates your concept well enough to test — a sketch, cardboard model, role-play, or wireframe. Build fast. Learn faster. Fail cheaply on purpose.</p>
          <div class="ss-tools">
            <span class="ss-tool" style="background:rgba(255,92,26,.1);border:1px solid rgba(255,92,26,.25);color:#fdba74">Paper Prototypes</span>
            <span class="ss-tool" style="background:rgba(255,92,26,.1);border:1px solid rgba(255,92,26,.25);color:#fdba74">Wireframes</span>
            <span class="ss-tool" style="background:rgba(255,92,26,.1);border:1px solid rgba(255,92,26,.25);color:#fdba74">Storyboards</span>
            <span class="ss-tool" style="background:rgba(255,92,26,.1);border:1px solid rgba(255,92,26,.25);color:#fdba74">Wizard of Oz</span>
          </div>
          <div class="ss-quote" style="border-color:var(--orange);background:rgba(255,92,26,.05)"><p>"Prototype as if you know you're right. Test as if you know you're wrong. Both stances serve you equally."</p></div>
        </div>
        <div class="stage-img-side">
          <img src="https://images.unsplash.com/photo-1504639725590-34d0984388bd?w=900&q=80" alt="Prototype">
          <div class="stage-img-overlay" style="background:linear-gradient(135deg,rgba(255,92,26,.16),rgba(4,4,10,.5))"></div>
        </div>
      </div>

      <!-- Stage 5: Test -->
      <div class="stage-slide" id="ss4">
        <div class="stage-slide-bg">TEST</div>
        <div class="stage-img-side">
          <img src="https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?w=900&q=80" alt="Test">
          <div class="stage-img-overlay" style="background:linear-gradient(135deg,rgba(16,217,124,.16),rgba(4,4,10,.5))"></div>
        </div>
        <div class="stage-content-side">
          <div class="ss-num" style="color:var(--green)">05 / 05</div>
          <div class="ss-name" style="color:var(--green)">Test</div>
          <p class="ss-desc">Put your prototype in front of real users and watch silently. Do not explain — observe. Every confusion is data. Every delight is a signal. Testing often sends you back to Empathise. That is not failure. That is the process working.</p>
          <div class="ss-tools">
            <span class="ss-tool" style="background:rgba(16,217,124,.1);border:1px solid rgba(16,217,124,.25);color:#6ee7b7">Usability Testing</span>
            <span class="ss-tool" style="background:rgba(16,217,124,.1);border:1px solid rgba(16,217,124,.25);color:#6ee7b7">Think-Aloud</span>
            <span class="ss-tool" style="background:rgba(16,217,124,.1);border:1px solid rgba(16,217,124,.25);color:#6ee7b7">A/B Testing</span>
            <span class="ss-tool" style="background:rgba(16,217,124,.1);border:1px solid rgba(16,217,124,.25);color:#6ee7b7">Feedback Synthesis</span>
          </div>
          <div class="ss-quote" style="border-color:var(--green);background:rgba(16,217,124,.05)"><p>"The best data in the world is a real person trying to use your prototype. Nothing else compares."</p></div>
        </div>
      </div>

    </div><!-- /stages-track -->
    <div class="stages-progress" id="stagesProgress">
      <div class="sp-dot active" onclick="goToStage(0)"></div>
      <div class="sp-dot" onclick="goToStage(1)"></div>
      <div class="sp-dot" onclick="goToStage(2)"></div>
      <div class="sp-dot" onclick="goToStage(3)"></div>
      <div class="sp-dot" onclick="goToStage(4)"></div>
    </div>
  </div>
</div>

<div class="section-bridge">
  <div class="bridge-line"></div>
  <div class="bridge-label">↓ Apply It Now</div>
  <div class="bridge-line"></div>
</div>

<!-- PROBLEM LAB -->
<section id="lab">
  <div class="lab-header rev">
    <div class="sec-eyebrow">AI-Powered Problem Lab</div>
    <div class="sec-title">Transform Any Problem</div>
    <p class="sec-desc">Type any real-world challenge. The Design Thinking engine reframes your statement and maps it through all 5 stages — giving you a complete innovation roadmap.</p>
  </div>
  <div class="lab-split">
    <div class="lab-left">
      <div class="lab-lbl">Your Problem Statement</div>
      <div class="lab-ta-wrap" id="tawrap">
        <div class="scan-line" id="scanLine"></div>
        <textarea class="lab-ta" id="labTa" placeholder="Describe your real-world problem here... e.g. Students in rural schools cannot access quality science education because there are no labs, qualified teachers, or internet — which means they fall behind urban peers and lose career opportunities in STEM fields."></textarea>
      </div>
      <div class="lab-chips">
        <button class="lab-chip" onclick="fillEx(this)">Farmers losing crops to unpredictable weather</button>
        <button class="lab-chip" onclick="fillEx(this)">Urban youth unemployment in tier-2 cities</button>
        <button class="lab-chip" onclick="fillEx(this)">Hospital patients waiting hours for basic tests</button>
        <button class="lab-chip" onclick="fillEx(this)">Plastic waste in coastal fishing communities</button>
        <button class="lab-chip" onclick="fillEx(this)">Elderly people feeling isolated in cities</button>
      </div>
      <button class="lab-go" id="labGo" onclick="runLab()">
        <span class="shim"></span>
        <span>✦</span> Apply Design Thinking <span>→</span>
      </button>
      <div class="lab-actions">
        <button class="lab-act-btn" id="copyBtn" onclick="copyOutput()" style="display:none">⊕ Copy Output</button>
        <button class="lab-act-btn" id="resetBtn" onclick="resetLab()" style="display:none">↺ Start Over</button>
      </div>
    </div>
    <div class="lab-right">
      <div class="lab-out-header">
        <div class="out-indicator"></div>
        <span class="out-status" id="outStatus">Awaiting Problem Input</span>
      </div>
      <div class="lab-placeholder" id="labPH">
        <div class="pl-orb">🧠</div>
        <p class="pl-text">Enter your problem and hit<br><strong style="color:var(--orange)">Apply Design Thinking</strong><br>to receive your full 5-stage innovation roadmap</p>
      </div>
      <div class="lab-output" id="labOut"></div>
    </div>
  </div>
</section>

<!-- FRAMEWORKS -->
<section id="frameworks">
  <div class="fw-header">
    <div>
      <div class="sec-eyebrow rev">Innovation Toolbox</div>
      <div class="sec-title rev">Core Frameworks</div>
    </div>
    <p class="sec-desc rev">Proven methodologies that transform abstract thinking into structured, repeatable innovation action.</p>
  </div>
  <div class="fw-grid rev">
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1553028826-f4804a6dba3b?w=600&q=80" alt="Empathy Map"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">01 — Empathy Stage</div><div class="fw-title">Empathy Mapping</div><div class="fw-desc">Visualise what users say, think, do and feel simultaneously. Reveals contradictions between stated preferences and actual behaviour — where the real insights hide.</div><div class="fw-tags"><span class="fw-tag">Say</span><span class="fw-tag">Think</span><span class="fw-tag">Do</span><span class="fw-tag">Feel</span></div></div>
    </div>
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1611532736597-de2d4265fba3?w=600&q=80" alt="HMW"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">02 — Define Stage</div><div class="fw-title">How Might We (HMW)</div><div class="fw-desc">Reframe problems as open-ended opportunity questions that invite creativity without prescribing solutions. The bridge between problem and solution space.</div><div class="fw-tags"><span class="fw-tag">Reframe</span><span class="fw-tag">Opportunity</span><span class="fw-tag">Open-ended</span></div></div>
    </div>
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1531538606174-0f90ff5dce83?w=600&q=80" alt="Crazy 8s"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">03 — Ideation Stage</div><div class="fw-title">Crazy 8s Sprint</div><div class="fw-desc">Sketch 8 wildly different ideas in 8 minutes. Time pressure bypasses the inner critic and forces quantity — increasing the probability of a breakthrough concept.</div><div class="fw-tags"><span class="fw-tag">Speed</span><span class="fw-tag">Sketching</span><span class="fw-tag">8 min</span><span class="fw-tag">Diverge</span></div></div>
    </div>
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1586717799252-bd134ad00e26?w=600&q=80" alt="User Journey"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">04 — Empathy + Define</div><div class="fw-title">User Journey Map</div><div class="fw-desc">Chart every touchpoint of the user experience including emotions at each stage. Reveals pain points and moments of delight that traditional research misses entirely.</div><div class="fw-tags"><span class="fw-tag">Touchpoints</span><span class="fw-tag">Emotions</span><span class="fw-tag">Pain Points</span></div></div>
    </div>
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=600&q=80" alt="SCAMPER"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">05 — Ideation Stage</div><div class="fw-title">SCAMPER Technique</div><div class="fw-desc">Substitute, Combine, Adapt, Modify, Put to other uses, Eliminate, Reverse. A systematic checklist that forces 7 creative angles on any existing solution.</div><div class="fw-tags"><span class="fw-tag">Substitute</span><span class="fw-tag">Combine</span><span class="fw-tag">Adapt</span><span class="fw-tag">Eliminate</span></div></div>
    </div>
    <div class="fw-card">
      <div class="fw-img"><img src="https://images.unsplash.com/photo-1542744173-8e7e53415bb0?w=600&q=80" alt="BMC"><div class="fw-img-ov"></div></div>
      <div class="fw-body"><div class="fw-num">06 — Innovation Mgmt</div><div class="fw-title">Business Model Canvas</div><div class="fw-desc">Map how your innovation creates, delivers and captures value across 9 building blocks. The strategic bridge from validated solution to sustainable venture.</div><div class="fw-tags"><span class="fw-tag">Value Prop</span><span class="fw-tag">Channels</span><span class="fw-tag">Revenue</span><span class="fw-tag">Costs</span></div></div>
    </div>
  </div>
</section>

<!-- CANVAS -->
<section id="canvas-section">
  <div class="canvas-hdr">
    <div class="rev">
      <div class="sec-eyebrow">Strategic Tool</div>
      <div class="sec-title">Innovation Canvas</div>
      <p class="sec-desc">Map your venture across 8 critical innovation dimensions — the strategic backbone of entrepreneurial thinking.</p>
    </div>
    <div class="rev" style="text-align:right">
      <div style="font-family:'Bebas Neue',sans-serif;font-size:clamp(4rem,8vw,7rem);color:var(--orange);line-height:1;opacity:.2">8</div>
      <div style="font-size:.7rem;color:var(--muted);letter-spacing:.12em;text-transform:uppercase">Dimensions</div>
    </div>
  </div>
  <div class="canvas-grid rev">
    <div class="c-cell cp"><div class="c-ico">🎯</div><div class="c-lbl">Problem Space</div><div class="c-ttl">The Wicked Problem</div><p class="c-dsc">What deep systemic challenge are you tackling? Who suffers most and why can't they solve it themselves?</p></div>
    <div class="c-cell cb"><div class="c-ico">👤</div><div class="c-lbl">User Insight</div><div class="c-ttl">Who Feels the Pain</div><p class="c-dsc">Primary and secondary users. Their jobs-to-be-done, frustrations and aspirations beyond the obvious.</p></div>
    <div class="c-cell cg"><div class="c-ico">💡</div><div class="c-lbl">Innovation</div><div class="c-ttl">The Breakthrough</div><p class="c-dsc">What makes your solution 10× better? What new combination creates real, lasting change?</p></div>
    <div class="c-cell cy"><div class="c-ico">📊</div><div class="c-lbl">Impact</div><div class="c-ttl">Measurable Change</div><p class="c-dsc">Success in 1, 3 and 10 years. Lead and lag metrics that prove real-world transformation.</p></div>
    <div class="c-cell co span2"><div class="c-ico">⚡</div><div class="c-lbl">Value Proposition</div><div class="c-ttl">Why They Choose You</div><p class="c-dsc">The single most compelling, specific, believable reason your target user adopts your solution over every alternative — including doing nothing at all.</p></div>
    <div class="c-cell cpk"><div class="c-ico">💰</div><div class="c-lbl">Business Model</div><div class="c-ttl">How It Sustains</div><p class="c-dsc">Revenue streams, cost structure, key partnerships and the flywheel that makes this self-sustaining.</p></div>
    <div class="c-cell cb"><div class="c-ico">🌍</div><div class="c-lbl">Go To Market</div><div class="c-ttl">How You Reach Them</div><p class="c-dsc">Early adopter strategy, distribution channels, growth levers and the beachhead market.</p></div>
  </div>
</section>

<!-- CASE STUDIES BENTO -->
<section id="cases">
  <div class="cases-hdr">
    <div>
      <div class="sec-eyebrow rev">Real World Impact</div>
      <div class="sec-title rev">Design Thinking in Action</div>
    </div>
    <p class="sec-desc rev">Six transformative cases from India and the world — proof that human-centred process changes everything.</p>
  </div>
  <div class="bento rev">

    <div class="bcase big">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1572435555646-7ad9a149ad91?w=1400&q=80" alt="Jaipur Foot">
      <div class="bcase-ov" style="background:linear-gradient(135deg,rgba(245,158,11,.25) 0%,rgba(4,4,10,.85) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(245,158,11,.15);color:#fbbf24;border:1px solid rgba(245,158,11,.3)">🏆 Iconic Indian Innovation</div>
        <div class="bcase-title">Jaipur Foot — A $45 Prosthetic That Changed 1.3 Million Lives</div>
        <p class="bcase-desc">Deep empathy research with amputees in rural Rajasthan revealed Western prosthetics assumed sedentary indoor lifestyles. Indian users needed to walk barefoot on uneven terrain, sit cross-legged and cycle. Deep observation → redefinition → redesign. Anatomically precise, locally made, $45 — now in 26 countries.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">$45</span><span class="bcs-lbl">Cost</span></div>
          <div><span class="bcs-num">1.3M</span><span class="bcs-lbl">Lives Changed</span></div>
          <div><span class="bcs-num">26</span><span class="bcs-lbl">Countries</span></div>
          <div><span class="bcs-num">50yr</span><span class="bcs-lbl">Legacy</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span><span style="font-size:.65rem;color:var(--muted)">Jaipur Foot · India</span></div>
    </div>

    <div class="bcase">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1523961131990-5ea7c61b2107?w=800&q=80" alt="Airbnb">
      <div class="bcase-ov" style="background:linear-gradient(to top,rgba(255,92,26,.6) 0%,rgba(4,4,10,.3) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(255,92,26,.15);color:var(--orange2);border:1px solid rgba(255,92,26,.3)">🚀 Startup Turnaround</div>
        <div class="bcase-title">Airbnb — Empathy That Saved a $75B Company</div>
        <p class="bcase-desc">Founders flew to NYC, stayed with hosts, discovered: poor photos. One week of fieldwork. Revenue doubled.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">2×</span><span class="bcs-lbl">Revenue</span></div>
          <div><span class="bcs-num">$75B</span><span class="bcs-lbl">Today</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span></div>
    </div>

    <div class="bcase">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1598300042247-d088f8ab3a91?w=800&q=80" alt="M-Pesa">
      <div class="bcase-ov" style="background:linear-gradient(to top,rgba(20,184,166,.6) 0%,rgba(4,4,10,.3) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(20,184,166,.15);color:#2dd4bf;border:1px solid rgba(20,184,166,.3)">🌍 Social Innovation</div>
        <div class="bcase-title">M-Pesa — Mobile Money for the Unbanked</div>
        <p class="bcase-desc">Ethnographic research revealed airtime was already being traded as informal currency. Reframed into M-Pesa — $200B+ processed annually.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">$200B</span><span class="bcs-lbl">Annual Flow</span></div>
          <div><span class="bcs-num">50M</span><span class="bcs-lbl">Users</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span></div>
    </div>

    <div class="bcase">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1607748851687-ba9a10438621?w=800&q=80" alt="IDEO Cart">
      <div class="bcase-ov" style="background:linear-gradient(to top,rgba(168,85,247,.6) 0%,rgba(4,4,10,.3) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(168,85,247,.15);color:#c084fc;border:1px solid rgba(168,85,247,.3)">📐 Classic IDEO</div>
        <div class="bcase-title">IDEO's Shopping Cart — Full DT in 5 Days</div>
        <p class="bcase-desc">Full Design Thinking process executed live on ABC Nightline — 5 days, 7 prototypes, zero compromise.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">5</span><span class="bcs-lbl">Days</span></div>
          <div><span class="bcs-num">7</span><span class="bcs-lbl">Prototypes</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span></div>
    </div>

    <div class="bcase">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1574680178050-55c6a6a96e0a?w=800&q=80" alt="India Sanitation">
      <div class="bcase-ov" style="background:linear-gradient(to top,rgba(245,158,11,.6) 0%,rgba(4,4,10,.3) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(245,158,11,.15);color:var(--yellow);border:1px solid rgba(245,158,11,.3)">🇮🇳 India Scale</div>
        <div class="bcase-title">IDEO + Gates — Toilet Design for Rural India</div>
        <p class="bcase-desc">Months of ethnographic fieldwork → culturally appropriate designs communities actually used. Behaviour shift at population scale.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">600M</span><span class="bcs-lbl">Target Users</span></div>
          <div><span class="bcs-num">↑80%</span><span class="bcs-lbl">Adoption</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span></div>
    </div>

    <div class="bcase">
      <img class="bcase-img" src="https://images.unsplash.com/photo-1532634733-cae1395e440f?w=800&q=80" alt="Duolingo">
      <div class="bcase-ov" style="background:linear-gradient(to top,rgba(16,217,124,.6) 0%,rgba(4,4,10,.3) 60%)"></div>
      <div class="bcase-content">
        <div class="bcase-tag" style="background:rgba(16,217,124,.15);color:var(--green);border:1px solid rgba(16,217,124,.3)">🎓 EdTech</div>
        <div class="bcase-title">Duolingo — The Streak Feature Born from Testing</div>
        <p class="bcase-desc">User testing revealed drop-off from lost momentum, not lack of interest. Streak feature drove 5× retention. 500M users.</p>
        <div class="bcase-stats">
          <div><span class="bcs-num">500M</span><span class="bcs-lbl">Users</span></div>
          <div><span class="bcs-num">5×</span><span class="bcs-lbl">Retention</span></div>
        </div>
      </div>
      <div class="bcase-slide"><span>Read Case →</span></div>
    </div>

  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div class="sec-eyebrow rev">Learning Pathway</div>
  <div class="sec-title rev">Become a Design Thinker</div>
  <p class="sec-desc rev">Five progressive steps — from theory to validated real-world innovation.</p>
  <div class="process-grid rev">
    <div class="pstep act" onclick="actPS(this)"><div class="pstep-n">01</div><div class="pstep-b">📖</div><div class="pstep-t">Learn Theory</div><p class="pstep-d">Master the 5-stage framework, principles and mental models</p></div>
    <div class="pstep" onclick="actPS(this)"><div class="pstep-n">02</div><div class="pstep-b">👂</div><div class="pstep-t">Field Research</div><p class="pstep-d">Conduct 5 user interviews using empathy mapping techniques</p></div>
    <div class="pstep" onclick="actPS(this)"><div class="pstep-n">03</div><div class="pstep-b">🗺️</div><div class="pstep-t">Define POV</div><p class="pstep-d">Synthesise insights into a sharp Point of View statement</p></div>
    <div class="pstep" onclick="actPS(this)"><div class="pstep-n">04</div><div class="pstep-b">🌪️</div><div class="pstep-t">Ideate & Build</div><p class="pstep-d">Generate 50+ ideas, select top 3, build paper prototypes</p></div>
    <div class="pstep" onclick="actPS(this)"><div class="pstep-n">05</div><div class="pstep-b">🚀</div><div class="pstep-t">Test & Pitch</div><p class="pstep-d">Test with 5 users, iterate and present your validated solution</p></div>
  </div>
</section>

<!-- QUIZ -->
<section id="quiz">
  <div class="sec-eyebrow rev" style="justify-content:center">Test Your Knowledge</div>
  <div class="sec-title rev" style="text-align:center">Design Thinking Quiz</div>
  <div class="quiz-inner rev">
    <div class="qpbar"><div class="qpfill" id="qpf" style="width:0%"></div></div>
    <div id="qContent">
      <span class="qnum" id="qN"></span>
      <div class="qtext" id="qT"></div>
      <div class="qopts" id="qO"></div>
      <div class="qnav"><button class="btn-fire" id="qNext" onclick="nextQ()" style="display:none">Next →</button></div>
    </div>
    <div class="qres" id="qRes">
      <div class="qscore" id="qSc"></div>
      <p class="qmsg" id="qMsg"></p>
      <button class="btn-fire" onclick="resetQ()">Try Again ✦</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>
    <div class="ft-brand">DesignThink</div>
    <p class="ft-tagline">"One idea can change the future."</p>
    <p class="ft-desc">An immersive platform for teaching Entrepreneurship and Innovation Management through the Design Thinking framework — building the next generation of problem solvers.</p>
  </div>
  <div class="ft-col">
    <h4>Framework</h4>
    <a href="#stages-scroll">5 Stages</a>
    <a href="#frameworks">Toolbox</a>
    <a href="#canvas-section">Canvas</a>
  </div>
  <div class="ft-col">
    <h4>Explore</h4>
    <a href="#cases">Case Studies</a>
    <a href="#process">Pathway</a>
    <a href="#quiz">Quiz</a>
  </div>
  <div class="ft-col">
    <h4>Tools</h4>
    <a href="#lab">Problem Lab</a>
    <a href="#frameworks">Frameworks</a>
  </div>
  <div class="ft-bottom">
    <span>© 2026 DesignThink Platform — Built for Innovators</span>
    <span>Entrepreneurship & Innovation Management</span>
  </div>
</footer>
<script>
gsap.registerPlugin(ScrollTrigger);
const prefersReduced=window.matchMedia('(prefers-reduced-motion: reduce)').matches;

/* ============ LOADER ============ */
const pageStart=performance.now();
let ldVal=0;
const ldInterval=setInterval(()=>{ldVal=Math.min(ldVal+Math.floor(Math.random()*15)+5,99);document.getElementById('ldPct').textContent='Loading '+ldVal+'%'},120);
window.addEventListener('load',()=>{
  const elapsed=performance.now()-pageStart;
  const minDisplay=900;
  const remaining=Math.max(0,minDisplay-elapsed);
  clearInterval(ldInterval);
  document.getElementById('ldPct').textContent='Loading 100%';
  setTimeout(()=>{
    const l=document.getElementById('loader');
    l.style.opacity='0';l.style.transform='scale(1.04)';
    setTimeout(()=>l.style.display='none',800);
    initHero();
  },remaining);
});

/* ============ CUSTOM CURSOR ============ */
const curEl=document.getElementById('cur'),ringEl=document.getElementById('cur-ring'),lblEl=document.getElementById('cur-label');
let mx=0,my=0,rx=0,ry=0,lx=0,ly=0;
const interactiveEls=[];
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;curEl.style.left=mx+'px';curEl.style.top=my+'px';lblEl.style.left=mx+'px';lblEl.style.top=(my+30)+'px'});
(function animCursor(){
  rx+=(mx-rx)*.12;ry+=(my-ry)*.12;lx+=(mx-lx)*.08;ly+=(my-ly)*.08;
  ringEl.style.left=rx+'px';ringEl.style.top=ry+'px';
  requestAnimationFrame(animCursor);
})();

function addMagnet(sel,label){
  document.querySelectorAll(sel).forEach(el=>{
    el.addEventListener('mouseenter',()=>{
      document.body.classList.add('hovering-card');
      lblEl.textContent=label||'EXPLORE →';
    });
    el.addEventListener('mouseleave',()=>{
      document.body.classList.remove('hovering-card');
    });
  });
}
setTimeout(()=>{
  addMagnet('.fw-card','EXPLORE →');
  addMagnet('.bcase','READ CASE →');
  addMagnet('.btn-fire','GO →');
  addMagnet('.btn-ghost','EXPLORE →');
  addMagnet('.lab-go','APPLY DT →');
},500);

/* ============ NAV ============ */
const nav=document.getElementById('mainNav');
const pill=document.getElementById('navPill');
let lastScroll=0;
window.addEventListener('scroll',()=>{
  const s=window.scrollY;
  nav.classList.toggle('short',s>80);
  nav.classList.toggle('tall',s<=80);
  lastScroll=s;
  updateNavActive();
});
const navLinks=document.querySelectorAll('.nav-link');
function updateNavActive(){
  const secs=['home','stages-scroll','lab','frameworks','cases','quiz'];
  let current='home';
  secs.forEach(id=>{const el=document.getElementById(id);if(el&&el.getBoundingClientRect().top<120)current=id});
  navLinks.forEach(a=>{
    const isAct=a.getAttribute('href')==='#'+current||a.getAttribute('href').includes(current);
    a.classList.toggle('active',isAct);
    if(isAct){
      const r=a.getBoundingClientRect();const pr=a.closest('.nav-links').getBoundingClientRect();
      pill.style.left=(r.left-pr.left)+'px';pill.style.width=r.width+'px';
    }
  });
}
function openMob(){document.getElementById('mobMenu').classList.add('open');document.body.style.overflow='hidden'}
function closeMob(){document.getElementById('mobMenu').classList.remove('open');document.body.style.overflow=''}

/* ============ THREE.JS WebGL BACKGROUND ============ */
let renderer,scene,camera,meshes=[],mouseX=0,mouseY=0;
function initThree(){
  const canvas=document.getElementById('webgl-canvas');
  renderer=new THREE.WebGLRenderer({canvas,antialias:true,alpha:true});
  renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));
  renderer.setSize(canvas.parentElement.offsetWidth,canvas.parentElement.offsetHeight);
  scene=new THREE.Scene();
  camera=new THREE.PerspectiveCamera(60,canvas.parentElement.offsetWidth/canvas.parentElement.offsetHeight,.1,100);
  camera.position.z=5;
  const orangeLight=new THREE.PointLight(0xe8521a,1.8,20);orangeLight.position.set(3,3,2);scene.add(orangeLight);
  const purpLight=new THREE.PointLight(0x8b42d4,1.2,15);purpLight.position.set(-4,-2,1);scene.add(purpLight);
  const ambLight=new THREE.AmbientLight(0xffffff,.05);scene.add(ambLight);
  const geos=[
    new THREE.IcosahedronGeometry(.55,0),new THREE.OctahedronGeometry(.45,0),
    new THREE.IcosahedronGeometry(.35,0),new THREE.OctahedronGeometry(.6,0),
    new THREE.IcosahedronGeometry(.7,0),new THREE.OctahedronGeometry(.3,0),
    new THREE.IcosahedronGeometry(.4,0),new THREE.OctahedronGeometry(.5,0),
    new THREE.IcosahedronGeometry(.25,0)
  ];
  const colors=[0xff5c1a,0xa855f7,0x3b82f6,0x10d97c,0xfbbf24,0xff8c42,0xc084fc,0x93c5fd,0x34d399];
  geos.forEach((geo,i)=>{
    const mat=new THREE.MeshPhongMaterial({color:colors[i],wireframe:true,opacity:.28,transparent:true,shininess:80});
    const mesh=new THREE.Mesh(geo,mat);
    mesh.position.set((Math.random()-.5)*12,(Math.random()-.5)*7,(Math.random()-.5)*4-1);
    mesh.rotation.set(Math.random()*Math.PI,Math.random()*Math.PI,Math.random()*Math.PI);
    mesh.userData={vx:(Math.random()-.5)*.006,vy:(Math.random()-.5)*.004,rx:Math.random()*.008+.002,ry:Math.random()*.006+.001,rz:Math.random()*.004};
    scene.add(mesh);meshes.push(mesh);
  });
  window.addEventListener('resize',()=>{
    const w=canvas.parentElement.offsetWidth,h=canvas.parentElement.offsetHeight;
    renderer.setSize(w,h);camera.aspect=w/h;camera.updateProjectionMatrix();
  });
  document.getElementById('home').addEventListener('mousemove',e=>{
    mouseX=(e.clientX/window.innerWidth-.5)*2;
    mouseY=-(e.clientY/window.innerHeight-.5)*2;
  });
  animThree();
}
function animThree(){
  if(!prefersReduced)requestAnimationFrame(animThree);
  meshes.forEach(m=>{
    m.rotation.x+=m.userData.rx;m.rotation.y+=m.userData.ry;m.rotation.z+=m.userData.rz;
    m.position.x+=m.userData.vx;m.position.y+=m.userData.vy;
    if(m.position.x>8)m.position.x=-8;if(m.position.x<-8)m.position.x=8;
    if(m.position.y>5)m.position.y=-5;if(m.position.y<-5)m.position.y=5;
  });
  camera.position.x+=(mouseX*.8-camera.position.x)*.04;
  camera.position.y+=(mouseY*.5-camera.position.y)*.04;
  camera.lookAt(scene.position);
  renderer.render(scene,camera);
}
if(!prefersReduced)initThree();

/* ============ HERO INIT ============ */
function initHero(){
  const tl=gsap.timeline();
  tl.to('#heroTag',{opacity:1,y:0,duration:.8,ease:'power3.out'})
    .to('#heroPhil',{opacity:1,duration:1,ease:'power2.out'},'-=.4')
    .add(()=>{scrambleText('scramble1','REAL PROBLEMS');scrambleText('scramble2','BOLD IDEAS');scrambleText('scramble3','FUTURE BUILT.')},'-=.3')
    .to('#heroSub',{opacity:1,duration:.9,ease:'power2.out'},'+=.6')
    .to('#heroBtns',{opacity:1,duration:.8,ease:'power2.out'},'-=.4')
    .to('#heroCounter',{opacity:1,duration:.6,ease:'power2.out'},'-=.3')
    .to('#heroScroll',{opacity:1,duration:.6},'-=.2')
    .to(['.hf1','.hf2','.hf3','.hf4'],{opacity:1,duration:.6,stagger:.15,ease:'power2.out'},'-=.4');
}

/* ============ TEXT SCRAMBLE ============ */
const chars='ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%';
function scrambleText(id,target){
  const el=document.getElementById(id);if(!el)return;
  if(prefersReduced){el.textContent=target;return;}
  let iter=0;const maxIter=target.length*3;
  const interval=setInterval(()=>{
    el.textContent=target.split('').map((c,i)=>{
      if(c===' ')return ' ';
      if(i<Math.floor(iter/3))return target[i];
      return chars[Math.floor(Math.random()*chars.length)];
    }).join('');
    iter++;if(iter>maxIter){el.textContent=target;clearInterval(interval);}
  },40);
}

/* ============ HERO GHOST PARALLAX ============ */
gsap.to('#heroGhost',{yPercent:-30,ease:'none',scrollTrigger:{trigger:'#home',start:'top top',end:'bottom top',scrub:1}});

/* ============ HERO COUNTER ============ */
let counter=Math.floor(Math.random()*800)+1200;
document.getElementById('counterNum').textContent=counter;
setInterval(()=>{counter+=Math.floor(Math.random()*3)+1;document.getElementById('counterNum').textContent=counter.toLocaleString()},Math.floor(Math.random()*3000)+2000);

/* ============ HORIZONTAL STAGES SCROLL ============ */
let currentStage=0;
const stTrack=document.getElementById('stagesTrack');
const stDots=document.querySelectorAll('.sp-dot');

function initMobileStages(){
  const sticky=document.getElementById('stages-sticky');
  const scrollWrap=document.getElementById('stages-scroll');
  sticky.style.position='relative';
  sticky.style.height='auto';
  sticky.style.overflow='visible';
  stTrack.style.display='block';
  stTrack.style.width='100%';
  document.querySelectorAll('.stage-slide').forEach(s=>{
    s.style.width='100%';
    s.style.height='auto';
    s.style.gridTemplateColumns='1fr';
  });
  const dots=document.getElementById('stagesProgress');
  if(dots)dots.style.display='flex';
}

function initDesktopStages(){
  if(prefersReduced)return;
  gsap.to(stTrack,{
    x:()=>-(stTrack.offsetWidth-window.innerWidth),
    ease:'none',
    scrollTrigger:{
      id:'stages-scroll',
      trigger:'#stages-scroll',
      start:'top top',
      end:'+=400%',
      scrub:1.2,
      pin:true,
      anticipatePin:1,
      onUpdate:self=>{
        const idx=Math.round(self.progress*4);
        if(idx!==currentStage){currentStage=idx;updateStageDots(idx);}
      }
    }
  });
}

if(window.innerWidth>=768){
  initDesktopStages();
}else{
  initMobileStages();
}

window.addEventListener('resize',()=>{
  if(window.innerWidth<768){
    ScrollTrigger.getAll().forEach(st=>{if(st.vars&&st.vars.id==='stages-scroll')st.kill();});
    initMobileStages();
  }
});

function updateStageDots(i){
  stDots.forEach((d,idx)=>d.classList.toggle('active',idx===i));
}
function goToStage(i){
  const progress=i/4;
  const st=ScrollTrigger.getById('stages-scroll');
  if(st){const scrollTo=st.start+(st.end-st.start)*progress;window.scrollTo({top:scrollTo,behavior:'smooth'});}
  else{
    const slides=document.querySelectorAll('.stage-slide');
    if(slides[i])slides[i].scrollIntoView({behavior:'smooth',block:'start'});
  }
}

/* ============ SCROLL REVEAL ============ */
const revObs=new IntersectionObserver(ents=>{ents.forEach((e,i)=>{if(e.isIntersecting){e.target.style.transitionDelay=(i*.08)+'s';e.target.classList.add('vis');}});},{threshold:.1});
document.querySelectorAll('.rev').forEach(el=>revObs.observe(el));

/* ============ GSAP COUNTER ANIM ============ */
function animCounter(el,target){
  const obj={n:0};
  gsap.to(obj,{n:target,duration:2.5,ease:'power2.out',onUpdate:()=>{el.textContent=Math.round(obj.n).toLocaleString()},scrollTrigger:{trigger:el,start:'top 90%',once:true}});
}
document.querySelectorAll('.bcs-num,.ci-num,.hstat-num').forEach(el=>{
  const txt=el.textContent.trim();
  const skip=['∞','×','yr','↑','↓','%'];
  if(skip.some(s=>txt.includes(s)))return;
  const num=parseFloat(txt.replace(/[^0-9.]/g,''));
  if(isNaN(num)||num===0||txt.length>7)return;
  const prefix=txt.match(/^[^0-9]*/)[0];
  const suffix=txt.match(/[^0-9.M B]*$/)[0];
  ScrollTrigger.create({trigger:el,start:'top 90%',once:true,onEnter:()=>{
    const o={n:0};
    gsap.to(o,{n:num,duration:2,ease:'power2.out',onUpdate:()=>{el.textContent=prefix+Math.round(o.n).toLocaleString()+suffix;}});
  }});
});

/* ============ PROBLEM LAB ============ */
let labHasOutput=false;
function fillEx(el){
  document.getElementById('labTa').value=el.textContent;
  document.querySelectorAll('.lab-chip').forEach(c=>{c.classList.remove('sel');c.style.borderColor=''});
  el.classList.add('sel');
}

async function runLab(){
  const prob=document.getElementById('labTa').value.trim();
  if(!prob){document.getElementById('labTa').focus();return;}
  const btn=document.getElementById('labGo');
  btn.disabled=true;
  btn.innerHTML='<span class="think-dots"><span></span><span></span><span></span></span> Applying Design Thinking...';
  document.getElementById('tawrap').classList.add('scanning');
  document.getElementById('labPH').style.display='none';
  document.getElementById('outStatus').textContent='Analysing Problem...';
  const out=document.getElementById('labOut');
  out.style.display='block';
  out.innerHTML='<div style="display:flex;align-items:center;gap:12px;padding:1rem 0;color:var(--muted)"><div class="think-dots"><span></span><span></span><span></span></div><span style="font-size:.82rem">Mapping your problem through all 5 Design Thinking stages...</span></div>';
  labHasOutput=false;

  const prompt=`You are an expert Design Thinking facilitator and Innovation Management professor. A student has submitted this real-world problem statement:

"${prob}"

Apply Design Thinking to this problem. Your response must follow EXACTLY this structure with these exact headers:

## REFINED PROBLEM STATEMENT
Rewrite the problem statement using proper Design Thinking language — make it human-centred, specific, and action-oriented. Explain briefly what you changed and why.

## STAGE 1 — EMPATHISE
Who are the primary users/stakeholders? What are their 3 key unmet needs, fears, and frustrations? What deeper human truth lies beneath this problem?

## STAGE 2 — DEFINE (Point of View Statement)
Write a proper POV statement in this format: [USER] needs [NEED] because [INSIGHT]. Then write 2 strong "How Might We" questions that open up creative solution space.

## STAGE 3 — IDEATE
List 4 creative, diverse solution ideas ranging from practical to bold. Briefly describe each idea (1-2 sentences). Include at least one unexpected/disruptive idea.

## STAGE 4 — PROTOTYPE
What should be prototyped first and why? Describe the ideal low-fidelity prototype for the top idea — what it looks like, what it tests, and how to build it in under 48 hours with minimal resources.

## STAGE 5 — TEST
Design a specific user test for this prototype. Who to test with (5 specific user types), 3 key questions to answer, and how to measure whether the solution works.

Keep each section concise but insightful. Use plain language. Be specific to THIS problem, not generic.`;

  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:2000,messages:[{role:'user',content:prompt}]})
    });
    const data=await res.json();
    const text=data.content?.[0]?.text||'';
    if(!text)throw new Error('empty');
    renderOutput(text);
  }catch(e){
    renderFallback(prob);
  }

  document.getElementById('tawrap').classList.remove('scanning');
  btn.disabled=false;
  btn.innerHTML='<span class="shim"></span><span>✦</span> Apply Design Thinking <span>→</span>';
  document.getElementById('outStatus').textContent='Analysis Complete ✓';
  document.getElementById('copyBtn').style.display='block';
  document.getElementById('resetBtn').style.display='block';
  labHasOutput=true;
}

function renderOutput(text){
  const blocks=[
    {key:'REFINED PROBLEM STATEMENT',cls:'refined',lbl:'✦ Refined Problem Statement',delay:0},
    {key:'STAGE 1',cls:'empathise',lbl:'01 — Empathise',delay:.2},
    {key:'STAGE 2',cls:'define',lbl:'02 — Define (POV)',delay:.4},
    {key:'STAGE 3',cls:'ideate',lbl:'03 — Ideate',delay:.6},
    {key:'STAGE 4',cls:'prototype',lbl:'04 — Prototype',delay:.8},
    {key:'STAGE 5',cls:'test',lbl:'05 — Test',delay:1.0}
  ];
  const out=document.getElementById('labOut');
  out.innerHTML='';
  blocks.forEach(b=>{
    const re=new RegExp('##\\s*'+b.key+'[^\\n]*\\n([\\s\\S]*?)(?=##|$)','i');
    const m=text.match(re);
    const content=m?m[1].trim().replace(/\n/g,'<br>').replace(/\*\*/g,'').replace(/\*/g,''):'Content processing...';
    const div=document.createElement('div');
    div.className='dt-block '+b.cls;
    div.innerHTML=`<div class="dt-blabel">${b.lbl}</div><div class="dt-bcontent">${content}</div>`;
    out.appendChild(div);
    setTimeout(()=>div.classList.add('in'),b.delay*1000+100);
  });
}

function renderFallback(prob){
  const short=prob.length>70?prob.substring(0,70)+'...':prob;
  const blocks=[
    {cls:'refined',lbl:'✦ Refined Problem Statement',content:`Your problem has been reframed from symptoms to a human-centred challenge: <em>"The people most affected by [${short}] need a reliable, contextually appropriate way to address their underlying needs — because existing systems were designed without understanding their real-world constraints, behaviours and aspirations."</em><br><br>This reframe shifts focus from the problem to the people experiencing it.`},
    {cls:'empathise',lbl:'01 — Empathise',content:'<strong>Primary users:</strong> Those directly experiencing this problem daily.<br><strong>Key unmet needs:</strong> Reliable access, dignity in the solution, agency over their situation, and understanding from the system.<br><strong>Deeper human truth:</strong> Most people affected have already tried to solve this themselves — their existing attempts reveal exactly what they value and what trade-offs they will accept.'},
    {cls:'define',lbl:'02 — Define (POV)',content:'<strong>POV Statement:</strong> An affected person needs a practical, dignified and contextually appropriate solution because current options were designed without understanding their actual daily reality.<br><br><strong>HMW 1:</strong> How might we redesign this solution to fit INTO people\'s existing lives rather than requiring them to change their behaviour?<br><strong>HMW 2:</strong> How might we involve the most affected people as co-designers from Day 1?'},
    {cls:'ideate',lbl:'03 — Ideate',content:'1. <strong>Community-led model:</strong> Train local community members as peer facilitators who deliver context-adapted support within trusted relationships.<br>2. <strong>Technology bridge:</strong> Use the most accessible tech — SMS, offline apps, feature phones — to bring solutions where people already are.<br>3. <strong>Institutional embed:</strong> Place the solution inside an existing trusted institution the community already uses daily.<br>4. <strong>Disruptive flip:</strong> Instead of bringing people to the solution, build the solution to travel to people.'},
    {cls:'prototype',lbl:'04 — Prototype',content:'<strong>First prototype:</strong> A role-play walkthrough of the community facilitator model. Paper cards represent each journey step. Two team members play user and facilitator.<br><strong>Build in 48 hours:</strong> Printed journey map on A4 sheets. 3 role-play sessions. Filmed on a phone.<br><strong>What it tests:</strong> Whether the model feels natural, trustworthy and practical for the actual user.'},
    {cls:'test',lbl:'05 — Test',content:'<strong>Test with:</strong> 5 people who currently experience this problem directly. Recruit through community organisations or NGOs — never through surveys.<br><strong>3 key questions:</strong><br>1. Do they immediately understand what this does?<br>2. Would they actually use this in their real life — not in theory?<br>3. What would make them stop after the first time?<br><strong>Success signal:</strong> At least 3 of 5 say "I would use this tomorrow" without prompting.'}
  ];
  const out=document.getElementById('labOut');out.innerHTML='';
  blocks.forEach((b,i)=>{
    const div=document.createElement('div');
    div.className='dt-block '+b.cls;
    div.innerHTML=`<div class="dt-blabel">${b.lbl}</div><div class="dt-bcontent">${b.content}</div>`;
    out.appendChild(div);
    setTimeout(()=>div.classList.add('in'),(i*.2)*1000+100);
  });
}

function copyOutput(){
  const out=document.getElementById('labOut');
  if(!out)return;
  const text=Array.from(out.querySelectorAll('.dt-block')).map(b=>{
    const lbl=b.querySelector('.dt-blabel')?.textContent||'';
    const content=b.querySelector('.dt-bcontent')?.innerText||'';
    return lbl+'\n'+content;
  }).join('\n\n---\n\n');
  navigator.clipboard.writeText(text).then(()=>{
    const btn=document.getElementById('copyBtn');btn.textContent='✓ Copied!';
    setTimeout(()=>btn.textContent='⊕ Copy Output',2000);
  });
}

function resetLab(){
  document.getElementById('labTa').value='';
  document.getElementById('labOut').style.display='none';
  document.getElementById('labOut').innerHTML='';
  document.getElementById('labPH').style.display='flex';
  document.getElementById('outStatus').textContent='Awaiting Problem Input';
  document.getElementById('copyBtn').style.display='none';
  document.getElementById('resetBtn').style.display='none';
  document.querySelectorAll('.lab-chip').forEach(c=>c.classList.remove('sel'));
  labHasOutput=false;
}

/* ============ PROCESS ============ */
function actPS(el){document.querySelectorAll('.pstep').forEach(p=>p.classList.remove('act'));el.classList.add('act')}

/* ============ QUIZ ============ */
const QS=[
  {q:"Which Design Thinking stage focuses on deeply understanding people's unspoken and emotional needs through observation?",opts:["Define","Ideate","Empathise","Prototype"],a:2},
  {q:"A Point of View (POV) statement is the primary output of which stage?",opts:["Empathise","Test","Ideate","Define"],a:3},
  {q:"During Ideation, which principle is MOST critical to creative output?",opts:["Only present feasible ideas","Work alone for best focus","Defer all judgement — quantity over quality","Focus immediately on the best one idea"],a:2},
  {q:"What is the defining characteristic of a Design Thinking prototype?",opts:["Must be digital and high-fidelity","Fast, cheap, designed to be tested — not to impress","Approved by stakeholders before testing","Must fully represent the final product"],a:1},
  {q:"When user testing reveals your prototype doesn't work, what does Design Thinking recommend?",opts:["Abandon the project","Go back to an earlier stage and iterate — the process working correctly","Present as-is to stakeholders","Move forward and fix later"],a:1},
  {q:"An Empathy Map captures which four dimensions of user experience?",opts:["Needs, Goals, Pain, Gain","Say, Think, Do, Feel","Problems, Solutions, Ideas, Actions","Research, Define, Ideate, Test"],a:1}
];
let cq=0,sc=0,qans=false;
function renderQ(){
  const q=QS[cq];
  document.getElementById('qN').textContent='Question '+(cq+1)+' of '+QS.length;
  document.getElementById('qT').textContent=q.q;
  document.getElementById('qpf').style.width=((cq/QS.length)*100)+'%';
  document.getElementById('qO').innerHTML=q.opts.map((o,i)=>`<button class="qopt" onclick="ansQ(${i})">${o}</button>`).join('');
  document.getElementById('qNext').style.display='none';
  qans=false;
}
function ansQ(i){
  if(qans)return;qans=true;
  const q=QS[cq];
  document.querySelectorAll('.qopt').forEach((o,idx)=>{
    if(idx===q.a)o.classList.add('correct');
    else if(idx===i&&i!==q.a)o.classList.add('wrong');
    o.disabled=true;
  });
  if(i===q.a)sc++;
  document.getElementById('qNext').style.display='flex';
  document.getElementById('qNext').textContent=cq<QS.length-1?'Next →':'See Results →';
}
function nextQ(){
  if(!qans)return;cq++;
  if(cq>=QS.length){
    document.getElementById('qContent').style.display='none';
    document.getElementById('qRes').style.display='block';
    document.getElementById('qpf').style.width='100%';
    document.getElementById('qSc').textContent=sc+'/'+QS.length;
    const msgs=['Keep exploring — review the 5 stages again!','Good start — dive deeper into the frameworks.','Solid foundation — you understand the core.','Great work — you think like a designer!','Perfect — you are a certified Design Thinker!','Master level — go change the world!'];
    document.getElementById('qMsg').textContent=msgs[Math.min(sc,5)];
    gsap.from('#qSc',{scale:.5,opacity:0,duration:.8,ease:'elastic.out(1,.6)'});
  }else renderQ();

const firstLink=document.querySelector('.nav-link');
if(firstLink){
  const r=firstLink.getBoundingClientRect();
  const pr=firstLink.closest('.nav-links').getBoundingClientRect();
  pill.style.left=(r.left-pr.left)+'px';
  pill.style.width=r.width+'px';
}
}
function resetQ(){cq=0;sc=0;document.getElementById('qContent').style.display='block';document.getElementById('qRes').style.display='none';renderQ();}
renderQ();

/* ============ GSAP SECTION REVEAL ============ */
gsap.utils.toArray('.sec-title').forEach(el=>{
  ScrollTrigger.create({trigger:el,start:'top 85%',once:true,onEnter:()=>{
    gsap.from(el,{y:40,opacity:0,duration:.9,ease:'power3.out'});
  }});
});
</script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DESIGN THINKING — Build. Innovate. Test. Transform.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --night:#050B16;          /* city night base */
  --panel:#0B1426;
  --volt:#37D1FF;           /* electric cyan */
  --amber:#FFB454;          /* signal amber */
  --mint:#5CF2B8;           /* success green */
  --rose:#FF6B8B;           /* risk red */
  --violet:#8E7BFF;
  --ink:#EBF3FF;
  --ink-dim:#8FA3C7;
  --glass:rgba(140,190,255,.06);
  --glass-edge:rgba(140,190,255,.18);
  --radius:18px;
  --disp:'Space Grotesk',system-ui,sans-serif;
  --body:'Inter',system-ui,sans-serif;
}
*{margin:0;padding:0;box-sizing:border-box}
html,body{height:100%}
body{font-family:var(--body);color:var(--ink);background:var(--night);overflow:hidden;-webkit-font-smoothing:antialiased}
button{font-family:inherit;cursor:pointer}
::selection{background:var(--volt);color:#04111f}

/* ---------- background ---------- */
#stars{position:fixed;inset:0;z-index:0}
.sky-glow{position:fixed;border-radius:50%;filter:blur(100px);opacity:.5;z-index:0;pointer-events:none;
  transition:transform 1.2s cubic-bezier(.2,.8,.2,1), background 1.6s ease}
#glowA{width:62vmax;height:62vmax;left:-22vmax;top:-26vmax;background:radial-gradient(circle,#0c3a5e,transparent 65%)}
#glowB{width:56vmax;height:56vmax;right:-18vmax;bottom:-24vmax;background:radial-gradient(circle,#23145e,transparent 65%)}

/* city skyline */
#city{position:fixed;left:0;right:0;bottom:0;height:30vh;z-index:1;pointer-events:none;opacity:.9;transition:opacity 1s}
#city svg{width:100%;height:100%;display:block}
.win{fill:#0a1220}
.win.lit{fill:var(--amber);opacity:.75;animation:flick 4s infinite}
.win.lit.c{fill:var(--volt)}
@keyframes flick{0%,92%,100%{opacity:.75}95%{opacity:.15}}
/* drones */
.drone{position:fixed;z-index:2;font-size:18px;pointer-events:none;opacity:.85;animation:dronefly linear infinite}
@keyframes dronefly{0%{transform:translateX(-8vw) translateY(0)}50%{transform:translateX(50vw) translateY(-26px)}100%{transform:translateX(110vw) translateY(0)}}
.drone::after{content:"";position:absolute;left:50%;top:100%;width:1px;height:14px;background:linear-gradient(var(--volt),transparent)}

#shutter{position:fixed;inset:0;background:#02060d;z-index:60;pointer-events:none;opacity:0;transition:opacity .55s ease}
#shutter.on{opacity:1}

#boot{position:fixed;inset:0;background:#02060d;z-index:70;display:flex;align-items:center;justify-content:center;
  flex-direction:column;gap:14px;transition:opacity .8s ease}
#boot .lab{font:600 11px/1 var(--disp);letter-spacing:.45em;color:var(--ink-dim);text-transform:uppercase}
#boot .bar{width:220px;height:3px;background:rgba(140,190,255,.12);border-radius:99px;overflow:hidden}
#boot .bar i{display:block;height:100%;width:0;background:linear-gradient(90deg,var(--volt),var(--mint));transition:width .25s}
#boot.gone{opacity:0;pointer-events:none}

/* ---------- HUD ---------- */
#hud{position:fixed;top:0;left:0;right:0;z-index:40;display:flex;align-items:center;gap:12px;
  padding:14px 20px;opacity:0;transform:translateY(-12px);transition:.6s ease;pointer-events:none}
#hud.show{opacity:1;transform:none;pointer-events:auto}
.hud-chip{display:flex;align-items:center;gap:8px;padding:8px 14px;border-radius:10px;
  background:var(--glass);border:1px solid var(--glass-edge);backdrop-filter:blur(14px);font-size:13px}
.hud-chip b{font-family:var(--disp)}
#xpchip b{color:var(--amber)}
#valchip b{color:var(--mint)}
.tracker{display:flex;gap:6px;margin-left:auto;align-items:center;padding:8px 12px;border-radius:10px;
  background:var(--glass);border:1px solid var(--glass-edge);backdrop-filter:blur(14px)}
.tracker .dot{width:26px;height:26px;border-radius:7px;display:grid;place-items:center;font:600 10px var(--disp);
  color:var(--ink-dim);border:1px dashed rgba(140,190,255,.3);transition:.4s}
.tracker .dot.done{background:linear-gradient(135deg,var(--volt),var(--mint));color:#04111f;border-color:transparent;
  box-shadow:0 0 14px rgba(55,209,255,.55)}
.tracker .dot.now{border:1px solid var(--volt);color:var(--volt);animation:pulse 1.6s infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(55,209,255,.35)}50%{box-shadow:0 0 0 7px rgba(55,209,255,0)}}
#badgewrap{display:flex;gap:6px}
.badge{width:30px;height:30px;border-radius:8px;display:grid;place-items:center;font-size:15px;
  background:var(--glass);border:1px solid var(--glass-edge);filter:grayscale(1);opacity:.4;transition:.5s}
.badge.won{filter:none;opacity:1;background:linear-gradient(135deg,rgba(255,180,84,.25),rgba(55,209,255,.25));
  border-color:var(--amber);animation:badgepop .6s cubic-bezier(.3,1.6,.5,1)}
@keyframes badgepop{0%{transform:scale(.2) rotate(-30deg)}100%{transform:scale(1) rotate(0)}}

.xp-float{position:fixed;z-index:55;font:700 15px var(--disp);color:var(--amber);pointer-events:none;
  text-shadow:0 2px 12px rgba(255,180,84,.6);animation:xpfly 1.1s ease forwards}
.xp-float.green{color:var(--mint);text-shadow:0 2px 12px rgba(92,242,184,.6)}
@keyframes xpfly{0%{opacity:0;transform:translateY(8px) scale(.7)}25%{opacity:1;transform:translateY(-6px) scale(1.1)}
  100%{opacity:0;transform:translateY(-46px) scale(1)}}

/* ---------- scenes ---------- */
.scene{position:fixed;inset:0;z-index:10;display:flex;align-items:center;justify-content:center;
  padding:84px 24px 170px;opacity:0;pointer-events:none;transform:scale(1.04);
  transition:opacity .7s ease,transform .7s ease;overflow-y:auto}
.scene.active{opacity:1;pointer-events:auto;transform:scale(1)}
.scene-inner{width:min(1040px,100%);margin:auto}
.eyebrow{font:700 11px/1 var(--disp);letter-spacing:.35em;text-transform:uppercase;color:var(--volt);
  display:flex;align-items:center;gap:10px;margin-bottom:14px}
.eyebrow::before{content:"";width:26px;height:1px;background:var(--volt)}
h1{font:700 clamp(36px,7.4vw,76px)/1 var(--disp);letter-spacing:-.03em}
h2{font:700 clamp(24px,4vw,38px)/1.1 var(--disp);letter-spacing:-.02em;margin-bottom:8px}
.lede{color:var(--ink-dim);font-size:clamp(14px,1.6vw,16.5px);line-height:1.65;max-width:580px}

#scene-title .scene-inner{text-align:center;display:flex;flex-direction:column;align-items:center;gap:20px}
.holo-title{position:relative;display:inline-block;opacity:0;transform:translateY(24px);transition:1s ease .2s}
.holo-title.in{opacity:1;transform:none}
.holo-title h1{background:linear-gradient(105deg,#fff 15%,var(--volt) 45%,var(--mint) 65%,#fff 95%);
  -webkit-background-clip:text;background-clip:text;color:transparent;background-size:220% 100%;animation:sheen 6s linear infinite}
@keyframes sheen{to{background-position:-220% 0}}
.tagline{font:600 clamp(13px,2vw,18px) var(--disp);letter-spacing:.28em;text-transform:uppercase;color:var(--amber)}
.holo-title::after{content:"";position:absolute;left:8%;right:8%;bottom:-16px;height:24px;
  background:radial-gradient(ellipse at center,rgba(55,209,255,.4),transparent 70%);filter:blur(6px)}
.scanline{position:absolute;left:-4%;right:-4%;height:2px;background:linear-gradient(90deg,transparent,var(--volt),transparent);
  opacity:.7;animation:scan 3.4s ease-in-out infinite}
@keyframes scan{0%,100%{top:8%}50%{top:92%}}

/* live ticker chart on title */
#ticker{display:flex;gap:18px;align-items:flex-end;height:54px;margin-top:4px;opacity:.9}
#ticker .bar{width:10px;border-radius:3px 3px 0 0;background:linear-gradient(180deg,var(--volt),rgba(55,209,255,.1));
  animation:barwave 2.6s ease-in-out infinite}
@keyframes barwave{0%,100%{transform:scaleY(.45)}50%{transform:scaleY(1)}}
#ticker .bar{transform-origin:bottom}

.cta{position:relative;border:none;border-radius:12px;padding:18px 46px;font:700 15px var(--disp);letter-spacing:.08em;
  text-transform:uppercase;color:#04111f;background:linear-gradient(115deg,var(--volt),var(--mint));
  box-shadow:0 10px 40px rgba(55,209,255,.4);transition:transform .25s,box-shadow .25s;overflow:hidden}
.cta:hover{transform:translateY(-3px) scale(1.02);box-shadow:0 16px 50px rgba(92,242,184,.5)}
.cta:active{transform:scale(.98)}
.cta:disabled{opacity:.35;cursor:not-allowed;transform:none}
.cta::after{content:"";position:absolute;inset:0;background:linear-gradient(115deg,transparent 30%,rgba(255,255,255,.5) 50%,transparent 70%);
  transform:translateX(-120%);animation:ctasheen 3.2s ease infinite}
@keyframes ctasheen{0%,60%{transform:translateX(-120%)}100%{transform:translateX(120%)}}

.glass{background:var(--glass);border:1px solid var(--glass-edge);border-radius:var(--radius);
  backdrop-filter:blur(16px);box-shadow:0 20px 60px rgba(0,0,0,.4)}

/* ---------- Round 1 ---------- */
.persona-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:14px;margin-top:24px}
.persona{padding:18px 14px;text-align:center;transition:.3s;position:relative;border-radius:var(--radius)}
.persona:hover{transform:translateY(-6px);border-color:var(--volt)}
.persona.solved{border-color:var(--mint);box-shadow:0 0 24px rgba(92,242,184,.2)}
.persona .face{font-size:42px;display:block;margin-bottom:8px;animation:bob 4s ease-in-out infinite}
.persona:nth-child(2) .face{animation-delay:.7s}.persona:nth-child(3) .face{animation-delay:1.4s}
.persona:nth-child(4) .face{animation-delay:2.1s}
@keyframes bob{0%,100%{transform:translateY(0)}50%{transform:translateY(-7px)}}
.persona b{font:700 14px var(--disp);display:block}
.persona small{color:var(--ink-dim);font-size:11px}
.persona .check{position:absolute;top:8px;right:10px;color:var(--mint);font-size:15px;opacity:0;transform:scale(0);transition:.4s}
.persona.solved .check{opacity:1;transform:scale(1)}

.dialog-panel{margin-top:20px;padding:24px;display:none}
.dialog-panel.open{display:block;animation:rise .45s ease}
@keyframes rise{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}
.quote{font-size:16px;line-height:1.65;border-left:3px solid var(--volt);padding-left:16px;margin:10px 0 18px}
.opt{display:block;width:100%;text-align:left;margin-top:10px;padding:14px 16px;border-radius:12px;
  background:rgba(140,190,255,.04);border:1px solid var(--glass-edge);color:var(--ink);font-size:14px;line-height:1.5;transition:.25s}
.opt:hover{border-color:var(--volt);background:rgba(55,209,255,.08);transform:translateX(4px)}
.opt.right{border-color:var(--mint);background:rgba(92,242,184,.12)}
.opt.wrong{border-color:var(--rose);background:rgba(255,107,139,.1);animation:shake .4s}
@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-6px)}75%{transform:translateX(6px)}}
.note-fly{position:fixed;z-index:56;padding:8px 14px;border-radius:8px;background:linear-gradient(135deg,var(--mint),#3ec98f);
  color:#03241a;font:600 12px var(--disp);pointer-events:none;box-shadow:0 8px 24px rgba(92,242,184,.45)}
#board{position:fixed;top:70px;right:26px;z-index:41;display:flex;flex-direction:column;gap:6px;align-items:flex-end;max-width:300px}
.board-note{padding:6px 12px;border-radius:8px;font:600 11px var(--disp);color:#03241a;
  background:linear-gradient(135deg,var(--mint),#3ec98f);box-shadow:0 0 18px rgba(92,242,184,.45);animation:rise .5s ease}
#oppZone{display:none;margin-top:24px}
#oppZone.open{display:block;animation:rise .5s ease}

/* ---------- Round 2 ---------- */
.define-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:22px}
.bucket{min-height:170px;padding:16px;border-radius:var(--radius);border:1.5px dashed rgba(140,190,255,.3);transition:.3s}
.bucket h4{font:700 13px var(--disp);letter-spacing:.05em;text-transform:uppercase;margin-bottom:10px}
.bucket.b1 h4{color:var(--volt)}.bucket.b2 h4{color:var(--violet)}
.bucket.glowok{border-style:solid;border-color:var(--mint);box-shadow:0 0 26px rgba(92,242,184,.2)}
.bucket.armed{border-color:var(--volt);background:rgba(55,209,255,.05);cursor:pointer}
.chip-pool{display:flex;flex-wrap:wrap;gap:10px;margin-top:18px;min-height:46px}
.ichip{padding:10px 14px;border-radius:10px;background:rgba(140,190,255,.05);border:1px solid var(--glass-edge);
  font-size:13px;transition:.25s;cursor:pointer;animation:chipfloat 5s ease-in-out infinite;color:var(--ink)}
.ichip:nth-child(odd){animation-delay:1.4s}
@keyframes chipfloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
.ichip:hover{border-color:var(--volt)}
.ichip.sel{border-color:var(--amber);background:rgba(255,180,84,.13);box-shadow:0 0 14px rgba(255,180,84,.3);animation:none}
.bucket .ichip{animation:none;cursor:default;margin:4px 4px 0 0;display:inline-block}
.bucket .ichip.ok{border-color:var(--mint);background:rgba(92,242,184,.08)}
#stmt-zone,#target-zone{display:none;margin-top:24px}
#stmt-zone.open,#target-zone.open{display:block;animation:rise .5s ease}
#crystal{display:none;margin:24px auto 0;width:110px;height:110px;position:relative}
#crystal.on{display:block;animation:crysin 1.1s cubic-bezier(.2,1.4,.4,1)}
#crystal i{position:absolute;inset:14px;background:linear-gradient(135deg,var(--volt),var(--violet),var(--mint));
  clip-path:polygon(50% 0,100% 38%,80% 100%,20% 100%,0 38%);animation:spin3 5s linear infinite;filter:drop-shadow(0 0 22px rgba(55,209,255,.7))}
@keyframes spin3{0%{transform:rotateY(0)}100%{transform:rotateY(360deg)}}
@keyframes crysin{0%{transform:scale(0) rotate(-120deg)}100%{transform:scale(1) rotate(0)}}

/* ---------- Round 3: model builder ---------- */
.builder{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:22px}
.bcol h5{font:700 11px var(--disp);letter-spacing:.18em;text-transform:uppercase;margin-bottom:10px;text-align:center}
.bcol:nth-child(1) h5{color:var(--volt)}.bcol:nth-child(2) h5{color:var(--violet)}.bcol:nth-child(3) h5{color:var(--amber)}
.bcard{display:block;width:100%;padding:13px 12px;margin-bottom:10px;border-radius:12px;text-align:center;
  font:600 12.5px/1.4 var(--disp);color:var(--ink);background:rgba(140,190,255,.05);border:1px solid var(--glass-edge);transition:.25s;cursor:pointer}
.bcard:hover{border-color:var(--volt);transform:translateY(-3px)}
.bcard.sel{border-color:var(--amber);background:rgba(255,180,84,.14);box-shadow:0 0 16px rgba(255,180,84,.35)}
.bcard.spent{opacity:.3;pointer-events:none}
.fuse-row{text-align:center;margin-top:14px}
.fuse-eq{font:700 13px var(--disp);color:var(--ink-dim);min-height:22px;margin-bottom:12px}
.models{display:flex;flex-direction:column;gap:10px;margin-top:18px}
.model{padding:16px 18px;border-radius:14px;border:1px solid var(--glass-edge);background:rgba(140,190,255,.05);
  display:flex;gap:14px;align-items:flex-start;animation:burst .6s cubic-bezier(.3,1.5,.5,1);cursor:pointer;transition:.3s}
.model:hover{border-color:var(--volt)}
.model.strong{border-color:var(--mint);background:linear-gradient(120deg,rgba(92,242,184,.1),rgba(55,209,255,.08))}
.model.chosen{border-color:var(--amber);box-shadow:0 0 24px rgba(255,180,84,.3)}
@keyframes burst{0%{transform:scale(.6);opacity:0}100%{transform:scale(1);opacity:1}}
.model .mtag{font:700 9.5px var(--disp);letter-spacing:.12em;padding:4px 9px;border-radius:6px;white-space:nowrap;
  background:var(--volt);color:#04111f;text-transform:uppercase}
.model.strong .mtag{background:var(--mint)}
.model b{font-family:var(--disp);font-size:15px}
.model p{font-size:12.5px;color:var(--ink-dim);margin-top:3px;line-height:1.5}
.model .pick-hint{font:600 10px var(--disp);letter-spacing:.1em;color:var(--amber);text-transform:uppercase;margin-top:6px;display:none}
.model.pickable .pick-hint{display:block}

/* ---------- Round 4 ---------- */
.deck{margin-top:20px;display:flex;flex-direction:column;gap:16px}
.cat h5{font:700 12px var(--disp);letter-spacing:.15em;text-transform:uppercase;color:var(--volt);margin-bottom:8px}
.cat-opts{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px}
.copt{padding:13px 14px;border-radius:12px;border:1px solid var(--glass-edge);background:rgba(140,190,255,.04);
  cursor:pointer;transition:.25s;font-size:12.5px;line-height:1.45;text-align:left;color:var(--ink)}
.copt:hover{border-color:var(--volt)}
.copt b{display:block;font:700 12.5px var(--disp);margin-bottom:3px}
.copt small{color:var(--ink-dim)}
.copt.picked{border-color:var(--amber);background:rgba(255,180,84,.1);box-shadow:0 0 14px rgba(255,180,84,.2)}
.copt.weakflag{border-color:var(--rose);background:rgba(255,107,139,.12);animation:shake .45s}
#launchpad{margin-top:24px;display:none}
#launchpad.open{display:block;animation:rise .5s ease}
.machine{position:relative;margin:10px auto;width:min(460px,94%);padding:22px;border-radius:18px;
  background:linear-gradient(165deg,#0e1a33,#070d1c);border:1px solid var(--glass-edge);overflow:hidden}
.machine::before{content:"";position:absolute;inset:0;background:
  repeating-linear-gradient(0deg,transparent 0 22px,rgba(55,209,255,.05) 22px 23px)}
.slots{display:grid;grid-template-columns:1fr 1fr;gap:10px;position:relative}
.slot{min-height:58px;border-radius:10px;border:1.5px dashed rgba(140,190,255,.25);display:grid;place-items:center;
  font:600 11px/1.35 var(--disp);text-align:center;padding:7px;color:var(--ink-dim);transition:.4s}
.slot.wide{grid-column:1/-1}
.slot.fill{border-style:solid;border-color:var(--volt);color:var(--ink);background:rgba(55,209,255,.08);
  animation:slotin .5s cubic-bezier(.3,1.5,.5,1)}
@keyframes slotin{0%{transform:scale(.4) rotate(6deg);opacity:0}100%{transform:scale(1) rotate(0);opacity:1}}
.testers{display:flex;flex-direction:column;gap:10px;margin-top:14px}
.tester{display:flex;gap:12px;padding:12px 14px;border-radius:12px;background:rgba(140,190,255,.05);
  border:1px solid var(--glass-edge);font-size:13px;line-height:1.5;opacity:0;transform:translateY(10px);transition:.5s}
.tester.in{opacity:1;transform:none}
.tester .tface{font-size:24px}
.tester.neg{border-color:rgba(255,107,139,.6)}
.tester.pos{border-color:rgba(92,242,184,.5)}

/* ---------- Arena ---------- */
.score-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px;margin-top:24px}
.score-card{padding:18px 12px;text-align:center}
.score-card .ring{width:92px;height:92px;margin:0 auto 10px;border-radius:50%;display:grid;place-items:center;position:relative}
.score-card .ring svg{position:absolute;inset:0;transform:rotate(-90deg)}
.score-card .ring b{font:700 22px var(--disp)}
.score-card small{font:600 10.5px var(--disp);letter-spacing:.1em;text-transform:uppercase;color:var(--ink-dim)}
#level-banner{margin-top:26px;text-align:center;padding:30px 20px;position:relative;overflow:hidden}
#level-banner .lvl{font:700 clamp(26px,4.6vw,42px)/1.1 var(--disp);
  background:linear-gradient(110deg,var(--amber),var(--volt),var(--mint));-webkit-background-clip:text;background-clip:text;color:transparent}
#cert{margin-top:18px;padding:26px;text-align:center;border:1px solid var(--amber);border-radius:var(--radius);
  background:linear-gradient(160deg,rgba(255,180,84,.07),rgba(55,209,255,.06))}
#cert input{background:transparent;border:none;border-bottom:1.5px dashed var(--glass-edge);color:var(--ink);
  font:700 20px var(--disp);text-align:center;padding:6px 10px;outline:none;width:min(320px,80%)}
#cert input:focus{border-color:var(--volt)}
.cert-line{font:600 10px var(--disp);letter-spacing:.3em;text-transform:uppercase;color:var(--ink-dim);margin-top:14px}

.confetti{position:fixed;width:9px;height:9px;z-index:58;pointer-events:none;border-radius:2px;animation:confall linear forwards}
@keyframes confall{0%{transform:translateY(-10px) rotate(0)}100%{transform:translateY(105vh) rotate(720deg);opacity:.2}}

/* ---------- Nova ---------- */
#nova-dock{position:fixed;left:22px;bottom:14px;z-index:50;display:flex;align-items:flex-end;gap:14px;
  transition:transform .9s cubic-bezier(.3,1,.3,1)}
#nova{width:126px;height:156px;filter:drop-shadow(0 14px 22px rgba(0,0,0,.55));transition:transform .5s ease}
#nova .breathe{animation:breathe 3.4s ease-in-out infinite;transform-origin:64px 110px}
@keyframes breathe{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-3px) scale(1.012)}}
#nova .armR{transform-origin:88px 86px;transition:transform .4s}
#nova .armL{transform-origin:40px 86px;transition:transform .4s}
#nova.wave .armR{animation:wavearm .9s ease-in-out 2}
@keyframes wavearm{0%,100%{transform:rotate(0)}30%{transform:rotate(-130deg)}50%{transform:rotate(-100deg)}70%{transform:rotate(-130deg)}}
#nova.point .armR{transform:rotate(-78deg)}
#nova.think .armL{transform:rotate(95deg) translate(6px,-4px)}
#nova.think .browL{transform:translateY(2px) rotate(-8deg)}
#nova.celebrate{animation:hop .55s ease 2}
#nova.celebrate .armR{transform:rotate(-150deg)}
#nova.celebrate .armL{transform:rotate(150deg)}
@keyframes hop{0%,100%{transform:translateY(0)}40%{transform:translateY(-22px)}}
#nova.confused{animation:tilt 1.1s ease}
@keyframes tilt{0%,100%{transform:rotate(0)}30%{transform:rotate(-7deg)}65%{transform:rotate(5deg)}}
#nova .mouth{transition:.2s}
#nova.talk .mouth{animation:talkm .28s ease-in-out infinite}
@keyframes talkm{0%,100%{transform:scaleY(.5)}50%{transform:scaleY(1.25)}}
#nova .lid{transform-origin:center;transform:scaleY(0);transition:.08s}
#nova.blink .lid{transform:scaleY(1)}
#nova .pupils{transition:transform .25s ease}
#nova .ring-glow{animation:ringpulse 2.6s ease-in-out infinite}
@keyframes ringpulse{0%,100%{opacity:.55}50%{opacity:1}}
#nova-bubble{position:relative;max-width:min(350px,58vw);margin-bottom:84px;padding:14px 18px;border-radius:14px 14px 14px 4px;
  background:rgba(11,20,38,.94);border:1px solid var(--glass-edge);backdrop-filter:blur(12px);
  font-size:13.5px;line-height:1.55;box-shadow:0 14px 40px rgba(0,0,0,.5);
  opacity:0;transform:translateY(10px) scale(.96);transition:.35s ease}
#nova-bubble.show{opacity:1;transform:none}
#nova-bubble .who{font:700 10px var(--disp);letter-spacing:.22em;color:var(--volt);text-transform:uppercase;margin-bottom:5px;display:block}
#nova-bubble::after{content:"";position:absolute;left:-7px;bottom:14px;width:14px;height:14px;
  background:inherit;border-left:1px solid var(--glass-edge);border-bottom:1px solid var(--glass-edge);
  transform:rotate(45deg);border-radius:0 0 0 4px}
.thought-dots{position:fixed;z-index:51;display:none;gap:5px;left:126px;bottom:166px}
.thought-dots.on{display:flex}
.thought-dots i{width:8px;height:8px;border-radius:50%;background:var(--volt);animation:dotty 1s infinite}
.thought-dots i:nth-child(2){animation-delay:.18s}.thought-dots i:nth-child(3){animation-delay:.36s}
@keyframes dotty{0%,100%{transform:translateY(0);opacity:.4}50%{transform:translateY(-7px);opacity:1}}

footer-spacer{display:block;height:120px}

@media (max-width:680px){
  .scene{padding:78px 16px 210px}
  #nova{width:90px;height:112px}
  #nova-bubble{margin-bottom:54px;font-size:12.5px;max-width:62vw}
  #nova-dock{left:12px;bottom:8px}
  .define-grid,.builder{grid-template-columns:1fr}
  #hud{flex-wrap:wrap;gap:8px;padding:10px 12px}
  .tracker{margin-left:0}
  #city{height:20vh}
}
@media (prefers-reduced-motion:reduce){
  *,*::before,*::after{animation-duration:.01ms !important;animation-iteration-count:1 !important;transition-duration:.15s !important}
}
</style>
</head>
<body>

<canvas id="stars"></canvas>
<div class="sky-glow" id="glowA"></div>
<div class="sky-glow" id="glowB"></div>

<!-- digital city skyline -->
<div id="city"></div>
<span class="drone" style="top:22%;animation-duration:26s">🛸</span>
<span class="drone" style="top:34%;animation-duration:34s;animation-delay:-14s">🛸</span>
<span class="drone" style="top:14%;animation-duration:42s;animation-delay:-26s;font-size:13px">🛸</span>

<div id="shutter"></div>

<div id="boot">
  <div class="lab">Innovation HQ · Powering Up</div>
  <div class="bar"><i id="bootbar"></i></div>
</div>

<!-- HUD -->
<div id="hud">
  <div class="hud-chip" id="xpchip">⚡ <b id="xpval">0</b>&nbsp;XP</div>
  <div class="hud-chip" id="valchip">📈 <b id="valval">₹0</b>&nbsp;valuation</div>
  <div class="hud-chip" id="badgewrap-chip"><div id="badgewrap">
    <div class="badge" id="bd-emp" title="Customer Whisperer">🎧</div>
    <div class="badge" id="bd-def" title="Strategy Forger">💎</div>
    <div class="badge" id="bd-ide" title="Model Maker">🧬</div>
    <div class="badge" id="bd-pro" title="Launch Commander">🚀</div>
    <div class="badge" id="bd-fin" title="Design Thinking Entrepreneur">🏆</div>
  </div></div>
  <div class="tracker" id="tracker">
    <div class="dot" data-s="1" title="Empathy Valley">E</div>
    <div class="dot" data-s="2" title="Define Mountain">D</div>
    <div class="dot" data-s="3" title="Idea Forest">I</div>
    <div class="dot" data-s="4" title="Prototype City">P</div>
    <div class="dot" data-s="5" title="Business Arena">★</div>
  </div>
</div>

<!-- research board (flying notes land here) -->
<div id="board"></div>

<!-- ===== SCENE: TITLE ===== -->
<section class="scene" id="scene-title">
  <div class="scene-inner">
    <div class="eyebrow" style="justify-content:center">Innovation Headquarters · Sector 7</div>
    <div class="holo-title" id="holoTitle">
      <div class="scanline"></div>
      <h1>DESIGN<br>THINKING</h1>
    </div>
    <div class="tagline">Build · Innovate · Test · Transform</div>
    <div id="ticker"></div>
    <p class="lede" style="margin:0 auto">You're not here to read about design thinking. You're here to found a startup, interview real customers, and ship a business that survives testing — with Nova, your AI business mentor, at your side.</p>
    <button class="cta" id="startBtn">Start building</button>
  </div>
</section>

<!-- ===== SCENE: MISSION ===== -->
<section class="scene" id="scene-brief">
  <div class="scene-inner" style="max-width:680px">
    <div class="eyebrow">Founder briefing · Mission 01</div>
    <h2>Build a sustainable food delivery startup.</h2>
    <p class="lede">The city below eats badly, wastes mountains of food, and runs on chaotic deliveries. Investors believe one founder can fix all three. The board just transferred the mission to <b style="color:var(--ink)">you</b>.</p>
    <div class="glass" style="margin-top:20px;padding:20px">
      <p style="font-size:14px;line-height:1.75;color:var(--ink-dim)">Your build route:<br>
      <b style="color:var(--volt)">Empathy Valley</b> → interview customers ·
      <b style="color:var(--violet)">Define Mountain</b> → forge the opportunity ·
      <b style="color:var(--amber)">Idea Forest</b> → assemble business models ·
      <b style="color:var(--rose)">Prototype City</b> → build, launch & survive testing.</p>
      <p style="font-size:12.5px;margin-top:12px;color:var(--ink-dim)">📈 Every smart decision raises your <b style="color:var(--mint)">startup valuation</b>. Weak decisions cost you. Choose like a founder.</p>
    </div>
    <button class="cta" style="margin-top:24px" id="briefBtn">Deploy to Empathy Valley</button>
  </div>
</section>

<!-- ===== SCENE 1: EMPATHIZE ===== -->
<section class="scene" id="scene-emp">
  <div class="scene-inner">
    <div class="eyebrow">Round 1 · Empathy Valley</div>
    <h2>Founders who skip this round build products nobody wants.</h2>
    <p class="lede">Four people of the city are living the problem right now. Interview each one, then log the finding that captures a real <b style="color:var(--mint)">pain point</b> — not a surface complaint.</p>
    <div class="persona-row" id="personaRow"></div>
    <div class="dialog-panel glass" id="dialogPanel">
      <b id="dpName" style="font:700 16px var(--disp)"></b>
      <p class="quote" id="dpQuote"></p>
      <p style="font:600 11.5px var(--disp);letter-spacing:.1em;text-transform:uppercase;color:var(--ink-dim)">What goes on the research board?</p>
      <div id="dpOptions"></div>
    </div>
    <div id="oppZone">
      <h2 style="font-size:clamp(20px,3vw,28px)">Your research board is glowing. Where's the biggest opportunity?</h2>
      <p class="lede">A founder can't chase everything. Pick the opportunity hiding inside all four interviews.</p>
      <div id="oppOptions" style="margin-top:12px"></div>
    </div>
    <button class="cta" id="empDone" style="display:none;margin-top:22px">Merge insights into the customer map</button>
  </div>
</section>

<!-- ===== SCENE 2: DEFINE ===== -->
<section class="scene" id="scene-def">
  <div class="scene-inner">
    <div class="eyebrow">Round 2 · Define Mountain</div>
    <h2>Turn pain into a business opportunity.</h2>
    <p class="lede">The strategy room loaded your research. Sort each finding onto its holo-board — tap a finding, then tap a board.</p>
    <div class="chip-pool" id="chipPool"></div>
    <div class="define-grid">
      <div class="bucket glass b1" id="bucket1" data-b="demand"><h4>🍽️ Customers can't get what they need</h4><div class="bslot"></div></div>
      <div class="bucket glass b2" id="bucket2" data-b="supply"><h4>📦 The supply side runs blind</h4><div class="bslot"></div></div>
    </div>
    <div id="stmt-zone">
      <h2 style="font-size:clamp(20px,3vw,28px);margin-top:8px">Forge the problem statement.</h2>
      <p class="lede">Weak: "People need food." Strong statements name the customer, the need, and the why. Choose the one that deserves the crystal.</p>
      <div id="stmtOptions" style="margin-top:12px"></div>
      <div id="crystal"><i></i></div>
    </div>
    <div id="target-zone">
      <h2 style="font-size:clamp(20px,3vw,26px)">Lock your target customer.</h2>
      <p class="lede">Who does version one serve? "Everyone" is how startups die.</p>
      <div id="targetOptions" style="margin-top:12px"></div>
    </div>
    <button class="cta" id="defDone" style="display:none;margin-top:22px">Carry the crystal to Idea Forest</button>
  </div>
</section>

<!-- ===== SCENE 3: IDEATE ===== -->
<section class="scene" id="scene-ide">
  <div class="scene-inner">
    <div class="eyebrow">Round 3 · Idea Forest</div>
    <h2>Product + Technology + Customer need = Business model.</h2>
    <p class="lede">The innovation chambers are open. Pick <b style="color:var(--volt)">one card from each column</b> and fuse them. Build <b style="color:var(--mint)">two business models</b>, then choose the one your startup will bet on.</p>
    <div class="builder" id="builder"></div>
    <div class="fuse-row">
      <div class="fuse-eq" id="fuseEq">Pick one card from each column…</div>
      <button class="cta" id="fuseBtn" disabled>⚡ Fuse business model</button>
    </div>
    <div class="models" id="modelList"></div>
    <button class="cta" id="ideDone" style="display:none;margin-top:20px">Take this model to Prototype City</button>
  </div>
</section>

<!-- ===== SCENE 4: PROTOTYPE ===== -->
<section class="scene" id="scene-pro">
  <div class="scene-inner">
    <div class="eyebrow">Round 4 · Prototype City</div>
    <h2>Assemble the launch version of <span id="chosenModelName" style="color:var(--volt)">your startup</span>.</h2>
    <p class="lede">Five founding decisions: product, business model, customer experience, marketing, technology. One choice per category — the fabricator builds in real time.</p>
    <div class="deck" id="deck"></div>
    <button class="cta" id="buildBtn" style="margin-top:22px" disabled>Launch prototype (5 decisions needed)</button>
    <div id="launchpad">
      <div class="machine">
        <p style="font:700 11px var(--disp);letter-spacing:.2em;text-transform:uppercase;color:var(--volt);margin-bottom:12px;position:relative">Startup Fabricator · v1.0</p>
        <div class="slots" id="slotGrid">
          <div class="slot wide" id="slot0">product</div>
          <div class="slot" id="slot1">business model</div><div class="slot" id="slot2">experience</div>
          <div class="slot" id="slot3">marketing</div><div class="slot" id="slot4">technology</div>
        </div>
      </div>
      <div class="testers" id="testerList"></div>
      <div id="improveZone" style="display:none;margin-top:16px">
        <p class="lede"><b style="color:var(--rose)">The market pushed back.</b> Tap the flagged decision above to pivot — every great startup iterates.</p>
      </div>
      <button class="cta" id="proDone" style="display:none;margin-top:18px">Enter the Business Arena</button>
    </div>
  </div>
</section>

<!-- ===== SCENE 5: ARENA ===== -->
<section class="scene" id="scene-fin">
  <div class="scene-inner">
    <div class="eyebrow">Final · Business Arena</div>
    <h2>The board reviews your company.</h2>
    <div class="score-grid" id="scoreGrid"></div>
    <div class="glass" id="level-banner">
      <p style="font:600 11px var(--disp);letter-spacing:.3em;text-transform:uppercase;color:var(--ink-dim)">Founder rank unlocked</p>
      <div class="lvl" id="levelName">—</div>
      <p class="lede" style="margin:8px auto 0;max-width:500px" id="levelDesc"></p>
    </div>
    <div id="cert">
      <p class="cert-line" style="margin-top:0">Founder's certificate · Design Thinking</p>
      <p style="margin:14px 0 6px;color:var(--ink-dim);font-size:13px">This certifies that</p>
      <input id="certName" placeholder="type your name" maxlength="32">
      <p style="margin-top:10px;color:var(--ink-dim);font-size:13px">founded <b style="color:var(--volt)" id="certCo">a startup</b>, reached a valuation of <b style="color:var(--mint)" id="certVal">₹0</b> and earned <b style="color:var(--amber)"><span id="certXP">0</span> XP</b>.</p>
      <p class="cert-line">Empathize · Define · Ideate · Prototype · Test</p>
    </div>
    <div style="display:flex;gap:12px;margin-top:22px;flex-wrap:wrap">
      <button class="cta" id="replayBtn">Found another startup</button>
    </div>
    <footer-spacer></footer-spacer>
  </div>
</section>

<!-- ===== NOVA ===== -->
<div class="thought-dots" id="thoughtDots"><i></i><i></i><i></i></div>
<div id="nova-dock">
  <svg id="nova" viewBox="0 0 128 158" aria-label="Nova, your AI business mentor">
    <g class="breathe">
      <ellipse cx="64" cy="150" rx="30" ry="6" fill="rgba(0,0,0,.45)"/>
      <g class="legs">
        <rect x="50" y="118" width="10" height="22" rx="5" fill="#19233E"/>
        <rect x="68" y="118" width="10" height="22" rx="5" fill="#19233E"/>
        <ellipse cx="55" cy="142" rx="9" ry="5" fill="#37D1FF"/>
        <ellipse cx="73" cy="142" rx="9" ry="5" fill="#37D1FF"/>
      </g>
      <g class="armL">
        <rect x="30" y="84" width="12" height="30" rx="6" fill="#19233E"/>
        <circle cx="36" cy="116" r="7" fill="#37D1FF"/>
      </g>
      <g class="armR">
        <rect x="86" y="84" width="12" height="30" rx="6" fill="#19233E"/>
        <circle cx="92" cy="116" r="7" fill="#37D1FF"/>
      </g>
      <rect x="40" y="76" width="48" height="50" rx="18" fill="url(#bodyGrad)"/>
      <!-- tie: business mentor detail -->
      <path d="M64 78 l5 7 -5 16 -5 -16 z" fill="#FFB454"/>
      <circle cx="64" cy="104" r="7" fill="#04111F"/>
      <circle cx="64" cy="104" r="4.4" fill="#5CF2B8" class="ring-glow"/>
      <circle cx="64" cy="46" r="34" fill="url(#headGrad)" stroke="rgba(160,210,255,.3)" stroke-width="1.5"/>
      <ellipse cx="50" cy="30" rx="10" ry="6" fill="rgba(255,255,255,.3)"/>
      <g class="face">
        <g class="pupils" id="pupils">
          <circle cx="52" cy="46" r="5.5" fill="#EBF3FF"/>
          <circle cx="76" cy="46" r="5.5" fill="#EBF3FF"/>
          <circle cx="52" cy="46" r="2.6" fill="#04111F"/>
          <circle cx="76" cy="46" r="2.6" fill="#04111F"/>
        </g>
        <rect class="lid" x="45" y="40" width="14" height="12" rx="6" fill="#101A30"/>
        <rect class="lid" x="69" y="40" width="14" height="12" rx="6" fill="#101A30"/>
        <rect class="browL" x="46" y="33" width="12" height="3" rx="1.5" fill="#EBF3FF" opacity=".8"/>
        <rect class="browR" x="70" y="33" width="12" height="3" rx="1.5" fill="#EBF3FF" opacity=".8"/>
        <rect class="mouth" x="58" y="58" width="12" height="5" rx="2.5" fill="#37D1FF"/>
      </g>
      <line x1="64" y1="12" x2="64" y2="4" stroke="#37D1FF" stroke-width="2.5"/>
      <circle cx="64" cy="3.5" r="3.5" fill="#FFB454" class="ring-glow"/>
    </g>
    <defs>
      <linearGradient id="headGrad" x1="0" y1="0" x2="1" y2="1">
        <stop offset="0" stop-color="#16224A"/><stop offset="1" stop-color="#0B1228"/>
      </linearGradient>
      <linearGradient id="bodyGrad" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0" stop-color="#233060"/><stop offset="1" stop-color="#121A3A"/>
      </linearGradient>
    </defs>
  </svg>
  <div id="nova-bubble"><span class="who">Nova · AI mentor</span><span id="novaText"></span></div>
</div>
<script>
/* ================= state ================= */
const S = {
  xp:0, val:0, stage:0,
  scores:{cu:0, pd:0, inn:0, pq:0, mp:0},
  empSolved:0, empAttempts:0, oppRight:false,
  defAttempts:0, stmtAttempts:0, targetRight:false,
  models:[], chosenModel:null,
  picks:{}, improved:false,
  idleTimer:null, talkTimer:null, bubbleTimer:null
};
const $ = s => document.querySelector(s);
const $$ = s => [...document.querySelectorAll(s)];
const fmtVal = v => v >= 10000000 ? '₹'+(v/10000000).toFixed(1)+' Cr' : '₹'+(v/100000).toFixed(1)+' L';

/* ================= skyline ================= */
(function buildCity(){
  let svg = `<svg viewBox="0 0 1200 220" preserveAspectRatio="xMidYMax slice">`;
  let x = 0, seed = 7;
  const rnd = ()=> (seed = (seed*9301+49297)%233280)/233280;
  while(x < 1200){
    const w = 36 + rnd()*70, h = 60 + rnd()*150, y = 220 - h;
    svg += `<rect x="${x}" y="${y}" width="${w}" height="${h}" fill="#070F1E" stroke="rgba(55,209,255,.12)" stroke-width="1"/>`;
    if(rnd() > .55) svg += `<rect x="${x+w*.3}" y="${y-8}" width="2" height="8" fill="#37D1FF" opacity=".8"/>`;
    for(let wy = y+10; wy < 210; wy += 16){
      for(let wx = x+6; wx < x+w-8; wx += 13){
        const lit = rnd() > .6;
        svg += `<rect class="win ${lit ? (rnd()>.5?'lit c':'lit') : ''}" x="${wx}" y="${wy}" width="6" height="8" style="animation-delay:${(rnd()*5).toFixed(1)}s"/>`;
      }
    }
    x += w + 8 + rnd()*22;
  }
  svg += `</svg>`;
  $('#city').innerHTML = svg;
})();

/* ================= starfield + particles ================= */
const cv = $('#stars'), cx = cv.getContext('2d');
let stars = [], motes = [];
function sizeCanvas(){ cv.width = innerWidth; cv.height = innerHeight; }
sizeCanvas(); addEventListener('resize', sizeCanvas);
for(let i=0;i<130;i++) stars.push({x:Math.random(),y:Math.random()*.8,r:Math.random()*1.4+.3,tw:Math.random()*6.3,sp:.4+Math.random()});
for(let i=0;i<30;i++) motes.push({x:Math.random(),y:Math.random(),r:Math.random()*2.4+.8,vy:-(.06+Math.random()*.12),vx:(Math.random()-.5)*.05,hue:Math.random()<.5?'55,209,255':'92,242,184',a:.1+Math.random()*.22});
let px=0, py=0;
addEventListener('mousemove', e=>{ px=(e.clientX/innerWidth-.5); py=(e.clientY/innerHeight-.5); novaEyes(e); pokeIdle(); });
addEventListener('touchstart', pokeIdle, {passive:true});
function drawBG(t){
  cx.clearRect(0,0,cv.width,cv.height);
  for(const s of stars){
    const a = .3 + .7*Math.abs(Math.sin(t/900*s.sp + s.tw));
    cx.fillStyle = `rgba(235,243,255,${a*.75})`;
    cx.beginPath(); cx.arc(s.x*cv.width + px*18, s.y*cv.height + py*12, s.r, 0, 7); cx.fill();
  }
  for(const m of motes){
    m.y += m.vy/100; m.x += m.vx/100;
    if(m.y < -0.05){ m.y = 1.05; m.x = Math.random(); }
    if(m.x < -0.05) m.x = 1.05; if(m.x > 1.05) m.x = -0.05;
    cx.fillStyle = `rgba(${m.hue},${m.a})`;
    cx.beginPath(); cx.arc(m.x*cv.width + px*40, m.y*cv.height + py*26, m.r, 0, 7); cx.fill();
  }
  $('#glowA').style.transform = `translate(${px*-30}px,${py*-20}px)`;
  $('#glowB').style.transform = `translate(${px*30}px,${py*20}px)`;
  requestAnimationFrame(drawBG);
}
requestAnimationFrame(drawBG);

const moods = {
  'scene-title':['#0c3a5e','#23145e'], 'scene-brief':['#0c3a5e','#23145e'],
  'scene-emp':['#5e3a14','#0c3a5e'], 'scene-def':['#1d2a6e','#0c4a52'],
  'scene-ide':['#0e5436','#23145e'], 'scene-pro':['#5e1437','#1d2a6e'],
  'scene-fin':['#5e4a0c','#0c3a5e']
};
function setMood(id){
  const [a,b] = moods[id] || moods['scene-title'];
  $('#glowA').style.background = `radial-gradient(circle, ${a}, transparent 65%)`;
  $('#glowB').style.background = `radial-gradient(circle, ${b}, transparent 65%)`;
}

/* title ticker bars */
(function(){ const t = $('#ticker');
  for(let i=0;i<14;i++){ const b=document.createElement('i'); b.className='bar';
    b.style.height=(14+Math.random()*40)+'px'; b.style.animationDelay=(i*.16)+'s';
    if(i%4===3) b.style.background='linear-gradient(180deg,var(--mint),rgba(92,242,184,.1))';
    t.appendChild(b);} })();

/* ================= Nova engine ================= */
const nova = $('#nova'), bubble = $('#nova-bubble'), novaTxt = $('#novaText');
function novaEyes(e){
  const r = nova.getBoundingClientRect();
  const cxm = r.left + r.width*.5, cym = r.top + r.height*.32;
  const dx = Math.max(-1, Math.min(1, (e.clientX - cxm)/300));
  const dy = Math.max(-1, Math.min(1, (e.clientY - cym)/300));
  $('#pupils').style.transform = `translate(${dx*3.4}px, ${dy*2.6}px)`;
}
setInterval(()=>{ nova.classList.add('blink'); setTimeout(()=>nova.classList.remove('blink'), 130); }, 3300 + Math.random()*1400);
function novaPose(pose, ms=1600){
  ['wave','point','think','celebrate','confused'].forEach(p=>nova.classList.remove(p));
  if(pose){ nova.classList.add(pose); if(ms) setTimeout(()=>nova.classList.remove(pose), ms); }
  $('#thoughtDots').classList.toggle('on', pose==='think');
  if(pose!=='think') $('#thoughtDots').classList.remove('on');
}
function novaSay(text, pose, hold){
  clearTimeout(S.bubbleTimer); clearInterval(S.talkTimer);
  if(pose!==undefined) novaPose(pose, pose==='think'?2600:1600);
  bubble.classList.add('show'); nova.classList.add('talk');
  novaTxt.textContent = '';
  let i = 0;
  S.talkTimer = setInterval(()=>{
    novaTxt.textContent = text.slice(0, ++i);
    if(i >= text.length){ clearInterval(S.talkTimer); nova.classList.remove('talk');
      S.bubbleTimer = setTimeout(()=>bubble.classList.remove('show'), hold || (2600 + text.length*28));
    }
  }, 14);
}
const nudges = [
  "Need a little help?",
  "Let's analyze the situation together.",
  "Great businesses start with understanding people.",
  "Investors are patient. Markets aren't. Shall we?",
  "Take your time -- but the city's still hungry."
];
function pokeIdle(){
  clearTimeout(S.idleTimer);
  if(S.stage===0) return;
  S.idleTimer = setTimeout(()=>{ novaSay(nudges[Math.floor(Math.random()*nudges.length)], 'wave'); pokeIdle(); }, 26000);
}
document.addEventListener('mouseover', e=>{
  if(e.target.closest('.cta, .opt, .bcard, .copt, .model')) { if(!nova.classList.contains('celebrate')) novaPose('point', 900); }
});

/* ================= XP / valuation / badges / confetti ================= */
function gainXP(n, x, y){
  S.xp += n; $('#xpval').textContent = S.xp;
  const f = document.createElement('div'); f.className='xp-float'; f.textContent = `+${n} XP`;
  f.style.left = (x ?? innerWidth*.5)+'px'; f.style.top = (y ?? innerHeight*.4)+'px';
  document.body.appendChild(f); setTimeout(()=>f.remove(), 1200);
}
function gainVal(n, x, y){
  S.val = Math.max(0, S.val + n); $('#valval').textContent = fmtVal(S.val);
  const f = document.createElement('div'); f.className='xp-float green';
  f.textContent = (n>=0?'+':'−') + fmtVal(Math.abs(n)).replace('₹','₹');
  f.style.left = ((x ?? innerWidth*.5)+60)+'px'; f.style.top = (y ?? innerHeight*.42)+'px';
  document.body.appendChild(f); setTimeout(()=>f.remove(), 1200);
}
function winBadge(id){ const b = $('#bd-'+id); if(b && !b.classList.contains('won')) b.classList.add('won'); }
function confetti(n=70){
  const colors = ['#FFB454','#37D1FF','#5CF2B8','#8E7BFF','#EBF3FF'];
  for(let i=0;i<n;i++){
    const c = document.createElement('i'); c.className='confetti';
    c.style.left = Math.random()*100+'vw'; c.style.top='-12px';
    c.style.background = colors[i%colors.length];
    c.style.animationDuration = (1.6+Math.random()*1.8)+'s';
    c.style.animationDelay = Math.random()*.5+'s';
    if(Math.random()<.4) c.style.borderRadius='50%';
    document.body.appendChild(c); setTimeout(()=>c.remove(), 4200);
  }
}
function burst(x, y){
  for(let i=0;i<14;i++){
    const p = document.createElement('i'); p.className='confetti';
    p.style.left=x+'px'; p.style.top=y+'px'; p.style.position='fixed';
    p.style.background = i%2 ? 'var(--volt)' : 'var(--mint)';
    p.style.animation='none'; p.style.borderRadius='50%';
    document.body.appendChild(p);
    const a = Math.random()*Math.PI*2, d = 40+Math.random()*70;
    p.animate([{transform:'translate(0,0) scale(1)',opacity:1},{transform:`translate(${Math.cos(a)*d}px,${Math.sin(a)*d}px) scale(.2)`,opacity:0}],{duration:650+Math.random()*300,easing:'cubic-bezier(.2,.8,.3,1)'}).onfinish=()=>p.remove();
  }
}

/* ================= routing ================= */
function goScene(id, stageNum, onIn){
  $('#shutter').classList.add('on');
  $('#nova-dock').style.transform = 'translateX(40vw)';
  setTimeout(()=>{
    $$('.scene').forEach(s=>s.classList.remove('active'));
    $('#'+id).classList.add('active');
    $('#'+id).scrollTop = 0;
    setMood(id);
    if(stageNum !== undefined){
      S.stage = stageNum;
      $$('.tracker .dot').forEach(d=>{
        const n = +d.dataset.s;
        d.classList.toggle('done', n < stageNum);
        d.classList.toggle('now', n === stageNum);
      });
    }
    $('#shutter').classList.remove('on');
    $('#nova-dock').style.transform = 'translateX(0)';
    if(onIn) setTimeout(onIn, 650);
    pokeIdle();
  }, 600);
}

/* ================= boot + opening ================= */
let bootP = 0;
const bootInt = setInterval(()=>{
  bootP = Math.min(100, bootP + 9 + Math.random()*14);
  $('#bootbar').style.width = bootP + '%';
  if(bootP >= 100){
    clearInterval(bootInt);
    setTimeout(()=>{
      $('#boot').classList.add('gone');
      $('#scene-title').classList.add('active');
      setMood('scene-title');
      $('#nova-dock').style.transform = 'translateX(-60vw)';
      requestAnimationFrame(()=>requestAnimationFrame(()=>{ $('#nova-dock').style.transform = 'translateX(0)'; }));
      setTimeout(()=>{
        $('#holoTitle').classList.add('in');
        novaSay("Welcome to Design Thinking. Today you will build a business -- from an idea to a tested solution. I'm Nova, your mentor. Press Start building.", 'wave');
      }, 1100);
    }, 350);
  }
}, 140);

$('#startBtn').onclick = ()=>{
  $('#hud').classList.add('show');
  gainXP(10); gainVal(100000);
  goScene('scene-brief', 0, ()=> novaSay("Your mission, founder. Read it twice -- everything we build flows from it.", 'point'));
};
$('#briefBtn').onclick = ()=>{
  goScene('scene-emp', 1, ()=>{ initEmpathy(); novaSay("Empathy Valley. Most founders start with their idea. We start with their people. Tap someone and really listen.", 'point'); });
};
</script>
<script>
/* ================= ROUND 1 ================= */
const personas = [
  { id:'student', face:'🧑‍🎓', name:'Zoya', role:'Student, hostel life',
    quote:"I study till 1 a.m. and that's exactly when I'm starving. By then it's greasy leftovers or instant noodles -- the third night in a row. Healthy food after 10 p.m. basically doesn't exist here.",
    options:[
      {t:"Zoya should cook meals in advance on weekends.", ok:false, why:"That's advice, not research. In Empathy Valley we collect understanding, not solutions."},
      {t:"Zoya's real hunger window opens exactly when healthy options shut down.", ok:true, chip:"Healthy options vanish exactly when Zoya needs them", b:'demand', v:300000},
      {t:"Zoya eats instant noodles sometimes.", ok:false, why:"Surface fact. The pain is in the timing mismatch -- listen again."}
    ]},
  { id:'pro', face:'👩‍💼', name:'Aarav', role:'Working professional',
    quote:"I get 30 minutes for lunch. The healthy places take 50 minutes to deliver and cost like a small festival. So I eat whatever arrives fast -- and feel like a sandbag by 4 p.m.",
    options:[
      {t:"Aarav doesn't care about his health.", ok:false, why:"He clearly does -- he's frustrated he can't act on it. Don't invent attitudes."},
      {t:"Healthy food fails Aarav on the two things he can't flex: time and price.", ok:true, chip:"For Aarav, healthy = too slow AND too pricey", b:'demand', v:300000},
      {t:"Aarav has short lunch breaks.", ok:false, why:"True, but it's only half the picture. What collides with that short break?"}
    ]},
  { id:'owner', face:'👨‍🍳', name:'Priya', role:'Restaurant owner',
    quote:"Every night I throw away food that was perfectly good at 7 p.m. Demand is a mystery -- Tuesday I run out by 8, Wednesday I bin half my stock. I'm cooking blindfolded.",
    options:[
      {t:"Priya wastes good food because she can't see demand coming.", ok:true, chip:"Priya cooks blind -- unpredictable demand creates waste", b:'supply', v:300000},
      {t:"Priya should simply cook less food.", ok:false, why:"Then she runs out on busy days. The problem is visibility, not volume -- re-listen."},
      {t:"Priya throws away food at night.", ok:false, why:"That's the symptom. The insight is WHY it happens."}
    ]},
  { id:'rider', face:'🛵', name:'Karan', role:'Delivery partner',
    quote:"I do five trips to the same tower in one hour -- separately. Then nothing for two hours, then chaos again. The routes make no sense and my fuel money disappears into the zigzag.",
    options:[
      {t:"Karan burns time and fuel because orders aren't batched or routed smartly.", ok:true, chip:"Karan's trips overlap & spike -- zero smart routing", b:'supply', v:300000},
      {t:"Karan should buy an electric scooter.", ok:false, why:"A fix, not a finding. And it wouldn't touch the zigzag problem."},
      {t:"Karan is sometimes idle between orders.", ok:false, why:"Half the story -- the waste in the busy hours is the louder pain."}
    ]}
];
const opps = [
  {t:"Build a premium late-night dessert delivery brand for students.", ok:false,
   why:"That serves one slice of one interview. Three of your four interviews go unanswered."},
  {t:"Connect surplus restaurant food to people who need fast, affordable healthy meals -- with smarter routing in between.", ok:true},
  {t:"Launch a cooking-class app so customers stop needing delivery.", ok:false,
   why:"Interesting -- but it ignores Priya's waste, Karan's routes, and Aarav's 30 minutes. The opportunity should connect the pains."}
];
let currentPersona = null;
function initEmpathy(){
  const row = $('#personaRow'); row.innerHTML = '';
  personas.forEach(p=>{
    const d = document.createElement('button');
    d.className = 'persona glass'; d.id = 'pp-'+p.id;
    d.innerHTML = `<span class="check">✔</span><span class="face">${p.face}</span><b>${p.name}</b><small>${p.role}</small>`;
    d.onclick = ()=> openPersona(p);
    row.appendChild(d);
  });
}
function openPersona(p){
  if($('#pp-'+p.id).classList.contains('solved')){ novaSay(`${p.name}'s finding is already on the research board. Interview someone new.`, 'point'); return; }
  currentPersona = p;
  $('#dpName').textContent = `${p.face} ${p.name} · ${p.role}`;
  $('#dpQuote').textContent = '“' + p.quote + '”';
  const wrap = $('#dpOptions'); wrap.innerHTML = '';
  p.options.forEach(o=>{
    const b = document.createElement('button'); b.className='opt'; b.textContent = o.t;
    b.onclick = (ev)=> answerEmpathy(o, b, ev);
    wrap.appendChild(b);
  });
  $('#dialogPanel').classList.add('open');
  $('#dialogPanel').scrollIntoView({behavior:'smooth', block:'nearest'});
  novaSay(`Interview mode. Don't note what ${p.name} said -- note what it *means* for the business.`, 'think', 4200);
}
function answerEmpathy(o, btn, ev){
  if(o.ok){
    btn.classList.add('right');
    S.empSolved++;
    gainXP(30, ev.clientX, ev.clientY); gainVal(o.v, ev.clientX, ev.clientY);
    $('#pp-'+currentPersona.id).classList.add('solved');
    const n = document.createElement('div'); n.className='note-fly'; n.textContent = '📌 ' + o.chip;
    n.style.left = ev.clientX+'px'; n.style.top = ev.clientY+'px';
    document.body.appendChild(n);
    requestAnimationFrame(()=>{ n.style.transition='all .9s cubic-bezier(.3,.8,.3,1)';
      n.style.left=(innerWidth-200)+'px'; n.style.top='80px'; n.style.opacity='0'; n.style.transform='scale(.6)'; });
    setTimeout(()=>{ n.remove();
      const note = document.createElement('div'); note.className='board-note'; note.textContent='📌 '+o.chip;
      $('#board').appendChild(note);
    }, 880);
    const praise = ["Logged. That's a finding with money in it.","Exactly -- you heard the business problem under the complaint.","Research board: growing. Investors love this part.","Sharp ears, founder."];
    novaSay(praise[S.empSolved % praise.length] + (S.empSolved<4 ? ` ${4-S.empSolved} interview${4-S.empSolved>1?'s':''} left.` : ""), 'celebrate');
    setTimeout(()=>{ $('#dialogPanel').classList.remove('open'); }, 900);
    if(S.empSolved === 4){
      setTimeout(()=>{
        $('#oppZone').classList.add('open');
        $('#oppZone').scrollIntoView({behavior:'smooth', block:'nearest'});
        novaSay("Four interviews, four pains. Now the founder question: where do they overlap? Pick the biggest opportunity.", 'think', 5200);
        renderOpps();
      }, 1400);
    }
  } else {
    btn.classList.add('wrong'); S.empAttempts++;
    gainVal(-50000, ev.clientX, ev.clientY);
    setTimeout(()=>btn.classList.remove('wrong'), 500);
    novaSay("Hmm. " + o.why, 'think', 5200);
  }
}
function renderOpps(){
  const w = $('#oppOptions'); w.innerHTML='';
  opps.forEach(o=>{
    const b = document.createElement('button'); b.className='opt'; b.textContent=o.t;
    b.onclick = (ev)=>{
      if(o.ok){
        b.classList.add('right'); S.oppRight = true;
        gainXP(40, ev.clientX, ev.clientY); gainVal(500000, ev.clientX, ev.clientY);
        $$('#oppOptions .opt').forEach(x=>{ if(x!==b) x.style.opacity='.35'; x.onclick=null; });
        $('#empDone').style.display='inline-block';
        novaSay("YES. One opportunity, four pains answered. THAT is pattern recognition. Merge the board into the customer map.", 'celebrate');
      } else {
        S.empAttempts++; b.classList.add('wrong'); gainVal(-100000, ev.clientX, ev.clientY);
        setTimeout(()=>b.classList.remove('wrong'), 500);
        novaSay(o.why, 'think', 5600);
      }
    };
    w.appendChild(b);
  });
}
$('#empDone').onclick = ()=>{
  S.scores.cu = Math.max(50, 100 - S.empAttempts*8);
  winBadge('emp'); confetti(50);
  novaSay("Customer map: formed and glowing. Great businesses solve real human problems -- and now we know ours. To the mountain!", 'celebrate');
  setTimeout(()=> goScene('scene-def', 2, ()=>{
    initDefine();
    novaSay("Define Mountain -- the strategy floor. Sort each finding onto the board where it belongs. Tap a finding, then a board.", 'point');
  }), 1700);
};

/* ================= ROUND 2 ================= */
const chips = [
  {t:"Healthy options vanish exactly when Zoya needs them", b:'demand'},
  {t:"For Aarav, healthy = too slow AND too pricey", b:'demand'},
  {t:"Lunch & midnight demand spikes go unserved", b:'demand'},
  {t:"Priya cooks blind -- unpredictable demand creates waste", b:'supply'},
  {t:"Karan's trips overlap & spike -- zero smart routing", b:'supply'},
  {t:"Perfectly good surplus food gets binned nightly", b:'supply'}
];
const stmts = [
  {t:"People in the city need food.", ok:false,
   why:"Weak. True of every city since cities existed. A statement this wide can't aim a business."},
  {t:"Busy professionals and students need affordable healthy meals delivered fast -- while restaurants waste the very food that could feed them.", ok:true},
  {t:"The city needs our AI-powered food delivery app with smart routing.", ok:false,
   why:"That's your solution in a trench coat. Problem statements never name the product."}
];
const targets = [
  {t:"🌍 Everyone who eats food in the city", ok:false, why:"\"Everyone\" means a product built for no one. Focus wins beachheads."},
  {t:"🎯 Busy professionals + late-night students", ok:true},
  {t:"✈️ Tourists visiting on weekends", ok:false, why:"They weren't in a single interview. Build on the pain you actually found."}
];
let selChip = null, sorted = 0;
function initDefine(){
  $('#board').innerHTML = '';
  const pool = $('#chipPool'); pool.innerHTML = '';
  chips.forEach(c=>{
    const el = document.createElement('button'); el.className='ichip'; el.textContent='📌 '+c.t; el.dataset.b=c.b;
    el.onclick = ()=>{
      $$('.chip-pool .ichip').forEach(x=>x.classList.remove('sel'));
      el.classList.add('sel'); selChip = el;
      $$('.bucket').forEach(b=>b.classList.add('armed'));
      novaPose('point', 800);
    };
    pool.appendChild(el);
  });
  $$('.bucket').forEach(b=>{
    b.onclick = (ev)=>{
      if(!selChip){ novaSay("Pick a finding first, then tap its board.", 'think', 3000); return; }
      if(b.dataset.b === selChip.dataset.b){
        selChip.classList.remove('sel'); selChip.classList.add('ok');
        b.querySelector('.bslot').appendChild(selChip);
        selChip.onclick = null; selChip = null; sorted++;
        gainXP(20, ev.clientX, ev.clientY); gainVal(150000, ev.clientX, ev.clientY);
        $$('.bucket').forEach(x=>x.classList.remove('armed'));
        if(sorted === chips.length){
          $$('.bucket').forEach(x=>x.classList.add('glowok'));
          novaSay("Patterns found: a starving demand side and a blindfolded supply side. Connect those two and you have a company. Forge the statement.", 'celebrate');
          openStatement();
        } else novaPose('celebrate', 900);
      } else {
        S.defAttempts++; gainVal(-50000, ev.clientX, ev.clientY);
        selChip.classList.add('sel');
        b.style.borderColor = 'var(--rose)';
        setTimeout(()=>b.style.borderColor='', 600);
        novaSay("Read it once more -- is this about customers not *getting* what they need, or the supply side running *blind*?", 'think', 5200);
      }
    };
  });
}
function openStatement(){
  const z = $('#stmt-zone'); z.classList.add('open');
  const w = $('#stmtOptions'); w.innerHTML='';
  stmts.sort(()=>Math.random()-.5).forEach(s=>{
    const b = document.createElement('button'); b.className='opt'; b.textContent=s.t;
    b.onclick = (ev)=>{
      if(s.ok){
        b.classList.add('right'); gainXP(40, ev.clientX, ev.clientY); gainVal(700000, ev.clientX, ev.clientY);
        $('#crystal').classList.add('on');
        $$('#stmtOptions .opt').forEach(x=>{ if(x!==b) x.style.opacity='.35'; x.onclick=null; });
        novaSay("Customer ✓ need ✓ reason ✓ -- and no product hiding inside. The statement crystallized. Now we know what problem our business will solve.", 'celebrate');
        setTimeout(openTarget, 1300);
      } else {
        S.stmtAttempts++; b.classList.add('wrong'); gainVal(-100000, ev.clientX, ev.clientY);
        setTimeout(()=>b.classList.remove('wrong'), 500);
        novaSay(s.why, 'think', 5600);
      }
    };
    w.appendChild(b);
  });
  setTimeout(()=>z.scrollIntoView({behavior:'smooth', block:'nearest'}), 300);
}
function openTarget(){
  const z = $('#target-zone'); z.classList.add('open');
  const w = $('#targetOptions'); w.innerHTML='';
  targets.forEach(t=>{
    const b = document.createElement('button'); b.className='opt'; b.textContent=t.t;
    b.onclick = (ev)=>{
      if(t.ok){
        b.classList.add('right'); S.targetRight = true;
        gainXP(30, ev.clientX, ev.clientY); gainVal(500000, ev.clientX, ev.clientY);
        $$('#targetOptions .opt').forEach(x=>{ if(x!==b) x.style.opacity='.35'; x.onclick=null; });
        S.scores.pd = Math.max(50, 100 - (S.defAttempts + S.stmtAttempts)*8);
        winBadge('def'); confetti(40);
        $('#defDone').style.display='inline-block';
        novaSay("Target locked: the exact people from your interviews. The mountain approves. The forest is next -- bring your imagination.", 'celebrate');
      } else {
        S.stmtAttempts++; b.classList.add('wrong'); gainVal(-100000, ev.clientX, ev.clientY);
        setTimeout(()=>b.classList.remove('wrong'), 500);
        novaSay(t.why, 'think', 5200);
      }
    };
    w.appendChild(b);
  });
  setTimeout(()=>z.scrollIntoView({behavior:'smooth', block:'nearest'}), 300);
}
$('#defDone').onclick = ()=> goScene('scene-ide', 3, ()=>{
  initIdeate();
  novaSay("The Idea Forest! Product plus technology plus customer need -- fuse them and business models grow on trees here. Literally. Pick one card per column.", 'wave');
});
</script>
<script>
/* ================= ROUND 3 · model builder ================= */
const cols = [
  {key:'prod', title:'Product', cards:[
    {id:'surplus', t:'🍱 Surplus-meal marketplace'},
    {id:'subs', t:'🥗 Healthy meal subscriptions'},
    {id:'cloud', t:'🏭 Late-night cloud kitchen'}
  ]},
  {key:'tech', title:'Technology', cards:[
    {id:'predict', t:'🔮 AI demand prediction'},
    {id:'routes', t:'🗺️ Smart route batching'},
    {id:'perso', t:'🤖 Personalization engine'}
  ]},
  {key:'need', title:'Customer need', cards:[
    {id:'fastcheap', t:'⚡ Affordable, healthy, fast'},
    {id:'latenight', t:'🌙 Late-night availability'},
    {id:'zerowaste', t:'♻️ Zero-waste values'}
  ]}
];
const modelNames = {
  'surplus+predict+fastcheap': {n:'FreshLoop', d:'Restaurants list tonight\'s surplus; AI predicts tomorrow\'s demand so they cook right -- customers get healthy meals at honest prices.', strong:true},
  'surplus+routes+zerowaste':  {n:'ZeroMile', d:'Surplus meals batched onto smart routes -- food rescued, fuel saved, the greenest plate in the city.', strong:true},
  'surplus+predict+zerowaste': {n:'SecondServe', d:'Prediction shrinks waste before it happens; whatever remains becomes affordable rescued meals.', strong:true},
  'cloud+routes+latenight':    {n:'MoonKitchen', d:'A late-night cloud kitchen with batched routes -- hot, healthy food at 1 a.m. without the chaos.', strong:true},
  'subs+perso+fastcheap':      {n:'DailyDabba', d:'Personalized healthy subscriptions tuned to budget and schedule -- lunch that lands inside Aarav\'s 30 minutes.', strong:true},
  'subs+predict+fastcheap':    {n:'PlanPlate', d:'Subscriptions give restaurants predictable demand; predictability makes meals cheaper. Everyone wins.', strong:true},
  'cloud+perso+latenight':     {n:'NightOwl Eats', d:'A midnight kitchen that learns what each night-studier craves.', strong:false},
  'subs+routes+zerowaste':     {n:'GreenTiffin', d:'Subscription tiffins on optimized loops -- steady, sustainable, a little sleepy on innovation.', strong:false},
  'surplus+perso+latenight':   {n:'Rescue Bites', d:'Personalized surplus deals for night owls -- charming, but supply at midnight is thin.', strong:false},
  'cloud+predict+fastcheap':   {n:'SmartStove', d:'A predictive kitchen for cheap healthy meals -- solid, though it leaves Priya\'s waste on the table.', strong:false}
};
let sel = {prod:null, tech:null, need:null};
function initIdeate(){
  const b = $('#builder'); b.innerHTML='';
  cols.forEach(c=>{
    const col = document.createElement('div'); col.className='bcol';
    col.innerHTML = `<h5>${c.title}</h5>`;
    c.cards.forEach(card=>{
      const el = document.createElement('button'); el.className='bcard'; el.id='bc-'+card.id; el.textContent=card.t;
      el.onclick = ()=>{
        if(el.classList.contains('spent')) return;
        $$('#builder .bcol').forEach((cc,i)=>{ if(cols[i].key===c.key) cc.querySelectorAll('.bcard').forEach(x=>x.classList.remove('sel')); });
        el.classList.add('sel'); sel[c.key] = card;
        updateFuse();
      };
      col.appendChild(el);
    });
    b.appendChild(col);
  });
  $('#modelList').innerHTML=''; sel={prod:null,tech:null,need:null};
}
function updateFuse(){
  const ready = sel.prod && sel.tech && sel.need;
  $('#fuseBtn').disabled = !ready;
  $('#fuseEq').textContent = ready
    ? `${sel.prod.t}  +  ${sel.tech.t}  +  ${sel.need.t}  =  ?`
    : 'Pick one card from each column…';
}
$('#fuseBtn').onclick = (ev)=>{
  const key = `${sel.prod.id}+${sel.tech.id}+${sel.need.id}`;
  const m = modelNames[key] || {n:'Hybrid Venture', d:`A fusion of ${sel.prod.t.slice(2).toLowerCase()}, ${sel.tech.t.slice(2).toLowerCase()} and ${sel.need.t.slice(2).toLowerCase()}.`, strong:false};
  ['prod','tech','need'].forEach(k=>{ const el=$('#bc-'+sel[k].id); el.classList.remove('sel'); el.classList.add('spent'); });
  burst(ev.clientX, ev.clientY);
  const card = document.createElement('div'); card.className = 'model'+(m.strong?' strong':'');
  card.innerHTML = `<span class="mtag">${m.strong?'⚡ high potential':'model'}</span>
    <div><b>${m.n}</b><p>${m.d}</p><span class="pick-hint">tap to bet on this model →</span></div>`;
  m.el = card;
  $('#modelList').appendChild(card);
  S.models.push(m);
  gainXP(m.strong?45:30, ev.clientX, ev.clientY); gainVal(m.strong?800000:400000, ev.clientX, ev.clientY);
  sel = {prod:null,tech:null,need:null}; updateFuse();
  if(S.models.length < 2){
    novaSay(m.strong
      ? `"${m.n}" -- now THAT has legs. One more model so we have options. Strategy means choosing between good things.`
      : `"${m.n}" -- workable. Build one more; let's see if you can find a sharper combination.`, 'celebrate');
  } else {
    $('#fuseBtn').style.display='none';
    S.models.forEach(mm=>{
      mm.el.classList.add('pickable');
      mm.el.onclick = ()=> chooseModel(mm);
    });
    novaSay("Two models on the table. Founders don't keep options forever -- tap the one your startup will bet on.", 'point');
  }
};
function chooseModel(m){
  S.chosenModel = m;
  S.models.forEach(x=>{ x.el.classList.remove('chosen','pickable'); x.el.onclick=null; });
  m.el.classList.add('chosen');
  S.scores.inn = 55 + S.models.filter(x=>x.strong).length*15 + (m.strong?15:0);
  winBadge('ide'); confetti(45);
  gainXP(30); gainVal(m.strong?1000000:300000);
  $('#ideDone').style.display='inline-block';
  novaSay(m.strong
    ? `"${m.n}" -- great ideas become great businesses when they solve real problems, and this one solves several. Prototype City, here we come.`
    : `"${m.n}" it is. Not the boldest play on the table -- but execution can outwork strategy. Let's build it well.`, m.strong?'celebrate':'think');
}
$('#ideDone').onclick = ()=> goScene('scene-pro', 4, ()=>{
  $('#chosenModelName').textContent = '“'+S.chosenModel.n+'”';
  $('#certCo').textContent = S.chosenModel.n;
  initProto();
  novaSay(`Prototype City. We assemble "${S.chosenModel.n}" v1 right here -- five founding decisions, then real customers test it. No pressure. Some pressure.`, 'point');
});

/* ================= ROUND 4 ================= */
const cats = [
  {key:'product', title:'🍱 Core product', opts:[
    {t:'Tonight\'s rescue menu', d:'Live surplus meals at honest prices, refreshed hourly.', v:3},
    {t:'Chef-story video feed', d:'Beautiful mini-documentaries about each restaurant.', v:1},
    {t:'NFT loyalty meal cards', d:'Collectible digital meal tokens.', v:0, weak:true, fb:'too complicated'}
  ]},
  {key:'biz', title:'💰 Business model', opts:[
    {t:'Pay-per-order + small restaurant fee', d:'Cheap to try, fair to partners, scales with trust.', v:3},
    {t:'Premium-only membership, ₹1999/mo', d:'Exclusive access for those who can pay.', v:0, weak:true, fb:'too expensive'},
    {t:'Free for all, ads everywhere', d:'No revenue from food; banner ads pay the bills.', v:1}
  ]},
  {key:'cx', title:'🤝 Customer experience', opts:[
    {t:'2-tap ordering, no account needed', d:'Phone number in, food out. Grandparent-proof.', v:3},
    {t:'10-step onboarding questionnaire', d:'Deep personalization… after 10 screens of forms.', v:0, weak:true, fb:'too complicated'},
    {t:'Chat-only ordering via support agents', d:'A human types your order for you.', v:1}
  ]},
  {key:'mkt', title:'📣 Marketing', opts:[
    {t:'Campus & office pilot programs', d:'Start exactly where your target customers live and work.', v:3},
    {t:'City-wide billboard blitz', d:'Maximum eyeballs, maximum burn rate.', v:1},
    {t:'Celebrity brand film', d:'One glorious ad, half the runway gone.', v:0, weak:true, fb:'too expensive'}
  ]},
  {key:'tech', title:'⚙️ Technology', opts:[
    {t:'Demand prediction + route batching', d:'The engine that kills waste and zigzag routes.', v:3},
    {t:'AR menu previews', d:'Spin a 3D biryani above your desk.', v:0, weak:true, fb:'too complicated'},
    {t:'Basic website + spreadsheets', d:'Scrappy and honest; creaks at scale.', v:1}
  ]}
];
const pivots = {
  product:{t:'Tonight\'s rescue menu', d:'Pivoted after testing: customers wanted the food, not the gimmick.', v:3},
  biz:{t:'Pay-per-order + small restaurant fee', d:'Pivoted after testing: priced for students AND professionals.', v:3},
  cx:{t:'2-tap ordering, no account needed', d:'Pivoted after testing: friction deleted.', v:3},
  mkt:{t:'Campus & office pilot programs', d:'Pivoted after testing: aimed at the actual target.', v:3},
  tech:{t:'Demand prediction + route batching', d:'Pivoted after testing: the engine the model needed.', v:3}
};
let testPhase = 0;
function initProto(){
  S.picks = {}; testPhase = 0; S.improved = false;
  $('#launchpad').classList.remove('open');
  $('#testerList').innerHTML=''; $('#improveZone').style.display='none'; $('#proDone').style.display='none';
  const d = $('#deck'); d.innerHTML='';
  cats.forEach(c=>{
    const sec = document.createElement('div'); sec.className='cat';
    sec.innerHTML = `<h5>${c.title}</h5>`;
    const grid = document.createElement('div'); grid.className='cat-opts';
    c.opts.forEach(o=>{
      const el = document.createElement('button'); el.className='copt';
      el.innerHTML = `<b>${o.t}</b><small>${o.d}</small>`;
      el.onclick = ()=>{
        if(testPhase>0) return;
        grid.querySelectorAll('.copt').forEach(x=>x.classList.remove('picked'));
        el.classList.add('picked');
        S.picks[c.key] = {...o, cat:c.key, el, grid};
        const n = Object.keys(S.picks).length;
        $('#buildBtn').disabled = n !== 5;
        $('#buildBtn').textContent = n===5 ? '🚀 Launch prototype' : `Launch prototype (${5-n} decision${5-n>1?'s':''} left)`;
      };
      grid.appendChild(el);
    });
    sec.appendChild(grid); d.appendChild(sec);
  });
  $('#buildBtn').disabled = true; $('#buildBtn').style.display='';
  $('#buildBtn').textContent = 'Launch prototype (5 decisions needed)';
}
const slotOrder = ['product','biz','cx','mkt','tech'];
$('#buildBtn').onclick = ()=>{
  testPhase = 1;
  $('#buildBtn').style.display='none';
  $('#launchpad').classList.add('open');
  slotOrder.forEach((k,i)=>{
    setTimeout(()=>{
      const s = $('#slot'+i); s.classList.add('fill'); s.textContent = S.picks[k].t;
      gainXP(12);
    }, 350 + i*380);
  });
  setTimeout(()=>{
    $('#launchpad').scrollIntoView({behavior:'smooth', block:'nearest'});
    novaSay("v1.0 assembled and live in the testing district. Virtual customers incoming -- whatever they say, remember: feedback is free consulting.", 'celebrate');
    runTesters();
  }, 350 + 5*380 + 400);
};
function runTesters(){
  const list = $('#testerList'); list.innerHTML='';
  const weakPicks = Object.values(S.picks).filter(p=>p.weak);
  const fb = [];
  fb.push({f:'🧑‍🎓', n:'Zoya', pos:true, t:`Ordered at 12:40 a.m. -- real food, real fast. "This solves my problem." Direct quote. From me. Just now.`});
  fb.push({f:'👨‍🍳', n:'Priya', pos:true, t:`First week ever I didn't bin a single tray. Whatever your machine predicts, it predicts well.`});
  if(weakPicks.length){
    const w = weakPicks[0];
    const line = w.fb === 'too expensive'
      ? `I did the math on "${w.t}" -- ${w.fb}. I earn a salary, not a treasury. I'm out until this changes.`
      : `I tried "${w.t}" three times and gave up. ${w.fb[0].toUpperCase()+w.fb.slice(1)}. I just want food, not a puzzle.`;
    fb.push({f:'👩‍💼', n:'Aarav', pos:false, t:line});
  } else {
    fb.push({f:'👩‍💼', n:'Aarav', pos:false, t:`Honestly? It works. But one of these choices is the weakest link -- a sharper option exists and your competitors will find it.`});
  }
  fb.forEach((x,i)=>{
    const t = document.createElement('div'); t.className='tester '+(x.pos?'pos':'neg');
    t.innerHTML = `<span class="tface">${x.f}</span><div><b style="font:700 12px var(--disp)">${x.n}</b><br>${x.t}</div>`;
    list.appendChild(t);
    setTimeout(()=>t.classList.add('in'), 500 + i*800);
  });
  setTimeout(()=>{
    testPhase = 2;
    const weak = weakPicks[0] || Object.values(S.picks).reduce((a,b)=> a.v <= b.v ? a : b);
    S.weakOne = weak;
    $('#improveZone').style.display='block';
    weak.el.classList.add('weakflag');
    weak.el.onclick = ()=> doImprove(weak);
    novaSay("Hear that? That's not failure -- that's a map. Tap the flagged decision and pivot. Iteration IS the method.", 'point');
  }, 500 + fb.length*800 + 900);
}
function doImprove(weak){
  if(testPhase !== 2) return;
  testPhase = 3; S.improved = true;
  const piv = pivots[weak.cat];
  weak.el.classList.remove('weakflag','picked'); weak.el.style.opacity='.35'; weak.el.onclick=null;
  S.picks[weak.cat] = {...piv, cat:weak.cat};
  const idx = slotOrder.indexOf(weak.cat);
  const s = $('#slot'+idx); s.classList.remove('fill');
  setTimeout(()=>{ s.classList.add('fill'); s.textContent = piv.t; }, 250);
  gainXP(50); gainVal(1500000);
  const base = Object.values(S.picks).reduce((a,p)=>a+p.v,0); // max 15
  S.scores.pq = Math.min(100, Math.round(base/15*78) + 22);
  winBadge('pro'); confetti(55);
  const t = document.createElement('div'); t.className='tester pos in';
  t.innerHTML = `<span class="tface">👩‍💼</span><div><b style="font:700 12px var(--disp)">Aarav</b><br>"Okay. NOW it fits my lunch break and my wallet. Tell the founder they actually listen -- rare species."</div>`;
  $('#testerList').appendChild(t);
  $('#proDone').style.display='inline-block';
  novaSay("v1.1 shipped -- built, tested, improved. That loop you just ran? Founders pay consultants crores to learn it. The Arena awaits.", 'celebrate');
}
$('#proDone').onclick = ()=> goScene('scene-fin', 5, finale);

/* ================= FINALE ================= */
function finale(){
  if(!S.scores.pq){ const base = Object.values(S.picks).reduce((a,p)=>a+p.v,0); S.scores.pq = Math.round(base/15*78); }
  S.scores.mp = Math.min(100, 40 + (S.chosenModel.strong?25:8) + (S.targetRight?15:0) + (S.picks.biz && S.picks.biz.v===3?15:0) + (S.improved?5:0));
  const overall = Math.round((S.scores.cu + S.scores.pd + S.scores.inn + S.scores.pq + S.scores.mp)/5);
  const data = [
    {k:'Customer understanding', v:S.scores.cu, c:'#FFB454'},
    {k:'Problem definition', v:S.scores.pd, c:'#8E7BFF'},
    {k:'Innovation level', v:S.scores.inn, c:'#37D1FF'},
    {k:'Prototype quality', v:S.scores.pq, c:'#5CF2B8'},
    {k:'Market potential', v:S.scores.mp, c:'#FF6B8B'},
    {k:'Business success', v:overall, c:'#EBF3FF'}
  ];
  const g = $('#scoreGrid'); g.innerHTML='';
  data.forEach((d,i)=>{
    const card = document.createElement('div'); card.className='score-card glass';
    const circ = 2*Math.PI*40;
    card.innerHTML = `<div class="ring">
      <svg width="92" height="92"><circle cx="46" cy="46" r="40" fill="none" stroke="rgba(140,190,255,.1)" stroke-width="6"/>
      <circle class="arc" cx="46" cy="46" r="40" fill="none" stroke="${d.c}" stroke-width="6" stroke-linecap="round"
        stroke-dasharray="${circ}" stroke-dashoffset="${circ}"/></svg>
      <b>0</b></div><small>${d.k}</small>`;
    g.appendChild(card);
    setTimeout(()=>{
      card.querySelector('.arc').style.transition = 'stroke-dashoffset 1.4s cubic-bezier(.2,.8,.2,1)';
      card.querySelector('.arc').style.strokeDashoffset = circ*(1 - d.v/100);
      const bEl = card.querySelector('b'); let n=0;
      const ti = setInterval(()=>{ n+=2; if(n>=d.v){n=d.v; clearInterval(ti);} bEl.textContent=n; }, 24);
    }, 300 + i*220);
  });
  const lvls = [
    [0,  'Beginner Entrepreneur','You shipped a real venture end to end. Run it again -- your founder instincts compound fast.'],
    [62, 'Creative Builder','Strong listening, real ideas, a business that works. The city is eating better because of you.'],
    [78, 'Innovation Strategist','Sharp research, a high-potential model, smart pivots. Investors are circling.'],
    [90, 'Design Thinking Master','A near-flawless founding run. You didn\'t study design thinking -- you ran a company on it.']
  ];
  const lvl = lvls.filter(l=>overall>=l[0]).pop();
  setTimeout(()=>{
    $('#levelName').textContent = lvl[1];
    $('#levelDesc').textContent = lvl[2];
    $('#certXP').textContent = S.xp;
    gainVal(overall*100000);
    $('#certVal').textContent = fmtVal(S.val);
    winBadge('fin'); confetti(130); gainXP(100);
    novaSay(`${lvl[1]} -- business success score ${overall}. ${S.chosenModel.n} went from a stranger's complaint to a tested company. I'd invest. Sign your certificate, founder.`, 'celebrate');
  }, 1900);
}
$('#replayBtn').onclick = ()=> location.reload();
addEventListener('keydown', e=>{ if(e.key==='Enter' && S.stage===0 && $('#scene-title').classList.contains('active')) $('#startBtn').click(); pokeIdle(); });
</script>
</body>
</html>
