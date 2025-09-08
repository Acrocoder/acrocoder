## Hi there 👋
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acro Coder - Frontend Developer Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables for Theming */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --accent-color: #e74c3c;
            --text-color: #333;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
            --shining-color: rgba(255, 255, 255, 0.5);
        }

        [data-theme="dark"] {
            --primary-color: #5dade2;
            --secondary-color: #58d68d;
            --accent-color: #ec7063;
            --text-color: #f8f9fa;
            --bg-color: #1a1a2e;
            --card-bg: #16213e;
            --shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            --shining-color: rgba(255, 255, 255, 0.3);
        }

        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            transition: var(--transition);
            overflow-x: hidden;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Moving Stars Background */
        .stars-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: transparent;
        }

        .star {
            position: absolute;
            background-color: #fff;
            border-radius: 50%;
            animation: moveStars linear infinite;
        }

        .star.shining {
            animation: moveStars linear infinite, shine 3s infinite;
        }

        @keyframes moveStars {
            from {
                transform: translateY(0);
            }
            to {
                transform: translateY(-2000px);
            }
        }

        @keyframes shine {
            0%, 100% {
                opacity: 0.3;
                box-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
            }
            50% {
                opacity: 1;
                box-shadow: 0 0 20px rgba(255, 255, 255, 0.8), 0 0 30px rgba(255, 255, 255, 0.6);
            }
        }

        /* Shining Effect */
        .shining-effect {
            position: relative;
            overflow: hidden;
        }

        .shining-effect::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                to right,
                transparent 0%,
                var(--shining-color) 45%,
                var(--shining-color) 55%,
                transparent 100%
            );
            transform: rotate(45deg) translateX(-100%);
            transition: transform 0.6s;
        }

        .shining-effect:hover::before {
            transform: rotate(45deg) translateX(100%);
        }

        /* Header Styles */
        header {
            background-color: var(--card-bg);
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            transition: var(--transition);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-img {
            height: 40px;
            width: auto;
            transition: var(--transition);
        }

        .logo-img:hover {
            transform: scale(1.1);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
            position: relative;
            z-index: 1;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary-color);
            transition: width 0.3s;
        }

        .logo:hover::after {
            width: 100%;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 1.5rem;
            position: relative;
        }

        .nav-links a {
            color: var(--text-color);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            z-index: 1;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .theme-toggle {
            background: none;
            border: none;
            color: var(--text-color);
            font-size: 1.2rem;
            cursor: pointer;
            transition: var(--transition);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .theme-toggle:hover {
            color: var(--primary-color);
            background: var(--bg-color);
        }

        /* Hero Section */
        .hero {
            padding: 5rem 0;
            text-align: center;
            position: relative;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            display: inline-block;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .typing-effect {
            border-right: 3px solid var(--primary-color);
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% {
                border-color: var(--primary-color);
            }
            51%, 100% {
                border-color: transparent;
            }
        }

        .profile-img-container {
            margin: 0 auto 2rem;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;
            border: 5px solid var(--primary-color);
            box-shadow: var(--shadow);
            position: relative;
            z-index: 1;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: var(--card-bg);
        }

        .profile-img-container:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .profile-img {
            width: 80%;
            height: 80%;
            object-fit: contain;
        }

        .btn {
            display: inline-block;
            background: var(--primary-color);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--secondary-color);
            transform: translateX(-100%);
            transition: transform 0.3s;
            z-index: -1;
        }

        .btn:hover::before {
            transform: translateX(0);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Section Styles */
        section {
            padding: 4rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--primary-color);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: flex;
            gap: 2rem;
            align-items: center;
        }

        .about-text {
            flex: 1;
        }

        .about-img {
            flex: 1;
            text-align: center;
        }

        .about-img img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .about-img img:hover {
            transform: scale(1.03);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: var(--card-bg);
            padding: 2rem;
            border-radius: 10px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            transform: translateX(-100%);
            transition: transform 0.5s;
        }

        .skill-card:hover::before {
            transform: translateX(0);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .skill-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
            transition: var(--transition);
        }

        .skill-card:hover .skill-icon {
            transform: scale(1.1);
            color: var(--secondary-color);
        }

        .skill-card h3 {
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        /* Projects Section */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .project-img {
            height: 200px;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            position: relative;
            overflow: hidden;
        }

        .project-img::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                to right,
                transparent 0%,
                rgba(255, 255, 255, 0.3) 45%,
                rgba(255, 255, 255, 0.3) 55%,
                transparent 100%
            );
            transform: rotate(45deg) translateX(-100%);
            transition: transform 0.8s;
        }

        .project-card:hover .project-img::after {
            transform: rotate(45deg) translateX(100%);
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-info h3 {
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tag {
            background: var(--bg-color);
            color: var(--text-color);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            transition: var(--transition);
        }

        .tag:hover {
            background: var(--primary-color);
            color: white;
            transform: scale(1.05);
        }

        /* Videos Section */
        .videos-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .video-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .video-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            height: 0;
            overflow: hidden;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .video-info {
            padding: 1.5rem;
        }

        .video-info h3 {
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            font-size: 1.3rem;
        }

        .video-description {
            margin-bottom: 1rem;
            color: var(--text-color);
            opacity: 0.8;
        }

        .video-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.9rem;
            color: var(--text-color);
            opacity: 0.7;
        }

        .video-date {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .video-views {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        /* Video Instructions */
        .video-instructions {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            box-shadow: var(--shadow);
            border-left: 4px solid var(--primary-color);
        }

        .video-instructions h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        .video-instructions ul {
            padding-left: 1.5rem;
        }

        .video-instructions li {
            margin-bottom: 0.5rem;
        }

        .code-block {
            background: var(--bg-color);
            padding: 1rem;
            border-radius: 5px;
            font-family: monospace;
            margin: 1rem 0;
            overflow-x: auto;
        }

        /* Contact Section */
        .contact-container {
            display: flex;
            gap: 2rem;
        }

        .contact-form {
            flex: 2;
        }

        .contact-info {
            flex: 1;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            background: var(--card-bg);
            color: var(--text-color);
            transition: var(--transition);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
            padding: 1rem;
            border-radius: 8px;
            background: var(--bg-color);
            transition: var(--transition);
        }

        .contact-item:hover {
            transform: translateX(10px);
            background: var(--primary-color);
            color: white;
        }

        .contact-item:hover .contact-icon {
            color: white;
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-right: 1rem;
            width: 30px;
            transition: var(--transition);
        }

        /* Footer */
        footer {
            background: var(--card-bg);
            padding: 2rem 0;
            text-align: center;
            border-top: 1px solid rgba(0, 0, 0, 0.1);
        }

        .social-links {
            margin-bottom: 1.5rem;
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .social-links a {
            color: var(--text-color);
            font-size: 1.8rem;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background: var(--bg-color);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .social-links a::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--primary-color);
            transition: var(--transition);
            z-index: -1;
        }

        .social-links a:hover::before {
            width: 100%;
        }

        .social-links a:hover {
            color: white;
            transform: translateY(-5px) rotate(5deg);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Specific colors for each social media on hover */
        .social-links a[href*="github"]:hover::before {
            background: #333;
        }

        .social-links a[href*="youtube"]:hover::before {
            background: #FF0000;
        }

        .social-links a[href*="facebook"]:hover::before {
            background: #1877F2;
        }

        .social-links a[href*="instagram"]:hover::before {
            background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
        }

        .social-links a[href*="twitter"]:hover::before {
            background: #1DA1F2;
        }

        /* Scroll Progress Bar */
        .scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            z-index: 1000;
            transition: width 0.1s;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 1rem;
            }

            .nav-links {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }

            .nav-links li {
                margin: 0 0.5rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content {
                flex-direction: column;
            }

            .contact-container {
                flex-direction: column;
            }

            .section-title {
                font-size: 2rem;
            }

            .videos-container {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .profile-img-container {
                width: 150px;
                height: 150px;
            }

            .nav-links {
                flex-direction: column;
                align-items: center;
                gap: 0.5rem;
            }

            .nav-links li {
                margin: 0;
            }

            .social-links a {
                width: 40px;
                height: 40px;
                font-size: 1.5rem;
            }
        }

        /* Animation for elements appearing on scroll */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Ripple effect */
        .ripple {
            position: absolute;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.6);
            transform: scale(0);
            animation: ripple-animation 0.6s linear;
        }

        @keyframes ripple-animation {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Scroll Progress Bar -->
    <div class="scroll-progress" id="scrollProgress"></div>

    <!-- Moving Stars Background -->
    <div class="stars-bg">
        <div class="stars" id="stars"></div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo-container">
                    <img src="https://z-cdn-media.chatglm.cn/files/fd14c993-62bd-4522-8b32-cdda2406e9d6_acro%20logo.png?auth_key=1788877531-9c2b85b30db84af69acd6e890145fc07-0-f4871deff81ec58cdc012ccd2021d859" alt="Acro Coder Logo" class="logo-img">
                    <a href="#" class="logo">Acro Coder</a>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#videos">Videos</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <button class="theme-toggle" id="theme-toggle">
                    <i class="fas fa-moon"></i>
                </button>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="profile-img-container">
                    <img src="https://z-cdn-media.chatglm.cn/files/fd14c993-62bd-4522-8b32-cdda2406e9d6_acro%20logo.png?auth_key=1788877531-9c2b85b30db84af69acd6e890145fc07-0-f4871deff81ec58cdc012ccd2021d859" alt="Acro Coder Logo" class="profile-img">
                </div>
                <h1>Frontend Developer & Tech Enthusiast</h1>
                <p>I create beautiful, responsive websites and applications with modern technologies. Passionate about clean code and user experience.</p>
                <p class="typing-effect" id="typingText"></p>
                <a href="#projects" class="btn shining-effect">View My Work</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="fade-in">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Hello! I'm Acro Coder, a passionate frontend developer with a growing interest in backend technologies. I specialize in creating responsive, user-friendly websites and applications.</p>
                    <p>With a strong foundation in HTML, CSS, and JavaScript, I build modern web experiences that work seamlessly across all devices. I'm constantly learning and expanding my skill set to include more backend technologies.</p>
                    <p>When I'm not coding, you'll find me sharing my knowledge through motivational videos to inspire others in their tech journey.</p>
                </div>
                <div class="about-img">
                    <img src="https://via.placeholder.com/400" alt="Acro Coder">
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="fade-in">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-container">
                <div class="skill-card shining-effect">
                    <div class="skill-icon">
                        <i class="fab fa-html5"></i>
                    </div>
                    <h3>Frontend Development</h3>
                    <p>HTML5, CSS3, JavaScript (ES6+), React, Vue.js, Responsive Design, UI/UX Principles</p>
                </div>
                <div class="skill-card shining-effect">
                    <div class="skill-icon">
                        <i class="fas fa-server"></i>
                    </div>
                    <h3>Backend Basics</h3>
                    <p>Node.js, Express, REST APIs, Basic Database Concepts (MongoDB, MySQL), Authentication</p>
                </div>
                <div class="skill-card shining-effect">
                    <div class="skill-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <h3>Tools & Others</h3>
                    <p>Git, GitHub, VS Code, Figma, npm, Webpack, Basic DevOps, Agile Methodologies</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="fade-in">
        <div class="container">
            <h2 class="section-title">My Projects</h2>
            <div class="projects-container">
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <div class="project-info">
                        <h3>E-Commerce Website</h3>
                        <p>A fully responsive e-commerce platform with product listings, cart functionality, and checkout process.</p>
                        <div class="project-tags">
                            <span class="tag">HTML</span>
                            <span class="tag">CSS</span>
                            <span class="tag">JavaScript</span>
                            <span class="tag">React</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-tasks"></i>
                    </div>
                    <div class="project-info">
                        <h3>Task Management App</h3>
                        <p>A productivity app for managing tasks with drag-and-drop functionality and local storage.</p>
                        <div class="project-tags">
                            <span class="tag">Vue.js</span>
                            <span class="tag">CSS</span>
                            <span class="tag">Firebase</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-temperature-high"></i>
                    </div>
                    <div class="project-info">
                        <h3>Weather Dashboard</h3>
                        <p>A weather application that displays current weather and forecasts using a third-party API.</p>
                        <div class="project-tags">
                            <span class="tag">JavaScript</span>
                            <span class="tag">API</span>
                            <span class="tag">CSS</span>
                            <span class="tag">Node.js</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Videos Section -->
    <section id="videos" class="fade-in">
        <div class="container">
            <h2 class="section-title">Motivational Videos</h2>
            
            <!-- Video Instructions -->
            <div class="video-instructions">
                <h3><i class="fas fa-info-circle"></i> How to Add Your Videos</h3>
                <p>To add your own videos to this portfolio, follow these simple steps:</p>
                <ul>
                    <li>Upload your video to YouTube, Vimeo, or any video hosting platform</li>
                    <li>Get the embed code for your video</li>
                    <li>Replace the iframe src attribute in the video cards below with your video's embed URL</li>
                    <li>Update the video title, description, and metadata</li>
                </ul>
                <p>Example YouTube embed URL format:</p>
                <div class="code-block">
                    https://www.youtube.com/embed/YOUR_VIDEO_ID
                </div>
                <p>Example Vimeo embed URL format:</p>
                <div class="code-block">
                    https://player.vimeo.com/video/YOUR_VIDEO_ID
                </div>
            </div>
            
            <div class="videos-container">
                <!-- Video 1 -->
                <div class="video-card">
                    <div class="video-wrapper">
                        <!-- Replace the src attribute with your video embed URL -->
                        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Overcoming Imposter Syndrome" allowfullscreen></iframe>
                    </div>
                    <div class="video-info">
                        <h3>Overcoming Imposter Syndrome</h3>
                        <p class="video-description">How I dealt with imposter syndrome as a new developer and tips to help you overcome it too.</p>
                        <div class="video-meta">
                            <div class="video-date">
                                <i class="far fa-calendar"></i>
                                <span>Oct 15, 2023</span>
                            </div>
                            <div class="video-views">
                                <i class="far fa-eye"></i>
                                <span>1.2K views</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Video 2 -->
                <div class="video-card">
                    <div class="video-wrapper">
                        <!-- Replace the src attribute with your video embed URL -->
                        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="My Journey to Frontend Development" allowfullscreen></iframe>
                    </div>
                    <div class="video-info">
                        <h3>My Journey to Frontend Development</h3>
                        <p class="video-description">Sharing my personal story of how I transitioned into tech and the challenges I faced along the way.</p>
                        <div class="video-meta">
                            <div class="video-date">
                                <i class="far fa-calendar"></i>
                                <span>Sep 28, 2023</span>
                            </div>
                            <div class="video-views">
                                <i class="far fa-eye"></i>
                                <span>856 views</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Video 3 -->
                <div class="video-card">
                    <div class="video-wrapper">
                        <!-- Replace the src attribute with your video embed URL -->
                        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="5 Tips for Learning to Code" allowfullscreen></iframe>
                    </div>
                    <div class="video-info">
                        <h3>5 Tips for Learning to Code</h3>
                        <p class="video-description">Practical advice for anyone starting their coding journey based on my own experience.</p>
                        <div class="video-meta">
                            <div class="video-date">
                                <i class="far fa-calendar"></i>
                                <span>Sep 10, 2023</span>
                            </div>
                            <div class="video-views">
                                <i class="far fa-eye"></i>
                                <span>2.4K views</span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="video-card">
                    <div class="video-wrapper">
                        <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Building Your First Portfolio" allowfullscreen></iframe>
                    </div>
                    <div class="video-info">
                        <h3>Building Your First Portfolio</h3>
                        <p class="video-description">Step-by-step guide to creating an impressive developer portfolio that showcases your skills.</p>
                        <div class="video-meta">
                            <div class="video-date">
                                <i class="far fa-calendar"></i>
                                <span>Aug 22, 2023</span>
                            </div>
                            <div class="video-views">
                                <i class="far fa-eye"></i>
                                <span>3.1K views</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="fade-in">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-container">
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn shining-effect">Send Message</button>
                    </form>
                </div>
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h4>Email</h4>
                            <p>acrocoder@example.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h4>Location</h4>
                            <p>Rubavu-Gisenyi, Rwanda</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <h4>Phone</h4>
                            <p>+250 798359897</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="https://github.com/acrocoder" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
                <a href="https://youtube.com/@acrocoder" target="_blank" title="YouTube"><i class="fab fa-youtube"></i></a>
                <a href="https://facebook.com/acrocoder" target="_blank" title="Facebook"><i class="fab fa-facebook"></i></a>
                <a href="https://instagram.com/acrocoder" target="_blank" title="Instagram"><i class="fab fa-instagram"></i></a>
                <a href="https://twitter.com/acrocoder" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
            </div>
            <p>&copy; 2023 Acro Coder. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Create Moving Stars Background
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const starsCount = 200;
            
            for (let i = 0; i < starsCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Randomly decide if this star should shine
                if (Math.random() > 0.8) {
                    star.classList.add('shining');
                }
                
                // Random size for stars
                const size = Math.random() * 3;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                // Random position
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                
                // Random opacity
                star.style.opacity = Math.random();
                
                // Random animation duration
                const duration = 50 + Math.random() * 100;
                star.style.animationDuration = `${duration}s`;
                
                // Random animation delay
                star.style.animationDelay = `${Math.random() * 5}s`;
                
                starsContainer.appendChild(star);
            }
        }
        
        // Initialize stars when page loads
        window.addEventListener('load', createStars);

        // Theme Toggle Functionality
        const themeToggle = document.getElementById('theme-toggle');
        const body = document.body;
        const themeIcon = themeToggle.querySelector('i');

        // Check for saved theme preference or default to light mode
        const currentTheme = localStorage.getItem('theme') || 'light';
        body.setAttribute('data-theme', currentTheme);
        updateThemeIcon(currentTheme);

        themeToggle.addEventListener('click', () => {
            const theme = body.getAttribute('data-theme');
            const newTheme = theme === 'light' ? 'dark' : 'light';
            
            body.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
            updateThemeIcon(newTheme);
        });

        function updateThemeIcon(theme) {
            if (theme === 'dark') {
                themeIcon.classList.remove('fa-moon');
                themeIcon.classList.add('fa-sun');
            } else {
                themeIcon.classList.remove('fa-sun');
                themeIcon.classList.add('fa-moon');
            }
        }

        // Smooth Scrolling for Navigation Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Form Submission
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            // Here you would normally send the form data to a server
            // For this example, we'll just show a success message
            alert(`Thank you, ${name}! Your message has been sent successfully.`);
            
            // Reset the form
            this.reset();
        });

        // Typing Effect
        const typingText = document.getElementById('typingText');
        const phrases = [
            "Turning ideas into interactive experiences.",
            "Crafting beautiful user interfaces.",
            "Building responsive web applications.",
            "Always learning, always growing."
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        let typingSpeed = 100;

        function typeEffect() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingText.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
                typingSpeed = 50;
            } else {
                typingText.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
                typingSpeed = 100;
            }
            
            if (!isDeleting && charIndex === currentPhrase.length) {
                isDeleting = true;
                typingSpeed = 2000; // Pause at end
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                typingSpeed = 500; // Pause before typing next phrase
            }
            
            setTimeout(typeEffect, typingSpeed);
        }

        // Start typing effect when page loads
        window.addEventListener('load', () => {
            setTimeout(typeEffect, 1000);
        });

        // Scroll Progress Bar
        window.addEventListener('scroll', () => {
            const scrollProgress = document.getElementById('scrollProgress');
            const scrollHeight = document.documentElement.scrollHeight - window.innerHeight;
            const scrolled = (window.scrollY / scrollHeight) * 100;
            scrollProgress.style.width = `${scrolled}%`;
        });

        // Fade in animation on scroll
        const fadeElements = document.querySelectorAll('.fade-in');
        
        const fadeInOnScroll = () => {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible');
                }
            });
        };
        
        window.addEventListener('scroll', fadeInOnScroll);
        window.addEventListener('load', fadeInOnScroll);

        // Parallax effect for stars background
        window.addEventListener('scroll', () => {
            const scrolled = window.scrollY;
            const stars = document.querySelector('.stars');
            stars.style.transform = `translateY(${scrolled * 0.2}px)`;
        });

        // Add interactive hover effect to project cards
        const projectCards = document.querySelectorAll('.project-card');
        
        projectCards.forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Add interactive hover effect to video cards
        const videoCards = document.querySelectorAll('.video-card');
        
        videoCards.forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Add ripple effect to buttons
        const buttons = document.querySelectorAll('.btn');
        
        buttons.forEach(button => {
            button.addEventListener('click', function(e) {
                const ripple = document.createElement('span');
                const rect = this.getBoundingClientRect();
                const size = Math.max(rect.width, rect.height);
                const x = e.clientX - rect.left - size / 2;
                const y = e.clientY - rect.top - size / 2;
                
                ripple.style.width = ripple.style.height = size + 'px';
                ripple.style.left = x + 'px';
                ripple.style.top = y + 'px';
                ripple.classList.add('ripple');
                
                this.appendChild(ripple);
                
                setTimeout(() => {
                    ripple.remove();
                }, 600);
            });
        });
    </script>
</body>
</html>
