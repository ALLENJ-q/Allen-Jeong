<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Allen Jeong - AI Engineer Portfolio</title>
    <style>
        :root {
            /* Professional Color Palette */
            --primary: #1e293b;        /* Slate 800 - Deep professional blue-gray */
            --primary-light: #334155;  /* Slate 700 */
            --accent: #d97706;         /* Amber 600 - Professional gold/amber */
            --accent-light: #f59e0b;   /* Amber 500 */
            --bg: #f8fafc;            /* Slate 50 - Off-white */
            --surface: #ffffff;        /* Pure white */
            --text: #0f172a;          /* Slate 900 - Near black */
            --text-secondary: #475569; /* Slate 600 */
            --text-muted: #94a3b8;    /* Slate 400 */
            --border: #e2e8f0;        /* Slate 200 */
            
            /* Typography Scale */
            --text-xs: 0.75rem;
            --text-sm: 0.875rem;
            --text-base: 1rem;
            --text-lg: 1.125rem;
            --text-xl: 1.25rem;
            --text-2xl: 1.5rem;
            --text-3xl: 1.875rem;
            --text-4xl: 2.25rem;
            --text-5xl: 3rem;
            
            /* Spacing Scale */
            --space-1: 0.25rem;
            --space-2: 0.5rem;
            --space-3: 0.75rem;
            --space-4: 1rem;
            --space-6: 1.5rem;
            --space-8: 2rem;
            --space-12: 3rem;
            --space-16: 4rem;
            --space-20: 5rem;
            --space-24: 6rem;
            
            /* Shadows */
            --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--bg);
            -webkit-font-smoothing: antialiased;
        }

        /* Layout Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--space-6);
        }

        /* Header - Minimal & Balanced */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border);
            z-index: 1000;
            height: 70px;
            display: flex;
            align-items: center;
        }

        .nav-content {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--space-6);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: var(--text-xl);
            font-weight: 700;
            color: var(--primary);
            letter-spacing: -0.025em;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: var(--space-2);
        }

        .logo::before {
            content: '';
            width: 8px;
            height: 8px;
            background: var(--accent);
            border-radius: 50%;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: var(--space-8);
        }

        nav a {
            text-decoration: none;
            color: var(--text-secondary);
            font-size: var(--text-sm);
            font-weight: 500;
            transition: color 0.2s;
            position: relative;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Hero Section - Asymmetric Balance */
        .hero {
            min-height: calc(100vh - 70px);
            margin-top: 70px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: var(--space-16);
            padding: var(--space-16) var(--space-6);
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-tag {
            display: inline-block;
            padding: var(--space-2) var(--space-4);
            background: rgba(217, 119, 6, 0.1);
            color: var(--accent);
            font-size: var(--text-sm);
            font-weight: 600;
            border-radius: 9999px;
            margin-bottom: var(--space-6);
            letter-spacing: 0.05em;
            text-transform: uppercase;
        }

        .hero h1 {
            font-size: var(--text-5xl);
            font-weight: 800;
            line-height: 1.1;
            color: var(--primary);
            margin-bottom: var(--space-6);
            letter-spacing: -0.025em;
        }

        .hero p {
            font-size: var(--text-xl);
            color: var(--text-secondary);
            line-height: 1.7;
            margin-bottom: var(--space-8);
        }

        .hero-cta {
            display: flex;
            gap: var(--space-4);
            align-items: center;
        }

        .btn-primary {
            display: inline-flex;
            align-items: center;
            padding: var(--space-4) var(--space-8);
            background: var(--primary);
            color: white;
            text-decoration: none;
            font-weight: 600;
            border-radius: 6px;
            transition: all 0.2s;
            border: 2px solid var(--primary);
        }

        .btn-primary:hover {
            background: var(--primary-light);
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .btn-secondary {
            display: inline-flex;
            align-items: center;
            padding: var(--space-4) var(--space-8);
            background: transparent;
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            border-radius: 6px;
            border: 2px solid var(--border);
            transition: all 0.2s;
        }

        .btn-secondary:hover {
            border-color: var(--primary);
            background: rgba(30, 41, 59, 0.05);
        }

        /* Hero Visual Element */
        .hero-visual {
            position: relative;
            height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .code-window {
            width: 100%;
            max-width: 500px;
            background: var(--surface);
            border-radius: 12px;
            box-shadow: var(--shadow-xl);
            border: 1px solid var(--border);
            overflow: hidden;
        }

        .code-header {
            background: var(--bg);
            padding: var(--space-4);
            border-bottom: 1px solid var(--border);
            display: flex;
            gap: var(--space-2);
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot-red { background: #ef4444; }
        .dot-yellow { background: #eab308; }
        .dot-green { background: #22c55e; }

        .code-content {
            padding: var(--space-6);
            font-family: 'Monaco', 'Menlo', monospace;
            font-size: var(--text-sm);
            line-height: 1.6;
            color: var(--text-secondary);
        }

        .code-line {
            margin-bottom: var(--space-2);
        }

        .code-keyword { color: var(--accent); font-weight: 600; }
        .code-function { color: #2563eb; }
        .code-string { color: #059669; }

        /* Section Spacing */
        section {
            padding: var(--space-24) 0;
        }

        .section-header {
            text-align: center;
            max-width: 600px;
            margin: 0 auto var(--space-16);
        }

        .section-label {
            color: var(--accent);
            font-size: var(--text-sm);
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-bottom: var(--space-4);
            display: block;
        }

        .section-title {
            font-size: var(--text-4xl);
            font-weight: 800;
            color: var(--primary);
            margin-bottom: var(--space-4);
            letter-spacing: -0.025em;
        }

        .section-subtitle {
            font-size: var(--text-lg);
            color: var(--text-secondary);
            line-height: 1.7;
        }

        /* About Section - Balanced Two Column */
        .about-grid {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: var(--space-16);
            align-items: start;
        }

        .about-image {
            position: relative;
        }

        .about-image-frame {
            width: 100%;
            aspect-ratio: 3/4;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: var(--text-4xl);
            box-shadow: var(--shadow-xl);
        }

        .about-content h3 {
            font-size: var(--text-2xl);
            color: var(--primary);
            margin-bottom: var(--space-6);
            font-weight: 700;
        }

        .about-content p {
            color: var(--text-secondary);
            font-size: var(--text-lg);
            line-height: 1.8;
            margin-bottom: var(--space-6);
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: var(--space-6);
            margin-top: var(--space-8);
            padding-top: var(--space-8);
            border-top: 1px solid var(--border);
        }

        .stat-item h4 {
            font-size: var(--text-3xl);
            color: var(--accent);
            font-weight: 800;
            margin-bottom: var(--space-1);
        }

        .stat-item p {
            font-size: var(--text-sm);
            color: var(--text-muted);
            margin: 0;
        }

        /* Skills Section - Grid Balance */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: var(--space-6);
        }

        .skill-item {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: var(--space-6);
            transition: all 0.3s;
        }

        .skill-item:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent);
        }

        .skill-icon {
            width: 48px;
            height: 48px;
            background: rgba(217, 119, 6, 0.1);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: var(--text-2xl);
            margin-bottom: var(--space-4);
        }

        .skill-item h3 {
            font-size: var(--text-lg);
            color: var(--primary);
            margin-bottom: var(--space-2);
            font-weight: 700;
        }

        .skill-item p {
            font-size: var(--text-sm);
            color: var(--text-secondary);
            line-height: 1.6;
        }

        /* Projects Section - Asymmetric Grid */
        .projects-container {
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            grid-template-rows: auto auto;
            gap: var(--space-6);
        }

        .project-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s;
            display: flex;
            flex-direction: column;
        }

        .project-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-xl);
        }

        .project-card.featured {
            grid-row: span 2;
        }

        .project-image {
            width: 100%;
            height: 240px;
            background: var(--bg);
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-muted);
        }

        .project-card.featured .project-image {
            height: 400px;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .project-card:hover .project-image img {
            transform: scale(1.05);
        }

        .placeholder-icon {
            font-size: 3rem;
            opacity: 0.3;
        }

        .project-content {
            padding: var(--space-6);
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .project-tag {
            display: inline-block;
            padding: var(--space-1) var(--space-3);
            background: rgba(217, 119, 6, 0.1);
            color: var(--accent);
            font-size: var(--text-xs);
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            border-radius: 4px;
            margin-bottom: var(--space-3);
            width: fit-content;
        }

        .project-content h3 {
            font-size: var(--text-xl);
            color: var(--primary);
            margin-bottom: var(--space-3);
            font-weight: 700;
        }

        .project-content p {
            color: var(--text-secondary);
            font-size: var(--text-base);
            line-height: 1.6;
            margin-bottom: var(--space-4);
            flex: 1;
        }

        .project-links {
            display: flex;
            gap: var(--space-4);
            margin-top: auto;
        }

        .link-btn {
            font-size: var(--text-sm);
            font-weight: 600;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: var(--space-2);
            transition: color 0.2s;
        }

        .link-btn:hover {
            color: var(--accent);
        }

        /* Contact Section - Split Layout */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: var(--space-16);
            background: var(--surface);
            border-radius: 16px;
            padding: var(--space-12);
            border: 1px solid var(--border);
        }

        .contact-info h3 {
            font-size: var(--text-2xl);
            color: var(--primary);
            margin-bottom: var(--space-6);
        }

        .contact-info p {
            color: var(--text-secondary);
            margin-bottom: var(--space-8);
            line-height: 1.7;
        }

        .contact-methods {
            display: flex;
            flex-direction: column;
            gap: var(--space-4);
        }

        .contact-method {
            display: flex;
            align-items: center;
            gap: var(--space-4);
            padding: var(--space-4);
            background: var(--bg);
            border-radius: 8px;
            text-decoration: none;
            color: var(--text);
            transition: all 0.2s;
        }

        .contact-method:hover {
            background: rgba(217, 119, 6, 0.1);
            transform: translateX(4px);
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background: var(--surface);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: var(--text-xl);
            border: 1px solid var(--border);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: var(--space-6);
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: var(--space-2);
        }

        .form-group label {
            font-size: var(--text-sm);
            font-weight: 600;
            color: var(--primary);
        }

        .form-group input,
        .form-group textarea {
            padding: var(--space-3) var(--space-4);
            border: 1px solid var(--border);
            border-radius: 6px;
            font-family: inherit;
            font-size: var(--text-base);
            transition: border-color 0.2s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent);
        }

        .submit-btn {
            padding: var(--space-4) var(--space-8);
            background: var(--accent);
            color: white;
            border: none;
            border-radius: 6px;
            font-weight: 600;
            font-size: var(--text-base);
            cursor: pointer;
            transition: all 0.2s;
            align-self: flex-start;
        }

        .submit-btn:hover {
            background: #b45309;
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        /* Footer - Minimal */
        footer {
            background: var(--primary);
            color: white;
            padding: var(--space-8) 0;
            text-align: center;
            font-size: var(--text-sm);
        }

        footer p {
            opacity: 0.7;
        }

        /* Animations */
        .fade-up {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-up.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 968px) {
            .hero {
                grid-template-columns: 1fr;
                text-align: center;
                gap: var(--space-8);
            }

            .hero-cta {
                justify-content: center;
            }

            .hero-visual {
                display: none;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: var(--space-8);
            }

            .about-image {
                max-width: 300px;
                margin: 0 auto;
            }

            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .projects-container {
                grid-template-columns: 1fr;
            }

            .project-card.featured {
                grid-row: span 1;
            }

            .contact-container {
                grid-template-columns: 1fr;
                gap: var(--space-8);
            }
        }

        @media (max-width: 640px) {
            .skills-grid {
                grid-template-columns: 1fr;
            }

            .stats {
                grid-template-columns: 1fr;
                text-align: center;
            }

            nav ul {
                gap: var(--space-4);
            }

            .hero h1 {
                font-size: var(--text-4xl);
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div class="nav-content">
            <a href="#" class="logo">Allen Jeong</a>
            <nav>
                <ul>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <span class="hero-tag">Available for opportunities</span>
            <h1>AI Engineer & NLP Specialist</h1>
            <p>Building intelligent systems that bridge language barriers and enhance human communication through practical, user-centered AI solutions.</p>
            <div class="hero-cta">
                <a href="#projects" class="btn-primary">View Projects</a>
                <a href="#contact" class="btn-secondary">Get in Touch</a>
            </div>
        </div>
        <div class="hero-visual">
            <div class="code-window">
                <div class="code-header">
                    <div class="dot dot-red"></div>
                    <div class="dot dot-yellow"></div>
                    <div class="dot dot-green"></div>
                </div>
                <div class="code-content">
                    <div class="code-line"><span class="code-keyword">class</span> <span class="code-function">AIEngineer</span>:</div>
                    <div class="code-line">&nbsp;&nbsp;<span class="code-keyword">def</span> <span class="code-function">__init__</span>(self):</div>
                    <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;self.name = <span class="code-string">"Allen Jeong"</span></div>
                    <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;self.focus = [<span class="code-string">"NLP"</span>, <span class="code-string">"Python"</span>]</div>
                    <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;self.passion = <span class="code-string">"Building bridges"</span></div>
                    <div class="code-line">&nbsp;&nbsp;</div>
                    <div class="code-line">&nbsp;&nbsp;<span class="code-keyword">def</span> <span class="code-function">solve</span>(self, problem):</div>
                    <div class="code-line">&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-keyword">return</span> <span class="code-string">"AI Solution"</span></div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="container">
        <div class="section-header fade-up">
            <span class="section-label">About Me</span>
            <h2 class="section-title">Bridging Technology & Communication</h2>
        </div>
        
        <div class="about-grid fade-up">
            <div class="about-image">
                <div class="about-image-frame">
                    👨‍💻
                </div>
            </div>
            <div class="about-content">
                <h3>Korea-born Chinese AI enthusiast crafting practical solutions.</h3>
                <p>With hands-on experience in Python development and a deep passion for NLP, I specialize in building AI-powered applications that enhance daily productivity. My multicultural background gives me unique insight into creating tools that serve diverse, global users.</p>
                <p>My approach combines technical precision with user empathy, ensuring every solution not only works flawlessly but feels intuitive to use.</p>
                
                <div class="stats">
                    <div class="stat-item">
                        <h4>2+</h4>
                        <p>Years Experience</p>
                    </div>
                    <div class="stat-item">
                        <h4>15+</h4>
                        <p>Projects Completed</p>
                    </div>
                    <div class="stat-item">
                        <h4>100%</h4>
                        <p>Commitment</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="container">
        <div class="section-header fade-up">
            <span class="section-label">Expertise</span>
            <h2 class="section-title">Technical Arsenal</h2>
            <p class="section-subtitle">A balanced mix of engineering skills and domain knowledge in AI/ML.</p>
        </div>

        <div class="skills-grid">
            <div class="skill-item fade-up">
                <div class="skill-icon">🐍</div>
                <h3>Python Development</h3>
                <p>Proficient in Python with focus on clean, efficient code for AI applications.</p>
            </div>
            <div class="skill-item fade-up">
                <div class="skill-icon">🧠</div>
                <h3>Machine Learning</h3>
                <p>NLP fundamentals, Hugging Face transformers, spaCy, and text analysis.</p>
            </div>
            <div class="skill-item fade-up">
                <div class="skill-icon">📊</div>
                <h3>Data Engineering</h3>
                <p>Pandas, NumPy, JSON/CSV manipulation, and data preprocessing pipelines.</p>
            </div>
            <div class="skill-item fade-up">
                <div class="skill-icon">⚡</div>
                <h3>API Integration</h3>
                <p>RESTful APIs, OpenAI integration, and backend service development.</p>
            </div>
            <div class="skill-item fade-up">
                <div class="skill-icon">🎨</div>
                <h3>UI/UX Basics</h3>
                <p>User-centric design thinking and frontend implementation.</p>
            </div>
            <div class="skill-item fade-up">
                <div class="skill-icon">🔧</div>
                <h3>DevOps Tools</h3>
                <p>Git/GitHub, version control, and collaborative development workflows.</p>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="container">
        <div class="section-header fade-up">
            <span class="section-label">Portfolio</span>
            <h2 class="section-title">Featured Projects</h2>
            <p class="section-subtitle">Real-world applications solving real communication challenges.</p>
        </div>

        <div class="projects-container">
            <!-- Featured Project -->
            <div class="project-card featured fade-up">
                <div class="project-image">
                    <!-- Replace with: <img src="./assets/text-enhancement.jpg" alt="Text Enhancement Suite"> -->
                    <span class="placeholder-icon">📝</span>
                </div>
                <div class="project-content">
                    <span class="project-tag">Featured Project</span>
                    <h3>AI-Powered Text Enhancement Suite</h3>
                    <p>A comprehensive writing assistant combining real-time grammar checking, style rewriting, and dictionary lookup. Built with Python and modern NLP libraries to unify essential writing tools in one seamless interface.</p>
                    <div style="margin-bottom: 1rem; font-size: 0.875rem; color: var(--text-muted);">
                        <strong>Key Features:</strong> Grammar correction • Tone adjustment • Dictionary integration
                    </div>
                    <div class="project-links">
                        <a href="https://github.com/allenjeong/text-enhancement-suite" class="link-btn" target="_blank">View Code →</a>
                        <a href="#" class="link-btn">Live Demo →</a>
                    </div>
                </div>
            </div>

            <!-- Secondary Project -->
            <div class="project-card fade-up">
                <div class="project-image">
                    <!-- Replace with: <img src="./assets/translation-app.jpg" alt="Translation App"> -->
                    <span class="placeholder-icon">🌐</span>
                </div>
                <div class="project-content">
                    <span class="project-tag">NLP Application</span>
                    <h3>Multilingual Translation App</h3>
                    <p>Context-aware translation supporting 20+ languages with formal/casual speech adaptation and phrase saving capabilities.</p>
                    <div class="project-links">
                        <a href="https://github.com/allenjeong/ai-translation-app" class="link-btn" target="_blank">View Code →</a>
                    </div>
                </div>
            </div>

            <!-- Third Project (Example for balance) -->
            <div class="project-card fade-up">
                <div class="project-image">
                    <span class="placeholder-icon">🤖</span>
                </div>
                <div class="project-content">
                    <span class="project-tag">Automation</span>
                    <h3>Data Processing Pipeline</h3>
                    <p>Automated text preprocessing system for ML training data with cleaning, normalization, and augmentation features.</p>
                    <div class="project-links">
                        <a href="#" class="link-btn">Coming Soon →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="container">
        <div class="section-header fade-up">
            <span class="section-label">Contact</span>
            <h2 class="section-title">Let's Build Together</h2>
        </div>

        <div class="contact-container fade-up">
            <div class="contact-info">
                <h3>Start a Conversation</h3>
                <p>Interested in collaborating on AI projects or discussing NLP innovations? I'm always open to meaningful conversations about technology and its impact.</p>
                
                <div class="contact-methods">
                    <a href="mailto:allen.jeong.ai@gmail.com" class="contact-method">
                        <div class="contact-icon">📧</div>
                        <div>
                            <div style="font-weight: 600; color: var(--primary);">Email</div>
                            <div style="font-size: 0.875rem; color: var(--text-secondary);">allen.jeong.ai@gmail.com</div>
                        </div>
                    </a>
                    <a href="https://github.com/allenjeong" class="contact-method" target="_blank">
                        <div class="contact-icon">💻</div>
                        <div>
                            <div style="font-weight: 600; color: var(--primary);">GitHub</div>
                            <div style="font-size: 0.875rem; color: var(--text-secondary);">github.com/allenjeong</div>
                        </div>
                    </a>
                    <a href="https://linkedin.com/in/allenjeong" class="contact-method" target="_blank">
                        <div class="contact-icon">🔗</div>
                        <div>
                            <div style="font-weight: 600; color: var(--primary);">LinkedIn</div>
                            <div style="font-size: 0.875rem; color: var(--text-secondary);">linkedin.com/in/allenjeong</div>
                        </div>
                    </a>
                </div>
            </div>

            <form class="contact-form" onsubmit="event.preventDefault(); alert('Thank you for your message! This is a demo form.');">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" placeholder="Your name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" placeholder="your@email.com" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" rows="4" placeholder="Tell me about your project..." required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2024 Allen Jeong. Crafted with precision & passion.</p>
        </div>
    </footer>

    <script>
        // Intersection Observer for fade-up animations
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-up').forEach((el) => observer.observe(el));

        // Smooth scroll for navigation
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </
