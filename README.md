<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jaba Janelidze - Fullstack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 25%, #1a1f3a 50%, #1e293b 75%, #0f172a 100%);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: #e2e8f0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating orbs */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(60px);
            opacity: 0.4;
            z-index: -1;
        }

        .orb-1 {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.6), transparent);
            top: -150px;
            left: -150px;
            animation: float 20s ease-in-out infinite;
        }

        .orb-2 {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(139, 92, 246, 0.5), transparent);
            bottom: -200px;
            right: -200px;
            animation: float 25s ease-in-out infinite reverse;
        }

        .orb-3 {
            width: 250px;
            height: 250px;
            background: radial-gradient(circle, rgba(236, 72, 153, 0.4), transparent);
            top: 50%;
            right: 10%;
            animation: float 22s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px); }
            25% { transform: translateY(40px) translateX(40px); }
            50% { transform: translateY(80px) translateX(-20px); }
            75% { transform: translateY(40px) translateX(-40px); }
        }

        /* Grid background */
        .grid {
            position: fixed;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(59, 130, 246, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(59, 130, 246, 0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            z-index: -1;
            pointer-events: none;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 60px 30px;
            position: relative;
            z-index: 1;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 80px;
        }

        .emoji-icon {
            font-size: 4rem;
            display: inline-block;
            animation: bounce 2s ease-in-out infinite;
            margin-bottom: 20px;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        h1 {
            font-size: 3.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6, #ec4899, #f59e0b);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientFlow 8s ease infinite;
            margin-bottom: 10px;
            letter-spacing: -1px;
        }

        @keyframes gradientFlow {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .tagline {
            font-size: 1.3rem;
            color: #94a3b8;
            margin-bottom: 15px;
            animation: slideDown 0.8s ease 0.2s backwards;
        }

        .location {
            font-size: 1rem;
            color: #64748b;
            animation: slideDown 0.8s ease 0.3s backwards;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Social Links */
        .social-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 40px 0;
            flex-wrap: wrap;
            animation: fadeIn 1s ease 0.4s backwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .social-btn {
            padding: 12px 24px;
            background: rgba(30, 41, 59, 0.8);
            border: 2px solid rgba(59, 130, 246, 0.3);
            color: #3b82f6;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
            backdrop-filter: blur(10px);
            font-weight: 600;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(59, 130, 246, 0.2);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .social-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .social-btn:hover {
            border-color: #3b82f6;
            transform: translateY(-4px);
            box-shadow: 0 20px 40px rgba(59, 130, 246, 0.3);
        }

        /* Divider */
        .divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.5), transparent);
            margin: 60px 0;
            animation: expand 1s ease 0.5s backwards;
        }

        @keyframes expand {
            from { width: 0; opacity: 0; }
            to { width: 100%; opacity: 1; }
        }

        /* Section */
        .section {
            margin-bottom: 60px;
            animation: slideUp 0.8s ease backwards;
        }

        .section:nth-child(1) { animation-delay: 0.6s; }
        .section:nth-child(2) { animation-delay: 0.7s; }
        .section:nth-child(3) { animation-delay: 0.8s; }
        .section:nth-child(4) { animation-delay: 0.9s; }
        .section:nth-child(5) { animation-delay: 1s; }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section h2 {
            font-size: 1.8rem;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 12px;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section h2::before {
            content: '';
            display: inline-block;
            width: 4px;
            height: 28px;
            background: linear-gradient(180deg, #3b82f6, #8b5cf6);
            border-radius: 2px;
            animation: expand-height 0.6s ease;
        }

        @keyframes expand-height {
            from { height: 0; }
            to { height: 28px; }
        }

        /* Card */
        .card {
            background: rgba(30, 41, 59, 0.6);
            border: 1px solid rgba(59, 130, 246, 0.2);
            border-radius: 16px;
            padding: 24px;
            margin-bottom: 20px;
            backdrop-filter: blur(10px);
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            border-color: rgba(59, 130, 246, 0.5);
            background: rgba(30, 41, 59, 0.8);
            transform: translateY(-5px);
            box-shadow: 0 25px 50px rgba(59, 130, 246, 0.15);
        }

        .card h3 {
            color: #f1f5f9;
            margin-bottom: 5px;
            font-size: 1.2rem;
        }

        .card .role {
            color: #3b82f6;
            font-weight: 600;
            font-size: 0.95rem;
            margin-bottom: 8px;
        }

        .card .date {
            color: #64748b;
            font-size: 0.85rem;
            margin-bottom: 12px;
        }

        .card p {
            color: #cbd5e1;
            font-size: 0.95rem;
            margin-bottom: 8px;
        }

        /* Tech Stack */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 15px;
            margin-top: 25px;
        }

        .tech-badge {
            background: rgba(59, 130, 246, 0.1);
            border: 1px solid rgba(59, 130, 246, 0.3);
            padding: 12px 16px;
            border-radius: 8px;
            text-align: center;
            font-size: 0.9rem;
            font-weight: 600;
            color: #3b82f6;
            transition: all 0.3s ease;
            cursor: pointer;
            animation: popIn 0.5s ease backwards;
        }

        @keyframes popIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .tech-badge:hover {
            background: rgba(59, 130, 246, 0.2);
            border-color: rgba(59, 130, 246, 0.6);
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.2);
        }

        .tech-badge:nth-child(1) { animation-delay: 0s; }
        .tech-badge:nth-child(2) { animation-delay: 0.05s; }
        .tech-badge:nth-child(3) { animation-delay: 0.1s; }
        .tech-badge:nth-child(4) { animation-delay: 0.15s; }
        .tech-badge:nth-child(5) { animation-delay: 0.2s; }
        .tech-badge:nth-child(6) { animation-delay: 0.25s; }

        /* Table */
        table {
            width: 100%;
            margin-top: 20px;
            border-collapse: collapse;
        }

        table th, table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid rgba(59, 130, 246, 0.2);
        }

        table th {
            color: #3b82f6;
            font-weight: 700;
            background: rgba(59, 130, 246, 0.05);
        }

        table tr:hover {
            background: rgba(59, 130, 246, 0.1);
        }

        /* Progress Bar */
        .progress-bar {
            display: flex;
            gap: 3px;
            margin: 8px 0;
        }

        .bar-segment {
            flex: 1;
            height: 6px;
            background: rgba(59, 130, 246, 0.3);
            border-radius: 3px;
            transition: all 0.3s ease;
        }

        .bar-segment.active {
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            animation: fillBar 0.6s ease forwards;
        }

        @keyframes fillBar {
            from { width: 0; }
            to { width: 100%; }
        }

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 80px;
            padding-top: 40px;
            border-top: 1px solid rgba(59, 130, 246, 0.2);
            animation: slideUp 0.8s ease 1.1s backwards;
        }

        .footer p {
            color: #94a3b8;
            font-size: 0.95rem;
            margin-bottom: 15px;
        }

        .footer .heart {
            display: inline-block;
            animation: heartbeat 1.2s ease infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        /* Category Label */
        .category-label {
            display: inline-block;
            padding: 4px 12px;
            background: rgba(139, 92, 246, 0.2);
            border: 1px solid rgba(139, 92, 246, 0.4);
            border-radius: 20px;
            font-size: 0.8rem;
            color: #c4b5fd;
            margin-right: 8px;
            margin-bottom: 12px;
        }

        /* Scroll reveal */
        .reveal {
            opacity: 0;
            animation: slideUp 0.8s ease forwards;
        }

        /* Stats */
        .stat {
            display: inline-block;
            margin-right: 30px;
            margin-bottom: 15px;
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: #94a3b8;
            font-size: 0.9rem;
            margin-top: 5px;
        }
    </style>
</head>
<body>
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>
    <div class="grid"></div>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="emoji-icon">👨‍💻</div>
            <h1>Jaba Janelidze</h1>
            <p class="tagline">Fullstack Developer & Scrum Master</p>
            <p class="location">📍 Tbilisi, Georgia • 🌍 Open to Remote & On-site</p>
            
            <div class="social-container">
                <a href="mailto:jabajnldz.dev@gmail.com" class="social-btn">📧 Email</a>
                <a href="https://linkedin.com/in/jaba-janelidze-2517b0389/" class="social-btn">💼 LinkedIn</a>
                <a href="https://github.com/jabjubinski" class="social-btn">💻 GitHub</a>
            </div>

            <div style="text-align: center; margin-top: 30px;">
                <div class="stat">
                    <div class="stat-number">3+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat">
                    <div class="stat-number">20+</div>
                    <div class="stat-label">Projects Delivered</div>
                </div>
                <div class="stat">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Client Satisfaction</div>
                </div>
            </div>
        </div>

        <div class="divider"></div>

        <!-- About Section -->
        <div class="section">
            <h2>🎯 About Me</h2>
            <div class="card">
                <p>Passionate <strong>Fullstack Developer</strong> with <strong>3+ years of experience</strong> building responsive, interactive web applications. I specialize in creating seamless user experiences while maintaining clean, scalable code.</p>
                <p>I wear multiple hats — from developer to <strong>Scrum Master</strong>, <strong>Product Owner</strong>, and <strong>Freelance Consultant</strong> — bringing comprehensive understanding of the full development lifecycle.</p>
                <p>Currently leveraging <strong>React</strong>, <strong>Next.js</strong>, <strong>TypeScript</strong>, and <strong>Node.js</strong> to build products that matter. Driven by problem-solving, continuous learning, and delivering exceptional results in fast-paced, agile environments.</p>
            </div>
        </div>

        <!-- Experience Section -->
        <div class="section">
            <h2>💼 Experience</h2>
            
            <div class="card">
                <h3>Self-Employed Fullstack Developer & Consultant</h3>
                <div class="role">Jan 2022 – Present • 3+ years</div>
                <p>⚙️ Architected and deployed full-stack applications for diverse clients across multiple industries</p>
                <p>⚙️ Managed projects end-to-end: requirements gathering, design, development, deployment</p>
                <p>⚙️ <strong>Scrum Master & Product Owner</strong> for agile team coordination and product strategy</p>
                <p>⚙️ Mentored junior developers and established best practices for code quality</p>
            </div>

            <div class="card">
                <h3>Fullstack Developer Intern</h3>
                <div class="role">Resoft • Oct 2024 – Mar 2025</div>
                <p>⚙️ Developed interactive web applications using React and Node.js</p>
                <p>⚙️ Transitioned to Business Analyst role, shaping project roadmaps</p>
                <p>⚙️ Collaborated in agile sprints with cross-functional teams</p>
            </div>

            <div class="card">
                <h3>Part-time Fullstack Developer & Business Analyst</h3>
                <div class="role">Re:Invent • Mar 2025 – Oct 2025</div>
                <p>⚙️ Contributed to Georgian AI-based virtual assistant platform</p>
                <p>⚙️ Built responsive UI with seamless UX using modern frameworks</p>
                <p>⚙️ Worked alongside designers and product managers in sprint cycles</p>
            </div>
        </div>

        <!-- Tech Stack Section -->
        <div class="section">
            <h2>🛠️ Tech Stack</h2>
            
            <div style="margin-bottom: 25px;">
                <div class="category-label">🎨 Frontend</div>
                <div class="tech-grid">
                    <div class="tech-badge">React</div>
                    <div class="tech-badge">Next.js</div>
                    <div class="tech-badge">TypeScript</div>
                    <div class="tech-badge">JavaScript</div>
                    <div class="tech-badge">HTML5</div>
                    <div class="tech-badge">CSS3</div>
                </div>
            </div>

            <div style="margin-bottom: 25px;">
                <div class="category-label">🎭 Styling & Animation</div>
                <div class="tech-grid">
                    <div class="tech-badge">Tailwind CSS</div>
                    <div class="tech-badge">Sass/SCSS</div>
                    <div class="tech-badge">LESS</div>
                    <div class="tech-badge">Framer Motion</div>
                </div>
            </div>

            <div style="margin-bottom: 25px;">
                <div class="category-label">🧠 State Management</div>
                <div class="tech-grid">
                    <div class="tech-badge">React Query</div>
                    <div class="tech-badge">Zustand</div>
                    <div class="tech-badge">Redux</div>
                </div>
            </div>

            <div style="margin-bottom: 25px;">
                <div class="category-label">🔧 Backend</div>
                <div class="tech-grid">
                    <div class="tech-badge">Node.js</div>
                    <div class="tech-badge">Express</div>
                    <div class="tech-badge">Firebase</div>
                    <div class="tech-badge">Python</div>
                </div>
            </div>

            <div style="margin-bottom: 25px;">
                <div class="category-label">💻 Languages</div>
                <div class="tech-grid">
                    <div class="tech-badge">C++</div>
                    <div class="tech-badge">C#</div>
                    <div class="tech-badge">JavaScript</div>
                    <div class="tech-badge">TypeScript</div>
                    <div class="tech-badge">Python</div>
                </div>
            </div>

            <div style="margin-bottom: 25px;">
                <div class="category-label">🚀 Essential Web Dev Tools</div>
                <div class="tech-grid">
                    <div class="tech-badge">Git</div>
                    <div class="tech-badge">REST API</div>
                    <div class="tech-badge">GraphQL</div>
                    <div class="tech-badge">Webpack</div>
                    <div class="tech-badge">Figma</div>
                    <div class="tech-badge">VS Code</div>
                </div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2>🎯 Key Skills</h2>
            
            <div class="card">
                <strong style="color: #3b82f6;">Development:</strong>
                <p>Full-Stack Web Development • React & Next.js • RESTful APIs • Database Design • Performance Optimization</p>
            </div>

            <div class="card">
                <strong style="color: #8b5cf6;">Soft Skills:</strong>
                <p>Scrum Master • Product Owner • Agile Methodology • Team Leadership • Cross-functional Collaboration • Problem Solving</p>
            </div>

            <div class="card">
                <strong style="color: #ec4899;">Project Management:</strong>
                <p>Sprint Planning • Backlog Management • Stakeholder Communication • Agile Transformation • Risk Management</p>
            </div>
        </div>

        <!-- Languages Section -->
        <div class="section">
            <h2>🗣️ Languages</h2>
            <table>
                <thead>
                    <tr>
                        <th>Language</th>
                        <th>Proficiency</th>
                        <th>Level</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Georgian</td>
                        <td>Native</td>
                        <td><div class="progress-bar"><div class="bar-segment active" style="animation-delay: 0s;"></div><div class="bar-segment active" style="animation-delay: 0.1s;"></div><div class="bar-segment active" style="animation-delay: 0.2s;"></div><div class="bar-segment active" style="animation-delay: 0.3s;"></div><div class="bar-segment active" style="animation-delay: 0.4s;"></div></div></td>
                    </tr>
                    <tr>
                        <td>English</td>
                        <td>Full Professional</td>
                        <td><div class="progress-bar"><div class="bar-segment active" style="animation-delay: 0s;"></div><div class="bar-segment active" style="animation-delay: 0.1s;"></div><div class="bar-segment active" style="animation-delay: 0.2s;"></div><div class="bar-segment active" style="animation-delay: 0.3s;"></div><div class="bar-segment"></div></div></td>
                    </tr>
                    <tr>
                        <td>Russian</td>
                        <td>Professional</td>
                        <td><div class="progress-bar"><div class="bar-segment active" style="animation-delay: 0s;"></div><div class="bar-segment active" style="animation-delay: 0.1s;"></div><div class="bar-segment active" style="animation-delay: 0.2s;"></div><div class="bar-segment"></div><div class="bar-segment"></div></div></td>
                    </tr>
                    <tr>
                        <td>Swedish</td>
                        <td>Basic</td>
                        <td><div class="progress-bar"><div class="bar-segment active" style="animation-delay: 0s;"></div><div class="bar-segment"></div><div class="bar-segment"></div><div class="bar-segment"></div><div class="bar-segment"></div></div></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- Education Section -->
        <div class="section">
            <h2>🎓 Education & Certifications</h2>
            
            <div class="card">
                <h3>Bachelor of Science in Geology</h3>
                <div class="role">Ilia State University • 2024</div>
            </div>

            <div class="card">
                <h3>Master of IT Technology</h3>
                <div class="role">Georgian Technical University • 2025 (Expected)</div>
            </div>

            <div class="card">
                <h3>📜 Certifications</h3>
                <p>✅ CS50: Introduction to Computer Science — Harvard University (Ongoing)</p>
                <p>✅ Modern JavaScript (ES6+) Bootcamp — Udemy</p>
                <p>✅ IT Step Academy HTML/CSS/JavaScript/Angular Bootcamp</p>
                <p>✅ Agile & Scrum Fundamentals</p>
            </div>
        </div>

        <!-- Currently Focused On -->
        <div class="section">
            <h2>🚀 Currently Focused On</h2>
            <div class="card">
                <p>⚡ Mastering <strong>Next.js 14+</strong> with App Router and Server Components</p>
                <p>⚡ Advanced <strong>TypeScript</strong> patterns and best practices</p>
                <p>⚡ Building scalable microservices architectures</p>
                <p>⚡ Deepening Scrum Master certifications and agile practices</p>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>💬 <strong>Let's Connect!</strong> I'm always interested in discussing new projects, collaborations, or opportunities.</p>
            <p>Reach out via <a href="mailto:jabajnldz.dev@gmail.com" style="color: #3b82f6; text-decoration: none; font-weight: 600;">Email</a> • <a href="https://linkedin.com/in/jaba-janelidze-2517b0389/" style="color: #3b82f6; text-decoration: none; font-weight: 600;">LinkedIn</a> • <a href="https://github.com/jabjubinski" style="color: #3b82f6; text-decoration: none; font-weight: 600;">GitHub</a></p>
            <p>Made with <span class="heart">❤️</span> in Tbilisi, Georgia | ⭐ If you like what you see, give this repo a star!</p>
        </div>
    </div>

    <script>
        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('reveal');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section').forEach(el => {
            observer.observe(el);
        });

        // Smooth scroll for links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target?.scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
