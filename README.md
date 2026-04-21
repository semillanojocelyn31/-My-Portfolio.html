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
.sparkles {position:fixed;top:0;left:0;width:100%;height:100%;background:transparent url('https://www.transparenttextures.com/patterns/stardust.png') repeat;background-size:cover;mix-blend-mode:screen;opacity:.3;animation:drift 20s linear infinite;z-index:-1;}
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
.glow-border{box-shadow:0 0 15px 4px #ff66ff;transition:.3s;cursor:pointer;}
.glow-border:hover{box-shadow:0 0 30px 10px #ff99ff;transform:scale(1.03);}

/* ✨ Floating animation */
@keyframes float{0%,100%{transform:translateY(0);}50%{transform:translateY(-10px);}}
.float{animation:float 6s ease-in-out infinite;}

/* Scrollbar */
::-webkit-scrollbar{width:6px;}::-webkit-scrollbar-thumb{background:#ff66ff;border-radius:4px;}
section{scroll-margin-top:80px;}

/* 🤖 Chatbot Styles */
#chat-container {
  position: fixed;
  bottom: 90px;
  right: 20px;
  width: 300px;
  max-height: 400px;
  background: rgba(26, 0, 51, 0.95);
  border: 2px solid #ff66cc;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  z-index: 1000;
  box-shadow: 0 0 20px #ff66cc;
  display: none;
}

#chat-header {
  background: #ff66cc;
  padding: 10px;
  border-radius: 12px 12px 0 0;
  font-weight: bold;
  display: flex;
  justify-content: space-between;
}

#chat-messages {
  flex: 1;
  padding: 10px;
  overflow-y: auto;
  font-size: 0.9rem;
}

.bot-msg { color: #ff99ff; margin-bottom: 8px; border-left: 2px solid #ff66cc; padding-left: 8px; }
.user-msg { color: #fff; margin-bottom: 8px; text-align: right; background: rgba(255, 102, 204, 0.2); padding: 5px; border-radius: 5px; align-self: flex-end; }

#chat-input-area {
  display: flex;
  padding: 10px;
  border-top: 1px solid #ff66cc;
}

#chat-input {
  flex: 1;
  background: transparent;
  border: 1px solid #ff66cc;
  border-radius: 5px;
  color: white;
  padding: 5px;
  outline: none;
}

#chat-toggle {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #ff66cc;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 1001;
  box-shadow: 0 0 15px #ff66cc;
  font-size: 30px;
}
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
  <a href="#skills">Skills</a>
  <a href="#experience">Experience</a>
  <a href="#tutorials">Tutorials</a>
  <a href="#contact">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-16">
  <h1 class="text-3xl sm:text-4xl font-bold mb-6 glow-text">Welcome to My Portfolio!</h1>
  <div class="relative mb-6">
    <img src="Just me.jpg" alt="Celyn" class="w-40 h-40 rounded-full border-4 border-pink-500 object-cover glow-border float">
  </div>
</section>

<section id="about" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-6 text-pink-400 glow-text">✨ About Me ✨</h2>
  <div class="max-w-md sm:max-w-2xl mx-auto text-gray-200">
    <p>I am <span class="font-bold text-white">Celyn</span>, a 2nd Year BSIT Student. I create magical digital experiences through technology and design.</p>
  </div>
</section>

<section id="resume" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">📄 My Resume</h2>
  <div class="max-w-xs mx-auto">
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-4 glow-border float">
      <img src="resume.jpg" alt="Resume Preview" class="w-full rounded-lg mb-4 cursor-pointer">
      <div class="flex flex-col gap-2">
        <a href="resume.jpg" target="_blank" class="w-full py-2 bg-purple-600 text-white font-bold rounded-lg hover:bg-purple-700 transition">View Full</a>
        <a href="resume.jpg" download class="w-full py-2 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition">Download</a>
      </div>
    </div>
  </div>
</section>

