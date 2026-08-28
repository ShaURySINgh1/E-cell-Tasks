# E-cell


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>E-Cell — Startup Pitch</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800;900&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>

:root{
    --black:#070707;
    --black2:#111111;
    --white:#f7f5ef;
    --orange:#ff6900;
    --orange2:#ff8a32;
    --grey:#9b9b96;

    --radius:32px;
    --border:rgba(255,255,255,.12);
}

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:var(--black);
    color:var(--white);

    font-family:"DM Sans",sans-serif;

    overflow-x:hidden;
}

/* =====================================================
   TEXTURE
===================================================== */

body::before{
    content:"";

    position:fixed;
    inset:0;

    pointer-events:none;

    opacity:.055;

    z-index:100;

    background-image:
    url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.5'/%3E%3C/svg%3E");
}

/* =====================================================
   BACKGROUND
===================================================== */

.bg{
    position:fixed;
    inset:0;

    overflow:hidden;

    pointer-events:none;

    z-index:-5;

    background:
        radial-gradient(
            circle at 78% 18%,
            rgba(255,105,0,.28),
            transparent 27%
        ),
        radial-gradient(
            circle at 5% 80%,
            rgba(255,105,0,.10),
            transparent 28%
        ),
        #070707;
}

/* diagonal glass slab */

.bg::before{
    content:"";

    position:absolute;

    width:70vw;
    height:130vh;

    right:-25vw;
    top:-15vh;

    transform:rotate(17deg);

    background:
        linear-gradient(
            130deg,
            rgba(255,105,0,.20),
            rgba(255,105,0,.025)
        );

    border-left:1px solid rgba(255,255,255,.10);

    backdrop-filter:blur(30px);
}

/* orange glow */

.bg::after{
    content:"";

    position:absolute;

    width:500px;
    height:500px;

    right:8%;
    top:8%;

    background:var(--orange);

    filter:blur(180px);

    opacity:.16;
}

/* =====================================================
   MOVING GLASS PARTICLES
===================================================== */

.particle{
    position:fixed;

    width:10px;
    height:10px;

    border-radius:50%;

    background:
        rgba(255,105,0,.15);

    border:
        1px solid rgba(255,150,80,.4);

    box-shadow:
        inset 0 0 7px rgba(255,255,255,.15),
        0 0 25px rgba(255,105,0,.2);

    backdrop-filter:blur(10px);

    z-index:-1;

    transition:
        left 1s cubic-bezier(.2,.8,.2,1),
        top 1s cubic-bezier(.2,.8,.2,1),
        transform 1s ease;
}

/* =====================================================
   NAV
===================================================== */

.nav{
    width:min(1380px,92%);

    margin:auto;

    padding:22px 0;

    display:flex;

    justify-content:space-between;

    align-items:center;

    position:relative;

    z-index:10;
}

.brand{
    display:flex;

    align-items:center;

    gap:11px;

    font-weight:900;

    letter-spacing:-.5px;
}

.brandIcon{
    width:38px;
    height:38px;

    display:grid;
    place-items:center;

    border-radius:12px;

    background:var(--white);

    color:#000;

    font-weight:900;

    box-shadow:0 5px 25px rgba(255,255,255,.08);
}

.navLinks{
    display:flex;

    gap:7px;

    padding:5px;

    border:
        1px solid var(--border);

    border-radius:100px;

    background:
        rgba(255,255,255,.045);

    backdrop-filter:blur(20px);
}

.navLinks a{
    color:#aaa;

    text-decoration:none;

    padding:9px 15px;

    border-radius:100px;

    font-size:12px;

    font-weight:700;
}

.navLinks a:hover{
    background:#fff;
    color:#000;
}

.navButton{
    border:0;

    background:var(--orange);

    color:#000;

    padding:13px 21px;

    border-radius:100px;

    font-weight:900;

    cursor:pointer;

    transition:.25s;
}

.navButton:hover{
    transform:translateY(-3px) scale(1.02);

    box-shadow:
        0 15px 35px rgba(255,105,0,.22);
}

/* =====================================================
   HERO
===================================================== */

.container{
    width:min(1380px,92%);

    margin:auto;
}

.hero{
    min-height:92vh;

    display:grid;

    grid-template-columns:
        1.15fr .85fr;

    gap:60px;

    align-items:center;

    padding:
        60px 0
        100px;
}

.kicker{
    display:inline-flex;

    align-items:center;

    gap:8px;

    border:
        1px solid var(--border);

    background:
        rgba(255,255,255,.045);

    backdrop-filter:blur(20px);

    padding:9px 14px;

    border-radius:100px;

    color:#bbb;

    font-size:11px;

    font-weight:800;

    margin-bottom:25px;
}

.kicker i{
    width:7px;
    height:7px;

    border-radius:50%;

    background:var(--orange);

    box-shadow:
        0 0 15px var(--orange);
}

.hero h1{
    font-family:
        "Space Grotesk",
        sans-serif;

    font-size:
        clamp(65px,9.8vw,150px);

    line-height:.82;

    letter-spacing:-8px;

    max-width:900px;
}

.hero h1 span{
    color:var(--orange);
}

.heroDescription{
    margin-top:38px;

    max-width:590px;

    font-size:18px;

    line-height:1.7;

    color:#aaa;
}

.heroButtons{
    display:flex;

    flex-wrap:wrap;

    gap:10px;

    margin-top:32px;
}

.primary{
    border:0;

    background:#fff;

    color:#000;

    padding:16px 23px;

    border-radius:100px;

    font-weight:900;

    cursor:pointer;

    transition:.25s;
}

.primary:hover{
    background:var(--orange);

    transform:translateY(-3px);
}

.secondary{
    border:
        1px solid rgba(255,255,255,.16);

    background:
        rgba(255,255,255,.05);

    color:white;

    padding:16px 23px;

    border-radius:100px;

    font-weight:800;

    cursor:pointer;

    backdrop-filter:blur(15px);
}

/* =====================================================
   HERO VISUAL
===================================================== */

.heroVisual{
    position:relative;

    min-height:540px;

    border-radius:48px;

    overflow:hidden;

    background:
        linear-gradient(
            145deg,
            #2a1005,
            #0b0b0b 65%
        );

    border:
        1px solid rgba(255,255,255,.12);

    box-shadow:
        0 40px 100px rgba(0,0,0,.45);
}

/* simulated startup image */

.heroVisual::before{
    content:"";

    position:absolute;

    width:400px;
    height:400px;

    border-radius:50%;

    background:
        radial-gradient(
            circle,
            #ff9a55,
            #ff6900 38%,
            transparent 70%
        );

    right:-100px;
    top:-80px;

    filter:blur(5px);
}

.heroVisual::after{
    content:"";

    position:absolute;

    width:300px;
    height:500px;

    background:
        linear-gradient(
            160deg,
            rgba(255,255,255,.12),
            transparent
        );

    transform:rotate(25deg);

    left:30%;
    top:-60px;

    border-radius:100px;

    backdrop-filter:blur(10px);
}

.visualGrid{
    position:absolute;

    inset:0;

    background-image:
        linear-gradient(
            rgba(255,255,255,.05) 1px,
            transparent 1px
        ),
        linear-gradient(
            90deg,
            rgba(255,255,255,.05) 1px,
            transparent 1px
        );

    background-size:50px 50px;

    mask-image:
        linear-gradient(
            to bottom,
            black,
            transparent
        );
}

.visualContent{
    position:absolute;

    left:32px;
    right:32px;
    bottom:32px;

    z-index:2;
}

.visualNumber{
    font-family:"Space Grotesk";

    font-size:130px;

    font-weight:900;

    line-height:.8;

    opacity:.85;
}

.visualLabel{
    margin-top:20px;

    font-size:12px;

    letter-spacing:2px;

    color:#bbb;

    font-weight:800;
}

/* =====================================================
   MARQUEE
===================================================== */

.marquee{
    width:100%;

    overflow:hidden;

    border-top:
        1px solid var(--border);

    border-bottom:
        1px solid var(--border);

    background:#0b0b0b;

    white-space:nowrap;
}

.marqueeTrack{
    display:inline-flex;

    animation:
        marquee 22s linear infinite;
}

.marquee span{
    padding:24px 32px;

    font-family:"Space Grotesk";

    font-size:14px;

    font-weight:900;

    letter-spacing:1px;
}

.marquee b{
    color:var(--orange);
}

@keyframes marquee{

    from{
        transform:translateX(0);
    }

    to{
        transform:translateX(-50%);
    }

}

/* =====================================================
   INTRO
===================================================== */

.intro{
    padding:150px 0;
}

.sectionNumber{
    color:var(--orange);

    font-size:12px;

    font-weight:900;

    letter-spacing:2px;

    margin-bottom:20px;
}

.bigStatement{
    font-family:"Space Grotesk";

    font-size:
        clamp(45px,7vw,100px);

    line-height:.94;

    letter-spacing:-5px;

    max-width:1100px;
}

.bigStatement span{
    color:#555;
}

/* =====================================================
   CARDS
===================================================== */

.sectionHeader{
    display:flex;

    justify-content:space-between;

    align-items:end;

    gap:30px;

    margin-bottom:35px;
}

.sectionHeader h2{
    font-family:"Space Grotesk";

    font-size:
        clamp(45px,6vw,82px);

    letter-spacing:-4px;

    line-height:.9;
}

