
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sleek Floating Banner</title>
    <style>
        /* Modern CSS reset for consistency */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            min-height: 200vh; /* Adds scrollable height to visualize the fixed positioning */
            background-color: #121212; /* A dark, neutral background */
            color: #fff;
        }

        /* MAIN FLOATING BANNER CONTAINER
           Fixed to the top center of the screen
        */
        #sleek-floating-banner {
            position: fixed;
            top: 20px; /* Slight offset from the top border */
            left: 50%;
            transform: translateX(-50%); /* Centers horizontally */
            width: 340px; /* Compact, friendly width for desktop/mobile */
            height: 52px;
            background: rgba(30, 30, 30, 0.9); /* Dark semi-transparent background */
            backdrop-filter: blur(10px); /* Modern 'glassmorphism' effect */
            -webkit-backdrop-filter: blur(10px); /* Safari support */
            border: 1px solid rgba(255, 255, 255, 0.1); /* Subtle outline */
            border-radius: 50px; /* Fully rounded edges for a sleek pill look */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); /* Strong shadow for depth */
            display: flex;
            align-items: center;
            justify-content: space-between; /* Icon+Text on left, button on right */
            padding: 0 6px 0 16px; /* Optimized padding for the components */
            z-index: 10000; /* Ensures it stays above all other content */
            overflow: hidden; /* Needed for the marquee slide effect */
            
            /* Entry animation */
            animation: bannerEntry 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            opacity: 0;
            transition: all 0.3s ease;
        }

        /* Hover effect to highlight the interactive nature */
        #sleek-floating-banner:hover {
            transform: translateX(-50%) scale(1.03);
            border-color: #FF1493; /* DeepPink border highlight on hover */
        }

        /* Banner entry animation (slides in and bounces slightly) */
        @keyframes bannerEntry {
            from { top: -60px; opacity: 0; }
            to { top: 20px; opacity: 1; }
        }

        /* --- MARQUEE SLIDER STYLES --- */
        .banner-text-slider {
            flex: 1;
            height: 22px; /* Set height to constrain the text */
            overflow: hidden; /* Masks text outside the area */
            position: relative;
            margin-right: 12px;
        }

        .slide-inner {
            display: flex;
            flex-direction: column; /* Stacks text vertically for sliding */
            animation: verticalSlide 8s cubic-bezier(0.645, 0.045, 0.355, 1) infinite;
        }

        /* Text element properties */
        .slide-inner span {
            height: 22px; /* Matches parent height */
            color: rgba(255, 255, 255, 0.9); /* Slightly off-white for better readability */
            font-size: 0.8rem;
            font-weight: 600; /* Semi-bold */
            display: flex;
            align-items: center;
            gap: 8px; /* Gap for the indicator dot */
            white-space: nowrap; /* Prevents text wrapping */
        }

        /* Color highlight for key inscriptions */
        .highlight-text {
            color: #FF1493; /* DeepPink */
        }

        /* Subtle animated dot for live status feel */
        .live-dot {
            width: 7px;
            height: 7px;
            background-color: #FF1493;
            border-radius: 50%;
            box-shadow: 0 0 10px rgba(255, 20, 147, 0.8);
            animation: pulseDot 1.5s infinite;
        }

        /* Pulse animation for the live dot */
        @keyframes pulseDot {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.2); }
        }

        /* Vertical Slide Keyframes:
           4 states (3 texts + return to 1). 
           Uses percentages to control pause duration at each state.
        */
        @keyframes verticalSlide {
            0%, 22% { transform: translateY(0); } /* Pauses on Text 1 */
            33%, 55% { transform: translateY(-22px); } /* Slides to and Pauses on Text 2 */
            66%, 88% { transform: translateY(-44px); } /* Slides to and Pauses on Text 3 */
            100% { transform: translateY(0); } /* Loops back to Text 1 smoothly */
        }

        /* --- BUTTON STYLES --- */
        .launch-btn {
            background-color: #FF1493; /* Vibrant DeepPink for main color */
            color: #fff;
            padding: 9px 20px;
            border-radius: 25px; /* Rounded pill style to match banner */
            font-size: 0.75rem;
            font-weight: 900; /* Extra bold text for contrast */
            border: none;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none; /* Removes underline for <a> tags */
            display: flex;
            align-items: center;
            gap: 6px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 20, 147, 0.3); /* Soft DeepPink glow */
        }

        /* Button interaction effects */
        .launch-btn:hover {
            background-color: #ff50ac; /* Lighter DeepPink on hover */
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(255, 20, 147, 0.5); /* Stronger DeepPink glow */
        }

        .launch-btn:active {
            transform: translateY(1px) scale(0.98); /* Click interaction feedback */
        }

        /* --- SVG ICON STYLE --- */
        .arrow-icon {
            width: 13px;
            height: 13px;
            fill: none;
            stroke: currentColor; /* Matches text color (#fff) */
            stroke-width: 3;
            transition: transform 0.3s ease;
        }

        /* Hover animation specifically for the icon */
        .launch-btn:hover .arrow-icon {
            transform: translateX(3px); /* Arrow nudges right on hover */
        }
    </style>
