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
  background: #ff66cc;
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
  background: rgba(10, 0, 21, 0.5);
}

.bot-msg { color: #ff99ff; margin-bottom: 12px; border-left: 3px solid #ff66cc; padding-left: 10px; line-height: 1.4; }
.user-msg { color: #fff; margin-bottom: 12px; text-align: right; background: rgba(255, 102, 204, 0.2); padding: 8px; border-radius: 8px; align-self: flex-end; width: fit-content; }

#chat-input-area {
  display: flex;
  padding: 12px;
  border-top: 1px solid #ff66cc;
  background: #1a0033;
}

#chat-input {
  flex: 1;
  background: rgba(0,0,0,0.3);
  border: 1px solid #ff66cc;
  border-radius: 5px;
  color: white;
  padding: 8px;
  outline: none;
}

#chat-toggle {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #ff66cc;
  width: 65px;
  height: 65px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  z-index: 1001;
  box-shadow: 0 0 20px #ff66cc;
  font-size: 35px;
  transition: 0.3s;
}
#chat-toggle:hover { transform: scale(1.1) rotate(10deg); }

/* Modal for viewing images */
.modal {
  display: none;
  position: fixed;
  z-index: 2000;
  top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(0,0,0,0.9);
  align-items: center; justify-content: center;
}
.modal img { max-width: 90%; max-height: 85%; border: 2px solid #ff66cc; border-radius: 10px; }
</style>
</head>

<body>

<div class="mist"></div>
<div class="stars"></div>
<div class="sparkles"></div>
<div class="magic-frame"></div>

<div id="imgModal" class="modal" onclick="this.style.display='none'">
  <img id="modalContent">
</div>

<nav class="py-4 px-2 text-center text-white font-bold text-xs sm:text-base flex flex-wrap justify-center gap-4 sticky top-0 z-50 bg-pink-700/40 backdrop-blur-lg border-b border-pink-500/30">
  <a href="#home" class="hover:text-pink-300 transition">Home</a>
  <a href="#about" class="hover:text-pink-300 transition">About</a>
  <a href="#resume" class="hover:text-pink-300 transition">Resume</a>
  <a href="#certificates" class="hover:text-pink-300 transition">Certificates</a>
  <a href="#simulation" class="hover:text-pink-300 transition">Simulation</a>
  <a href="#skills" class="hover:text-pink-300 transition">Skills</a>
  <a href="#experience" class="hover:text-pink-300 transition">Experience</a>
  <a href="#tutorials" class="hover:text-pink-300 transition">Tutorials</a>
  <a href="#contact" class="hover:text-pink-300 transition">Contact</a>
</nav>

<section id="home" class="flex flex-col items-center text-center px-4 py-20">
  <h1 class="text-4xl sm:text-5xl font-bold mb-8 glow-text">Welcome to My Portfolio!</h1>
  <div class="relative">
    <img src="Just me.jpg" alt="Celyn" class="w-48 h-48 rounded-full border-4 border-pink-500 object-cover glow-border float" onclick="showImg(this.src)">
  </div>
</section>

<section id="about" class="text-center px-4 py-16 bg-black/20">
  <h2 class="text-3xl font-bold mb-6 text-pink-400 glow-text">✨ About Me ✨</h2>
  <div class="max-w-2xl mx-auto text-gray-200 leading-relaxed bg-[#1a0033]/40 p-8 rounded-3xl border border-pink-500/20">
    <p>I am <span class="font-bold text-white text-xl">Celyn</span> (Jocelyn Semillano), a passionate 2nd Year BSIT Student. I specialize in weaving together code and design to create magical digital experiences.</p>
  </div>
</section>

<section id="resume" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">📄 My Resume</h2>
  <div class="max-w-xs mx-auto">
    <div class="bg-[#1a0033]/80 border border-pink-500 rounded-2xl p-4 glow-border float">
      <img src="resume.jpg" alt="Resume Preview" class="w-full rounded-lg mb-4 cursor-zoom-in" onclick="showImg(this.src)">
      <div class="flex flex-col gap-2">
        <a href="resume.jpg" target="_blank" class="py-2 px-6 bg-purple-600 text-white font-bold rounded-lg hover:bg-purple-700 transition text-sm">View Full Document</a>
        <a href="resume.jpg" download class="py-2 px-6 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition text-sm">Download (.JPG)</a>
      </div>
    </div>
  </div>
</section>

<section id="certificates" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-10 text-pink-400 glow-text">📜 IT Training Certificates</h2>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float">
      <p class="text-pink-300 font-bold mb-2">March 10, 2026</p>
      <img src="March 10.jpg" class="w-full h-auto rounded-lg border border-pink-400 mb-4 cursor-pointer" alt="Cert 1" onclick="showImg(this.src)">
      <a href="March 10.jpg" download class="text-xs bg-pink-600 py-1 px-3 rounded hover:bg-pink-700 transition">Download Copy</a>
    </div>
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float">
      <p class="text-pink-300 font-bold mb-2">March 12, 2026</p>
      <img src="March 12.jpg" class="w-full h-auto rounded-lg border border-pink-400 mb-4 cursor-pointer" alt="Cert 2" onclick="showImg(this.src)">
      <a href="March 12.jpg" download class="text-xs bg-pink-600 py-1 px-3 rounded hover:bg-pink-700 transition">Download Copy</a>
    </div>
  </div>
</section>

<section id="simulation" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text">🧪 My Simulation</h2>
  <div class="max-w-4xl mx-auto bg-[#1a0033]/90 border-2 border-pink-500 rounded-3xl p-8 shadow-[0_0_30px_rgba(255,102,204,0.4)]">
    <h3 class="text-2xl font-bold mb-6 text-white">BSIT-2B Attendance System</h3>
    
    <div class="flex flex-wrap justify-center gap-4 mb-8">
      <div class="text-left">
        <label class="text-xs text-pink-300 block mb-1 ml-1">Select Date</label>
        <input type="date" id="attendanceDate" class="bg-black/60 border border-pink-500 text-white p-2 rounded-lg outline-none">
      </div>
      <div class="text-left">
        <label class="text-xs text-pink-300 block mb-1 ml-1">Subject</label>
        <input type="text" id="subjectName" placeholder="e.g. Web Dev" class="bg-black/60 border border-pink-500 text-white p-2 rounded-lg outline-none w-48">
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8 text-left">
      <div class="bg-white/5 p-5 rounded-2xl border border-pink-400/30">
        <h4 class="text-pink-300 font-bold mb-4 flex justify-between items-center">Girls 🌸 <span class="text-[10px] font-normal opacity-70">Total: 15</span></h4>
        <div id="girlsList" class="space-y-2 h-64 overflow-y-auto pr-2 custom-scroll"></div>
      </div>
      <div class="bg-white/5 p-5 rounded-2xl border border-blue-400/30">
        <h4 class="text-blue-300 font-bold mb-4 flex justify-between items-center">Boys 💎 <span class="text-[10px] font-normal opacity-70">Total: 14</span></h4>
        <div id="boysList" class="space-y-2 h-64 overflow-y-auto pr-2 custom-scroll"></div>
      </div>
    </div>

    <button onclick="generateSummary()" class="px-20 py-4 bg-pink-600 rounded-full font-bold hover:bg-pink-700 transition transform hover:scale-105 shadow-xl border-2 border-pink-400">DONE ✨</button>

    <div id="summaryPanel" class="hidden mt-8 p-8 bg-black/80 rounded-3xl border-2 border-pink-500 text-left scale-up-center">
      <h3 class="text-2xl font-bold text-center text-pink-400 mb-4">Attendance Report</h3>
      <p id="reportMeta" class="text-center text-gray-400 mb-8 pb-4 border-b border-pink-500/20 italic"></p>
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-8">
        <div>
          <h4 class="text-green-400 font-bold text-lg mb-3">Present: <span id="countPresent">0</span></h4>
          <div id="listPresent" class="text-xs space-y-1 text-gray-300 leading-relaxed bg-green-900/10 p-3 rounded-xl min-h-[50px]"></div>
        </div>
        <div>
          <h4 class="text-red-400 font-bold text-lg mb-3">Absent: <span id="countAbsent">0</span></h4>
          <div id="listAbsent" class="text-xs space-y-1 text-gray-300 leading-relaxed bg-red-900/10 p-3 rounded-xl min-h-[50px]"></div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="skills" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-10 text-pink-400 glow-text">🛠️ My Skills & Designs</h2>
  <div class="flex flex-wrap justify-center gap-8 max-w-5xl mx-auto">
    <img src="figma ecommerce.jpg" class="w-64 h-auto rounded-xl glow-border float" onclick="showImg(this.src)">
    <img src="product design.png" class="w-64 h-auto rounded-xl glow-border float" onclick="showImg(this.src)">
    <img src="tshirt layout.png" class="w-64 h-auto rounded-xl glow-border float" onclick="showImg(this.src)">
    <img src="chessboard.png" class="w-64 h-auto rounded-xl glow-border float" onclick="showImg(this.src)">
  </div>
</section>

<section id="experience" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">🏆 Achievements</h2>
  <div class="max-w-3xl mx-auto bg-[#1a0033]/70 border border-pink-500 rounded-3xl p-8 glow-border float">
    <h3 class="text-2xl font-bold text-pink-300 mb-2">Video Editing Champion (2021)</h3>
    <p class="text-gray-300 italic mb-6 text-sm">PNP Anniversary Video Editing Contest</p>
    <div class="flex justify-center gap-12 grayscale hover:grayscale-0 transition duration-500">
      <img src="film maker pro.png" class="w-20 h-20 rounded-2xl shadow-lg">
      <img src="kinemaster.png" class="w-20 h-20 rounded-2xl shadow-lg">
    </div>
  </div>
</section>

<section id="tutorials" class="text-center px-4 py-16">
  <h2 class="text-3xl font-bold mb-10 text-pink-300 glow-text">✨ Tutorials</h2>
  <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-5xl mx-auto">
    <iframe class="rounded-2xl w-full h-72 glow-border" src="https://www.youtube.com/embed/wCEtWz5imUs"></iframe>
    <iframe class="rounded-2xl w-full h-72 glow-border" src="https://www.youtube.com/embed/ezldKx-jPag"></iframe>
  </div>
</section>

<section id="contact" class="text-center px-4 py-16 bg-black/30">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text">💌 Let's Connect</h2>
  <div class="max-w-md mx-auto p-8 bg-[#1a0033]/80 rounded-3xl border-2 border-pink-600 glow-border">
    <form class="space-y-4">
      <input type="text" placeholder="Your Name" class="w-full p-3 border border-pink-400 rounded-xl bg-black/40 text-white outline-none focus:border-white transition">
      <input type="email" placeholder="Your Email" class="w-full p-3 border border-pink-400 rounded-xl bg-black/40 text-white outline-none focus:border-white transition">
      <textarea placeholder="Write your magical message..." rows="4" class="w-full p-3 border border-pink-400 rounded-xl bg-black/40 text-white outline-none focus:border-white transition"></textarea>
      <button type="button" class="w-full py-3 bg-pink-600 rounded-xl font-bold hover:bg-pink-700 transition shadow-lg">Send Message ✨</button>
    </form>
  </div>
</section>

<footer class="py-10 text-center text-gray-500 text-sm">
  <p>&copy; 2026 Jocelyn Semillano | Crafted with Magic & IT Skill</p>
</footer>

<div id="chat-toggle" onclick="toggleChat()">🤖</div>
<div id="chat-container">
  <div id="chat-header">
    <span>Celyn's Magical Bot</span>
    <button onclick="toggleChat()" class="text-xl">&times;</button>
  </div>
  <div id="chat-messages">
    <div class="bot-msg">✨ Hello! I am Celyn's magical assistant. I can tell you about her BSIT-2B projects, her design skills, or her achievements. What would you like to know?</div>
  </div>
  <div id="chat-input-area">
    <input type="text" id="chat-input" placeholder="Type a message..." onkeypress="handleChat(event)">
  </div>
</div>

<script>
  /* --- Image Viewer --- */
  function showImg(src) {
    document.getElementById('modalContent').src = src;
    document.getElementById('imgModal').style.display = 'flex';
  }

  /* --- 🧪 ATTENDANCE SYSTEM LOGIC --- */
  const girls = ["Jocelyn Semillano","Andrea Jean Occeña","Gene Mae Caramihan","Jessa Erosido","Jessa Hilardino","Kristine Joy Basa","Lena Bahian","Rechelle An Casilangan","Roxan Pracio","Shannon De La Cruz","Jeca Dagumboy","Martina Cabrillos","Nera Bahilot","Sheila Marie Lañojan","Trisha Agravante"];
  const boys = ["Archie Vidal","John Rogen Bullag","Mario Nebres Jr.","AjhannAylle Marfil","Anthony Espinosa","Dave Rivera","Jeffrey Coriento","Kenneth Espinosa","Kevin James Plaza","Luke Axel Barrocum","Mark Angelou Banatasa","Nathaniel Pojas","Paul John Malba","Rodel Cepeda"];

  document.getElementById('attendanceDate').valueAsDate = new Date();

  function renderList(list, elementId) {
    const container = document.getElementById(elementId);
    list.sort().forEach(name => {
      container.innerHTML += `
      <div class="flex justify-between items-center p-3 bg-white/5 rounded-xl mb-2 hover:bg-pink-500/20 transition group">
          <span class="text-sm font-medium group-hover:text-pink-200">${name}</span>
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
    document.getElementById('listPresent').innerHTML = p.length > 0 ? p.map(n => "• " + n).join("<br>") : "No students present.";
    document.getElementById('listAbsent').innerHTML = a.length > 0 ? a.map(n => "• " + n).join("<br>") : "No students absent.";
    const sub = document.getElementById('subjectName').value || "General Class";
    const date = document.getElementById('attendanceDate').value;
    document.getElementById('reportMeta').innerText = `Report for: ${sub} | Date: ${date}`;
    const panel = document.getElementById('summaryPanel');
    panel.style.display = 'block';
    panel.scrollIntoView({ behavior: 'smooth', block: 'center' });
  }

  /* --- 🤖 CHATBOT KNOWLEDGE BASE --- */
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
    let r = "That sounds interesting! ✨ I can tell you more about Celyn's BSIT Journey, her UI/UX designs, or her Video Editing championship. What's on your mind?";

    if (t.includes("hi") || t.includes("hello")) {
      r = "Magical greetings! How can I assist you with Celyn's portfolio today? ✨";
    } 
    else if (t.includes("attendance") || t.includes("bsit-2b") || t.includes("simulation")) {
      r = "Celyn built a fully functional Attendance System for her class, BSIT-2B! It tracks 15 girls and 14 boys. You can try it yourself in the 'Simulation' section! 🧪";
    }
    else if (t.includes("cert") || t.includes("training") || t.includes("march")) {
      r = "Celyn earned two major IT Training Certificates on March 10 and March 12, 2026! You can view and download them in the Certificates section. 📜";
    }
    else if (t.includes("resume") || t.includes("cv") || t.includes("download")) {
      r = "Celyn's resume is available in the Resume section. You can view it as a JPG or download a copy for your records! 📄";
    }
    else if (t.includes("design") || t.includes("figma") || t.includes("canva") || t.includes("skills")) {
      r = "Celyn is a creative wizard! She uses Figma for UI/UX, Canva for layouts, and Photoshop for design. She's even designed e-commerce sites and t-shirts! 🎨";
    }
    else if (t.includes("award") || t.includes("champion") || t.includes("pnp")) {
      r = "In 2021, Celyn won the PNP Anniversary Video Editing Contest! She is a pro at using Film Maker Pro and KineMaster. 🏅";
    }
    else if (t.includes("youtube") || t.includes("tutorial")) {
      r = "Celyn shares her knowledge through video tutorials! You can watch her editing and design guides in the Tutorials section. 🎥";
    }
    else if (t.includes("thank")) {
      r = "You're very welcome! Let me know if you want to explore more magic! ✨";
    }

    addMsg(r, 'bot-msg');
  }
</script>
</body>
</html>
