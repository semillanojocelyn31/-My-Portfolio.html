<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Jocelyn Semillano - Enchanted Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>

<style>
body {
  font-family: 'Poppins', sans-serif;
  margin: 0;
  color: white;
  background: radial-gradient(circle at top, #2b003a, #0a0015 80%);
}
.glow-border { box-shadow: 0 0 15px #ff66ff; }
.glow-text { text-shadow: 0 0 10px #ff99ff; }
</style>
</head>

<body>

<nav class="text-center p-3 bg-pink-700/40">
  <a href="#home">Home</a> |
  <a href="#resume">Resume</a> |
  <a href="#certificates">Certificates</a>
</nav>

<!-- HOME -->
<section id="home" class="text-center py-10">
  <h1 class="text-3xl glow-text">Welcome to My Portfolio</h1>
  <img src="images/Just me.jpg" class="w-40 h-40 rounded-full mx-auto mt-4 glow-border">
</section>

<!-- RESUME -->
<section id="resume" class="text-center py-10">
  <h2 class="text-2xl glow-text">My Resume</h2>

  <div class="max-w-xs mx-auto mt-6 bg-black/40 p-4 rounded-lg glow-border">
    <img src="images/resume.jpg" class="w-full rounded mb-3">
    
    <a href="images/resume.jpg" download 
    class="bg-pink-600 px-4 py-2 rounded">
    Download Resume
    </a>
  </div>
</section>

<!-- CERTIFICATES -->
<section id="certificates" class="text-center py-10">
  <h2 class="text-2xl glow-text">Certificates</h2>

  <div class="max-w-xl mx-auto space-y-6 mt-6">

    <div class="bg-black/40 p-4 rounded glow-border">
      <p>March 10, 2026</p>
      <img src="images/March 10.jpg" class="w-full rounded">
    </div>

    <div class="bg-black/40 p-4 rounded glow-border">
      <p>March 12, 2026</p>
      <img src="images/March 12.jpg" class="w-full rounded">
    </div>

  </div>
</section>

</body>
</html>
