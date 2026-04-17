<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Avanthika K S — Developer & Designer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0f172a;
            --secondary: #1e293b;
            --accent: #60a5fa;
            --accent-dark: #3b82f6;
            --text-light: #f1f5f9;
            --text-muted: #cbd5e1;
            --border: #334155;
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
            background-attachment: fixed;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(96, 165, 250, 0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: drift 20s linear infinite;
            z-index: 0;
        }

        @keyframes drift {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 800;
            margin-bottom: 10px;
            background: linear-gradient(135deg, var(--accent) 0%, #93c5fd 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero .subtitle {
            font-size: 1.25rem;
            color: var(--text-muted);
            margin-bottom: 40px;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .cta-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 80px;
        }

        .btn {
            padding: 12px 28px;
            border-radius: 8px;
            border: none;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: var(--accent-dark);
            color: white;
        }

        .btn-primary:hover {
            background: var(--accent);
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(96, 165, 250, 0.3);
        }

        .btn-secondary {
            border: 2px solid var(--accent);
            background: transparent;
            color: var(--accent);
        }

        .btn-secondary:hover {
            background: rgba(96, 165, 250, 0.1);
            transform: translateY(-2px);
        }

        .scroll-hint {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--text-muted);
            font-size: 0.9rem;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-10px); }
        }

        /* Timeline Section */
        .section {
            padding: 100px 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 60px;
            text-align: center;
            position: relative;
            padding-bottom: 20px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--accent), transparent);
        }

        .timeline {
            position: relative;
            padding: 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 30px;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--accent) 0%, transparent 100%);
        }

        .timeline-item {
            margin-left: 80px;
            margin-bottom: 50px;
            position: relative;
            opacity: 0;
            animation: fadeInLeft 0.8s ease-out forwards;
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .timeline-item:nth-child(1) { animation-delay: 0.1s; }
        .timeline-item:nth-child(2) { animation-delay: 0.2s; }
        .timeline-item:nth-child(3) { animation-delay: 0.3s; }

        .timeline-item::before {
            content: '';
            position: absolute;
            width: 12px;
            height: 12px;
            background: var(--accent);
            border: 3px solid var(--primary);
            border-radius: 50%;
            left: -56px;
            top: 0;
            box-shadow: 0 0 0 4px rgba(96, 165, 250, 0.2);
        }

        .timeline-item h3 {
            font-size: 1.3rem;
            margin-bottom: 8px;
            color: var(--accent);
        }

        .timeline-item p {
            color: var(--text-muted);
            line-height: 1.8;
        }

        /* Cards Grid */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 60px;
        }

        .card {
            background: rgba(30, 41, 59, 0.5);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--accent), transparent);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }

        .card:hover {
            border-color: var(--accent);
            background: rgba(30, 41, 59, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(96, 165, 250, 0.1);
        }

        .card:hover::before {
            transform: scaleX(1);
        }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 12px;
            color: var(--accent);
        }

        .card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 15px;
        }

        .card-link {
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: gap 0.3s ease;
        }

        .card-link:hover {
            gap: 12px;
        }

        /* Interactive Skills */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 30px;
        }

        .skill-tag {
            background: rgba(96, 165, 250, 0.1);
            border: 1px solid var(--accent);
            color: var(--accent);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: var(--accent);
            color: var(--primary);
            transform: scale(1.05);
        }

        /* Contact Section */
        .contact-section {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, rgba(96, 165, 250, 0.05) 0%, transparent 100%);
            border-radius: 20px;
            margin: 0 20px;
        }

        .contact-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .contact-link {
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
            padding: 10px 20px;
            border: 2px solid var(--accent);
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            background: var(--accent);
            color: var(--primary);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .section {
                padding: 60px 20px;
            }

            .timeline::before {
                left: 15px;
            }

            .timeline-item {
                margin-left: 50px;
            }

            .timeline-item::before {
                left: -36px;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                max-width: 300px;
            }
        }

        /* Scroll reveal animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Avanthika K S</h1>
            <p class="subtitle">Frontend Developer | UI/UX Designer | Tinkerer with Code & Hardware</p>
            <div class="cta-buttons">
                <button class="btn btn-primary" onclick="scrollToSection('journey')">My Journey</button>
                <button class="btn btn-secondary" onclick="scrollToSection('projects')">See Projects</button>
            </div>
        </div>
        <div class="scroll-hint">↓ Scroll to explore</div>
    </section>

    <!-- Journey Section -->
    <section class="section" id="journey">
        <h2 class="section-title">How I Got Here</h2>
        <div class="timeline">
            <div class="timeline-item">
                <h3>Started with Circuits</h3>
                <p>My journey began with Electronics and Communication Engineering—breadboards, microcontrollers, and the magic of watching LEDs respond to code. There was immediate feedback, a direct cause-and-effect that felt tangible.</p>
            </div>
            <div class="timeline-item">
                <h3>Shifted to Interfaces</h3>
                <p>But somewhere along the way, I realized I spent more time designing how people interact with systems than soldering components. I wanted to build things that reached beyond a breadboard—things actual humans could use.</p>
            </div>
            <div class="timeline-item">
                <h3>Building & Learning in Public</h3>
                <p>Now I ship web apps, break things on purpose, fix them in weird ways, and document the chaos. Every failed experiment, every refactor, every "why did I write it that way?"—that's the actual learning.</p>
            </div>
        </div>
    </section>

    <!-- What I Do Section -->
    <section class="section">
        <h2 class="section-title">What I Actually Do</h2>
        <div class="cards-grid">
            <div class="card reveal">
                <h3>Design Interfaces</h3>
                <p>Figma is my sketchbook. I prototype ideas, test them, then build them. Design and code aren't separate in my workflow—they're two sides of the same coin.</p>
                <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 15px; font-style: italic;">Learning design by doing, not by theory.</p>
            </div>
            <div class="card reveal">
                <h3>Build Web Experiences</h3>
                <p>React, TypeScript, Tailwind CSS. I treat components like circuits—organized, reusable, and predictable. Every interface is a function of state.</p>
                <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 15px; font-style: italic;">Clean code, even cleaner interfaces.</p>
            </div>
            <div class="card reveal">
                <h3>Explore Emerging Tech</h3>
                <p>AI agents, automation workflows, prompt engineering. I see new tools as amplifiers for creativity, not replacements. I experiment fearlessly.</p>
                <p style="font-size: 0.85rem; color: var(--text-muted); margin-top: 15px; font-style: italic;">Building with the future, today.</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <h2 class="section-title">Projects That Taught Me</h2>
        <div class="cards-grid">
            <div class="card reveal">
                <h3>Inclusive Language Checker</h3>
                <p>Built because language matters. This tool analyzes text and suggests kinder, more inclusive alternatives. Small, focused, solves a real problem.</p>
                <a href="https://inclusive-checker-b3lh.vercel.app/" target="_blank" class="card-link">Launch → </a>
            </div>
            <div class="card reveal">
                <h3>Odin Calculator</h3>
                <p>Not just math. This project taught me React state management, event handling, and how every interaction should feel intentional. Simple on the surface.</p>
                <a href="https://odin-calculator-project.vercel.app/" target="_blank" class="card-link">Launch → </a>
            </div>
            <div class="card reveal">
                <h3>Study Buddy</h3>
                <p>Built during exam season. A simple study assistant that works exactly the way I need it to. Not portfolio-perfect, but genuinely useful.</p>
                <a href="https://study-buddy-swart.vercel.app/" target="_blank" class="card-link">Launch → </a>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section">
        <h2 class="section-title">My Toolkit</h2>
        <div>
            <h3 style="margin-bottom: 20px; color: var(--accent);">Frontend</h3>
            <div class="skills-container">
                <span class="skill-tag">HTML</span>
                <span class="skill-tag">CSS</span>
                <span class="skill-tag">JavaScript</span>
                <span class="skill-tag">React</span>
                <span class="skill-tag">TypeScript</span>
                <span class="skill-tag">Tailwind CSS</span>
            </div>
        </div>

        <div style="margin-top: 40px;">
            <h3 style="margin-bottom: 20px; color: var(--accent);">Languages & Tools</h3>
            <div class="skills-container">
                <span class="skill-tag">Python</span>
                <span class="skill-tag">C</span>
                <span class="skill-tag">Git</span>
                <span class="skill-tag">GitHub</span>
                <span class="skill-tag">Figma</span>
                <span class="skill-tag">VS Code</span>
                <span class="skill-tag">Firebase</span>
                <span class="skill-tag">Vercel</span>
            </div>
        </div>

        <div style="margin-top: 40px;">
            <h3 style="margin-bottom: 20px; color: var(--accent);">Emerging</h3>
            <div class="skills-container">
                <span class="skill-tag">AI Tools</span>
                <span class="skill-tag">AI Agents</span>
                <span class="skill-tag">Automation</span>
                <span class="skill-tag">Make</span>
            </div>
        </div>
    </section>

    <!-- Unique Experiences -->
    <section class="section">
        <h2 class="section-title">What Makes Me Different</h2>
        <div class="cards-grid">
            <div class="card reveal">
                <h3>Hardware Background</h3>
                <p>Coming from embedded systems gave me a different lens. I think about performance, constraints, and efficiency. Why waste resources when you can be elegant?</p>
            </div>
            <div class="card reveal">
                <h3>Trial & Error Philosophy</h3>
                <p>I learn by building, breaking, and understanding why it broke. It's slower but sticks harder. Every bug is a lesson archived in my GitHub.</p>
            </div>
            <div class="card reveal">
                <h3>Designer + Developer</h3>
                <p>I refused to pick one. This dual perspective means my code thinks about UX, and my designs think about implementation. Both benefit.</p>
            </div>
            <div class="card reveal">
                <h3>Learning in Public</h3>
                <p>My GitHub isn't polished. It's raw. Messy commits, failed experiments, terrible commit messages. That's where real learning happens.</p>
            </div>
            <div class="card reveal">
                <h3>Collaborative Mindset</h3>
                <p>Explaining code to others forces understanding. I value community and conversation over isolated genius. Better ideas come from collaboration.</p>
            </div>
            <div class="card reveal">
                <h3>Critical AI Adoption</h3>
                <p>I use AI tools as a thinking partner, not a crutch. They amplify my thinking—I ask good questions, then critique the answers.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section">
        <h2 class="section-title">Let's Talk</h2>
        <p style="font-size: 1.1rem; color: var(--text-light); margin-bottom: 30px; max-width: 600px; margin-left: auto; margin-right: auto;">
            Interested in frontend work, design, automation, or just want to geek out about building things?
        </p>
        <div class="contact-links">
            <a href="mailto:avanthikaks1874@gmail.com" class="contact-link">Email</a>
            <a href="https://www.linkedin.com/in/avanthika-k-s-1643a0281/" target="_blank" class="contact-link">LinkedIn</a>
            <a href="https://github.com/AVA-NTHIKA14" target="_blank" class="contact-link">GitHub</a>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>Build → Break → Understand → Improve → Repeat</p>
        <p style="margin-top: 10px; font-size: 0.8rem;">Learning through experimentation and continuous iteration</p>
    </footer>

    <script>
        // Scroll reveal animation
        const reveals = document.querySelectorAll('.reveal');

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, { threshold: 0.1 });

        reveals.forEach(el => observer.observe(el));

        // Smooth scroll function
        function scrollToSection(id) {
            const element = document.getElementById(id);
            element?.scrollIntoView({ behavior: 'smooth' });
        }

        // Parallax effect on hero
        window.addEventListener('scroll', () => {
            const hero = document.querySelector('.hero');
            if (hero) {
                hero.style.transform = `translateY(${window.scrollY * 0.5}px)`;
            }
        });
    </script>
</body>
</html>
