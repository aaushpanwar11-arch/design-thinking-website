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
