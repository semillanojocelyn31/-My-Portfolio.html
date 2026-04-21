<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Jocelyn Semillano - Enchanted Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>

    <style>
        /* ✨ Body & Background */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
            background: radial-gradient(circle at top, #2b003a, #0a0015 80%);
        }

        /* ✨ Animated mist */
        @keyframes swirl {0%{background-position:0 0;}100%{background-position:1000px 1000px;}}
        .mist {
            position: fixed;top:0;left:0;width:100%;height:100%;
            background: radial-gradient(circle, rgba(255,182,193,0.2), transparent 70%), radial-gradient(circle, rgba(255,105,180,0.15), transparent 60%);
            background-size: 2000px 2000px;
            animation: swirl 60s linear infinite;
            z-index:-3;pointer-events:none;
        }

        /* ✨ Stars + sparkles */
        .stars {position:fixed;width:100%;height:100%;background:transparent url('https://www.transparenttextures.com/patterns/stardust.png') repeat;opacity:.7;z-index:-2;}
        .sparkles {position:fixed;top:0;left:0;width:100%;height:100%;background-size:cover;mix-blend-mode:screen;opacity:.3;animation:drift 20s linear infinite;z-index:-1;}
        @keyframes drift{0%{transform:translate(0,0);}50%{transform:translate(-20px,20px);}100%{transform:translate(20px,-20px);}}

        /* ✨ Magical frame */
        .magic-frame::before {
            content:"";position:fixed;top:0;left:0;width:100%;height:100%;
            border-radius:25px;box-shadow:0 0 40px 10px #ff66cc;
            animation:pulse 6s ease-in-out infinite alternate;
            pointer-events:none;z-index:-1;
        }
        @keyframes pulse{0%{opacity:.7;box-shadow:0 0 20px 5px #ff66cc;}100%{opacity:1;box-shadow:0 0 60px 20px #ff99ff;}}

        /* ✨ Text glow */
        .glow-text{text-shadow:0 0 10px #ff99ff,0 0 20px #ff66cc;}
        .glow-border{box-shadow:0 0 15px 4px #ff66ff;transition:.3s; overflow: hidden; }
        .glow-border:hover{box-shadow:0 0 30px 10px #ff99ff;transform:scale(1.03);}

        /* ✨ Floating animation */
        @keyframes float{0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);}}
        .float{animation:float 6s ease-in-out infinite;}

        /* ✨ Scrollbar */
        ::-webkit-scrollbar{width:6px;}::-webkit-scrollbar-thumb{background:#ff66ff;border-radius:4px;}
        section{scroll-margin-top:80px;}

        /* 🤖 Chatbot Styles */
        #chat-container {
            position: fixed;
            bottom: 90px;
            right: 20px;
            width: 320px;
            max-height: 450px;
            background: rgba(26, 0, 51, 0.98);
            border: 2px solid #ff66cc;
            border-radius: 15px;
            display: flex;
            flex-direction: column;
            z-index: 1000;
            box-shadow: 0 0 25px #ff66cc;
            display: none;
        }

        #chat-header {
            background: linear-gradient(to right, #ff66cc, #b026ff);
            padding: 12px;
            border-radius: 12px 12px 0 0;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        #chat-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            font-size: 0.85rem;
            max-height: 300px;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .bot-msg { 
            background: rgba(255, 102, 204, 0.2);
            color: #ffccff; 
            padding: 8px 12px;
            border-radius: 15px 15px 15px 0;
            align-self: flex-start;
            max-width: 85%;
            border-left: 3px solid #ff66cc;
        }

        .user-msg { 
            background: rgba(255, 255, 255, 0.1);
            color: #fff; 
            padding: 8px 12px;
            border-radius: 15px 15px 0 15px;
            align-self: flex-end;
            max-width: 85%;
        }

        #chat-input-area {
            display: flex;
            padding: 12px;
            border-top: 1px solid rgba(255, 102, 204, 0.3);
        }

        #chat-input {
            flex: 1;
            background: rgba(0,0,0,0.3);
            border: 1px solid #ff66cc;
            border-radius: 20px;
            color: white;
            padding: 8px 15px;
            outline: none;
            font-size: 0.85rem;
        }

        #chat-toggle {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(45deg, #ff66cc, #b026ff);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1001;
            box-shadow: 0 0 20px #ff66cc;
            font-size: 30px;
            transition: transform 0.3s;
        }
        #chat-toggle:hover { transform: scale(1.1); }
    </style>
</head>

<body>

<div class="mist"></div>
<div class="stars"></div>
<div class="sparkles"></div>
<div class="magic-frame"></div>

<nav class="py-3 px-2 text-center text-white font-bold text-sm sm:text-base flex flex-wrap justify-center gap-3 sticky top-0 z-50 bg-pink-700/40 backdrop-blur-md">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#resume">Resume</a>
    <a href="#certificates">Certificates</a>
    <a href="#simulation">Simulation</a>
    <a href="#projects">My Projects</a>
    <a href="#experience">Experience</a>
    <a href="#tutorials">Tutorials</a>
    <a href="#contact">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-16">
    <h1 class="text-3xl sm:text-4xl font-bold mb-6 glow-text whitespace-nowrap">Welcome to My Portfolio!</h1>
    <div class="relative mb-6">
        <img src="Just me.jpg" alt="Celyn" class="w-40 h-40 rounded-full border-4 border-pink-500 object-cover glow-border float">
    </div>
</section>

<section id="about" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-6 text-pink-400 glow-text whitespace-nowrap">✨ About Me ✨</h2>
    <div class="max-w-md sm:max-w-2xl mx-auto text-gray-200">
        <p>I am <span class="font-bold text-white">Celyn</span>, a 2nd Year BSIT Student. I enjoy creating magical digital experiences through technology and design.</p>
    </div>
</section>

<section id="resume" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">📄 My Resume</h2>
    <div class="max-w-xs mx-auto">
        <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="resume.jpg" alt="My Resume" class="w-full rounded-lg mb-4">
            <div class="flex gap-2">
                <a href="resume.jpg" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="resume.jpg" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>
    </div>
</section>

<section id="certificates" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">📜 IT Training Certificate</h2>
    <div class="flex flex-col items-center gap-8 max-w-2xl mx-auto">
        <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
            <p class="text-pink-300 font-semibold mb-2">March 10, 2026</p>
            <img src="March 10.jpg" class="w-full h-auto rounded-lg border border-pink-400 shadow-md mb-4" alt="Training Certificate 1">
            <div class="flex gap-2">
                <a href="March 10.jpg" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="March 10.jpg" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>
        <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
            <p class="text-pink-300 font-semibold mb-2">March 12, 2026</p>
            <img src="March 12.jpg" class="w-full h-auto rounded-lg border border-pink-400 shadow-md mb-4" alt="Training Certificate 2">
            <div class="flex gap-2">
                <a href="March 12.jpg" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="March 12.jpg" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>
    </div>
</section>

<section id="simulation" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text whitespace-nowrap">🧪 My Simulation</h2>
    <div class="max-w-4xl mx-auto bg-[#1a0033]/80 border border-pink-500 rounded-3xl p-6 shadow-[0_0_25px_#ff00cc]">
        <h3 class="text-2xl font-bold mb-6 text-white">BSIT-2B Attendance System</h3>
        
        <div class="flex flex-wrap justify-center gap-4 mb-8">
            <input type="date" id="attendanceDate" class="bg-black/50 border border-pink-500 text-white p-2 rounded-lg outline-none">
            <input type="text" id="subjectName" placeholder="Subject Name" class="bg-black/50 border border-pink-500 text-white p-2 rounded-lg outline-none">
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
            <div class="bg-white/5 p-4 rounded-2xl border border-pink-400/30">
                <h4 class="text-pink-300 font-bold mb-4">Girls 🌸</h4>
                <div id="girlsList" class="space-y-2 text-left h-64 overflow-y-auto pr-2"></div>
            </div>
            <div class="bg-white/5 p-4 rounded-2xl border border-blue-400/30">
                <h4 class="text-blue-300 font-bold mb-4">Boys 💎</h4>
                <div id="boysList" class="space-y-2 text-left h-64 overflow-y-auto pr-2"></div>
            </div>
        </div>

        <button onclick="generateSummary()" class="px-16 py-3 bg-pink-600 rounded-full font-bold hover:bg-pink-700 transition transform hover:scale-105 shadow-lg">DONE ✨</button>

        <div id="summaryPanel" class="hidden mt-8 p-6 bg-black/60 rounded-2xl border border-pink-500 text-left">
            <h3 class="text-xl font-bold text-center text-pink-400 mb-2">Attendance Report</h3>
            <p id="reportMeta" class="text-center text-gray-400 mb-6"></p>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                <div>
                    <h4 class="text-green-400 font-bold">Present: <span id="countPresent">0</span></h4>
                    <div id="listPresent" class="text-xs mt-2 whitespace-pre-line text-gray-300 leading-relaxed"></div>
                </div>
                <div>
                    <h4 class="text-red-400 font-bold">Absent: <span id="countAbsent">0</span></h4>
                    <div id="listAbsent" class="text-xs mt-2 whitespace-pre-line text-gray-300 leading-relaxed"></div>
                </div>
            </div>
        </div>
    </div>
</section>

<section id="projects" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">🛠️ My Projects</h2>
    <div class="flex flex-col items-center gap-10 max-w-md mx-auto">
        
        <div class="w-full bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="banner.jpg" class="w-full h-auto rounded-lg mb-4" alt="Banner Design">
            <div class="flex gap-2">
                <a href="banner.jpg" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="banner.jpg" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>

        <div class="w-full bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="chessboard.png" class="w-full h-auto rounded-lg mb-4" alt="Chessboard UI">
            <div class="flex gap-2">
                <a href="chessboard.png" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="chessboard.png" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>
        
        <div class="w-full bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="figma ecommerce.jpg" class="w-full h-auto rounded-lg mb-4" alt="Figma E-commerce">
            <div class="flex gap-2">
                <a href="https://www.figma.com/proto/9MoENLQK7Un0xgoNOWLQIS/?node-id=637-5447&p=f&t=f8hJwc3kD0kQkKZQ-1&scaling=scale-down&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=637%3A5447&show-proto-sidebar=1" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">View Figma</a>
                <a href="figma ecommerce.jpg" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>

        <div class="w-full bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="product design.png" class="w-full h-auto rounded-lg mb-4" alt="Product Design">
            <div class="flex gap-2">
                <a href="product design.png" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="product design.png" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>

        <div class="w-full bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
            <img src="tshirt layout.png" class="w-full h-auto rounded-lg mb-4" alt="T-Shirt Layout">
            <div class="flex gap-2">
                <a href="tshirt layout.png" target="_blank" class="flex-1 py-2 bg-pink-500 text-white font-bold rounded-lg hover:bg-pink-600 transition text-xs sm:text-sm">Full View</a>
                <a href="tshirt layout.png" download class="flex-1 py-2 bg-pink-700 text-white font-bold rounded-lg hover:bg-pink-800 transition text-xs sm:text-sm">Download</a>
            </div>
        </div>
    </div>
</section>

<section id="experience" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">🏆 Experience</h2>
    <div class="max-w-md sm:max-w-3xl mx-auto space-y-8 text-center">
        <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float">
            <h3 class="text-2xl font-semibold text-pink-300 glow-text mb-2">Video Editing Champion</h3>
            <p class="text-gray-300 mb-2">🏅 Year: 2021</p>
            <div class="flex flex-col items-center gap-6">
                <img src="film maker pro.png" class="w-24 h-24 rounded-lg glow-border">
                <img src="kinemaster.png" class="w-24 h-24 rounded-lg glow-border">
            </div>
        </div>
        <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float">
            <h3 class="text-2xl font-semibold text-pink-300 glow-text mb-2">Tarpapel Editor</h3>
            <p class="text-pink-300 font-medium mb-2">🎨 Year: 2020</p>
            <div class="flex flex-col items-center">
                <div class="relative w-28 h-28 bg-[#0a0015] border-2 border-pink-600 rounded-xl shadow-[0_0_15px_#ff66cc] flex items-center justify-center">
                    <img src="canva.jpeg" class="w-12 h-12 rounded-lg" alt="Canva Logo">
                </div>
            </div>
        </div>
    </div>
</section>

<section id="tutorials" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text whitespace-nowrap">✨ YouTube Tutorials</h2>
    <div class="flex flex-col items-center gap-8 max-w-2xl mx-auto">
        <iframe class="rounded-xl w-full h-64 glow-border" src="https://www.youtube.com/embed/wCEtWz5imUs"></iframe>
        <iframe class="rounded-xl w-full h-64 glow-border" src="https://www.youtube.com/embed/ezldKx-jPag"></iframe>
    </div>
</section>

<section id="tools" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">🪄 Tools I Used</h2>
    <div class="flex flex-row justify-center items-center gap-4 sm:gap-6">
        <img src="canva.jpeg" class="w-16 h-16 sm:w-24 sm:h-24 rounded-lg glow-border">
        <img src="figma.jpeg" class="w-16 h-16 sm:w-24 sm:h-24 rounded-lg glow-border">
        <img src="Adobe Photoshop.jpeg" class="w-16 h-16 sm:w-24 sm:h-24 rounded-lg glow-border">
        <img src="Adobe premiere.jpeg" class="w-16 h-16 sm:w-24 sm:h-24 rounded-lg glow-border">
    </div>
</section>

<section id="contact" class="text-center px-4 py-12">
    <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">💌 Let's Connect</h2>
    <div class="max-w-sm mx-auto p-6 bg-[#1a0033]/70 rounded-2xl border border-pink-600 glow-border">
        <form class="space-y-4">
            <input type="text" placeholder="Name" class="w-full p-2 border border-pink-400 rounded bg-transparent text-white">
            <input type="email" placeholder="Email" class="w-full p-2 border border-pink-400 rounded bg-transparent text-white">
            <textarea placeholder="Message" class="w-full p-2 border border-pink-400 rounded bg-transparent text-white"></textarea>
            <button type="button" class="w-full py-2 bg-pink-600 rounded font-bold hover:bg-pink-700 transition">Send</button>
        </form>
    </div>
</section>

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
    <div id="chat-header"><span>Celyn's AI Bot</span><button onclick="toggleChat()">✖</button></div>
    <div id="chat-messages"><div class="bot-msg">✨ Hi there! I am Celyn's AI Assistant. How can I help you today?</div></div>
    <div id="chat-input-area"><input type="text" id="chat-input" placeholder="Ask about projects, skills, resume..." onkeypress="handleChat(event)"></div>
</div>

<script>
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

        // 🧠 Keyword-based Logic (Acting like an AI)
        if (t.includes("hello") || t.includes("hi") || t.includes("hey")) {
            r = "Hello! ✨ I'm here to guide you through Celyn's portfolio. What would you like to know?";
        }
        else if (t.includes("project") || t.includes("work") || t.includes("figma") || t.includes("ecommerce")) {
            r = "Celyn has several projects like a Chessboard UI, T-shirt layouts, and a full Figma E-commerce prototype! Check the 'My Projects' section. 🛠️";
        }
        else if (t.includes("resume") || t.includes("cv") || t.includes("bio")) {
            r = "You can view or download Celyn's full resume in the 'Resume' section above! 📄";
        }
        else if (t.includes("cert") || t.includes("training") || t.includes("march")) {
            r = "Celyn earned IT Training Certificates in March 2026. They are displayed in the 'Certificates' section! 📜";
        }
        else if (t.includes("simulation") || t.includes("attendance") || t.includes("bsit")) {
            r = "The BSIT-2B Attendance System is an interactive tool Celyn built! You can try it out in the 'Simulation' section. 🧪";
        }
        else if (t.includes("skill") || t.includes("tool") || t.includes("canva") || t.includes("photoshop")) {
            r = "Celyn is skilled in Figma, Canva, Adobe Photoshop, and Premiere Pro. Check out the 'Tools I Used' section for more! 🪄";
        }
        else if (t.includes("experience") || t.includes("champion") || t.includes("winner")) {
            r = "Celyn was a Video Editing Champion in 2021 and a Tarpapel Editor in 2020! Details are in the 'Experience' section. 🏆";
        }
        else if (t.includes("tutorial") || t.includes("youtube") || t.includes("video")) {
            r = "Celyn has educational tutorials on YouTube. You can watch them directly in the 'Tutorials' section! ✨";
        }
        else if (t.includes("contact") || t.includes("email") || t.includes("message")) {
            r = "Feel free to send Celyn a message using the contact form at the bottom of the page! 💌";
        }
        else if (t.includes("who") || t.includes("about")) {
            r = "Celyn is a 2nd Year BSIT Student passionate about digital experiences and IT! 👩‍💻";
        }
        // Fallback for general inquiries
        else {
            const genericRespones = [
                "That's an interesting question! ✨ Feel free to explore the different sections of the portfolio to learn more about Celyn.",
                "I'm not quite sure about that, but I can tell you about Celyn's projects or resume! 🪄",
                "Celyn is always working on something magical! Check out the 'My Projects' section for her latest work. 🛠️",
                "I'm a simple AI here to help you navigate. Is there a specific section you'd like to see? ✨"
            ];
            r = genericRespones[Math.floor(Math.random() * genericRespones.length)];
        }
        
        addMessage(r, 'bot-msg');
    }

    const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan","Jessa Erosido","Jessa Hilardino","Kristine Joy Basa","Lena Bahian","Rechelle An Casilangan","Roxan Pracio","Shannon De La Cruz","Jeca Dagumboy","Martina Cabrillos","Nera Bahilot","Sheila Marie Lañojan","Trisha Agravante"];
    const boys = ["Archie Vidal","John Rogen Bullag","Mario Nebres Jr.","AjhannAylle Marfil","Anthony Espinosa","Dave Rivera","Jeffrey Coriento","Kenneth Espinosa","Kevin James Plaza","Luke Axel Barrocum","Mark Angelou Banatasa","Nathaniel Pojas","Paul John Malba","Rodel Cepeda"];

    document.getElementById('attendanceDate').valueAsDate = new Date();

    function renderList(list, elementId) {
        const container = document.getElementById(elementId);
        list.sort().forEach(name => {
            container.innerHTML += `
            <div class="flex justify-between items-center p-2 bg-white/5 rounded-lg mb-1 hover:bg-pink-500/20 transition">
                <span class="text-sm">${name}</span>
                <input type="checkbox" class="att-check w-4 h-4 accent-pink-500 cursor-pointer" data-name="${name}">
            </div>`;
        });
    }

    renderList(girls, 'girlsList');
    renderList(boys, 'boysList');

    function generateSummary() {
        const checks = document.querySelectorAll('.att-check');
        let present = []; let absent = [];
        checks.forEach(check => {
            const name = check.getAttribute('data-name');
            if (check.checked) present.push(name); else absent.push(name);
        });
        document.getElementById('countPresent').innerText = present.length;
        document.getElementById('countAbsent').innerText = absent.length;
        document.getElementById('listPresent').innerText = present.length > 0 ? present.map(n => "• " + n).join("\n") : "None";
        document.getElementById('listAbsent').innerText = absent.length > 0 ? absent.map(n => "• " + n).join("\n") : "None";
        const dateVal = document.getElementById('attendanceDate').value;
        const subVal = document.getElementById('subjectName').value || "Class Session";
        document.getElementById('reportMeta').innerText = `${subVal} — ${dateVal}`;
        const panel = document.getElementById('summaryPanel');
        panel.classList.remove('hidden');
        panel.style.display = 'block';
        panel.scrollIntoView({ behavior: 'smooth', block: 'center' });
    }
</script>
</body>
</html>
