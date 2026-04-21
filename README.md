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

        // --- 1. CORE PORTFOLIO RESPONSES (IN-CODE) ---
        if (t.includes("hello") || t.includes("hi") || t.includes("hey")) {
            r = "Hello! ✨ I'm Celyn's automated assistant. I can tell you about her projects, skills, or education!";
        }
        else if (t.includes("project") || t.includes("work")) {
            r = "Celyn has projects like the Chessboard UI, T-shirt designs, and a Figma E-commerce prototype. Check the 'My Projects' section! 🛠️";
        }
        else if (t.includes("attendance") || t.includes("system") || t.includes("bsit-2b")) {
            r = "The BSIT-2B Attendance System is an interactive tool Celyn built. You can try the simulation right on this page! 🧪";
        }
        else if (t.includes("skills") || t.includes("tools") || t.includes("canva") || t.includes("figma")) {
            r = "Celyn is skilled in HTML, CSS, PHP, MySQL, and design tools like Figma, Canva, and Adobe Photoshop.";
        }
        else if (t.includes("resume") || t.includes("cv") || t.includes("download")) {
            r = "You can view or download her full resume in the 'Resume' section of this page. 📄";
        }
        else if (t.includes("experience") || t.includes("champion")) {
            r = "Celyn is a Video Editing Champion (2021) and a Tarpapel Editor (2020). She has a strong creative background! 🏆";
        }

        // --- 2. OUT-OF-CODE / GENERAL AI RESPONSES ---
        else if (t.includes("what is it") || t.includes("information technology")) {
            r = "Information Technology (IT) is the use of computers, storage, networking, and other physical devices to manage and process data. Celyn is specializing in this field! 💻";
        }
        else if (t.includes("how are you")) {
            r = "I'm doing great! Just here waiting to help visitors learn more about Celyn's work. How about you? ✨";
        }
        else if (t.includes("help") || t.includes("homework") || t.includes("advice")) {
            r = "While I'm a bot for this portfolio, Celyn herself is a great student! You can try contacting her through the form below for academic collaborations. 📚";
        }
        else if (t.includes("who made you") || t.includes("your creator")) {
            r = "I was built by Celyn to help guide visitors through her enchanted portfolio! 🪄";
        }
        else if (t.includes("future") || t.includes("goals")) {
            r = "Celyn aims to become a professional IT specialist, focusing on creating beautiful and functional web applications.";
        }
        else if (t.includes("hobbies") || t.includes("like")) {
            r = "Besides coding, Celyn enjoys creative design, video editing, and exploring new tech trends! ✨";
        }
        else if (t.includes("meaning of life") || t.includes("joke")) {
            r = "The meaning of life? To code beautiful websites, of course! Or maybe 42? 😄 Here's a joke: Why do programmers prefer dark mode? Because light attracts bugs! 🐜";
        }
        else if (t.includes("thank") || t.includes("thanks")) {
            r = "You're very welcome! Feel free to explore the rest of the site. ✨";
        }
        else if (t.includes("bye") || t.includes("goodbye")) {
            r = "Goodbye! Enjoy your stay in Celyn's magical portfolio! 👋";
        }

        // --- 3. CATCH-ALL FOR UNKNOWN INQUIRIES ---
        else {
            const genericRespones = [
                "I'm not quite sure I understand, but I'd love to tell you more about Celyn's IT projects! 🛠️",
                "Interesting question! ✨ While I focus on Celyn's work, you can use the navigation links to find more information.",
                "I'm still learning! Try asking about her 'Skills', 'Certificates', or the 'Attendance System'.",
                "That sounds complex! 🪄 Why not check out Celyn's 'YouTube Tutorials' for some tech insights?"
            ];
            r = genericRespones[Math.floor(Math.random() * genericRespones.length)];
        }
        
        addMessage(r, 'bot-msg');
    }
</script>
