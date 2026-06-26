
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />

<title></title>

<!-- Tailwind -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Icons -->
<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>

<!-- Font -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

<style>

:root{
    --bg:#07111f;
    --card:#0f172a;
    --card2:#111c33;
    --primary:#00e5ff;
    --secondary:#6366f1;
    --text:#f8fafc;
    --muted:#94a3b8;
    --border:rgba(255,255,255,.08);
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
    font-family:'Inter',sans-serif;
    background:linear-gradient(180deg,#050b16,#081120,#0b1728);
    color:var(--text);
    overflow-x:hidden;
}

/* =========================
PRELOADER
========================= */

#loader{
    position:fixed;
    inset:0;
    background:#040812;
    z-index:99999;
    display:flex;
    align-items:center;
    justify-content:center;
    flex-direction:column;
    gap:20px;
}

.loader-ring{
    width:80px;
    height:80px;
    border-radius:50%;
    border:4px solid rgba(255,255,255,.08);
    border-top:4px solid var(--primary);
    animation:spin 1s linear infinite;
}

@keyframes spin{
    100%{transform:rotate(360deg);}
}

/* =========================
TOP FLOATING NAV
========================= */

.floating-nav{
    position:fixed;
    top:18px;
    left:50%;
    transform:translateX(-50%);
    width:min(92%,780px);
    height:72px;
    background:rgba(10,18,34,.7);
    backdrop-filter:blur(18px);
    border:1px solid rgba(255,255,255,.08);
    border-radius:30px;
    z-index:9999;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 12px 0 20px;
    box-shadow:0 20px 50px rgba(0,0,0,.45);
}

.brand{
    display:flex;
    align-items:center;
    gap:14px;
}

.brand-icon{
    width:45px;
    height:45px;
    border-radius:14px;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:1.2rem;
    box-shadow:0 10px 30px rgba(0,229,255,.3);
}

.brand h2{
    font-size:1rem;
    font-weight:800;
}

.brand p{
    color:var(--muted);
    font-size:.72rem;
}

.live-status{
    display:flex;
    align-items:center;
    gap:8px;
    color:#cbd5e1;
    font-size:.78rem;
}

.pulse-dot{
    width:10px;
    height:10px;
    border-radius:50%;
    background:#22c55e;
    animation:pulse 1.5s infinite;
}

@keyframes pulse{
    0%{transform:scale(1);}
    50%{transform:scale(1.5);opacity:.4;}
    100%{transform:scale(1);}
}

.nav-btn{
    border:none;
    padding:13px 22px;
    border-radius:16px;
    font-weight:800;
    cursor:pointer;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    color:#00111a;
    transition:.3s ease;
}

.nav-btn:hover{
    transform:translateY(-3px);
}

/* =========================
HERO
========================= */

.hero{
    padding:160px 6% 100px;
    text-align:center;
    position:relative;
    overflow:hidden;
}

.hero::before{
    content:'';
    position:absolute;
    width:500px;
    height:500px;
    background:radial-gradient(circle,var(--primary),transparent 70%);
    opacity:.12;
    top:-150px;
    left:-120px;
    filter:blur(50px);
}

