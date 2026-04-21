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

        // --- AUTOMATED RESPONSE MAPPING ---

        // 1. GREETINGS & WELL-BEING
        if (t.includes("hello") || t.includes("hi") || t.includes("hey") || t.includes("morning") || t.includes("afternoon")) {
            r = "Hello! ✨ I am Celyn's automated assistant. How can I help you explore this portfolio today?";
        }
        else if (t.includes("how are you")) {
            r = "I'm functioning perfectly! I'm here to answer any questions you have about Celyn's IT journey. How are you?";
        }

        // 2. SPECIFIC PORTFOLIO CONTENT (IN-CODE)
        else if (t.includes("project") || t.includes("work") || t.includes("portfolio")) {
            r = "Celyn has several projects: an Attendance System, Chessboard UI, T-shirt designs, and a Figma E-commerce prototype. You can find them in the 'My Projects' section! 🛠️";
        }
        else if (t.includes("attendance") || t.includes("system") || t.includes("simulation")) {
            r = "The BSIT-2B Attendance System is an automated tool Celyn developed using web technologies. You can actually test it in the Simulation section! 🧪";
        }
        else if (t.includes("resume") || t.includes("cv") || t.includes("background")) {
            r = "Celyn's resume is available right here! It details her education, skills, and experience. You can even download a copy. 📄";
        }
        else if (t.includes("certificate") || t.includes("training") || t.includes("march")) {
            r = "She completed IT Training in March 2026. The certificates for her achievements are displayed in the 'Certificates' section. 📜";
        }
        else if (t.includes("skills") || t.includes("tools") || t.includes("canva") || t.includes("figma") || t.includes("photoshop")) {
            r = "Celyn is proficient in Figma, Canva, Adobe Photoshop, and Premiere Pro. She also works with HTML, CSS, PHP, and MySQL for web projects! 🪄";
        }

        // 3. ABOUT CELYN (STUDENT INFO)
        else if (t.includes("who is") || t.includes("about celyn")) {
            r = "Celyn is a 2nd Year BSIT Student (Section 2B) who is passionate about frontend development and digital design. ✨";
        }
        else if (t.includes("location") || t.includes("live") || t.includes("negros") || t.includes("moises padilla")) {
            r = "She is based in Moises Padilla, Negros Occidental. 📍";
        }
        else if (t.includes("experience") || t.includes("champion") || t.includes("award")) {
            r = "She was a Video Editing Champion in 2021 and has been a skilled Tarpapel Editor since 2020! 🏆";
        }

        // 4. GENERAL IT & EXTERNAL QUESTIONS (NOT IN CODE)
        else if (t.includes("what is it") || t.includes("information technology")) {
            r = "Information Technology involves using computers and software to manage information. It's the core of everything Celyn builds! 💻";
        }
        else if (t.includes("web development") || t.includes("coding")) {
            r = "Web development is the process of building websites. Celyn uses HTML, CSS, and PHP to create interactive sites like this one!";
        }
        else if (t.includes("figma") && t.includes("what")) {
            r = "Figma is a collaborative design tool used for creating UI/UX prototypes. Celyn used it for her E-commerce project!";
        }
        else if (t.includes("help") || t.includes("advice") || t.includes("study")) {
            r = "Celyn is always open to collaborating on tech projects! You can use the contact form below to send her a message. 📚";
        }
        else if (t.includes("purpose") || t.includes("who made you")) {
            r = "I am an automated assistant created to provide information about Celyn's work and IT skills. 🪄";
        }

        // 5. CLOSING & THANKS
        else if (t.includes("thank") || t.includes("thanks")) {
            r = "You're very welcome! Feel free to ask if you want to know more about a specific project. ✨";
        }
        else if (t.includes("bye") || t.includes("goodbye") || t.includes("exit")) {
            r = "Goodbye! Thank you for visiting Celyn's portfolio. Have a wonderful day! 👋";
        }

        // 6. SMART FALLBACK (IF INQUIRY IS UNKNOWN)
        else {
            const fallbacks = [
                "That's an interesting question! ✨ While I might not have a specific answer for that, I can definitely tell you about Celyn's 'Projects' or 'Attendance System'.",
                "I'm still learning! 🪄 Try asking me about Celyn's 'Skills', her 'Education', or her 'YouTube Tutorials'.",
                "I'm not sure about that, but you should check out the 'Simulation' section to see her coding in action! 🧪",
                "Could you try rephrasing? I'm programmed to talk about Celyn's IT Portfolio and her background in BSIT. 👩‍💻"
            ];
            r = fallbacks[Math.floor(Math.random() * fallbacks.length)];
        }
        
        addMessage(r, 'bot-msg');
    }
</script>
