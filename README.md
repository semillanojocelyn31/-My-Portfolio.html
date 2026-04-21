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

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
    <div id="chat-header"><span>Celyn's Bot</span><button onclick="toggleChat()">✖</button></div>
    <div id="chat-messages"><div class="bot-msg">✨ Hi there! I am Celyn's Assistant. How can I help you navigate through her portfolio today?</div></div>
    <div id="chat-input-area"><input type="text" id="chat-input" placeholder="Ask anything about Celyn's work..." onkeypress="handleChat(event)"></div>
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
            if (msg) { 
                addMessage(msg, 'user-msg'); 
                input.value = ''; 
                setTimeout(() => botResponse(msg), 600); 
            }
        }
    }

    function addMessage(t, c) {
        const d = document.createElement('div'); 
        d.className = c; 
        d.innerText = t;
        const m = document.getElementById('chat-messages'); 
        m.appendChild(d); 
        m.scrollTop = m.scrollHeight;
    }

    function botResponse(u) {
        let r = "";
        const t = u.toLowerCase();

        // --- FULL AUTOMATED INQUIRY RESPONSES ---

        // 1. Greetings
        if (t.includes("hello") || t.includes("hi") || t.includes("hey") || t.includes("greetings")) {
            r = "Greetings! ✨ I'm Celyn's automated guide. You can ask me about her IT projects, background, or skills!";
        }
        
        // 2. Personal Info & Education
        else if (t.includes("who is") || t.includes("about celyn") || t.includes("tell me about her")) {
            r = "Celyn is a dedicated 2nd Year BSIT Student from Moises Padilla, Negros Occidental. She loves web development and interactive design!";
        }
        else if (t.includes("school") || t.includes("university") || t.includes("bsit") || t.includes("student")) {
            r = "She is currently pursuing a Bachelor of Science in Information Technology (BSIT) and is part of section BSIT-2B.";
        }
        else if (t.includes("location") || t.includes("live") || t.includes("negros") || t.includes("moises padilla")) {
            r = "Celyn is based in the beautiful municipality of Moises Padilla, Negros Occidental.";
        }

        // 3. Specific Projects
        else if (t.includes("project") || t.includes("work") || t.includes("portfolio")) {
            r = "Celyn has a variety of projects including a Chessboard UI, T-shirt layouts, and an Attendance System. Scroll to 'My Projects' to see them! 🛠️";
        }
        else if (t.includes("ecommerce") || t.includes("figma") || t.includes("online shop")) {
            r = "She designed a full E-commerce prototype using Figma. You can view the live prototype in the Projects section!";
        }
        else if (t.includes("chessboard")) {
            r = "The Chessboard project was a UI design exercise focusing on clean layouts and grid systems. ♟️";
        }
        else if (t.includes("vending machine") || t.includes("hoopshot") || t.includes("vendo")) {
            r = "She worked on a technical research project for an Arcade Basketball Vending Machine called 'HoopShot Vendo'!";
        }
        else if (t.includes("attendance") || t.includes("attendance system")) {
            r = "The BSIT-2B Attendance System is an automated tool she developed to track class presence efficiently. You can test it in the 'Simulation' section!";
        }

        // 4. Skills & Tools
        else if (t.includes("skills") || t.includes("what can she do")) {
            r = "Celyn is skilled in Frontend & Backend development (HTML, CSS, PHP, MySQL), UI/UX design (Figma), and Graphic Design (Canva, Photoshop).";
        }
        else if (t.includes("canva") || t.includes("photoshop") || t.includes("premiere")) {
            r = "She uses Canva for quick layouts, Photoshop for complex designs, and Premiere Pro for video editing champion-level work! 🪄";
        }
        else if (t.includes("code") || t.includes("programming") || t.includes("language")) {
            r = "Celyn works primarily with HTML, CSS, PHP, and MySQL to build functional web applications.";
        }

        // 5. Achievements & Experience
        else if (t.includes("experience") || t.includes("champion") || t.includes("win")) {
            r = "She was a Video Editing Champion in 2021 and has extensive experience as a Tarpapel Editor since 2020!";
        }
        else if (t.includes("certificates") || t.includes("training") || t.includes("march 10")) {
            r = "Celyn completed specialized IT trainings in March 2026. You can download her certificates in the 'Certificates' section! 📜";
        }

        // 6. Career & Contact
        else if (t.includes("resume") || t.includes("cv") || t.includes("download")) {
            r = "Her updated resume is available for viewing and download in the 'Resume' section above. 📄";
        }
        else if (t.includes("contact") || t.includes("hire") || t.includes("email") || t.includes("message")) {
            r = "You can reach out to her via the contact form at the bottom of the page or check her YouTube tutorials! 💌";
        }
        else if (t.includes("youtube") || t.includes("tutorial") || t.includes("video")) {
            r = "She has tutorials on her YouTube channel covering various IT topics. Check the 'YouTube Tutorials' section!";
        }

        // 7. Fun/Easter Eggs
        else if (t.includes("thank") || t.includes("thanks")) {
            r = "You're very welcome! Is there anything else about Celyn's work you'd like to explore? ✨";
        }
        else if (t.includes("bye") || t.includes("goodbye")) {
            r = "Goodbye! Have a magical day exploring the portfolio! 👋";
        }

        // 8. General AI Fallback
        else {
            const genericRespones = [
                "That's a great question! ✨ Celyn has many skills in BSIT—try asking about her projects or certificates.",
                "I'm here to help! You can ask about her 'Attendance System' or her 'Figma designs' for more details.",
                "Celyn's portfolio covers many areas like programming and design. Which one would you like to hear about? 🪄",
                "I'm Celyn's automated assistant. If you're looking for something specific, try the navigation bar or ask me about her 'Resume'!"
            ];
            r = genericRespones[Math.floor(Math.random() * genericRespones.length)];
        }
        
        addMessage(r, 'bot-msg');
    }
</script>
</body>
</html>
