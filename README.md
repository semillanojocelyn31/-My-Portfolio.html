<!DOCTYPE html>
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
.sparkles {position:fixed;top:0;left:0;width:100%;height:100%;background:transparent url() repeat;background-size:cover;mix-blend-mode:screen;opacity:.3;animation:drift 20s linear infinite;z-index:-1;}
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
.glow-border{box-shadow:0 0 15px 4px #ff66ff;transition:.3s;}
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
  max-height: 250px;
}

.bot-msg { color: #ff99ff; margin-bottom: 8px; }
.user-msg { color: #fff; margin-bottom: 8px; text-align: right; }

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
      <a href="resume.jpg" download class="inline-block py-2 px-6 bg-pink-600 text-white font-bold rounded-lg hover:bg-pink-700 transition">Download</a>
    </div>
  </div>
</section>

<section id="certificates" class="text-center px-4 py-12">
  <h2 class="text-3xl font-bold mb-8 text-pink-400 glow-text whitespace-nowrap">📜 IT Training Certificate</h2>
  <div class="flex flex-col items-center gap-8 max-w-2xl mx-auto">
    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
      <p class="text-pink-300 font-semibold mb-2">March 10, 2026</p>
      <p class="text-gray-200 text-sm mb-4">A touch of magic in technical training.</p>
      <img src="March 10.jpg" class="w-full h-auto rounded-lg border border-pink-400 shadow-md" alt="Training Certificate 1">
    </div>

    <div class="bg-[#1a0033]/70 border border-pink-500 rounded-2xl p-6 glow-border float w-full">
      <p class="text-pink-300 font-semibold mb-2">March 12, 2026</p>
      <p class="text-gray-200 text-sm mb-4">Enchanted skills mastered with care.</p>
      <img src="March 12.jpg" class="w-full h-auto rounded-lg border border-pink-400 shadow-md" alt="Training Certificate 2">
    </div>
  </div>
</section>

<!-- (UNCHANGED EVERYTHING BELOW) -->

</body>
</html>