</head>
<body>

    <div id="sleek-floating-banner" onclick="openHomeLink()">
        <div class="banner-text-slider">
            <div class="slide-inner">
                <span>
                    <div class="live-dot"></div> 
                    DeBeatz<span class="highlight-text">GH</span> Resource Hub
                </span>
                <span>
                    <div class="live-dot"></div>
                    Lifestyle <span class="highlight-text">&</span> Strategy
                </span>
                <span>
                    <div class="live-dot"></div>
                    Latest updates are <span class="highlight-text">Live</span>
                </span>
            </div>
        </div>

        <button class="launch-btn" onclick="openHomeLink(event)">
            OPEN 
            <svg class="arrow-icon" viewBox="0 0 24 24" aria-hidden="true">
                <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
        </button>
    </div>

    <script>
        /**
         * Opens the specified URL in a new tab without navigating
         * away from the current page.
         * @param {Event} e - Optional event object to prevent bubbling.
         */
        function openHomeLink(e) {
            // Check if event exists and stop propagation so clicking the button
            // doesn't also trigger the banner's onclick.
            if (e && e.stopPropagation) {
                e.stopPropagation();
            }
            
            // window.open(url, '_blank') opens in a new tab.
            window.open("https://debeatzgh1.github.io/-My-Brand-Online-Digital-Products-Affiliate-Shop/", "_blank");
        }
    </script>

</body>
</html>







<!-- Elfsight AI Chatbot | Assistant Bot -->
<script src="https://elfsightcdn.com/platform.js" async></script>
<div class="elfsight-app-2552d2e4-68c0-45de-b815-0f6717b1a0e6" data-elfsight-app-lazy></div>



# 🤖  AI Assistant Hub

A professional, high-performance portal for interacting with purpose-built AI agents. This UI is optimized for GitHub Pages and utilizes a dual-section layout to balance selection and interaction.

## 📂 Project Structure
* **Section 1: The Selection Lounge:** An auto-scrolling (touch-enabled) carousel containing Jotform AI Agents.
* **Section 2: The Interaction Bay:** A lazy-loading iframe environment that preserves system resources by only loading the chatbot interface when a user makes a selection.

## 🚀 Key Features
1.  **Lazy-Load Execution:** Chatbots (iframes) do not load on page start, ensuring a 100/100 performance score and fast initial paint.
2.  **Adaptive WordPress Nudge:** A floating notification system that prompts users for action after 5 seconds of engagement.
3.  **Cross-Platform Compatibility:** Responsive design that switches from a 3-column layout on desktop to a single-card swipeable carousel on mobile.
4.  **Jotform Agent Integration:** Specifically styled for the Jotform AI ecosystem, ensuring the chat interface fits perfectly within the viewport.

## 🛠 Setup & Customization
To add a new chatbot:
1.  Copy a `.bot-card` div in the first section.
2.  Update the `activateChat` function call with your new **Jotform Agent URL**.
3.  Replace the `img src` with your custom branding.

## 📜 Deployment
This script is standalone. Upload `index.html` to any GitHub Pages repository or paste it into a Blogger HTML gadget for instant deployment.

---




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
            width: 110%; height: 600px; background: #111;
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
