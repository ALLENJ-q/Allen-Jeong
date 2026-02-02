<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Allen Jeong - AI Engineer Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        /* CSS Variables & Reset */
        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #ec4899;
            --accent: #8b5cf6;
            --dark: #0f172a;
            --light: #f8fafc;
            --gray: #64748b;
            --gradient-1: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --gradient-3: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            --glass: rgba(255, 255, 255, 0.1);
            --shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
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
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background: var(--light);
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: 
                radial-gradient(circle at 20% 50%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(236, 72, 153, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(139, 92, 246, 0.1) 0%, transparent 50%);
            animation: bgPulse 8s ease-in-out infinite;
        }

        @keyframes bgPulse {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.05); }
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.3);
            transition: all 0.3s ease;
        }

        header.scrolled {
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            overflow: hidden;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: var(--gradient-1);
            animation: slideLine 3s infinite;
        }

        @keyframes slideLine {
            0% { left: -100%; }
            50% { left: 100%; }
            100% { left: 100%; }
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            font-size: 0.95rem;
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
            background: var(--gradient-1);
            transition: width 0.3s ease;
        }

        nav a:hover::before {
            width: 100%;
        }

        nav a:hover {
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 6rem 2rem 4rem;
            overflow: hidden;
        }

        .hero-content {
            text-align: center;
            max-width: 900px;
            z-index: 1;
        }

        .hero-badge {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            background: var(--glass);
            border: 1px solid rgba(99, 102, 241, 0.3);
            border-radius: 50px;
            font-size: 0.9rem;
            color: var(--primary);
            margin-bottom: 2rem;
            animation: float 3s ease-in-out infinite;
            backdrop-filter: blur(10px);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .hero h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, var(--dark) 0%, var(--primary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero h1 span {
            display: block;
            background: var(--gradient-2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto 2.5rem;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: var(--gradient-1);
            color: white;
            box-shadow: 0 10px 30px -10px rgba(99, 102, 241, 0.5);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 40px -10px rgba(99, 102, 241, 0.6);
        }

        .btn-secondary {
            background: white;
            color: var(--dark);
            border: 2px solid #e2e8f0;
        }

        .btn-secondary:hover {
            border-color: var(--primary);
            color: var(--primary);
            transform: translateY(-3px);
        }

        /* Floating Elements */
        .floating-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            overflow: hidden;
        }

        .shape {
            position: absolute;
            opacity: 0.1;
            animation: floatShape 20s infinite;
        }

        .shape-1 {
            top: 20%;
            left: 10%;
            width: 80px;
            height: 80px;
            background: var(--primary);
            border-radius: 50%;
            animation-delay: 0s;
        }

        .shape-2 {
            top: 60%;
            right: 10%;
            width: 120px;
            height: 120px;
            background: var(--secondary);
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            animation-delay: -5s;
        }

        .shape-3 {
            bottom: 20%;
            left: 20%;
            width: 60px;
            height: 60px;
            background: var(--accent);
            transform: rotate(45deg);
            animation-delay: -10s;
        }

        @keyframes floatShape {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            33% { transform: translate(30px, -30px) rotate(120deg); }
            66% { transform: translate(-20px, 20px) rotate(240deg); }
        }

        /* Section Styles */
        section {
            padding: 6rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-tag {
            display: inline-block;
            padding: 0.4rem 1rem;
            background: rgba(99, 102, 241, 0.1);
            color: var(--primary);
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--dark);
            margin-bottom: 1rem;
        }

        .section-subtitle {
            color: var(--gray);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        /* About Section */
        .about-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-image {
            position: relative;
        }

        .about-image-wrapper {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .about-image-wrapper::before {
            content: '';
            position: absolute;
            inset: -10px;
            background: var(--gradient-1);
            border-radius: 25px;
            z-index: -1;
            opacity: 0.5;
            filter: blur(20px);
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s ease;
        }

        .about-image-wrapper:hover img {
            transform: scale(1.05);
        }

        .about-content h3 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: var(--dark);
        }

        .about-content p {
            font-size: 1.1rem;
            color: var(--gray);
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid #e2e8f0;
        }

        .stat-item h4 {
            font-size: 2rem;
            font-weight: 800;
            color: var(--primary);
            font-family: 'JetBrains Mono', monospace;
        }

        .stat-item p {
            font-size: 0.9rem;
            color: var(--gray);
            margin: 0;
        }

        /* Skills Section */
        .skills {
            background: white;
            border-radius: 30px;
            padding: 3rem;
            box-shadow: 0 20px 60px -20px rgba(0, 0, 0, 0.1);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
        }

        .skill-category {
            padding: 2rem;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            border-radius: 20px;
            border: 1px solid rgba(99, 102, 241, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: var(--gradient-1);
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.3s ease;
        }

        .skill-category:hover::before {
            transform: scaleX(1);
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px -20px rgba(99, 102, 241, 0.3);
        }

        .skill-category h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .skill-icon {
            width: 40px;
            height: 40px;
            background: var(--gradient-1);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        .skill-category ul {
            list-style: none;
        }

        .skill-category li {
            padding: 0.75rem 0;
            border-bottom: 1px solid #e2e8f0;
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: var(--gray);
            transition: all 0.3s ease;
        }

        .skill-category li:last-child {
            border-bottom: none;
        }

        .skill-category li::before {
            content: '→';
            color: var(--primary);
            font-weight: bold;
            opacity: 0;
            transform: translateX(-10px);
            transition: all 0.3s ease;
        }

        .skill-category:hover li::before {
            opacity: 1;
            transform: translateX(0);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 2.5rem;
        }

        .project-card {
            background: white;
            border-radius: 24px;
            overflow: hidden;
            box-shadow: 0 10px 40px -10px rgba(0, 0, 0, 0.1);
            transition: all 0.4s ease;
            position: relative;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 30px 60px -20px rgba(0, 0, 0, 0.2);
        }

        .project-image-container {
            position: relative;
            height: 240px;
            overflow: hidden;
            background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
        }

        .project-image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .project-card:hover .project-image-container img {
            transform: scale(1.1);
        }

        .project-image-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(15, 23, 42, 0.8), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
            display: flex;
            align-items: flex-end;
            padding: 1.5rem;
        }

        .project-card:hover .project-image-overlay {
            opacity: 1;
        }

        .project-tech-stack {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .tech-tag {
            padding: 0.25rem 0.75rem;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 50px;
            font-size: 0.75rem;
            color: white;
            font-weight: 500;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .project-section {
            margin-bottom: 1.25rem;
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
            color: var(--gray);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .project-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .btn-small {
            padding: 0.6rem 1.2rem;
            font-size: 0.9rem;
        }

        /* Image Upload Placeholder Styles */
        .image-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            gap: 1rem;
            background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
        }

        .image-placeholder-icon {
            width: 60px;
            height: 60px;
            border: 3px dashed var(--primary);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            opacity: 0.5;
        }

        .image-placeholder-text {
            font-size: 0.9rem;
            opacity: 0.7;
            text-align: center;
            padding: 0 1rem;
        }

        /* Contact Section */
        .contact {
            background: white;
            border-radius: 30px;
            padding: 4rem;
            text-align: center;
            box-shadow: 0 20px 60px -20px rgba(0, 0, 0, 0.1);
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
            background: radial-gradient(circle, rgba(99, 102, 241, 0.03) 0%, transparent 70%);
            animation: rotate 30s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .contact-content {
            position: relative;
            z-index: 1;
        }

        .contact h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .contact > p {
            color: var(--gray);
            margin-bottom: 2.5rem;
            font-size: 1.1rem;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            padding: 1rem 2rem;
            background: #f8fafc;
            border-radius: 16px;
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .contact-link:hover {
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px -10px rgba(99, 102, 241, 0.3);
            color: var(--primary);
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background: var(--gradient-1);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 3rem 2rem;
            background: var(--dark);
            color: white;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            background: var(--gradient-1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #94a3b8;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: white;
        }

        footer p {
            color: #64748b;
            font-size: 0.9rem;
        }

        /* Scroll Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1.5rem;
                font-size: 0.9rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-container {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .stats {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .contact {
                padding: 2rem;
            }

            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }

        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-dark);
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="bg-animation"></div>

    <!-- Header -->
    <header id="header">
        <div class="header-content">
            <div class="logo">Allen<span style="color: var(--dark);">Jeong</span></div>
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
        <div class="floating-shapes">
            <div class="shape shape-1"></div>
            <div class="shape shape-2"></div>
            <div class="shape shape-3"></div>
        </div>
        <div class="hero-content">
            <div class="hero-badge">🚀 Available for Opportunities</div>
            <h1>AI Engineer <span>& NLP Enthusiast</span></h1>
            <p>Building intelligent solutions that bridge language barriers and enhance human communication through cutting-edge AI technology.</p>
            <div class="hero-buttons">
                <a href="#projects" class="btn btn-primary">View Projects →</a>
                <a href="#contact" class="btn btn-secondary">Get in Touch</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="section-header reveal">
            <span class="section-tag">About Me</span>
            <h2 class="section-title">Passionate About AI Innovation</h2>
            <p class="section-subtitle">Bridging technology and language to create meaningful impact</p>
        </div>
        <div class="about-container reveal">
            <div class="about-image">
                <div class="about-image-wrapper">
                    <!-- REPLACE WITH YOUR PHOTO: Add your image to /mnt/kimi/upload/ folder and update src -->
                    ![image alt](https://github.com/ALLENJ-q/Allen-Jeong/blob/a9e0566eecddfa632a3e6c0fca3f46ef19ef9955/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260202212203_263_2.jpg)
                </div>
            </div>
            <div class="about-content">
                <h3>Hello, I'm Allen Jeong</h3>
                <p>A Korea-born Chinese AI enthusiast with hands-on experience in Python development. I specialize in building practical AI-powered applications that enhance daily productivity and bridge communication gaps.</p>
                <p>My mission is to grow into a skilled AI Engineer who creates intuitive, technology-driven solutions that simplify communication, learning, and content refinement for diverse global users.</p>
                <div class="stats">
                    <div class="stat-item">
                        <h4>2+</h4>
                        <p>Years Experience</p>
                    </div>
                    <div class="stat-item">
                        <h4>10+</h4>
                        <p>Projects Built</p>
                    </div>
                    <div class="stat-item">
                        <h4>3+</h4>
                        <p>Languages</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="section-header reveal">
            <span class="section-tag">Expertise</span>
            <h2 class="section-title">Skills & Tools</h2>
            <p class="section-subtitle">Technologies and capabilities I bring to the table</p>
        </div>
        <div class="skills reveal">
            <div class="skills-grid">
                <div class="skill-category">
                    <h3><span class="skill-icon">💻</span> Technical Skills</h3>
                    <ul>
                        <li>Programming: Python (proficient), JavaScript/Java basics</li>
                        <li>AI/ML: NLP fundamentals, Hugging Face, spaCy</li>
                        <li>Data Handling: Pandas, JSON/CSV manipulation</li>
                        <li>Dev Tools: Git/GitHub, UI/UX basics</li>
                        <li>Language Tech: Text analysis, grammar algorithms</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3><span class="skill-icon">🎯</span> Professional Skills</h3>
                    <ul>
                        <li>Cross-team collaboration</li>
                        <li>User-centric problem-solving</li>
                        <li>Attention to detail (AI accuracy)</li>
                        <li>Adaptability to new AI tools</li>
                        <li>Multicultural user empathy</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <div class="section-header reveal">
            <span class="section-tag">Portfolio</span>
            <h2 class="section-title">Featured Projects</h2>
            <p class="section-subtitle">Real-world applications solving complex problems</p>
        </div>
        <div class="projects-grid">
            <!-- Project 1 -->
            <div class="project-card reveal">
                <div class="project-image-container">
                    <!-- REPLACE WITH YOUR PROJECT SCREENSHOT -->
                    <!-- Option 1: Use an image URL -->
                    <!-- <img src="https://github.com/ALLENJ-q/Allen-Jeong/blob/1617ddbbe2ea99500a05fa07194573913acb90e0/009e55b4e7c23a9e314fae8152dd4e1c.jpg" alt="Text Enhancement Suite"> -->
                    
                    <!-- Option 2: Placeholder showing where to add image -->
                    <div class="image-placeholder">
                        <div class="image-placeholder-icon">📸</div>
                        <div class="image-placeholder-text">
                            Add your screenshot:<br>
                            &lt;img src="your-image.jpg"&gt;
                        </div>
                    </div>
                    
                    <div class="project-image-overlay">
                        <div class="project-tech-stack">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">NLP</span>
                            <span class="tech-tag">Flask</span>
                        </div>
                    </div>
                </div>
                <div class="project-content">
                    <h3>AI-Powered Text Enhancement Suite</h3>
                    <div class="project-section">
                        <h4>⚡ What It Does</h4>
                        <p>Combines text modification, built-in dictionary, and real-time grammar checking—all powered by NLP models. Rewrites content for clarity/tone, provides definitions, and fixes grammatical errors.</p>
                    </div>
                    <div class="project-section">
                        <h4>🎯 Problem Solved</h4>
                        <p>Eliminates tool-switching by unifying essential writing features, saving users time on academic/professional content.</p>
                    </div>
                    <div class="project-section">
                        <h4>🚀 Future Improvements</h4>
                        <p>Multilingual support, style templates, plagiarism detection, mobile app.</p>
                    </div>
                    <div class="project-links">
                        <a href="https://github.com/allenjeong/text-enhancement-suite" class="btn btn-primary btn-small">View Code →</a>
                        <a href="#" class="btn btn-secondary btn-small">Live Demo</a>
                    </div>
                </div>
            </div>

            <!-- Project 2 -->
            <div class="project-card reveal">
                <div class="project-image-container">
                    <!-- REPLACE WITH YOUR PROJECT SCREENSHOT -->
                    <div class="image-placeholder">
                        <div class="image-placeholder-icon">📸</div>
                        <div class="image-placeholder-text">
                            Add your screenshot:<br>
                            &lt;img src="your-image.jpg"&gt;
                        </div>
                    </div>
                    <div class="project-image-overlay">
                        <div class="project-tech-stack">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">API</span>
                            <span class="tech-tag">i18n</span>
                        </div>
                    </div>
                </div>
                <div class="project-content">
                    <h3>AI-Driven Multilingual Translation App</h3>
                    <div class="project-section">
                        <h4>⚡ What It Does</h4>
                        <p>Translates text between 20+ languages with contextual accuracy, saves frequently used phrases, and adapts to formal/casual speech.</p>
                    </div>
                    <div class="project-section">
                        <h4>🎯 Problem Solved</h4>
                        <p>Breaks language barriers for travelers, students, and professionals with reliable, user-friendly translation.</p>
                    </div>
                    <div class="project-section">
                        <h4>🚀 Future Improvements</h4>
                        <p>Voice-to-text translation, offline mode, specialized terminology (legal/medical), conversation mode.</p>
                    </div>
                    <div class="project-links">
                        <a href="https://github.com/allenjeong/ai-translation-app" class="btn btn-primary btn-small">View Code →</a>
                        <a href="#" class="btn btn-secondary btn-small">Live Demo</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="contact reveal">
            <div class="contact-content">
                <span class="section-tag">Get in Touch</span>
                <h3>Let's Build Something Amazing Together</h3>
                <p>Interested in collaborating or discussing AI projects? I'm always open to new opportunities.</p>
                <div class="contact-links">
                    <a href="mailto:allen.jeong.ai@gmail.com" class="contact-link">
                        <span class="contact-icon">✉️</span>
                        <div>
                            <div style="font-weight: 600;">Email</div>
                            <div style="font-size: 0.85rem; color: var(--gray);">allen.jeong.ai@gmail.com</div>
                        </div>
                    </a>
                    <a href="https://github.com/allenjeong" class="contact-link">
                        <span class="contact-icon">💻</span>
                        <div>
                            <div style="font-weight: 600;">GitHub</div>
                            <div style="font-size: 0.85rem; color: var(--gray);">github.com/allenjeong</div>
                        </div>
                    </a>
                    <a href="https://linkedin.com/in/allenjeong" class="contact-link">
                        <span class="contact-icon">🔗</span>
                        <div>
                            <div style="font-weight: 600;">LinkedIn</div>
                            <div style="font-size: 0.85rem; color: var(--gray);">linkedin.com/in/allenjeong</div>
                        </div>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-logo">AllenJeong</div>
            <div class="footer-links">
                <a href="#about">About</a>
                <a href="#skills">Skills</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
            </div>
            <p>&copy; 2024 Allen Jeong. Crafted with passion and code.</p>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Scroll reveal animation
        const revealElements = document.querySelectorAll('.reveal');
        
        const revealOnScroll = () => {
            revealElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementTop < windowHeight - 100) {
                    element.classList.add('active');
                }
            });
        };

        window.addEventListener('scroll', revealOnScroll);
        window.addEventListener('load', revealOnScroll);

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
    </script>
</body>
</html>
