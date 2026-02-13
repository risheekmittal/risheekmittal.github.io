<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rishh - Mobile Engineer</title>
    
    <!-- CDN Libraries -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://unpkg.com/@studio-freight/lenis@1.0.42/dist/lenis.min.js"></script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;900&family=Rajdhani:wght@300;400;500;600;700&family=Syne:wght@400;500;600;700;800&display=swap');
        
        :root {
            --primary-bg: #0a0a0f;
            --secondary-bg: #12121a;
            --accent-blue: #00f0ff;
            --accent-purple: #b830ff;
            --accent-pink: #ff2e97;
            --accent-cyan: #00ffaa;
            --accent-yellow: #ffeb3b;
            --text-primary: #ffffff;
            --text-secondary: #a0a0b8;
            --glass-bg: rgba(255, 255, 255, 0.03);
            --glass-border: rgba(255, 255, 255, 0.1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Rajdhani', sans-serif;
            background: var(--primary-bg);
            color: var(--text-primary);
            overflow-x: hidden;
        }
        
        /* Custom Cursor */
        .cursor {
            width: 20px;
            height: 20px;
            border: 2px solid var(--accent-cyan);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 10000;
            transition: all 0.15s ease;
            mix-blend-mode: difference;
            box-shadow: 0 0 20px var(--accent-cyan);
            transform: translate(-50%, -50%);
        }
        
        .cursor-trail {
            width: 8px;
            height: 8px;
            background: var(--accent-blue);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            box-shadow: 0 0 30px var(--accent-blue);
            transform: translate(-50%, -50%);
        }
        
        .cursor.hover {
            width: 60px;
            height: 60px;
            background: rgba(0, 240, 255, 0.2);
            border-color: var(--accent-purple);
        }
        
        .cursor-glow {
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(0, 240, 255, 0.3) 0%, transparent 70%);
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            filter: blur(30px);
            transform: translate(-50%, -50%);
        }
        
        /* Scanlines */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 5;
            pointer-events: none;
            background: repeating-linear-gradient(
                0deg,
                rgba(0, 0, 0, 0.1),
                rgba(0, 0, 0, 0.1) 1px,
                transparent 1px,
                transparent 2px
            );
            animation: scanlineMove 8s linear infinite;
        }
        
        @keyframes scanlineMove {
            0% { transform: translateY(0); }
            100% { transform: translateY(100px); }
        }
        
        /* Grid Background */
        .grid-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background-image: 
                linear-gradient(rgba(0, 240, 255, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 240, 255, 0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: gridPulse 4s ease-in-out infinite;
        }
        
        @keyframes gridPulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.6; }
        }
        
        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background: 
                radial-gradient(circle at 20% 50%, rgba(184, 48, 255, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(0, 240, 255, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(255, 46, 151, 0.1) 0%, transparent 50%);
            animation: bgShift 20s ease-in-out infinite alternate;
        }
        
        @keyframes bgShift {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(50px, 30px) scale(1.1); }
        }
        
        /* Light Beams */
        .light-beam {
            position: fixed;
            width: 2px;
            height: 100%;
            background: linear-gradient(to bottom, transparent, var(--accent-cyan), transparent);
            top: 0;
            opacity: 0.2;
            animation: beamScan 6s ease-in-out infinite;
            pointer-events: none;
            z-index: 3;
        }
        
        .light-beam:nth-child(1) { left: 20%; }
        .light-beam:nth-child(2) { left: 50%; animation-delay: -2s; }
        .light-beam:nth-child(3) { left: 80%; animation-delay: -4s; }
        
        @keyframes beamScan {
            0%, 100% { opacity: 0.1; transform: translateX(0); }
            50% { opacity: 0.4; transform: translateX(100px); }
        }
        
        .noise {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            opacity: 0.05;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
            pointer-events: none;
            animation: grain 8s steps(10) infinite;
        }
        
        @keyframes grain {
            0%, 100% { transform: translate(0, 0); }
            10% { transform: translate(-5%, -10%); }
            30% { transform: translate(3%, -15%); }
            50% { transform: translate(12%, 9%); }
            70% { transform: translate(9%, 4%); }
            90% { transform: translate(-1%, 7%); }
        }
        
        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
        }
        
        /* Main Container */
        .main-container {
            position: relative;
            z-index: 2;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero-title {
            font-family: 'Syne', sans-serif;
            font-size: clamp(80px, 15vw, 220px);
            font-weight: 800;
            background: linear-gradient(135deg, var(--accent-cyan) 0%, var(--accent-blue) 30%, var(--accent-purple) 60%, var(--accent-pink) 100%);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            letter-spacing: -0.02em;
            text-transform: uppercase;
            filter: drop-shadow(0 0 60px rgba(0, 240, 255, 0.8));
            animation: titlePulse 3s ease-in-out infinite;
        }
        
        @keyframes titlePulse {
            0%, 100% { filter: drop-shadow(0 0 60px rgba(0, 240, 255, 0.8)); }
            50% { filter: drop-shadow(0 0 100px rgba(184, 48, 255, 0.9)); }
        }
        
        .hero-subtitle {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(16px, 2.5vw, 30px);
            font-weight: 300;
            letter-spacing: 0.3em;
            margin-top: 20px;
            color: var(--text-secondary);
            text-transform: uppercase;
            animation: subtitleGlow 2s ease-in-out infinite alternate;
        }
        
        @keyframes subtitleGlow {
            from { text-shadow: 0 0 10px rgba(0, 240, 255, 0.5); }
            to { text-shadow: 0 0 20px rgba(184, 48, 255, 0.8); }
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 50px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            animation: bounce 2s ease-in-out infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(-10px); }
        }
        
        .scroll-line {
            width: 2px;
            height: 60px;
            background: linear-gradient(to bottom, var(--accent-cyan), transparent);
            position: relative;
            overflow: hidden;
        }
        
        .scroll-line::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 20px;
            background: var(--accent-blue);
            box-shadow: 0 0 20px var(--accent-blue);
            animation: scrollMove 2s ease-in-out infinite;
        }
        
        @keyframes scrollMove {
            0% { transform: translateY(-20px); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateY(60px); opacity: 0; }
        }
        
        .scroll-text {
            font-family: 'Orbitron', sans-serif;
            font-size: 12px;
            letter-spacing: 0.2em;
            color: var(--text-secondary);
        }
        
        /* Section Styles */
        section {
            min-height: 100vh;
            padding: 100px 5%;
            position: relative;
        }
        
        .section-title {
            font-family: 'Syne', sans-serif;
            font-size: clamp(50px, 8vw, 100px);
            font-weight: 700;
            margin-bottom: 60px;
            background: linear-gradient(135deg, var(--accent-blue), var(--accent-purple));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-cyan), transparent);
        }
        
        /* Glass Card */
        .glass-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 40px;
            position: relative;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .glass-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }
        
        .glass-card:hover::before {
            left: 100%;
        }
        
        .glass-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-cyan);
            box-shadow: 0 20px 60px rgba(0, 240, 255, 0.3);
        }
        
        /* About Section */
        .about-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            position: relative;
            z-index: 1;
        }
        
        .about-text h3 {
            font-family: 'Syne', sans-serif;
            font-size: 32px;
            margin-bottom: 20px;
            color: var(--accent-cyan);
        }
        
        .about-text p {
            font-size: 18px;
            line-height: 1.8;
            color: var(--text-secondary);
            margin-bottom: 20px;
        }
        
        .about-image {
            position: relative;
            perspective: 1000px;
        }
        
        .avatar-container {
            width: 100%;
            aspect-ratio: 1;
            background: linear-gradient(135deg, var(--accent-purple), var(--accent-blue));
            border-radius: 20px;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            transition: transform 0.3s ease;
        }
        
        .avatar-container::before {
            content: 'RISHH';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-family: 'Syne', sans-serif;
            font-size: 80px;
            font-weight: 900;
            color: rgba(255, 255, 255, 0.1);
            letter-spacing: 0.1em;
        }
        
        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 30px;
            margin-top: 60px;
            position: relative;
            z-index: 1;
        }
        
        .skill-item {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        
        .skill-item::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: radial-gradient(circle, var(--accent-cyan), transparent);
            transform: translate(-50%, -50%);
            transition: width 0.4s, height 0.4s;
            opacity: 0.3;
        }
        
        .skill-item:hover::before {
            width: 300px;
            height: 300px;
        }
        
        .skill-item:hover {
            transform: scale(1.05);
            border-color: var(--accent-cyan);
            box-shadow: 0 10px 40px rgba(0, 240, 255, 0.4);
        }
        
        .skill-icon {
            font-size: 48px;
            margin-bottom: 15px;
            display: block;
        }
        
        .skill-name {
            font-family: 'Orbitron', sans-serif;
            font-size: 16px;
            font-weight: 600;
            color: var(--text-primary);
            position: relative;
            z-index: 1;
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 60px;
            position: relative;
            z-index: 1;
        }
        
        .project-card {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            overflow: hidden;
            position: relative;
            transform-style: preserve-3d;
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--accent-purple), var(--accent-blue));
            opacity: 0;
            transition: opacity 0.4s;
            z-index: 0;
        }
        
        .project-card:hover::before {
            opacity: 0.1;
        }
        
        .project-card:hover {
            transform: rotateY(5deg) rotateX(5deg) scale(1.02);
            box-shadow: 0 30px 80px rgba(184, 48, 255, 0.4);
            border-color: var(--accent-purple);
        }
        
        .project-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #1a1a2e, #16213e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            position: relative;
            overflow: hidden;
        }
        
        .project-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%) rotate(45deg); }
            100% { transform: translateX(100%) rotate(45deg); }
        }
        
        .project-content {
            padding: 30px;
            position: relative;
            z-index: 1;
        }
        
        .project-title {
            font-family: 'Syne', sans-serif;
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--accent-cyan);
        }
        
        .project-description {
            font-size: 16px;
            color: var(--text-secondary);
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .tag {
            padding: 5px 15px;
            background: rgba(0, 240, 255, 0.1);
            border: 1px solid var(--accent-cyan);
            border-radius: 20px;
            font-size: 12px;
            font-family: 'Orbitron', sans-serif;
            color: var(--accent-cyan);
        }
        
        /* Experience Timeline */
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 60px auto;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, var(--accent-cyan), var(--accent-purple));
            transform: translateX(-50%);
        }
        
        .timeline-item {
            position: relative;
            margin-bottom: 80px;
            width: 45%;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
            text-align: right;
        }
        
        .timeline-item:nth-child(even) {
            left: 55%;
        }
        
        .timeline-marker {
            position: absolute;
            top: 0;
            width: 20px;
            height: 20px;
            background: var(--accent-cyan);
            border-radius: 50%;
            box-shadow: 0 0 20px var(--accent-cyan);
            animation: pulse 2s ease-in-out infinite;
        }
        
        .timeline-item:nth-child(odd) .timeline-marker {
            right: -56%;
        }
        
        .timeline-item:nth-child(even) .timeline-marker {
            left: -56%;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.3); opacity: 0.7; }
        }
        
        .timeline-content {
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 15px;
            padding: 30px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .timeline-content:hover {
            transform: scale(1.05);
            border-color: var(--accent-purple);
            box-shadow: 0 20px 60px rgba(184, 48, 255, 0.3);
        }
        
        .timeline-date {
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            color: var(--accent-cyan);
            margin-bottom: 10px;
        }
        
        .timeline-title {
            font-family: 'Syne', sans-serif;
            font-size: 22px;
            font-weight: 700;
            margin-bottom: 10px;
        }
        
        .timeline-description {
            font-size: 16px;
            color: var(--text-secondary);
            line-height: 1.6;
        }
        
        /* Contact Section */
        .contact-container {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }
        
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }
        
        .form-group {
            position: relative;
        }
        
        .form-label {
            font-family: 'Orbitron', sans-serif;
            font-size: 14px;
            color: var(--accent-cyan);
            margin-bottom: 10px;
            display: block;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }
        
        .form-input,
        .form-textarea {
            width: 100%;
            padding: 15px 20px;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 10px;
            color: var(--text-primary);
            font-family: 'Rajdhani', sans-serif;
            font-size: 16px;
            transition: all 0.3s ease;
        }
        
        .form-input:focus,
        .form-textarea:focus {
            outline: none;
            border-color: var(--accent-cyan);
            box-shadow: 0 0 30px rgba(0, 240, 255, 0.3);
            background: rgba(0, 240, 255, 0.05);
        }
        
        .form-textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .submit-btn {
            padding: 18px 50px;
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-blue));
            border: none;
            border-radius: 50px;
            color: var(--primary-bg);
            font-family: 'Orbitron', sans-serif;
            font-size: 16px;
            font-weight: 700;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            align-self: center;
        }
        
        .submit-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.5s, height 0.5s;
        }
        
        .submit-btn:hover::before {
            width: 300px;
            height: 300px;
        }
        
        .submit-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 40px rgba(0, 240, 255, 0.5);
        }
        
        /* Footer */
        footer {
            padding: 60px 5%;
            background: rgba(10, 10, 15, 0.9);
            backdrop-filter: blur(20px);
            border-top: 1px solid var(--glass-border);
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .footer-logo {
            font-family: 'Syne', sans-serif;
            font-size: 36px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--accent-cyan), var(--accent-purple));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .social-links {
            display: flex;
            gap: 30px;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            background: var(--glass-bg);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-cyan);
            font-size: 20px;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background: var(--accent-cyan);
            color: var(--primary-bg);
            transform: translateY(-5px) rotate(360deg);
            box-shadow: 0 10px 30px rgba(0, 240, 255, 0.5);
        }
        
        .copyright {
            text-align: center;
            margin-top: 40px;
            color: var(--text-secondary);
            font-size: 14px;
        }
        
        /* Floating Elements */
        .floating-shape {
            position: absolute;
            border-radius: 50%;
            filter: blur(40px);
            opacity: 0.3;
            animation: float 20s ease-in-out infinite;
            pointer-events: none;
        }
        
        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(100px, -100px) rotate(90deg); }
            50% { transform: translate(200px, 0) rotate(180deg); }
            75% { transform: translate(100px, 100px) rotate(270deg); }
        }
        
        /* Glitch Effect */
        .glitch {
            position: relative;
            animation: glitch-skew 1s infinite linear alternate-reverse;
        }
        
        @keyframes glitch-skew {
            0% { transform: skew(0deg); }
            10% { transform: skew(-2deg); }
            20% { transform: skew(2deg); }
            30% { transform: skew(0deg); }
            40% { transform: skew(1deg); }
            50% { transform: skew(0deg); }
            60% { transform: skew(-1deg); }
            70% { transform: skew(2deg); }
            80% { transform: skew(-2deg); }
            90% { transform: skew(1deg); }
            100% { transform: skew(0deg); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .about-container {
                grid-template-columns: 1fr;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item {
                width: 100%;
                left: 60px !important;
                text-align: left !important;
            }
            
            .timeline-item .timeline-marker {
                left: -70px !important;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Custom Cursor -->
    <div class="cursor"></div>
    <div class="cursor-trail"></div>
    <div class="cursor-glow"></div>
    
    <!-- Scanlines -->
    <div class="scanlines"></div>
    
    <!-- Grid Background -->
    <div class="grid-background"></div>
    
    <!-- Background Elements -->
    <div class="bg-animation"></div>
    <div class="noise"></div>
    
    <!-- Light Beams -->
    <div class="light-beam"></div>
    <div class="light-beam"></div>
    <div class="light-beam"></div>
    
    <div id="canvas-container"></div>
    
    <!-- Floating Shapes -->
    <div class="floating-shape" style="width: 300px; height: 300px; background: var(--accent-purple); top: 10%; left: 5%;"></div>
    <div class="floating-shape" style="width: 400px; height: 400px; background: var(--accent-blue); top: 60%; right: 10%; animation-delay: -5s;"></div>
    <div class="floating-shape" style="width: 250px; height: 250px; background: var(--accent-cyan); bottom: 20%; left: 50%; animation-delay: -10s;"></div>
    <div class="floating-shape" style="width: 350px; height: 350px; background: var(--accent-pink); top: 40%; right: 30%; animation-delay: -7s;"></div>
    <div class="floating-shape" style="width: 200px; height: 200px; background: var(--accent-yellow); bottom: 40%; left: 20%; animation-delay: -12s;"></div>
    
    <div class="main-container">
        <!-- Hero Section -->
        <section class="hero">
            <h1 class="hero-title glitch">RISHH</h1>
            <p class="hero-subtitle">MOBILE ENGINEER • REACT NATIVE • CROSS-PLATFORM</p>
            
            <div class="scroll-indicator">
                <div class="scroll-line"></div>
                <span class="scroll-text">SCROLL</span>
            </div>
        </section>
        
        <!-- About Section -->
        <section id="about">
            <h2 class="section-title">About Me</h2>
            <div class="about-container">
                <div class="about-text glass-card">
                    <h3>Mid-Level Mobile Engineer</h3>
                    <p>With nearly 4 years of hands-on experience, I specialize in delivering high-performance mobile solutions across iOS, Android, and cross-platform frameworks. My expertise spans React Native, Flutter, Native iOS (Swift/SwiftUI), and Android (Kotlin).</p>
                    <p>Currently at Adglobal360, I've spearheaded critical stability improvements for production apps serving 10K+ daily active users, increasing crash-free sessions from 43% to 77% while reducing support tickets by 98%.</p>
                    <p>I'm passionate about building scalable architectures, hardening security vulnerabilities, and delivering polished user experiences that combine technical excellence with real business impact.</p>
                </div>
                <div class="about-image">
                    <div class="avatar-container"></div>
                </div>
            </div>
        </section>
        
        <!-- Skills Section -->
        <section id="skills">
            <h2 class="section-title">Tech Stack</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-icon">📱</span>
                    <div class="skill-name">React Native</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🦋</span>
                    <div class="skill-name">Flutter</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🍎</span>
                    <div class="skill-name">iOS (Swift)</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🤖</span>
                    <div class="skill-name">Android (Kotlin)</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚛️</span>
                    <div class="skill-name">React</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚡</span>
                    <div class="skill-name">TypeScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🗄️</span>
                    <div class="skill-name">SQLite</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔥</span>
                    <div class="skill-name">Firebase</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔐</span>
                    <div class="skill-name">Security (VAPT)</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🎯</span>
                    <div class="skill-name">MVVM/Clean Arch</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚙️</span>
                    <div class="skill-name">Jenkins/CI-CD</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">📊</span>
                    <div class="skill-name">SonarQube</div>
                </div>
            </div>
        </section>
        
        <!-- Projects Section -->
        <section id="projects">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">🚗</div>
                    <div class="project-content">
                        <h3 class="project-title">Maruti Suzuki 4-Wheeler Service App</h3>
                        <p class="project-description">Production app serving 10K+ DAU. Increased crash-free sessions from 43% to 77%, reduced support tickets from 300 to under 5 weekly.</p>
                        <div class="project-tags">
                            <span class="tag">React Native</span>
                            <span class="tag">Performance</span>
                            <span class="tag">Security</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🏍️</div>
                    <div class="project-content">
                        <h3 class="project-title">Suzuki Global 2-Wheeler Service App</h3>
                        <p class="project-description">Delivered from concept to production in 6 weeks with a lean 2-person team. Global deployment across multiple regions.</p>
                        <div class="project-tags">
                            <span class="tag">React Native</span>
                            <span class="tag">Fast Delivery</span>
                            <span class="tag">Clean Arch</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">💰</div>
                    <div class="project-content">
                        <h3 class="project-title">Vitta - AI Expense Tracker</h3>
                        <p class="project-description">Solo-developed FinTech app with NLP interface. Integrated HuggingFace ML models achieving 97% categorization accuracy.</p>
                        <div class="project-tags">
                            <span class="tag">React Native</span>
                            <span class="tag">ML/AI</span>
                            <span class="tag">RevenueCat</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🚕</div>
                    <div class="project-content">
                        <h3 class="project-title">Maruti Pick & Drop App</h3>
                        <p class="project-description">Overhauled 50,000+ lines legacy codebase ensuring 100% compliance with SonarQube and Snyk security standards.</p>
                        <div class="project-tags">
                            <span class="tag">Code Quality</span>
                            <span class="tag">Refactoring</span>
                            <span class="tag">Security</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🔐</div>
                    <div class="project-content">
                        <h3 class="project-title">Security Hardening Projects</h3>
                        <p class="project-description">Mitigated 14/14 critical VAPT vulnerabilities implementing Apple Keychain, Android Keystore, and SSL Pinning.</p>
                        <div class="project-tags">
                            <span class="tag">Security</span>
                            <span class="tag">VAPT</span>
                            <span class="tag">Encryption</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">⚙️</div>
                    <div class="project-content">
                        <h3 class="project-title">CI/CD & QA Automation</h3>
                        <p class="project-description">Developed automation scripts and negative test scenarios, reducing testing time by 25% while maintaining stability.</p>
                        <div class="project-tags">
                            <span class="tag">Fastlane</span>
                            <span class="tag">Jenkins</span>
                            <span class="tag">Automation</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Experience Section -->
        <section id="experience">
            <h2 class="section-title">Experience</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-marker"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">JUN 2022 - PRESENT</div>
                        <h3 class="timeline-title">Software Engineer @ Adglobal360</h3>
                        <p class="timeline-description">Leading mobile development for Maruti Suzuki and Suzuki Global apps. Stabilized production apps serving 10K+ DAU, reduced crashes by 34%, and deployed critical fixes within 2-hour SLA windows.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-marker"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">2024 - 2025</div>
                        <h3 class="timeline-title">Personal Project: Vitta AI Expense Tracker</h3>
                        <p class="timeline-description">Solo-developed FinTech app with NLP interface and ML-powered categorization. Integrated RevenueCat for subscription management and achieved 97% accuracy in transaction classification.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-marker"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">2023</div>
                        <h3 class="timeline-title">Mobile Security & Performance Optimization</h3>
                        <p class="timeline-description">Hardened applications against VAPT vulnerabilities by implementing Apple Keychain, Android Keystore, and SSL Pinning. Achieved zero critical security issues post-assessment.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-marker"></div>
                    <div class="timeline-content">
                        <div class="timeline-date">2018 - 2022</div>
                        <h3 class="timeline-title">B.Tech Computer Science @ RTU Rajasthan</h3>
                        <p class="timeline-description">Completed Bachelor of Technology in Computer Science from Rajasthan Technical University. Built foundation in software engineering, algorithms, and mobile development.</p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Contact Section -->
        <section id="contact">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-container">
                <div style="text-align: center; margin-bottom: 40px;">
                    <p style="font-size: 18px; color: var(--text-secondary); margin-bottom: 15px;">
                        📧 <a href="mailto:mittal.risheek@gmail.com" style="color: var(--accent-cyan); text-decoration: none;">mittal.risheek@gmail.com</a>
                    </p>
                    <p style="font-size: 18px; color: var(--text-secondary); margin-bottom: 15px;">
                        📱 <a href="tel:+917568544374" style="color: var(--accent-cyan); text-decoration: none;">+91-7568544374</a>
                    </p>
                    <p style="font-size: 18px; color: var(--text-secondary);">
                        🔗 <a href="https://linkedin.com/in/risheek" style="color: var(--accent-cyan); text-decoration: none;" target="_blank">linkedin.com/in/risheek</a>
                    </p>
                </div>
                <form class="contact-form glass-card">
                    <div class="form-group">
                        <label class="form-label" for="name">Name</label>
                        <input class="form-input" type="text" id="name" name="name" required>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label" for="email">Email</label>
                        <input class="form-input" type="email" id="email" name="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label class="form-label" for="message">Message</label>
                        <textarea class="form-textarea" id="message" name="message" required></textarea>
                    </div>
                    
                    <button class="submit-btn" type="submit">Send Message</button>
                </form>
            </div>
        </section>
        
        <!-- Footer -->
        <footer>
            <div class="footer-content">
                <div class="footer-logo">RISHH</div>
                <div class="social-links">
                    <a href="https://linkedin.com/in/risheek" class="social-link" title="LinkedIn">in</a>
                    <a href="https://github.com/risheekmittal" class="social-link" title="GitHub">gh</a>
                    <a href="mailto:mittal.risheek@gmail.com" class="social-link" title="Email">@</a>
                    <a href="tel:+917568544374" class="social-link" title="Phone">☎</a>
                </div>
            </div>
            <div class="copyright">
                © 2026 Risheek Mittal • React Native Developer • Cross-Platform Mobile Engineer
            </div>
        </footer>
    </div>
    
    <script>
        // Custom Cursor
        const cursor = document.querySelector('.cursor');
        const cursorTrail = document.querySelector('.cursor-trail');
        const cursorGlow = document.querySelector('.cursor-glow');
        let mouseX = 0, mouseY = 0;
        let cursorX = 0, cursorY = 0;
        let trailX = 0, trailY = 0;
        let glowX = 0, glowY = 0;
        
        document.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });
        
        function animateCursor() {
            cursorX += (mouseX - cursorX) * 0.2;
            cursorY += (mouseY - cursorY) * 0.2;
            trailX += (mouseX - trailX) * 0.1;
            trailY += (mouseY - trailY) * 0.1;
            glowX += (mouseX - glowX) * 0.05;
            glowY += (mouseY - glowY) * 0.05;
            
            cursor.style.left = cursorX + 'px';
            cursor.style.top = cursorY + 'px';
            cursorTrail.style.left = trailX + 'px';
            cursorTrail.style.top = trailY + 'px';
            cursorGlow.style.left = glowX + 'px';
            cursorGlow.style.top = glowY + 'px';
            
            requestAnimationFrame(animateCursor);
        }
        animateCursor();
        
        // Cursor Hover Effects
        const interactiveElements = document.querySelectorAll('a, button, .glass-card, .skill-item, .project-card, .timeline-content');
        interactiveElements.forEach(el => {
            el.addEventListener('mouseenter', () => cursor.classList.add('hover'));
            el.addEventListener('mouseleave', () => cursor.classList.remove('hover'));
        });
        
        // Three.js Background
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
        
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.getElementById('canvas-container').appendChild(renderer.domElement);
        
        // Create particle system
        const particlesGeometry = new THREE.BufferGeometry();
        const particlesCount = 3000;
        const posArray = new Float32Array(particlesCount * 3);
        
        for(let i = 0; i < particlesCount * 3; i++) {
            posArray[i] = (Math.random() - 0.5) * 100;
        }
        
        particlesGeometry.setAttribute('position', new THREE.BufferAttribute(posArray, 3));
        
        const particlesMaterial = new THREE.PointsMaterial({
            size: 0.03,
            color: 0x00f0ff,
            transparent: true,
            opacity: 0.6,
            blending: THREE.AdditiveBlending
        });
        
        const particlesMesh = new THREE.Points(particlesGeometry, particlesMaterial);
        scene.add(particlesMesh);
        
        // Add geometric shapes
        const geometry = new THREE.TorusGeometry(3, 0.5, 16, 100);
        const material = new THREE.MeshBasicMaterial({
            color: 0xb830ff,
            wireframe: true,
            transparent: true,
            opacity: 0.2
        });
        const torus = new THREE.Mesh(geometry, material);
        scene.add(torus);
        
        const sphereGeometry = new THREE.SphereGeometry(2, 32, 32);
        const sphereMaterial = new THREE.MeshBasicMaterial({
            color: 0x00f0ff,
            wireframe: true,
            transparent: true,
            opacity: 0.15
        });
        const sphere = new THREE.Mesh(sphereGeometry, sphereMaterial);
        sphere.position.set(-5, 2, -5);
        scene.add(sphere);
        
        // Add octahedron
        const octaGeometry = new THREE.OctahedronGeometry(1.5);
        const octaMaterial = new THREE.MeshBasicMaterial({
            color: 0xff2e97,
            wireframe: true,
            transparent: true,
            opacity: 0.2
        });
        const octa = new THREE.Mesh(octaGeometry, octaMaterial);
        octa.position.set(4, -3, -6);
        scene.add(octa);
        
        camera.position.z = 10;
        
        let mouseXThree = 0;
        let mouseYThree = 0;
        
        document.addEventListener('mousemove', (event) => {
            mouseXThree = (event.clientX / window.innerWidth) * 2 - 1;
            mouseYThree = -(event.clientY / window.innerHeight) * 2 + 1;
        });
        
        function animateThree() {
            requestAnimationFrame(animateThree);
            
            particlesMesh.rotation.y += 0.002;
            particlesMesh.rotation.x += 0.001;
            
            torus.rotation.x += 0.01;
            torus.rotation.y += 0.005;
            
            sphere.rotation.y += 0.003;
            
            octa.rotation.x += 0.015;
            octa.rotation.z += 0.01;
            
            camera.position.x += (mouseXThree * 2 - camera.position.x) * 0.05;
            camera.position.y += (mouseYThree * 2 - camera.position.y) * 0.05;
            
            renderer.render(scene, camera);
        }
        animateThree();
        
        // Smooth Scroll with Lenis
        let lenis;
        
        if (typeof Lenis !== 'undefined') {
            lenis = new Lenis({
                duration: 1.2,
                easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
                smooth: true,
                smoothTouch: false,
            });
            
            function raf(time) {
                lenis.raf(time);
                requestAnimationFrame(raf);
            }
            requestAnimationFrame(raf);
        } else {
            document.documentElement.style.scrollBehavior = 'smooth';
        }
        
        // GSAP Animations
        gsap.registerPlugin(ScrollTrigger);
        
        // Hero Animation
        gsap.from('.hero-title', {
            duration: 1.5,
            y: 100,
            opacity: 0,
            ease: 'power4.out',
            delay: 0.2
        });
        
        gsap.from('.hero-subtitle', {
            duration: 1.2,
            y: 50,
            opacity: 0,
            ease: 'power3.out',
            delay: 0.6
        });
        
        // Section Animations
        gsap.utils.toArray('section').forEach((section, i) => {
            if(i > 0) {
                gsap.from(section, {
                    scrollTrigger: {
                        trigger: section,
                        start: 'top 80%',
                        end: 'top 20%',
                        toggleActions: 'play none none reverse'
                    },
                    y: 100,
                    opacity: 0,
                    duration: 1,
                    ease: 'power3.out'
                });
            }
        });
        
        // Timeline Animation
        gsap.from('.timeline-item', {
            scrollTrigger: {
                trigger: '.timeline',
                start: 'top 70%'
            },
            x: (index) => index % 2 === 0 ? -100 : 100,
            opacity: 0,
            duration: 1,
            stagger: 0.2,
            ease: 'power3.out'
        });
        
        // Parallax Effects
        gsap.utils.toArray('.glass-card').forEach(card => {
            gsap.to(card, {
                scrollTrigger: {
                    trigger: card,
                    start: 'top bottom',
                    end: 'bottom top',
                    scrub: true
                },
                y: -50
            });
        });
        
        // 3D Tilt Effect
        const cards = document.querySelectorAll('.project-card, .avatar-container');
        cards.forEach(card => {
            card.addEventListener('mousemove', (e) => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateX = (y - centerY) / 10;
                const rotateY = (centerX - x) / 10;
                
                card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale3d(1.05, 1.05, 1.05)`;
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale3d(1, 1, 1)';
            });
        });
        
        // Form Submit
        document.querySelector('.contact-form').addEventListener('submit', (e) => {
            e.preventDefault();
            
            gsap.to('.submit-btn', {
                scale: 0.9,
                duration: 0.1,
                yoyo: true,
                repeat: 1,
                onComplete: () => {
                    alert('Message sent! (Demo only)');
                    e.target.reset();
                }
            });
        });
        
        // Magnetic Effect on Buttons
        const buttons = document.querySelectorAll('button, .social-link');
        buttons.forEach(button => {
            button.addEventListener('mousemove', (e) => {
                const rect = button.getBoundingClientRect();
                const x = e.clientX - rect.left - rect.width / 2;
                const y = e.clientY - rect.top - rect.height / 2;
                
                gsap.to(button, {
                    x: x * 0.3,
                    y: y * 0.3,
                    duration: 0.3,
                    ease: 'power2.out'
                });
            });
            
            button.addEventListener('mouseleave', () => {
                gsap.to(button, {
                    x: 0,
                    y: 0,
                    duration: 0.5,
                    ease: 'elastic.out(1, 0.3)'
                });
            });
        });
        
        // Window Resize
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
        
        // Text Scramble Effect
        class TextScramble {
            constructor(el) {
                this.el = el;
                this.chars = '!<>-_\\/[]{}—=+*^?#________';
                this.update = this.update.bind(this);
            }
            
            setText(newText) {
                const oldText = this.el.innerText;
                const length = Math.max(oldText.length, newText.length);
                const promise = new Promise((resolve) => this.resolve = resolve);
                this.queue = [];
                
                for (let i = 0; i < length; i++) {
                    const from = oldText[i] || '';
                    const to = newText[i] || '';
                    const start = Math.floor(Math.random() * 40);
                    const end = start + Math.floor(Math.random() * 40);
                    this.queue.push({ from, to, start, end });
                }
                
                cancelAnimationFrame(this.frameRequest);
                this.frame = 0;
                this.update();
                return promise;
            }
            
            update() {
                let output = '';
                let complete = 0;
                
                for (let i = 0, n = this.queue.length; i < n; i++) {
                    let { from, to, start, end, char } = this.queue[i];
                    
                    if (this.frame >= end) {
                        complete++;
                        output += to;
                    } else if (this.frame >= start) {
                        if (!char || Math.random() < 0.28) {
                            char = this.randomChar();
                            this.queue[i].char = char;
                        }
                        output += char;
                    } else {
                        output += from;
                    }
                }
                
                this.el.innerText = output;
                
                if (complete === this.queue.length) {
                    this.resolve();
                } else {
                    this.frameRequest = requestAnimationFrame(this.update);
                    this.frame++;
                }
            }
            
            randomChar() {
                return this.chars[Math.floor(Math.random() * this.chars.length)];
            }
        }
        
        // Apply scramble to hero title on load
        const heroTitle = document.querySelector('.hero-title');
        const scramble = new TextScramble(heroTitle);
        
        setTimeout(() => {
            scramble.setText('RISHH');
        }, 500);
    </script>
</body>
</html>
