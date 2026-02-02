<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Allen Jeong - AI Engineer & NLP Enthusiast Portfolio">
    <meta name="keywords" content="AI Engineer, NLP, Python, Machine Learning, Portfolio">
    <meta name="author" content="Allen Jeong">
    
    <!-- Open Graph for social sharing -->
    <meta property="og:title" content="Allen Jeong - AI Engineer Portfolio">
    <meta property="og:description" content="Building AI-powered tools that simplify communication and language learning">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://allenjeong.github.io">
    
    <title>Allen Jeong - AI Engineer Portfolio</title>
    
    <!-- Favicon (no external files needed) -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>🚀</text></svg>">
    
    <style>
        /* CSS Variables for theming */
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #7c3aed;
            --accent: #06b6d4;
            --bg: #f8fafc;
            --surface: #ffffff;
            --text: #1e293b;
            --text-light: #64748b;
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #2563eb 0%, #06b6d4 100%);
        }

        /* Reset & Base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--bg);
            overflow-x: hidden;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--gradient);
            border-radius: 5px;
        }

        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 20px rgba(37, 99, 235, 0.3); }
            50% { box-shadow: 0 0 40px rgba(37, 99, 235, 0.6); }
        }

        @keyframes gradient-shift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes slide-up {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fade-in {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Utility Classes */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .animate-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .stagger-1 { transition-delay: 0.1s; }
        .stagger-2 { transition-delay: 0.2s; }
        .stagger-3 { transition-delay: 0.3s; }

        /* Header with Glassmorphism */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
            animation: slide-up 0.8s ease-out;
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.2rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--gradient);
            transition: width 0.3s ease;
        }

        .logo:hover::after {
            width: 100%;
        }

        /* Navigation */
        nav ul {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        nav a {
            text-decoration: none;
            color: var(--text);
            font-weight: 600;
            position: relative;
            padding: 0.5rem 0;
            transition: color 0.3s ease;
        }

        nav a::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient);
            transition: width 0.3s ease;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a:hover::before {
            width: 100%;
        }

        /* Hero Section with Animated Background */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: 
                radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(37, 99, 235, 0.2) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(6, 182, 212, 0.2) 0%, transparent 50%);
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            animation: gradient-shift 15s linear infinite;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 1.5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: float 6s ease-in-out infinite;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.4rem;
            color: var(--text-light);
            margin-bottom: 2.5rem;
            animation: fade-in 1s ease-out 0.5s both;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: var(--gradient);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.3);
            transition: all 0.3s ease;
            animation: pulse-glow 2s infinite;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
            transition: left 0.5s ease;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(37, 99, 235, 0.4);
        }

        .cta-button:hover::before {
            left: 100%;
        }

        /* Section Styles */
        section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 3rem;
            text-align: center;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: var(--gradient);
            border-radius: 2px;
        }

        /* About Section */
        .about {
            background: var(--surface);
            border-radius: 20px;
            padding: 3rem;
            box-shadow: 0 20px 60px rgba(0,0,0,0.05);
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0,0,0,0.05);
        }

        .about::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient);
        }

        .about p {
            font-size: 1.2rem;
            line-height: 1.9;
            color: var(--text-light);
            text-align: center;
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background: var(--surface);
            border-radius: 16px;
            padding: 2.5rem;
            box-shadow: 0 10px 40px rgba(0,0,0,0.05);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0,0,0,0.05);
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            opacity: 0;
            transition: opacity 0.4s ease;
            z-index: 0;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 60px rgba(37, 99, 235, 0.15);
        }

        .skill-card:hover::before {
            opacity: 0.05;
        }

        .skill-card > * {
            position: relative;
            z-index: 1;
        }

        .skill-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skill-card ul {
            list-style: none;
        }

        .skill-card li {
            margin-bottom: 1rem;
            padding-left: 1.5rem;
            position: relative;
            color: var(--text-light);
            transition: color 0.3s ease;
        }

        .skill-card:hover li {
            color: var(--text);
        }

        .skill-card li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--primary);
            font-weight: bold;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .project-card {
            background: var(--surface);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            border: 1px solid rgba(0,0,0,0.05);
        }

        .project-card:hover {
            transform: translateY(-10px) rotateX(2deg);
            box-shadow: 0 30px 60px rgba(37, 99, 235, 0.15);
        }

        /* Project Image Container */
        .project-image-container {
            position: relative;
            height: 250px;
            overflow: hidden;
            background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
        }

        .project-image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .project-card:hover .project-image-container img {
            transform: scale(1.1);
        }

        /* Placeholder for projects without images */
        .image-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 1.1rem;
            background: linear-gradient(135deg, #f0f4ff 0%, #e0e7ff 100%);
        }

        .image-placeholder-icon {
            font-size: 3rem;
            margin-bottom: 0.5rem;
            opacity: 0.5;
        }

        /* Image overlay on hover */
        .image-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(37, 99, 235, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover .image-overlay {
            opacity: 1;
        }

        .image-overlay-text {
            color: white;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border: 2px solid white;
            border-radius: 20px;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--text);
            transition: color 0.3s ease;
        }

        .project-card:hover .project-content h3 {
            color: var(--primary);
        }

        .project-section {
            margin-bottom: 1.2rem;
        }

        .project-section h4 {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--primary);
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .project-section p {
            color: var(--text-light);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .project-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1.5rem;
            background: var(--bg);
            color: var(--primary);
            text-decoration: none;
            border-radius: 8px;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .btn:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(37, 99, 235, 0.3);
        }

        .btn-primary {
            background: var(--gradient);
            color: white;
        }

        .btn-primary:hover {
            box-shadow: 0 5px 20px rgba(37, 99, 235, 0.4);
        }

        /* Contact Section */
        .contact {
            background: var(--surface);
            border-radius: 20px;
            padding: 4rem 3rem;
            box-shadow: 0 20px 60px rgba(0,0,0,0.05);
            text-align: center;
            border: 1px solid rgba(0,0,0,0.05);
            position: relative;
            overflow: hidden;
        }

        .contact::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(37, 99, 235, 0.03) 0%, transparent 70%);
            animation: float 10s ease-in-out infinite;
        }

        .contact-content {
            position: relative;
            z-index: 1;
        }

        .contact p {
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 2rem;
        }

        .contact-grid {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            padding: 1rem 2rem;
            background: var(--bg);
            border-radius: 50px;
            text-decoration: none;
            color: var(--text);
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .contact-item:hover {
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.1);
            color: var(--primary);
        }

        .contact-icon {
            font-size: 1.3rem;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 3rem 2rem;
            background: var(--text);
            color: white;
            margin-top: 4rem;
        }

        footer p {
            opacity: 0.8;
            font-size: 0.9rem;
        }

        /* GitHub Corner */
        .github-corner {
            position: absolute;
            top: 0;
            right: 0;
            width: 80px;
            height: 80px;
            fill: var(--primary);
            color: white;
            z-index: 1001;
        }

        .github-corner:hover .octo-arm {
            animation: octocat-wave 560ms ease-in-out;
        }

        @keyframes octocat-wave {
            0%, 100% { transform: rotate(0); }
            20%, 60% { transform: rotate(-25deg); }
            40%, 80% { transform: rotate(10deg); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                gap: 1.5rem;
                font-size: 0.9rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 2rem;
            }

            .github-corner {
                width: 60px;
                height: 60px;
            }
        }

        /* Reduced motion preference */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>
    <!-- GitHub Corner (links to your repo) -->
    <a href="https://github.com/allenjeong" class="github-corner" aria-label="View source on GitHub">
        <svg width="80" height="80" viewBox="0 0 250 250" style="position: absolute; top: 0; border: 0; right: 0;" aria-hidden="true">
            <path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path>
            <path d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2" fill="currentColor" style="transform-origin: 130px 106px;" class="octo-arm"></path>
            <path d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z" fill="currentColor" class="octo-body"></path>
        </svg>
    </a>

    <!-- Header -->
    <header>
        <div class="header-content">
            <div class="logo">Allen Jeong</div>
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
            <h1>AI Engineer &<br>NLP Enthusiast</h1>
            <p>Building intelligent tools that bridge language barriers and enhance human communication through cutting-edge AI.</p>
            <a href="#projects" class="cta-button">View My Work</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title animate-on-scroll">About Me</h2>
        <div class="about animate-on-scroll stagger-1">
            <p>I am Allen Jeong, a Korea-born Chinese AI enthusiast with hands-on experience in Python development. Passionate about building practical AI-powered applications that enhance daily productivity, I aim to grow into a skilled AI Engineer who creates intuitive, technology-driven solutions bridging language tools and user needs. My focus lies in developing AI programs that simplify communication, learning, and content refinement for diverse users.</p>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2 class="section-title animate-on-scroll">Skills & Tools</h2>
        <div class="skills-container">
            <div class="skill-card animate-on-scroll stagger-1">
                <h3>💻 Technical Skills</h3>
                <ul>
                    <li>Programming: Python (proficient), basic JavaScript/Java</li>
                    <li>AI/ML: NLP fundamentals, Hugging Face, spaCy</li>
                    <li>Data Handling: Pandas, JSON/CSV manipulation</li>
                    <li>Dev Tools: Git/GitHub, UI/UX basics</li>
                    <li>Language Tech: Text analysis, grammar algorithms</li>
                </ul>
            </div>
            <div class="skill-card animate-on-scroll stagger-2">
                <h3>🚀 Professional Skills</h3>
                <ul>
                    <li>Cross-team collaboration</li>
                    <li>User-centric problem-solving</li>
                    <li>Attention to detail (AI accuracy)</li>
                    <li>Adaptability to new AI tools</li>
                    <li>Multicultural user empathy</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2 class="section-title animate-on-scroll">Project Showcase</h2>
        <div class="projects-grid">
            
            <!-- Project 1: Text Enhancement Suite -->
            <div class="project-card animate-on-scroll stagger-1">
                <div class="project-image-container">
                    <!-- 👇 REPLACE WITH YOUR PROJECT SCREENSHOT (optional but recommended) -->
                    <!-- Upload image to your GitHub repo (e.g., create an /assets/images/ folder) -->
                    <!-- Uncomment the line below and update the URL: -->
                    <!-- <img src="https://raw.githubusercontent.com/allenjeong/allenjeong.github.io/main/assets/images/text-enhancement-suite.png" alt="Text Enhancement Suite Screenshot" loading="lazy"> -->
                    
                    <!-- Keep this placeholder if you don’t have an image yet -->
                    <div class="image-placeholder">
                        <div class="image-placeholder-icon">📝</div>
                        <span>Text Enhancement Suite</span>
                    </div>
                    
                    <div class="image-overlay">
                        <span class="image-overlay-text">View Project</span>
                    </div>
                </div>
                <div class="project-content">
                    <h3>AI-Powered Text Enhancement Suite</h3>
                    
                    <div class="project-section">
                        <h4>What It Does</h4>
                        <p>Combines text modification, built-in dictionary, and real-time grammar checking—all powered by NLP models. Rewrites content for clarity/tone, provides definitions, and fixes grammatical errors.</p>
                    </div>
                    
                    <div class="project-section">
                        <h4>Problem Solved</h4>
                        <p>Eliminates tool-switching by unifying essential writing features, saving users time on academic/professional content.</p>
                    </div>
                    
                    <div class="project-section">
                        <h4>Future Improvements</h4>
                        <p>Multilingual support, style templates, plagiarism detection, mobile app.</p>
                    </div>
                    
                    <div class="project-links">
                        <!-- 👇 UPDATE WITH YOUR ACTUAL GITHUB REPO URL -->
                        <a href="https://github.com/allenjeong/text-enhancement-suite" class="btn btn-primary" target="_blank" rel="noopener noreferrer">GitHub Code</a>
                        <!-- 👇 ADD LIVE DEMO URL IF YOU HAVE ONE (e.g., Replit/Vercel) -->
                        <a href="#" class="btn" disabled>Live Demo</a>
                    </div>
                </div>
            </div>

            <!-- Project 2: AI Translation App -->
            <div class="project-card animate-on-scroll stagger-2">
                <div class="project-image-container">
                    <!-- 👇 REPLACE WITH YOUR PROJECT SCREENSHOT (optional but recommended) -->
                    <!-- <img src="https://raw.githubusercontent.com/allenjeong/allenjeong.github.io/main/assets/images/ai-translation-app.png" alt="AI Translation App Screenshot" loading="lazy"> -->
                    
                    <!-- Keep this placeholder if you don’t have an image yet -->
                    <div class="image-placeholder">
                        <div class="image-placeholder-icon">🌐</div>
                        <span>AI Translation App</span>
                    </div>
                    
                    <div class="image-overlay">
                        <span class="image-overlay-text">View Project</span>
                    </div>
                </div>
                <div class="project-content">
                    <h3>AI-Driven Multilingual Translation App</h3>
                    
                    <div class="project-section">
                        <h4>What It Does</h4>
                        <p>Translates text between 20+ languages with contextual accuracy, saves frequently used phrases, and adapts to formal/casual speech.</p>
                    </div>
                    
                    <div class="project-section">
                        <h4>Problem Solved</h4>
                        <p>Breaks language barriers for travelers, students, and professionals with reliable, user-friendly translation.</p>
                    </div>
                    
                    <div class="project-section">
                        <h4>Future Improvements</h4>
                        <p>Voice-to-text translation, offline mode, specialized terminology (legal/medical), conversation mode.</p>
                    </div>
                    
                    <div class="project-links">
                        <!-- 👇 UPDATE WITH YOUR ACTUAL GITHUB REPO URL -->
                        <a href="https://github.com/allenjeong/ai-translation-app" class="btn btn-primary" target="_blank" rel="noopener noreferrer">GitHub Code</a>
                        <!-- 👇 ADD LIVE DEMO URL IF YOU HAVE ONE -->
                        <a href="#" class="btn" disabled>Live Demo</a>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2 class="section-title animate-on-scroll">Get In Touch</h2>
        <div class="contact animate-on-scroll stagger-1">
            <div class="contact-content">
                <p>Interested in collaborating or discussing AI projects? I'd love to hear from you!</p>
                <div class="contact-grid">
                    <a href="mailto:allen.jeong.ai@gmail.com" class="contact-item">
                        <span class="contact-icon">📧</span>
                        <span>allen.jeong.ai@gmail.com</span>
                    </a>
                    <a href="https://github.com/allenjeong" class="contact-item" target="_blank" rel="noopener noreferrer">
                        <span class="contact-icon">💻</span>
                        <span>GitHub</span>
                    </a>
                    <!-- 👇 UPDATE WITH YOUR ACTUAL LINKEDIN URL (if you have one) -->
                    <a href="https://linkedin.com/in/allenjeong" class="contact-item" target="_blank" rel="noopener noreferrer">
                        <span class="contact-icon">🔗</span>
                        <span>LinkedIn</span>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Allen Jeong. Crafted with passion & code.</p>
    </footer>

    <!-- JavaScript (no external dependencies) -->
    <script>
        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all animated elements
        document.querySelectorAll('.animate-on-scroll').forEach((el) => observer.observe(el));

        // Smooth scroll for navigation links
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

        // Header shadow on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.boxShadow = '0 4px 30px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.boxShadow = '0 4px 30px rgba(0, 0, 0, 0.05)';
            }
        });

        // Parallax effect for hero (disabled on mobile)
        if (window.matchMedia('(pointer: fine)').matches) {
            window.addEventListener('scroll', () => {
                const scrolled = window.pageYOffset;
                const hero = document.querySelector('.hero');
                if (hero && scrolled < window.innerHeight) {
                    hero.style.transform = `translateY(${scrolled * 0.5}px)`;
                }
            });
        }
    </script>
</body>
</html>