.hero::after{
    content:'';
    position:absolute;
    width:500px;
    height:500px;
    background:radial-gradient(circle,#7c3aed,transparent 70%);
    opacity:.12;
    bottom:-180px;
    right:-120px;
    filter:blur(50px);
}

.hero-badge{
    display:inline-flex;
    align-items:center;
    gap:10px;
    padding:12px 20px;
    border-radius:999px;
    background:rgba(0,229,255,.08);
    border:1px solid rgba(0,229,255,.15);
    margin-bottom:30px;
    color:#bae6fd;
    font-size:.85rem;
}

.hero h1{
    font-size:clamp(2.8rem,7vw,5.5rem);
    line-height:1.05;
    font-weight:900;
    margin-bottom:24px;
}

.hero h1 span{
    background:linear-gradient(90deg,var(--primary),#818cf8);
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
}

.hero p{
    max-width:780px;
    margin:auto;
    color:var(--muted);
    line-height:1.9;
    font-size:1.05rem;
}

/* =========================
STATS
========================= */

.stats{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:24px;
    padding:0 6% 90px;
}

.stat-box{
    background:rgba(255,255,255,.03);
    border:1px solid rgba(255,255,255,.06);
    border-radius:26px;
    padding:35px;
    text-align:center;
    backdrop-filter:blur(12px);
}

.stat-box h2{
    font-size:2.8rem;
    margin-bottom:12px;
    color:#67e8f9;
}

.stat-box p{
    color:var(--muted);
}

/* =========================
SECTION TITLES
========================= */

.section{
    padding:0 6% 90px;
}

.section-head{
    margin-bottom:40px;
}

.section-tag{
    color:#67e8f9;
    text-transform:uppercase;
    letter-spacing:2px;
    font-size:.75rem;
    margin-bottom:16px;
    display:block;
}

.section-title{
    font-size:clamp(2rem,5vw,3rem);
    font-weight:900;
    margin-bottom:15px;
}

.section-desc{
    color:var(--muted);
    max-width:700px;
    line-height:1.8;
}

/* =========================
BOT CARDS
========================= */

.carousel{
    display:flex;
    overflow-x:auto;
    gap:24px;
    scroll-snap-type:x mandatory;
    scrollbar-width:none;
    padding-bottom:15px;
}

.carousel::-webkit-scrollbar{
    display:none;
}

.bot-card{
    min-width:340px;
    max-width:340px;
    background:linear-gradient(180deg,var(--card),var(--card2));
    border:1px solid rgba(255,255,255,.07);
    border-radius:30px;
    overflow:hidden;
    transition:.35s ease;
    scroll-snap-align:start;
    position:relative;
}

.bot-card:hover{
    transform:translateY(-8px);
    border-color:rgba(0,229,255,.25);
    box-shadow:0 20px 50px rgba(0,0,0,.35);
}

.bot-image{
    width:100%;
    height:220px;
    object-fit:cover;
    opacity:.78;
}

.bot-body{
    padding:28px;
}

.bot-badge{
    display:inline-flex;
    align-items:center;
    gap:8px;
    padding:8px 14px;
    border-radius:999px;
    background:rgba(0,229,255,.08);
    color:#a5f3fc;
    font-size:.72rem;
    margin-bottom:18px;
}

.bot-body h3{
    font-size:1.5rem;
    margin-bottom:12px;
}

.bot-body p{
    color:var(--muted);
    line-height:1.8;
    margin-bottom:28px;
}

.bot-actions{
    display:flex;
    gap:12px;
}

.bot-btn{
    flex:1;
    border:none;
    padding:14px;
    border-radius:16px;
    font-weight:800;
    cursor:pointer;
    transition:.3s ease;
}

.primary-btn{
    background:linear-gradient(135deg,var(--primary),#818cf8);
    color:#00111a;
}

.secondary-btn{
    background:rgba(255,255,255,.05);
    color:white;
    border:1px solid rgba(255,255,255,.06);
}

.bot-btn:hover{
    transform:translateY(-2px);
}

/* =========================
CHAT SECTION
========================= */

.chat-zone{
    background:rgba(255,255,255,.02);
    border-top:1px solid rgba(255,255,255,.05);
    padding:80px 6%;
}

.chat-placeholder{
    text-align:center;
    padding:100px 20px;
    border:2px dashed rgba(255,255,255,.08);
    border-radius:30px;
    background:rgba(255,255,255,.02);
}

.chat-placeholder i{
    font-size:4rem;
    color:#1e293b;
    margin-bottom:25px;
}

.chat-placeholder h3{
    font-size:1.7rem;
    margin-bottom:15px;
}

.chat-placeholder p{
    color:var(--muted);
    line-height:1.8;
}

.chat-frame{
    display:none;
    width:100%;
    height:780px;
    overflow:hidden;
    border-radius:30px;
    border:1px solid rgba(255,255,255,.08);
    background:#000;
    animation:fadeIn .6s ease;
}

.chat-frame.active{
    display:block;
}

.chat-frame iframe{
    width:100%;
    height:100%;
    border:none;
}

@keyframes fadeIn{
    from{
        opacity:0;
        transform:translateY(20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

/* =========================
FEATURES
========================= */

.features{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:24px;
}

.feature-card{
    background:rgba(255,255,255,.03);
    border:1px solid rgba(255,255,255,.05);
    border-radius:24px;
    padding:35px;
}

.feature-icon{
    width:65px;
    height:65px;
    border-radius:20px;
    background:linear-gradient(135deg,var(--primary),#6366f1);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:1.4rem;
    margin-bottom:20px;
}

.feature-card h3{
    margin-bottom:15px;
}

.feature-card p{
    color:var(--muted);
    line-height:1.8;
}

/* =========================
POPUP
========================= */

.popup{
    position:fixed;
    bottom:25px;
    right:25px;
    width:340px;
    background:rgba(15,23,42,.92);
    border:1px solid rgba(255,255,255,.08);
    border-radius:26px;
    padding:24px;
    z-index:99999;
    display:none;
    animation:fadeIn .5s ease;
    box-shadow:0 20px 50px rgba(0,0,0,.45);
}

.popup h4{
    margin-bottom:10px;
}

.popup p{
    color:var(--muted);
    font-size:.92rem;
    line-height:1.7;
    margin-bottom:18px;
}

.popup-actions{
    display:flex;
    gap:10px;
}

.popup button{
    flex:1;
    border:none;
    padding:12px;
    border-radius:14px;
    cursor:pointer;
    font-weight:700;
}

.popup-primary{
    background:linear-gradient(135deg,var(--primary),#6366f1);
    color:#00111a;
}

.popup-secondary{
    background:rgba(255,255,255,.06);
    color:white;
}

/* =========================
FOOTER
========================= */

footer{
    padding:60px 6%;
    text-align:center;
    border-top:1px solid rgba(255,255,255,.06);
}

footer p{
    color:var(--muted);
    line-height:1.8;
}

/* =========================
MOBILE
========================= */

@media(max-width:768px){

.floating-nav{
    height:auto;
    padding:14px;
    flex-direction:column;
    gap:15px;
    border-radius:26px;
}

.hero{
    padding-top:220px;
}

.bot-card{
    min-width:88%;
}

.chat-frame{
    height:650px;
}

.popup{
    width:90%;
    right:5%;
}

}

</style>
</head>

<body>

<!-- PRELOADER -->
<div id="loader">
    <div class="loader-ring"></div>
    <p style="color:#94a3b8;">Loading AI Workspace...</p>
</div>

<!-- FLOATING NAV -->
<div class="floating-nav">

    <div class="brand">

        <div class="brand-icon">
            <i class="fas fa-robot"></i>
        </div>

        <div>
            <h2>DebeatzGH AI Hub</h2>
            <p>Professional Chat Interfaces</p>
        </div>

    </div>

    <div class="live-status">
        <span class="pulse-dot"></span>
        AI Systems Online
    </div>

    <button class="nav-btn"
    onclick="window.open('https://debeatzgh1.github.io/','_blank')">
        Open Ecosystem
    </button>

</div>

<!-- HERO -->
<section class="hero">

    <div class="hero-badge">
        <i class="fas fa-sparkles"></i>
        Premium AI Assistant Workspace
    </div>

    <h1>
        Professional
        <span>AI Chat Experiences</span>
    </h1>

    <p>
        Modern GitHub Pages AI interface optimized for startups,
        automation systems, customer support, AI communities,
        productivity agents, and business intelligence assistants.
    </p>

</section>

<!-- STATS -->
<section class="stats">

    <div class="stat-box">
        <h2>24/7</h2>
        <p>AI Availability</p>
    </div>

    <div class="stat-box">
        <h2>Fast</h2>
        <p>Lazy Load Performance</p>
    </div>

    <div class="stat-box">
        <h2>Secure</h2>
        <p>Cloud Powered Workspace</p>
    </div>

    <div class="stat-box">
        <h2>Modern</h2>
        <p>Mobile Responsive UI</p>
    </div>

</section>

<!-- AI AGENTS -->
<section class="section">

    <div class="section-head">

        <span class="section-tag">
            AI Selection Lounge
        </span>

        <h2 class="section-title">
            Choose Your AI Assistant
        </h2>

        <p class="section-desc">
            Load chat agents dynamically using optimized lazy-loading
            architecture designed for GitHub Pages deployment.
        </p>

    </div>

    <div class="carousel">

        <!-- BOT 1 -->
        <div class="bot-card">

            <img loading="lazy"
            class="bot-image"
            src="https://images.unsplash.com/photo-1677442136019-21780ecad995?q=80&w=1200&auto=format&fit=crop"
            alt="AI Assistant">

            <div class="bot-body">

                <div class="bot-badge">
                    <i class="fas fa-bolt"></i>
                    Productivity AI
                </div>

                <h3>AI Companion</h3>

                <p>
                    Smart assistant for daily productivity,
                    brainstorming, content generation,
                    and creative workflows.
                </p>

                <div class="bot-actions">

                    <button class="bot-btn primary-btn"
                    onclick="activateChat('https://agent.jotform.com/0195482a4e8d72b894a09678ddb9b513d564')">
                        Launch Chat
                    </button>

                    <button class="bot-btn secondary-btn"
                    onclick="showInfo('AI Companion','Creative productivity assistant for writing, planning and workflow optimization.')">
                        Details
                    </button>

                </div>

            </div>

        </div>

        <!-- BOT 2 -->
        <div class="bot-card">

            <img loading="lazy"
            class="bot-image"
            src="https://images.unsplash.com/photo-1531482615713-2afd69097998?q=80&w=1200&auto=format&fit=crop"
            alt="Automation AI">

            <div class="bot-body">

                <div class="bot-badge">
                    <i class="fas fa-microchip"></i>
                    Automation AI
                </div>

                <h3>DebeatzGH AI</h3>

                <p>
                    Advanced automation assistant for
                    digital strategies, startup ideas,
                    monetization systems, and AI growth.
                </p>

                <div class="bot-actions">

                    <button class="bot-btn primary-btn"
                    onclick="activateChat('https://agent.jotform.com/0195424fb5d47897a72080768094791e9c32')">
                        Launch Chat
                    </button>

                    <button class="bot-btn secondary-btn"
                    onclick="showInfo('DebeatzGH AI','Premium business and automation assistant optimized for digital growth.')">
                        Details
                    </button>

                </div>

            </div>

        </div>

        <!-- BOT 3 -->
        <div class="bot-card">

            <img loading="lazy"
            class="bot-image"
            src="https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?q=80&w=1200&auto=format&fit=crop"
            alt="Business AI">

            <div class="bot-body">

                <div class="bot-badge">
                    <i class="fas fa-chart-line"></i>
                    Strategy AI
                </div>

                <h3>Income Strategist</h3>

                <p>
                    Discover side hustle opportunities,
                    online business systems,
                    affiliate growth, and monetization.
                </p>

                <div class="bot-actions">

                    <button class="bot-btn primary-btn"
                    onclick="activateChat('https://agent.jotform.com/0195479af1b879f3a82ea15cbaf3859eaa44')">
                        Launch Chat
                    </button>

                    <button class="bot-btn secondary-btn"
                    onclick="showInfo('Income Strategist','Business intelligence assistant focused on online income strategies.')">
                        Details
                    </button>

                </div>

            </div>

        </div>

    </div>

</section>

<!-- CHAT ZONE -->
<section class="chat-zone" id="chatZone">

    <div class="section-head">

        <span class="section-tag">
            Interaction Bay
        </span>

        <h2 class="section-title">
            Live AI Workspace
        </h2>

    </div>

    <!-- PLACEHOLDER -->
    <div class="chat-placeholder" id="placeholder">

        <i class="fas fa-comments"></i>

        <h3>Select an AI Assistant</h3>

        <p>
            The chat interface loads only when activated,
            ensuring fast performance and reduced bandwidth usage.
        </p>

    </div>

    <!-- FRAME -->
    <div class="chat-frame" id="chatFrame">

        <iframe
        id="chatIframe"
        loading="lazy"
        allowfullscreen>
        </iframe>

    </div>

</section>

<!-- FEATURES -->
<section class="section">

    <div class="section-head">

        <span class="section-tag">
            Premium Features
        </span>

        <h2 class="section-title">
            Optimized Professional Experience
        </h2>

    </div>

    <div class="features">

        <div class="feature-card">

            <div class="feature-icon">
                <i class="fas fa-gauge-high"></i>
            </div>

            <h3>Fast Performance</h3>

            <p>
                Lazy-loaded AI chat interfaces optimized
                for GitHub Pages and mobile browsers.
            </p>

        </div>

        <div class="feature-card">

            <div class="feature-icon">
                <i class="fas fa-layer-group"></i>
            </div>

            <h3>Modern UI System</h3>

            <p>
                Premium floating navigation,
                animated components,
                and futuristic design language.
            </p>

        </div>

        <div class="feature-card">

            <div class="feature-icon">
                <i class="fas fa-mobile-screen"></i>
            </div>

            <h3>Responsive Design</h3>

            <p>
                Fully responsive experience across
                desktop, tablet, and mobile devices.
            </p>

        </div>

        <div class="feature-card">

            <div class="feature-icon">
                <i class="fas fa-shield-halved"></i>
            </div>

            <h3>Professional Structure</h3>

            <p>
                Organized AI sections,
                structured layouts,
                and scalable deployment architecture.
            </p>

        </div>

    </div>

</section>

<!-- POPUP -->
<div class="popup" id="popup">

    <h4 id="popupTitle">Assistant Details</h4>

    <p id="popupText">
        Professional AI assistant information.
    </p>

    <div class="popup-actions">

        <button class="popup-primary"
        onclick="closePopup()">
            Continue
        </button>

        <button class="popup-secondary"
        onclick="closePopup()">
            Close
        </button>

    </div>

</div>

<!-- FOOTER -->
<footer>

    <h2 style="font-size:2rem;margin-bottom:16px;">
        Premium AI Workspace
    </h2>

    <p>
        Designed for creators, startups, AI educators,
        customer support systems, productivity hubs,
        and professional GitHub Pages deployment.
    </p>

</footer>

<script>

/* =========================
PRELOADER
========================= */

window.addEventListener('load',()=>{

    setTimeout(()=>{

        document.getElementById('loader').style.display='none';

    },1000);

});

/* =========================
CHAT ACTIVATION
========================= */

function activateChat(url){

    const frame=document.getElementById('chatFrame');
    const iframe=document.getElementById('chatIframe');
    const placeholder=document.getElementById('placeholder');

    placeholder.style.display='none';

    iframe.src=url;

    frame.classList.add('active');

    document.getElementById('chatZone')
    .scrollIntoView({
        behavior:'smooth'
    });

}

/* =========================
POPUP
========================= */

function showInfo(title,text){

    document.getElementById('popupTitle').innerText=title;

    document.getElementById('popupText').innerText=text;

    document.getElementById('popup').style.display='block';

}

function closePopup(){

    document.getElementById('popup').style.display='none';

}

/* =========================
WELCOME POPUP
========================= */

setTimeout(()=>{

    showInfo(
        'Welcome to AI Assistant Hub',
        'Choose an AI agent to begin a premium interactive workspace experience.'
    );

},4000);

</script>

</body>
</html>
