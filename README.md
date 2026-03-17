
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeBeatzGH | AI Assistant Hub</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');
        
        :root {
            --accent: #00f2ff;
            --bg-dark: #0a0a0c;
            --card-bg: rgba(255, 255, 255, 0.03);
            --border: rgba(255, 255, 255, 0.1);
        }

        body {
            background-color: var(--bg-dark);
            color: #fff;
            font-family: 'Plus Jakarta Sans', sans-serif;
            scroll-behavior: smooth;
        }

        /* --- SECTION 1: SELECTION CAROUSEL --- */
        .carousel-container {
            display: flex; overflow-x: auto; scroll-snap-type: x mandatory;
            gap: 20px; padding: 20px; scrollbar-width: none;
        }
        .carousel-container::-webkit-scrollbar { display: none; }

        .bot-card {
            min-width: 300px; background: var(--card-bg);
            border: 1px solid var(--border); border-radius: 24px;
            overflow: hidden; scroll-snap-align: start; transition: 0.4s;
            position: relative;
        }
        .bot-card:hover { border-color: var(--accent); transform: translateY(-5px); }

        /* --- SECTION 2: LAZY INTERFACE BAY --- */
        .interface-bay {
            background: rgba(0,0,0,0.3); border-top: 1px solid var(--border);
            min-height: 600px; margin-top: 50px; padding: 40px 20px;
        }

        .chat-frame-wrapper {
            width: 100%; height: 600px; background: #111;
            border-radius: 20px; border: 1px solid var(--border);
            overflow: hidden; margin-bottom: 40px; display: none;
        }
        .chat-frame-wrapper.active { display: block; animation: fadeIn 0.8s ease; }

        /* --- FLOATING COMPONENTS --- */
        .wp-float {
            position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%);
            z-index: 1000;
        }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>

    <header class="pt-20 pb-10 text-center">
        <h1 class="text-4xl font-black tracking-tighter">AI Assistant <span class="text-cyan-400">Hub</span></h1>
        <p class="text-gray-500 mt-2">Select an agent to begin your session</p>
    </header>

    <div class="carousel-container max-w-6xl mx-auto">
        <div class="bot-card">
            <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createavibranteye-catchingyoutubeblogthumbnailfeaturingafloatingquizpop-upicononadigitalblogpage5084708667809205788.jpg" class="h-40 w-full object-cover opacity-60">
            <div class="p-6">
                <h3 class="font-bold text-lg">AI Companion</h3>
                <p class="text-xs text-gray-400 mt-2 mb-4">Everyday productivity & creative ideas.</p>
                <button onclick="activateChat('bot1', 'https://agent.jotform.com/0195482a4e8d72b894a09678ddb9b513d564')" class="w-full py-3 bg-cyan-500 text-black font-black rounded-xl text-[10px] uppercase tracking-widest hover:bg-white transition">Initialize Chat</button>
            </div>
        </div>

        <div class="bot-card">
            <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createamodernandcleanthumbnailforawebdevelopmentproducttitledmodernhomepagestylingtemplatewithtailwindcss3420170625469385526.jpg" class="h-40 w-full object-cover opacity-60">
            <div class="p-6">
                <h3 class="font-bold text-lg">Debeatzgh AI</h3>
                <p class="text-xs text-gray-400 mt-2 mb-4">Expert automation & strategy assistant.</p>
                <button onclick="activateChat('bot2', 'https://agent.jotform.com/0195424fb5d47897a72080768094791e9c32')" class="w-full py-3 bg-blue-500 text-white font-black rounded-xl text-[10px] uppercase tracking-widest hover:bg-white hover:text-black transition">Initialize Chat</button>
            </div>
        </div>

        <div class="bot-card">
            <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg" class="h-40 w-full object-cover opacity-60">
            <div class="p-6">
                <h3 class="font-bold text-lg">Income Strategist</h3>
                <p class="text-xs text-gray-400 mt-2 mb-4">Monetization & side-hustle logic.</p>
                <button onclick="activateChat('bot3', 'https://agent.jotform.com/0195479af1b879f3a82ea15cbaf3859eaa44')" class="w-full py-3 bg-purple-500 text-white font-black rounded-xl text-[10px] uppercase tracking-widest hover:bg-white hover:text-black transition">Initialize Chat</button>
            </div>
        </div>
    </div>

    <div class="interface-bay" id="interaction-bay">
        <div class="max-w-4xl mx-auto text-center mb-10" id="bay-placeholder">
            <i class="fas fa-robot text-4xl text-gray-800 mb-4"></i>
            <p class="text-gray-600 font-bold uppercase text-xs tracking-widest">Select an agent above to load interface</p>
        </div>
        
        <div id="chat-viewport" class="max-w-5xl mx-auto">
            <div id="bot-frame-container" class="chat-frame-wrapper">
                <iframe id="active-iframe" src="" class="w-full h-full border-none"></iframe>
            </div>
        </div>
    </div>

    <div class="wp-float">
        <div id="wp-nudge" class="hidden bg-black/90 border border-cyan-500/30 p-3 rounded-2xl mb-4 flex items-center gap-4 shadow-2xl animate-bounce">
            <span class="text-[10px] text-white">Claim your <strong>.wordpress.com</strong> site!</span>
            <button onclick="document.getElementById('wp-nudge').remove()" class="text-gray-500">✕</button>
        </div>
        <button onclick="window.open('https://debeatzgh1.github.io/Blogger-sign-up-button-/', '_blank')" class="bg-cyan-400 text-black px-6 py-3 rounded-full font-black text-[10px] tracking-tighter uppercase flex items-center gap-2 shadow-lg">
            <i class="fab fa-wordpress text-lg"></i> Create Site
        </button>
    </div>

    <script>
        function activateChat(botId, url) {
            // Hide placeholder
            document.getElementById('bay-placeholder').style.display = 'none';
            
            // Setup Frame
            const container = document.getElementById('bot-frame-container');
            const iframe = document.getElementById('active-iframe');
            
            // Lazy load source
            iframe.src = url;
            container.classList.add('active');
            
            // Smooth scroll to chat
            window.scrollTo({
                top: document.getElementById('interaction-bay').offsetTop - 20,
                behavior: 'smooth'
            });
        }

        // Show WP Nudge after delay
        setTimeout(() => {
            document.getElementById('wp-nudge').classList.remove('hidden');
        }, 5000);
    </script>
</body>
</html>