<section id="certificates" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-10 text-pink-400 glow-text">📜 IT Training Certificates</h2>
  <div class="flex flex-col items-center gap-8 max-w-2xl mx-auto">
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
      <p class="text-pink-300 font-bold mb-4">March 10, 2026</p>
      <img src="March 10.jpg" class="w-full h-auto rounded-lg border border-pink-400 mb-6 cursor-pointer" alt="Certificate March 10">
      <a href="March 10.jpg" download class="inline-block py-2 px-8 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition">Download</a>
    </div>
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
      <p class="text-pink-300 font-bold mb-4">March 12, 2026</p>
      <img src="March 12.jpg" class="w-full h-auto rounded-lg border border-pink-400 mb-6 cursor-pointer" alt="Certificate March 12">
      <a href="March 12.jpg" download class="inline-block py-2 px-8 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition">Download</a>
    </div>
  </div>
</section>

<section id="simulation" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text">🧪 My Simulation</h2>
  <div class="max-w-4xl mx-auto bg-[#1a0033]/90 border border-pink-500 rounded-3xl p-8 shadow-[0_0_20px_rgba(255,102,204,0.3)]">
    <h3 class="text-2xl font-bold mb-6">BSIT-2B Attendance System</h3>
    <div class="flex flex-wrap justify-center gap-4 mb-8">
      <input type="date" id="attendanceDate" class="bg-black/60 border border-pink-500 text-white p-2 rounded-lg outline-none">
      <input type="text" id="subjectName" placeholder="Subject Name" class="bg-black/60 border border-pink-500 text-white p-2 rounded-lg outline-none">
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8 text-left">
      <div class="bg-white/5 p-5 rounded-2xl border border-pink-400/30">
        <h4 class="text-pink-300 font-bold mb-4">Girls 🌸</h4>
        <div id="girlsList" class="space-y-2 h-64 overflow-y-auto pr-2 custom-scroll"></div>
      </div>
      <div class="bg-white/5 p-5 rounded-2xl border border-blue-400/30">
        <h4 class="text-blue-300 font-bold mb-4">Boys 💎</h4>
        <div id="boysList" class="space-y-2 h-64 overflow-y-auto pr-2 custom-scroll"></div>
      </div>
    </div>

    <button onclick="generateSummary()" class="inline-block py-2 px-8 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition">DONE ✨</button>

    <div id="summaryPanel" class="hidden mt-8 p-8 bg-black/80 rounded-3xl border border-pink-500 text-left">
      <h3 class="text-xl font-bold text-center text-pink-400 mb-4">Attendance Report</h3>
      <p id="reportMeta" class="text-center text-gray-400 mb-8 pb-4 border-b border-pink-500/20 italic"></p>
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-8">
        <div>
          <h4 class="text-green-400 font-bold">Present: <span id="countPresent">0</span></h4>
          <div id="listPresent" class="text-xs mt-2 text-gray-300 leading-relaxed"></div>
        </div>
        <div>
          <h4 class="text-red-400 font-bold">Absent: <span id="countAbsent">0</span></h4>
          <div id="listAbsent" class="text-xs mt-2 text-gray-300 leading-relaxed"></div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="contact" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">💌 Let's Connect</h2>
  <div class="max-w-md mx-auto p-8 bg-[#1a0033]/80 rounded-3xl border-2 border-pink-600 glow-border">
    <form class="space-y-4">
      <input type="text" placeholder="Name" class="w-full p-3 border border-pink-400 rounded-xl bg-black/40 text-white outline-none focus:border-white transition">
      <textarea placeholder="Message" rows="4" class="w-full p-3 border border-pink-400 rounded-xl bg-black/40 text-white outline-none focus:border-white transition"></textarea>
      <button type="button" class="w-full py-3 bg-pink-600 rounded-xl font-bold hover:bg-pink-700 transition">Send Message ✨</button>
    </form>
  </div>
</section>

<footer class="py-6 text-center"></footer>

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
  <div id="chat-header"><span>Celyn's Magical Bot</span><button onclick="toggleChat()">&times;</button></div>
  <div id="chat-messages"><div class="bot-msg">✨ Hello! I am Celyn's assistant. Ask me about her BSIT-2B Attendance system or how to download her resume!</div></div>
  <div id="chat-input-area"><input type="text" id="chat-input" placeholder="Type a message..." onkeypress="handleChat(event)"></div>
</div>