.sectionHeader p{
    color:#888;

    max-width:300px;

    line-height:1.5;
}

.cards{
    display:grid;

    grid-template-columns:
        repeat(3,1fr);

    gap:14px;
}

.card{
    min-height:350px;

    border-radius:
        var(--radius);

    padding:28px;

    background:
        linear-gradient(
            145deg,
            rgba(255,255,255,.09),
            rgba(255,255,255,.025)
        );

    border:
        1px solid var(--border);

    position:relative;

    overflow:hidden;

    transition:
        transform .35s,
        border .35s;
}

.card:hover{
    transform:
        translateY(-8px);

    border-color:
        rgba(255,105,0,.35);
}

.card::before{
    content:"";

    position:absolute;

    width:180px;
    height:180px;

    border-radius:50%;

    background:
        rgba(255,105,0,.18);

    filter:blur(45px);

    right:-70px;
    top:-70px;
}

.cardNumber{
    font-size:12px;

    color:var(--orange);

    font-weight:900;
}

.cardIcon{
    width:55px;
    height:55px;

    display:grid;

    place-items:center;

    border-radius:18px;

    margin-top:80px;

    background:
        rgba(255,255,255,.09);

    border:
        1px solid rgba(255,255,255,.1);

    font-size:23px;
}

.card h3{
    font-family:"Space Grotesk";

    font-size:27px;

    margin-top:20px;
}

.card p{
    color:#888;

    font-size:14px;

    line-height:1.6;

    margin-top:8px;
}

/* =====================================================
   STARTUP SHOWCASE
===================================================== */

.showcase{
    padding:160px 0;
}

.startupGrid{
    display:grid;

    grid-template-columns:
        1.4fr .6fr;

    gap:14px;
}

.startup{
    min-height:520px;

    border-radius:
        40px;

    position:relative;

    overflow:hidden;

    padding:35px;

    background:
        linear-gradient(
            145deg,
            #301205,
            #111
        );

    border:
        1px solid var(--border);
}

.startup.small{
    min-height:250px;
}

.startup::before{
    content:"";

    position:absolute;

    inset:0;

    background:
        radial-gradient(
            circle at 80% 20%,
            rgba(255,105,0,.55),
            transparent 30%
        );
}

.startup::after{
    content:"";

    position:absolute;

    width:250px;
    height:250px;

    border:
        1px solid rgba(255,255,255,.15);

    border-radius:50%;

    right:-50px;
    bottom:-50px;

    box-shadow:
        0 0 0 30px rgba(255,255,255,.025),
        0 0 0 60px rgba(255,255,255,.015);
}

.startupContent{
    position:absolute;

    left:35px;
    right:35px;
    bottom:35px;

    z-index:2;
}

.startupTag{
    display:inline-block;

    background:
        rgba(255,255,255,.09);

    border:
        1px solid rgba(255,255,255,.12);

    padding:7px 11px;

    border-radius:100px;

    font-size:10px;

    font-weight:900;
}

.startup h3{
    font-family:"Space Grotesk";

    font-size:45px;

    letter-spacing:-2px;

    margin-top:15px;
}

.startup p{
    color:#aaa;

    max-width:500px;

    margin-top:8px;
}

/* =====================================================
   TIMELINE
===================================================== */

.timeline{
    padding:100px 0 160px;
}

.timelineItem{
    display:grid;

    grid-template-columns:
        100px 1fr 170px;

    gap:30px;

    padding:35px 0;

    border-top:
        1px solid var(--border);

    align-items:center;
}

.timelineItem:last-child{
    border-bottom:
        1px solid var(--border);
}

.timelineNo{
    color:var(--orange);

    font-size:13px;

    font-weight:900;
}

.timelineItem h3{
    font-family:"Space Grotesk";

    font-size:
        clamp(32px,4vw,60px);

    letter-spacing:-2px;
}

.timelineItem p{
    color:#888;

    margin-top:6px;
}

.timelineDate{
    text-align:right;

    color:#aaa;

    font-size:13px;

    font-weight:800;
}

/* =====================================================
   REGISTRATION
===================================================== */

.register{
    padding:80px 0 150px;
}

.registerBox{
    border-radius:50px;

    padding:
        clamp(25px,6vw,80px);

    background:
        linear-gradient(
            135deg,
            #f5f3ec,
            #dcd8cc
        );

    color:#080808;

    position:relative;

    overflow:hidden;
}

.registerBox::before{
    content:"";

    position:absolute;

    width:450px;
    height:450px;

    border-radius:50%;

    background:var(--orange);

    right:-150px;
    top:-180px;

    filter:blur(20px);

    opacity:.8;
}

.registerBox h2{
    font-family:"Space Grotesk";

    font-size:
        clamp(55px,8vw,110px);

    letter-spacing:-6px;

    line-height:.85;

    max-width:900px;

    position:relative;

    z-index:2;
}

.registerBox h2 span{
    color:var(--orange);
}

.form{
    margin-top:70px;

    display:grid;

    grid-template-columns:
        1fr 1fr;

    gap:15px;

    position:relative;

    z-index:2;
}

.input{
    border:
        1px solid rgba(0,0,0,.15);

    background:
        rgba(255,255,255,.55);

    border-radius:18px;

    padding:17px;

    outline:none;

    font:inherit;

    color:#000;
}

.input:focus{
    border-color:var(--orange);

    box-shadow:
        0 0 0 4px
        rgba(255,105,0,.12);
}

textarea.input{
    min-height:130px;

    resize:vertical;

    grid-column:1/-1;
}

.form button{
    grid-column:1/-1;

    border:0;

    padding:19px;

    border-radius:18px;

    background:#080808;

    color:#fff;

    font-weight:900;

    cursor:pointer;

    transition:.25s;
}

.form button:hover{
    background:var(--orange);

    color:#000;

    transform:translateY(-3px);
}

/* =====================================================
   SUCCESS
===================================================== */

.success{
    display:none;

    margin-top:40px;

    padding:30px;

    border-radius:24px;

    background:#080808;

    color:white;

    position:relative;

    z-index:2;
}

.success strong{
    color:var(--orange);

    font-size:30px;
}

/* =====================================================
   FOOTER
===================================================== */

footer{
    padding:30px 0 50px;

    color:#666;

    display:flex;

    justify-content:space-between;

    border-top:
        1px solid var(--border);

    font-size:12px;
}

/* =====================================================
   MOBILE
===================================================== */

@media(max-width:950px){

    .navLinks{
        display:none;
    }

    .hero{
        grid-template-columns:1fr;

        padding-top:40px;
    }

    .heroVisual{
        min-height:430px;
    }

    .cards{
        grid-template-columns:1fr 1fr;
    }

    .startupGrid{
        grid-template-columns:1fr;
    }

}

@media(max-width:650px){

    .container,
    .nav{
        width:90%;
    }

    .hero{
        min-height:auto;

        padding:
            45px 0
            80px;
    }

    .hero h1{
        font-size:
            clamp(60px,17vw,90px);

        letter-spacing:-5px;
    }

    .heroDescription{
        font-size:15px;
    }

    .heroVisual{
        min-height:370px;

        border-radius:30px;
    }

    .visualNumber{
        font-size:90px;
    }

    .intro{
        padding:100px 0;
    }

    .bigStatement{
        font-size:
            clamp(42px,11vw,65px);

        letter-spacing:-3px;
    }

    .sectionHeader{
        display:block;
    }

    .sectionHeader h2{
        font-size:55px;

        margin-bottom:20px;
    }

    .cards{
        grid-template-columns:1fr;
    }

    .card{
        min-height:280px;
    }

    .showcase{
        padding:100px 0;
    }

    .startup{
        min-height:420px;
    }

    .timelineItem{
        grid-template-columns:
            45px 1fr;

        gap:15px;
    }

    .timelineDate{
        grid-column:2;

        text-align:left;
    }

    .timelineItem h3{
        font-size:38px;
    }

    .register{
        padding-bottom:90px;
    }

    .registerBox{
        border-radius:30px;
    }

    .registerBox h2{
        font-size:
            clamp(52px,14vw,75px);

        letter-spacing:-4px;
    }

    .form{
        grid-template-columns:1fr;

        margin-top:45px;
    }

    textarea.input,
    .form button{
        grid-column:auto;
    }

    footer{
        flex-direction:column;

        gap:10px;
    }

}

</style>
</head>


<body>

<!-- =====================================================
     BACKGROUND
===================================================== -->

<div class="bg"></div>

<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>
<div class="particle"></div>


<!-- =====================================================
     NAV
===================================================== -->

<nav class="nav">

    <div class="brand">

        <div class="brandIcon">
            E
        </div>

        E-CELL

    </div>


    <div class="navLinks">

        <a href="#about">About</a>

        <a href="#benefits">Why Join</a>

        <a href="#timeline">Timeline</a>

        <a href="#register">Register</a>

    </div>


    <button
        class="navButton"
        onclick="goRegister()">

        Enter Competition ↗

    </button>

</nav>


<main>


<!-- =====================================================
     HERO
===================================================== -->

<section class="hero container">

    <div>

        <div class="kicker">

            <i></i>

            E-CELL STARTUP PITCH 2026

        </div>


        <h1>

            Build the
            <span>next.</span>

            Pitch it.

        </h1>


        <p class="heroDescription">

  
