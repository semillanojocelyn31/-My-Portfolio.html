<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Jocelyn Semillano - Enchanted Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        /* ✨ Magical Environment */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
            background: radial-gradient(circle at top, #2b003a, #0a0015 80%);
        }

        .mist {
            position: fixed; top:0; left:0; width:100%; height:100%;
            background: radial-gradient(circle, rgba(255,182,193,0.2), transparent 70%), radial-gradient(circle, rgba(255,105,180,0.15), transparent 60%);
            background-size: 2000px 2000px;
            animation: swirl 60s linear infinite;
            z-index:-3; pointer-events:none;
        }
        @keyframes swirl {0%{background-position:0 0;}100%{background-position:1000px 1000px;}}

        .stars { position:fixed; width:100%; height:100%; background:transparent url('https://www.transparenttextures.com/patterns/stardust.png') repeat; opacity:.7; z-index:-2; }

        .magic-frame::before {
            content:""; position:fixed; top:0; left:0; width:100%; height:100%;
            border-radius:25px; box-shadow:0 0 40px 10px #ff66cc;
            animation:pulse 6s ease-in-out infinite alternate;
            pointer-events:none; z-index:-1;
        }
        @keyframes pulse {0%{opacity:.7; box-shadow:0 0 20px 5px #ff66cc;} 100%{opacity:1; box-shadow:0 0 60px 20px #ff99ff;}}

        .glow-text { text-shadow:0 0 10px #ff99ff, 0 0 20px #ff66cc; }
        .glow-border { box-shadow:0 0 15px 4px #ff66ff; transition:.3s; overflow: hidden; }
        .glow-border:hover { box-shadow:0 0 30px 10px #ff99ff; transform:scale(1.03); }

        @keyframes float { 0%,100%{transform:translateY(0);} 50%{transform:translateY(-10px);} }
        .float { animation:float 6s ease-in-out infinite; }

        /* 🤖 Celyn's Bot UI */
        #chat-container {
            position: fixed; bottom: 90px; right: 20px; width: 320px; max-height: 450px;
            background: rgba(26, 0, 51, 0.98); border: 2px solid #ff66cc; border-radius: 15px;
            display: flex; flex-direction: column; z-index: 1000; box-shadow: 0 0 25px #ff66cc; display: none;
        }
        #chat-header {
            background: linear-gradient(to right, #ff66cc, #b026ff); padding: 12px;
            border-radius: 12px 12px 0 0; font-weight: bold; display: flex; justify-content: space-between; align-items: center;
        }
        #chat-messages { flex: 1; padding: 15px; overflow-y: auto; font-size: 0.85rem; display: flex; flex-direction: column; gap: 10px; }
        .bot-msg { background: rgba(255, 102, 204, 0.2); color: #ffccff; padding: 8px 12px; border-radius: 15px 15px 15px 0; align-self: flex-start; max-width: 85%; border-left: 3px solid #ff66cc; }
        .user-msg { background: rgba(255, 255, 255, 0.1); color: #fff; padding: 8px 12px; border-radius: 15px 15px 0 15px; align-self: flex-end; max-width: 85%; }
        #chat-input-area { display: flex; padding: 12px; border-top: 1px solid rgba(255, 102, 204, 0.3); }
        #chat-input { flex: 1; background: rgba(0,0,0,0.3); border: 1px solid #ff66cc; border-radius: 20px; color: white; padding: 8px 15px; outline: none; }
        #chat-toggle {
            position: fixed; bottom: 20px; right: 20px; background: linear-gradient(45deg, #ff66cc, #b026ff);
            width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center;
            cursor: pointer; z-index: 1001; box-shadow: 0 0 20px #ff66cc; font-size: 30px;
        }
        
        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-thumb { background: #ff66cc; border-radius: 10px; }
    </style>
</head>
<body>

<div class="mist"></div>
<div class="stars"></div>
<div class="magic-frame"></div>

<nav class="py-3 px-2 text-center text-white font-bold flex flex-wrap justify-center gap-4 sticky top-0 z-50 bg-pink-700/40 backdrop-blur-md">
    <a href="#home" class="hover:text-pink-300 transition">Home</a>
    <a href="#about" class="hover:text-pink-300 transition">About</a>
    <a href="#resume" class="hover:text-pink-300 transition">Resume</a>
    <a href="#certificates" class="hover:text-pink-300 transition">Certificates</a>
    <a href="#simulation" class="hover:text-pink-300 transition">Simulation</a>
    <a href="#projects" class="hover:text-pink-300 transition">Projects</a>
    <a href="#contact" class="hover:text-pink-300 transition">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-20">
    <h1 class="text-4xl sm:text-5xl font-bold mb-8 glow-text">Jocelyn Semillano</h1>
    <div class="relative">
        <img src="Just me.jpg" alt="Celyn" class="w-48 h-48 rounded-full border-4 border-pink-500 object-cover glow-border float">
    </div>
    <p class="mt-6 text-xl text-pink-200">BSIT Student | Digital Artist | Developer</p>
</section>

<section id="about" class="text-center px-4 py-16">
    <h2 class="text-3xl font-bold mb-6 text-pink-400 glow-text">✨ About Me ✨</h2>
    <div class="max-w-3xl mx-auto bg-black/30 p-8 rounded-3xl border border-pink-500/30 backdrop-blur-sm">
        <p class="text-lg leading-relaxed text-gray-200">
            I am a 2nd Year **Bachelor of Science in Information Technology** student from **Moises Padilla, Negros Occidental**. 
            I am passionate about building visually aesthetic digital experiences, from web applications to creative UI/UX designs in Figma.
        </p>
    </div>
</section>

<section id="simulation" class="text-center px-4 py-16">
    <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text">🧪 BSIT-2B Attendance System</h2>
    <div class="max-w-5xl mx-auto bg-[#1a0033]/80 border border-pink-500 rounded-3xl p-6 shadow-2xl">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
            <div class="bg-white/5 p-5 rounded-2xl border border-pink-400/30">
                <h4 class="text-pink-300 font-bold mb-4 text-xl">Girls 🌸</h4>
                <div id="girlsList" class="space-y-2 text-left h-72 overflow-y-auto pr-2"></div>
            </div>
            <div class="bg-white/5 p-5 rounded-2xl border border-blue-400/30">
                <h4 class="text-blue-300 font-bold mb-4 text-xl">Boys 💎</h4>
                <div id="boysList" class="space-y-2 text-left h-72 overflow-y-auto pr-2"></div>
            </div>
        </div>
        <button onclick="generateSummary()" class="px-20 py-4 bg-pink-600 rounded-full font-extrabold text-xl hover:bg-pink-700 transition transform hover:scale-105 shadow-[0_0_20px_rgba(255,102,204,0.5)]">DONE ✨</button>
        
        <div id="summaryPanel" class="hidden mt-10 p-8 bg-black/70 rounded-2xl border border-pink-500 text-left">
            <h3 class="text-2xl font-bold text-pink-400 text-center mb-6 underline">Attendance Report Summary</h3>
            <div id="reportContent" class="grid grid-cols-1 sm:grid-cols-2 gap-8"></div>
        </div>
    </div>
</section>

<section id="projects" class="text-center px-4 py-16">
    <h2 class="text-3xl font-bold mb-12 text-pink-400 glow-text">🛠️ My Digital Projects</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <div class="bg-[#1a0033]/70 border border-pink-500 p-4 rounded-2xl glow-border">
            <img src="figma ecommerce.jpg" class="w-full h-40 object-cover rounded-lg mb-4" alt="E-commerce">
            <h3 class="font-bold">Figma E-Commerce</h3>
        </div>
        <div class="bg-[#1a0033]/70 border border-pink-500 p-4 rounded-2xl glow-border">
            <img src="chessboard.png" class="w-full h-40 object-cover rounded-lg mb-4" alt="Chessboard">
            <h3 class="font-bold">Chessboard UI</h3>
        </div>
        <div class="bg-[#1a0033]/70 border border-pink-500 p-4 rounded-2xl glow-border">
            <img src="tshirt layout.png" class="w-full h-40 object-cover rounded-lg mb-4" alt="T-Shirt">
            <h3 class="font-bold">T-Shirt Layouts</h3>
        </div>
    </div>
</section>

<section id="contact" class="text-center px-4 py-16">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">💌 Get In Touch</h2>
    <div class="max-w-lg mx-auto bg-black/40 p-8 rounded-3xl border border-pink-600 backdrop-blur-md">
        <form class="space-y-4">
            <input type="text" placeholder="Your Name" class="w-full p-3 bg-transparent border border-pink-400 rounded-xl text-white outline-none focus:border-pink-300">
            <textarea placeholder="Your Message" rows="4" class="w-full p-3 bg-transparent border border-pink-400 rounded-xl text-white outline-none focus:border-pink-300"></textarea>
            <button type="button" class="w-full py-3 bg-pink-600 rounded-xl font-bold hover:bg-pink-700 transition">Send Magic ✨</button>
        </form>
    </div>
</section>

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
    <div id="chat-header"><span>Celyn's Bot</span><button onclick="toggleChat()">✖</button></div>
    <div id="chat-messages">
        <div class="bot-msg">✨ Hi! I am Celyn's automated assistant. I can answer questions about her education, skills, projects, and the attendance system!</div>
    </div>
    <div id="chat-input-area">
        <input type="text" id="chat-input" placeholder="Ask me anything..." onkeypress="handleChat(event)">
    </div>
</div>

<script>
    // --- ATTENDANCE LIST DATA ---
    const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan","Jessa Erosido","Jessa Hilardino","Kristine Joy Basa","Lena Bahian","Rechelle An Casilangan","Roxan Pracio","Shannon De La Cruz","Jeca Dagumboy","Martina Cabrillos","Nera Bahilot","Sheila Marie Lañojan","Trisha Agravante"];
    const boys = ["Archie Vidal","John Rogen Bullag","Mario Nebres Jr.","AjhannAylle Marfil","Anthony Espinosa","Dave Rivera","Jeffrey Coriento","Kenneth Espinosa","Kevin James Plaza","Luke Axel Barrocum","Mark Angelou Banatasa","Nathaniel Pojas","Paul John Malba","Rodel Cepeda"];

    function renderList(list, id) {
        const el = document.getElementById(id);
        list.sort().forEach(name => {
            el.innerHTML += `
                <div class="flex justify-between items-center p-3 bg-white/5 rounded-xl mb-2 hover:bg-pink-500/20 transition cursor-pointer" onclick="this.querySelector('input').click()">
                    <span class="text-sm font-medium">${name}</span>
                    <input type="checkbox" class="att-check w-5 h-5 accent-pink-500" data-name="${name}" onclick="event.stopPropagation()">
                </div>`;
        });
    }
    renderList(girls, 'girlsList'); 
    renderList(boys, 'boysList');

    function generateSummary() {
        const checks = document.querySelectorAll('.att-check');
        let p = [], a = [];
        checks.forEach(c => { if(c.checked) p.push(c.dataset.name); else a.push(c.dataset.name); });
        
        document.getElementById('reportContent').innerHTML = `
            <div class="p-4 bg-green-500/10 border border-green-500/30 rounded-xl">
                <b class="text-green-400 text-lg">Present: ${p.length}</b>
                <p class="text-xs mt-2 text-gray-300 leading-relaxed">${p.join(' • ')}</p>
            </div>
            <div class="p-4 bg-red-500/10 border border-red-500/30 rounded-xl">
                < b class="text-red-400 text-lg">Absent: ${a.length}</b>
                <p class="text-xs mt-2 text-gray-300 leading-relaxed">${a.join(' • ')}</p>
            </div>
        `;
        const panel = document.getElementById('summaryPanel');
        panel.classList.remove('hidden');
        panel.scrollIntoView({ behavior: 'smooth', block: 'center' });
    }

    // --- FULLY AUTOMATED BOT RESPONSES ---
    function toggleChat() {
        const chat = document.getElementById('chat-container');
        chat.style.display = (chat.style.display === 'none' || chat.style.display === '') ? 'flex' : 'none';
    }

    function handleChat(e) {
        if (e.key === 'Enter') {
            const input = document.getElementById('chat-input');
            const msg = input.value.trim();
            if (msg) { addMessage(msg, 'user-msg'); input.value = ''; setTimeout(() => botResponse(msg), 600); }
        }
    }

    function addMessage(t, c) {
        const d = document.createElement('div'); d.className = c; d.innerText = t;
        const m = document.getElementById('chat-messages'); m.appendChild(d); m.scrollTop = m.scrollHeight;
    }

    function botResponse(u) {
        let r = "";
        const t = u.toLowerCase();

        // Automated Intelligence Logic
        if (t.includes("hi") || t.includes("hello") || t.includes("hey")) {
            r = "Hello! ✨ I'm Celyn's automated assistant. How can I help you explore her portfolio today?";
        }
        else if (t.includes("who is celyn") || t.includes("about") || t.includes("owner")) {
            r = "Celyn (Jocelyn Semillano) is a BSIT-2B student from Moises Padilla. She is a developer, designer, and video editing champion! 🏆";
        }
        else if (t.includes("project") || t.includes("work")) {
            r = "Celyn has worked on an Attendance System, Chessboard UI, T-shirt designs, and a Figma E-commerce prototype. You can see them in the 'Projects' section! 🛠️";
        }
        else if (t.includes("attendance") || t.includes("system") || t.includes("simulation")) {
            r = "The BSIT-2B Attendance System is a web tool built by Celyn to track students. You can try the live simulation on this page! 🧪";
        }
        else if (t.includes("skill") || t.includes("code") || t.includes("language")) {
            r = "Celyn is skilled in HTML, CSS, PHP, and MySQL. She also uses Figma, Canva, and Adobe tools for design! 🪄";
        }
        else if (t.includes("location") || t.includes("live") || t.includes("negros")) {
            r = "Celyn is based in the municipality of Moises Padilla, Negros Occidental. 📍";
        }
        else if (t.includes("certificate") || t.includes("training") || t.includes("march")) {
            r = "Celyn completed IT trainings in March 2026. You can find her certificates in the Certificates section! 📜";
        }
        else if (t.includes("resume") || t.includes("cv")) {
            r = "You can view and download Celyn's full resume in the 'Resume' section above. 📄";
        }
        else if (t.includes("vending machine") || t.includes("hoopshot")) {
            r = "She worked on the HoopShot Vendo project, a technical research prototype for an arcade basketball vending machine! 🏀";
        }
        else if (t.includes("thank")) {
            r = "You're very welcome! Feel free to ask anything else about Celyn's work. ✨";
        }
        else if (t.includes("what is it") || t.includes("information technology")) {
            r = "Information Technology is the study and use of systems for storing and sending information. It's the core of everything Celyn builds! 💻";
        }
        else if (t.includes("bye") || t.includes("goodbye")) {
            r = "Goodbye! I hope you enjoyed your visit to Celyn's enchanted portfolio! 👋";
        }
        else {
            // Automated Fallback
            const generic = [
                "That's an interesting question! ✨ I'm programmed to talk about Celyn's IT projects, skills, and background. Try asking about those!",
                "I'm not sure about that, but I can tell you about Celyn's 'Attendance System' or her 'Figma designs'! 🪄",
                "I'm still learning! You can find more info in the 'About' or 'Experience' sections. 🛠️",
                "Celyn is always working on something magical. Ask me about her 'Projects' to see for yourself!"
            ];
            r = generic[Math.floor(Math.random() * generic.length)];
        }
        addMessage(r, 'bot-msg');
    }
</script>

</body>
</html>