<script>
  /* --- 🧪 ATTENDANCE SYSTEM LOGIC --- */
  const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan","Jessa Erosido","Jessa Hilardino","Kristine Joy Basa","Lena Bahian","Rechelle An Casilangan","Roxan Pracio","Shannon De La Cruz","Jeca Dagumboy","Martina Cabrillos","Nera Bahilot","Sheila Marie Lañojan","Trisha Agravante"];
  const boys = ["Archie Vidal","John Rogen Bullag","Mario Nebres Jr.","AjhannAylle Marfil","Anthony Espinosa","Dave Rivera","Jeffrey Coriento","Kenneth Espinosa","Kevin James Plaza","Luke Axel Barrocum","Mark Angelou Banatasa","Nathaniel Pojas","Paul John Malba","Rodel Cepeda"];

  document.getElementById('attendanceDate').valueAsDate = new Date();

  function renderList(list, elementId) {
    const container = document.getElementById(elementId);
    list.sort().forEach(name => {
      container.innerHTML += `
      <div class="flex justify-between items-center p-3 bg-white/5 rounded-xl mb-2 hover:bg-pink-500/20 transition">
          <span class="text-sm font-medium">${name}</span>
          <input type="checkbox" class="att-check w-5 h-5 accent-pink-500 cursor-pointer" data-name="${name}">
      </div>`;
    });
  }
  renderList(girls, 'girlsList');
  renderList(boys, 'boysList');

  function generateSummary() {
    const checks = document.querySelectorAll('.att-check');
    let p = []; let a = [];
    checks.forEach(c => {
      const name = c.getAttribute('data-name');
      if (c.checked) p.push(name); else a.push(name);
    });
    document.getElementById('countPresent').innerText = p.length;
    document.getElementById('countAbsent').innerText = a.length;
    document.getElementById('listPresent').innerHTML = p.map(n => "• " + n).join("<br>");
    document.getElementById('listAbsent').innerHTML = a.map(n => "• " + n).join("<br>");
    const sub = document.getElementById('subjectName').value || "Class Session";
    const date = document.getElementById('attendanceDate').value;
    document.getElementById('reportMeta').innerText = `Subject: ${sub} | Date: ${date}`;
    const panel = document.getElementById('summaryPanel');
    panel.style.display = 'block';
    panel.scrollIntoView({ behavior: 'smooth' });
  }

  /* --- 🤖 CHATBOT LOGIC --- */
  function toggleChat() {
    const chat = document.getElementById('chat-container');
    chat.style.display = (chat.style.display === 'none' || chat.style.display === '') ? 'flex' : 'none';
  }

  function handleChat(e) {
    if (e.key === 'Enter') {
      const input = document.getElementById('chat-input');
      const msg = input.value.trim();
      if (msg) { addMsg(msg, 'user-msg'); input.value = ''; setTimeout(() => botResp(msg), 600); }
    }
  }

  function addMsg(t, c) {
    const d = document.createElement('div'); d.className = c; d.innerText = t;
    const m = document.getElementById('chat-messages'); m.appendChild(d); m.scrollTop = m.scrollHeight;
  }

  function botResp(u) {
    const t = u.toLowerCase();
    let r = "I can tell you about Celyn's projects, certificates, or her achievements! ✨";
    
    if (t.includes("hello") || t.includes("hi")) {
      r = "✨ Magical greetings! How can I help you explore Celyn's portfolio today?";
    } else if (t.includes("resume") || t.includes("download")) {
      r = "You can download Celyn's resume in the Resume section. Just click the pink 'Download' button! 📄";
    } else if (t.includes("cert") || t.includes("training") || t.includes("march")) {
      r = "Celyn completed IT Training Seminars in March 2026. You can view her certificates in the Certificates section! 📜";
    } else if (t.includes("attendance") || t.includes("bsit") || t.includes("simulation")) {
      r = "The BSIT-2B Attendance System is an interactive simulation Celyn built to track student attendance. Try it out in the Simulation section! 🧪";
    } else if (t.includes("skills") || t.includes("expert")) {
      r = "Celyn specializes in BSIT studies, including web development and system design! ✨";
    } else if (t.includes("contact") || t.includes("message")) {
      r = "You can send a magical message to Celyn using the form in the Contact section! 💌";
    }
    
    addMsg(r, 'bot-msg');
  }
</script>
</body>
</html>
