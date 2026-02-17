<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Engineering Universe</title>
    <link
      href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Orbitron:wght@400;600;700&family=Rajdhani:wght@400;500;600&display=swap"
      rel="stylesheet"
    />
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        overflow-x: hidden;
        font-family: "Rajdhani", sans-serif;
        cursor: none;
        background: #000;
      }

      #scroll-container {
        height: 800vh;
        width: 100%;
      }

      #canvas-container {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 1;
      }

      canvas {
        display: block;
      }

      #custom-cursor {
        position: fixed;
        width: 30px;
        height: 30px;
        pointer-events: none;
        z-index: 9999;
        top: 0;
        left: 0;
        border: none;
        background: none;
      }

      #custom-cursor svg {
        width: 100%;
        height: 100%;
        filter: drop-shadow(0 0 6px currentColor);
      }

      #cursor-trail {
        position: fixed;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        pointer-events: none;
        z-index: 9998;
        background: #00ffff;
        opacity: 0.5;
        top: 0;
        left: 0;
      }

      #ui-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        z-index: 100;
      }

      #layer-title {
        position: fixed;
        top: 80px;
        left: 50%;
        transform: translateX(-50%);
        font-size: 64px;
        font-weight: bold;
        color: #fff;
        pointer-events: none;
        z-index: 102;
        text-shadow: 0 0 30px currentColor;
        text-align: center;
        letter-spacing: 4px;
        transition: all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
      }

      #narrative-text {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        max-width: 800px;
        font-size: 24px;
        color: #fff;
        pointer-events: none;
        z-index: 101;
        text-align: center;
        line-height: 1.6;
        opacity: 0;
        transition: all 0.8s;
        text-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
        padding: 0 40px;
      }

      #mini-map {
        position: fixed;
        bottom: 30px;
        right: 30px;
        width: 180px;
        height: 250px;
        background: rgba(0, 0, 0, 0.8);
        border: 2px solid rgba(0, 255, 255, 0.4);
        pointer-events: all;
        z-index: 101;
        overflow: hidden;
        backdrop-filter: blur(10px);
        padding: 15px;
      }

      .map-node {
        position: absolute;
        width: 10px;
        height: 10px;
        background: rgba(255, 255, 255, 0.4);
        border-radius: 50%;
        cursor: pointer;
        transition: all 0.3s;
        left: 50%;
        transform: translateX(-50%);
      }

      .map-node:hover {
        background: #00ff88;
        transform: translateX(-50%) scale(1.8);
      }

      .map-node.active {
        background: #00ffff;
        box-shadow: 0 0 20px #00ffff;
        transform: translateX(-50%) scale(1.5);
      }

      .map-label {
        position: absolute;
        font-size: 9px;
        color: rgba(255, 255, 255, 0.6);
        left: 25px;
        white-space: nowrap;
        pointer-events: none;
      }

      #scroll-depth {
        position: fixed;
        top: 50%;
        left: 20px;
        transform: translateY(-50%);
        width: 4px;
        height: 400px;
        background: rgba(255, 255, 255, 0.1);
        pointer-events: none;
        z-index: 101;
      }

      #scroll-depth-fill {
        width: 100%;
        height: 0%;
        background: linear-gradient(
          to bottom,
          #00ffff,
          #00ff88,
          #ffff00,
          #ff00ff
        );
        transition: height 0.1s;
      }

      #control-panel {
        position: fixed;
        top: 20px;
        right: 30px;
        background: rgba(0, 0, 0, 0.85);
        border: 1px solid rgba(0, 255, 255, 0.3);
        padding: 20px;
        z-index: 101;
        pointer-events: all;
        backdrop-filter: blur(10px);
        font-size: 12px;
        color: #00ffff;
        min-width: 220px;
      }

      .control-group {
        margin-bottom: 15px;
      }

      .control-label {
        display: block;
        margin-bottom: 5px;
        font-size: 11px;
        opacity: 0.8;
      }

      input[type="range"] {
        width: 100%;
        background: rgba(0, 255, 255, 0.2);
        height: 4px;
        border-radius: 2px;
        outline: none;
        cursor: pointer;
      }

      input[type="range"]::-webkit-slider-thumb {
        -webkit-appearance: none;
        width: 12px;
        height: 12px;
        background: #00ffff;
        border-radius: 50%;
        cursor: pointer;
      }

      .toggle-btn {
        background: rgba(0, 255, 255, 0.2);
        border: 1px solid #00ffff;
        color: #00ffff;
        padding: 8px 15px;
        cursor: pointer;
        font-size: 11px;
        font-family: "Courier New", monospace;
        transition: all 0.3s;
        width: 100%;
        margin-top: 5px;
      }

      .toggle-btn:hover {
        background: rgba(0, 255, 255, 0.4);
      }

      .toggle-btn.active {
        background: #00ffff;
        color: #000;
      }

      #command-palette {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) scale(0);
        width: 600px;
        max-width: 90%;
        background: rgba(0, 0, 0, 0.95);
        border: 2px solid #00ffff;
        padding: 25px;
        z-index: 1000;
        pointer-events: all;
        opacity: 0;
        transition: all 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        backdrop-filter: blur(20px);
      }

      #command-palette.active {
        transform: translate(-50%, -50%) scale(1);
        opacity: 1;
      }

      #command-input {
        width: 100%;
        background: transparent;
        border: none;
        border-bottom: 2px solid #00ffff;
        color: #00ffff;
        font-family: "Courier New", monospace;
        font-size: 18px;
        padding: 10px;
        outline: none;
      }

      .command-option {
        padding: 15px;
        color: #fff;
        cursor: pointer;
        transition: all 0.2s;
        margin-top: 10px;
        border-left: 3px solid transparent;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      .command-option:hover {
        background: rgba(0, 255, 255, 0.2);
        border-left-color: #00ffff;
        transform: translateX(10px);
      }

      .command-option-desc {
        font-size: 11px;
        opacity: 0.6;
      }

      .identity-panel {
        position: fixed;
        padding: 20px;
        background: rgba(0, 0, 0, 0.85);
        border-left: 3px solid currentColor;
        font-size: 14px;
        font-family: "Courier New", monospace;
        color: #fff;
        pointer-events: all;
        z-index: 101;
        backdrop-filter: blur(10px);
        max-width: 350px;
        line-height: 1.6;
        transition: all 0.5s;
        opacity: 0;
        transform: translateX(-50px);
      }

      .identity-panel.visible {
        opacity: 1;
        transform: translateX(0);
      }

      .identity-panel h3 {
        font-size: 12px;
        opacity: 0.7;
        margin-bottom: 10px;
        letter-spacing: 2px;
      }

      #architecture-diagram {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.95);
        z-index: 999;
        pointer-events: all;
        opacity: 0;
        display: none;
        transition: opacity 0.5s;
      }

      #architecture-diagram.active {
        display: block;
        opacity: 1;
      }

      .arch-node {
        position: absolute;
        padding: 15px 25px;
        background: rgba(0, 255, 255, 0.1);
        border: 2px solid #00ffff;
        color: #00ffff;
        font-size: 14px;
        cursor: pointer;
        transition: all 0.3s;
        backdrop-filter: blur(5px);
      }

      .arch-node:hover {
        background: rgba(0, 255, 255, 0.3);
        transform: scale(1.1);
        box-shadow: 0 0 30px rgba(0, 255, 255, 0.5);
      }

      #skill-focus {
        position: fixed;
        top: 20px;
        left: 50%;
        transform: translateX(-50%);
        padding: 15px 30px;
        background: rgba(0, 0, 0, 0.9);
        border: 2px solid #00ffff;
        color: #00ffff;
        font-size: 16px;
        z-index: 103;
        opacity: 0;
        pointer-events: none;
        backdrop-filter: blur(10px);
        transition: all 0.3s;
      }

      #skill-focus.active {
        opacity: 1;
      }

      #keyboard-hints {
        position: fixed;
        bottom: 20px;
        left: 20px;
        background: rgba(0, 0, 0, 0.8);
        border: 1px solid rgba(255, 255, 255, 0.2);
        padding: 15px;
        z-index: 101;
        font-size: 11px;
        color: rgba(255, 255, 255, 0.6);
        pointer-events: none;
        backdrop-filter: blur(5px);
      }

      .hint-key {
        display: inline-block;
        padding: 2px 8px;
        background: rgba(255, 255, 255, 0.1);
        border: 1px solid rgba(255, 255, 255, 0.3);
        margin: 0 5px;
        border-radius: 3px;
        font-weight: bold;
      }

      @media (max-width: 768px) {
        #custom-cursor,
        #cursor-trail {
          display: none !important;
        }
        body {
          cursor: auto;
        }
        #control-panel {
          font-size: 10px;
          padding: 15px;
          min-width: 180px;
        }
        #layer-title {
          font-size: 28px;
        }
        #narrative-text {
          font-size: 14px;
          padding: 0 20px;
        }
        #keyboard-hints {
          display: none;
        }
        #contact-cta {
          bottom: 30px;
          padding: 14px 32px;
          font-size: 13px;
          letter-spacing: 2px;
        }
        .contact-container {
          flex-direction: column;
          max-width: 500px;
          overflow-y: auto;
          max-height: 100vh;
        }
        .contact-left {
          padding: 30px 20px;
          text-align: center;
          align-items: center;
        }
        .contact-left h1 { font-size: 28px; }
        .contact-left p { max-width: 100%; }
        .contact-card {
          max-width: 100%;
          padding: 24px 20px;
          border-radius: 16px;
        }
        .identity-panel {
          display: none;
        }
      }

      @media (max-width: 480px) {
        #layer-title {
          font-size: 22px;
          top: 60px;
        }
        #narrative-text {
          font-size: 13px;
          bottom: 100px;
        }
        #contact-cta {
          bottom: 20px;
          padding: 12px 24px;
          font-size: 12px;
        }
        .contact-left h1 { font-size: 22px; }
        .contact-card h2 { font-size: 22px; }
      }

      body.frozen #canvas-container {
        filter: blur(2px);
      }

      body.xray #architecture-diagram {
        display: block;
        opacity: 0.7;
        pointer-events: none;
      }

      #landing-page {
        position: fixed;
        inset: 0;
        background: radial-gradient(circle at 30% 30%, #10101a, #000);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 9999;
        overflow: hidden;
      }

      .hero {
        text-align: center;
        position: relative;
        z-index: 10;
      }

      .hero-title {
        font-family: "Syne", sans-serif;
        font-size: clamp(80px, 15vw, 220px);
        font-weight: 800;

        background: linear-gradient(
          135deg,
          #00f0ff 0%,
          #00f0ff 30%,
          #b830ff 60%,
          #ff2e97 100%
        );

        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;

        letter-spacing: -0.02em;
        text-transform: uppercase;

        filter: drop-shadow(0 0 40px rgba(0, 240, 255, 0.5));
      }

      .hero-subtitle {
        font-family: "Orbitron", sans-serif;
        font-size: clamp(18px, 3vw, 28px);
        letter-spacing: 0.25em;
        margin-top: 20px;
        color: rgba(255, 255, 255, 0.6);
      }

      .enter-btn {
        margin-top: 60px;
        padding: 18px 50px;
        border-radius: 50px;
        border: 2px solid #00f0ff;
        background: transparent;
        color: #00f0ff;
        font-family: "Orbitron", sans-serif;
        font-size: 14px;
        letter-spacing: 0.15em;
        cursor: pointer;
        transition: 0.4s ease;
      }

      .enter-btn:hover {
        background: #00f0ff;
        color: #000;
        box-shadow: 0 0 40px #00f0ff;
      }

      .glitch {
        animation: glitchSkew 1.2s infinite linear alternate-reverse;
      }

      @keyframes glitchSkew {
        0% {
          transform: skew(0deg);
        }
        20% {
          transform: skew(-2deg);
        }
        40% {
          transform: skew(2deg);
        }
        60% {
          transform: skew(-1deg);
        }
        80% {
          transform: skew(1deg);
        }
        100% {
          transform: skew(0deg);
        }
      }
    </style>
    <style>
      /* ... existing styles ... */

      /* Landing Page Effects */
      .scanlines {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(
          to bottom,
          rgba(255, 255, 255, 0),
          rgba(255, 255, 255, 0) 50%,
          rgba(0, 0, 0, 0.2) 50%,
          rgba(0, 0, 0, 0.2)
        );
        background-size: 100% 4px;
        z-index: 2;
        pointer-events: none;
        opacity: 0.6;
      }

      .noise {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 1;
        opacity: 0.05;
        background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
        pointer-events: none;
      }

      #landing-particles {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        z-index: 0;
        pointer-events: none;
      }

      .landing-particle {
        position: absolute;
        background: rgba(0, 240, 255, 0.5);
        border-radius: 50%;
        box-shadow: 0 0 10px rgba(0, 240, 255, 0.3);
      }

      /* Vertical Scan Line */
      .scan-line-vertical {
        position: absolute;
        top: 0;
        left: 0;
        width: 3px;
        height: 100%;
        background: #00f0ff;
        box-shadow: 0 0 15px #00f0ff, 0 0 30px #b830ff;
        z-index: 1; /* Lowered z-index */
        opacity: 0.8;
        pointer-events: none;
        animation: scan-glitch 8s infinite linear; /* Slower animation */
      }

      @keyframes scan-glitch {
        0% { left: 0%; opacity: 0; }
        1% { opacity: 1; }
        10% { left: 10%; }
        15% { left: 10%; opacity: 0.2; }
        20% { left: 15%; opacity: 1; }
        40% { left: 40%; }
        42% { left: 38%; } /* Glitch back */
        45% { left: 42%; }
        60% { left: 60%; opacity: 1; }
        62% { left: 60%; opacity: 0.1; }
        65% { left: 65%; opacity: 1; }
        80% { left: 80%; }
        90% { left: 90%; opacity: 1; }
        100% { left: 100%; opacity: 0; }
      }

      /* Chaos Overlay */
      .chaos-overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 2;
        pointer-events: none;
        overflow: hidden;
      }

      .chaos-element {
        position: absolute;
        color: rgba(0, 240, 255, 0.3);
        font-family: 'Orbitron', monospace;
        font-size: 14px;
        pointer-events: none;
        user-select: none;
        white-space: nowrap;
      }

      /* Scan Line Particles */
      .scan-particle {
        position: absolute;
        width: 2px;
        height: 2px;
        background: #00f0ff;
        border-radius: 50%;
        pointer-events: none;
        box-shadow: 0 0 5px #00f0ff;
        z-index: 1;
      }

      #contact-cta {
        position: fixed;
        bottom: 60px;
        left: 50%;
        transform: translateX(-50%);
        padding: 16px 48px;
        font-family: 'Orbitron', sans-serif;
        font-size: 16px;
        font-weight: 700;
        letter-spacing: 3px;
        color: #fff;
        text-decoration: none;
        background: linear-gradient(135deg, rgba(0, 240, 255, 0.2), rgba(184, 48, 255, 0.2));
        border: 1px solid rgba(0, 240, 255, 0.5);
        border-radius: 4px;
        cursor: pointer;
        z-index: 100;
        pointer-events: auto;
        box-shadow: 0 0 20px rgba(0, 240, 255, 0.3), 0 0 40px rgba(0, 240, 255, 0.1), inset 0 0 20px rgba(0, 240, 255, 0.1);
        animation: cta-glow 2s ease-in-out infinite alternate;
        transition: all 0.3s ease;
      }

      #contact-cta:hover {
        box-shadow: 0 0 40px rgba(0, 240, 255, 0.7), 0 0 80px rgba(184, 48, 255, 0.4), inset 0 0 40px rgba(0, 240, 255, 0.3);
        background: linear-gradient(135deg, rgba(0, 240, 255, 0.5), rgba(184, 48, 255, 0.5));
        transform: translateX(-50%) scale(1.08);
        border-color: rgba(0, 240, 255, 0.9);
      }

      #contact-cta:active {
        transform: translateX(-50%) scale(0.96);
        box-shadow: 0 0 15px rgba(0, 240, 255, 0.5), inset 0 0 30px rgba(0, 240, 255, 0.4);
        background: linear-gradient(135deg, rgba(0, 240, 255, 0.6), rgba(184, 48, 255, 0.6));
      }

      @keyframes cta-glow {
        0% {
          box-shadow: 0 0 20px rgba(0, 240, 255, 0.3), 0 0 40px rgba(0, 240, 255, 0.1), inset 0 0 20px rgba(0, 240, 255, 0.1);
        }
        100% {
          box-shadow: 0 0 30px rgba(184, 48, 255, 0.4), 0 0 50px rgba(184, 48, 255, 0.2), inset 0 0 25px rgba(184, 48, 255, 0.15);
        }
      }

      /* Contact Overlay */
      #contact-overlay {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        z-index: 9999;
        display: none;
        align-items: center;
        justify-content: center;
        background: rgba(5, 5, 10, 0.92);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
      }

      #contact-overlay.active {
        display: flex;
      }

      .contact-bg-grid {
        position: absolute;
        top: 0; left: 0;
        width: 100%; height: 100%;
        background-image:
          linear-gradient(rgba(0, 240, 255, 0.03) 1px, transparent 1px),
          linear-gradient(90deg, rgba(0, 240, 255, 0.03) 1px, transparent 1px);
        background-size: 60px 60px;
        pointer-events: none;
      }

      .contact-glow {
        position: absolute;
        width: 400px; height: 400px;
        border-radius: 50%;
        filter: blur(120px);
        opacity: 0.12;
        pointer-events: none;
      }
      .contact-glow-1 { top: -100px; left: -50px; background: #00f0ff; }
      .contact-glow-2 { bottom: -100px; right: -80px; background: #b830ff; }

      .contact-container {
        display: flex;
        width: 100%;
        max-width: 1100px;
        position: relative;
        z-index: 10;
        margin: 20px;
      }

      .contact-left {
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 60px 50px;
      }

      .contact-close {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        color: rgba(255,255,255,0.5);
        background: none;
        border: none;
        font-size: 14px;
        font-family: 'Inter', sans-serif;
        cursor: pointer;
        margin-bottom: 40px;
        transition: color 0.3s;
      }
      .contact-close:hover { color: #00f0ff; }
      .contact-close svg { width: 16px; height: 16px; }

      .contact-left h1 {
        font-family: 'Orbitron', sans-serif;
        font-size: 48px;
        font-weight: 900;
        line-height: 1.1;
        margin-bottom: 16px;
        background: linear-gradient(135deg, #00f0ff, #b830ff);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
      }

      .contact-left p {
        color: rgba(255,255,255,0.5);
        font-size: 15px;
        line-height: 1.6;
        max-width: 350px;
      }

      .contact-card {
        flex: 1;
        max-width: 480px;
        background: rgba(255,255,255,0.05);
        backdrop-filter: blur(30px);
        -webkit-backdrop-filter: blur(30px);
        border: 1px solid rgba(255,255,255,0.08);
        border-radius: 20px;
        padding: 50px 40px;
        display: flex;
        flex-direction: column;
      }

      .contact-brand {
        display: flex;
        align-items: center;
        gap: 10px;
        margin-bottom: 30px;
      }
      .contact-brand-icon {
        width: 28px; height: 28px;
        background: linear-gradient(135deg, #00f0ff, #b830ff);
        border-radius: 6px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-family: 'Orbitron', sans-serif;
        font-size: 12px;
        font-weight: 900;
        color: #000;
      }
      .contact-brand-text {
        font-family: 'Orbitron', sans-serif;
        font-size: 14px;
        font-weight: 700;
        letter-spacing: 2px;
      }

      .contact-card h2 {
        font-family: 'Orbitron', sans-serif;
        font-size: 28px;
        font-weight: 700;
        margin-bottom: 8px;
      }
      .contact-card .subtitle {
        color: rgba(255,255,255,0.4);
        font-size: 13px;
        margin-bottom: 30px;
      }

      .form-group {
        margin-bottom: 20px;
      }
      .form-group label {
        display: block;
        font-size: 13px;
        color: rgba(255,255,255,0.5);
        margin-bottom: 8px;
        letter-spacing: 0.5px;
      }
      .form-group input,
      .form-group select,
      .form-group textarea {
        width: 100%;
        padding: 14px 16px;
        background: rgba(255,255,255,0.06);
        border: 1px solid rgba(255,255,255,0.1);
        border-radius: 10px;
        color: #fff;
        font-family: 'Inter', sans-serif;
        font-size: 14px;
        outline: none;
        transition: border-color 0.3s, box-shadow 0.3s;
      }
      .form-group input::placeholder,
      .form-group textarea::placeholder {
        color: rgba(255,255,255,0.25);
      }
      .form-group input:focus,
      .form-group select:focus,
      .form-group textarea:focus {
        border-color: rgba(0,240,255,0.5);
        box-shadow: 0 0 15px rgba(0,240,255,0.1);
      }
      .form-group select {
        -webkit-appearance: none;
        appearance: none;
        background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' fill='rgba(255,255,255,0.5)' viewBox='0 0 16 16'%3E%3Cpath d='M8 11L3 6h10l-5 5z'/%3E%3C/svg%3E");
        background-repeat: no-repeat;
        background-position: right 16px center;
        cursor: pointer;
      }
      .form-group select option {
        background: #1a1a2e;
        color: #fff;
      }
      .form-group textarea {
        resize: vertical;
        min-height: 100px;
      }

      .contact-submit {
        width: 100%;
        padding: 16px;
        font-family: 'Orbitron', sans-serif;
        font-size: 14px;
        font-weight: 700;
        letter-spacing: 2px;
        color: #fff;
        background: linear-gradient(135deg, #2563eb, #3b82f6);
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: all 0.3s;
        margin-top: 10px;
      }
      .contact-submit:hover {
        background: linear-gradient(135deg, #3b82f6, #60a5fa);
        box-shadow: 0 0 25px rgba(59,130,246,0.4);
        transform: translateY(-1px);
      }

      @media (max-width: 768px) {
        .contact-container {
          flex-direction: column;
          max-width: 500px;
        }
        .contact-left {
          padding: 30px 20px;
          text-align: center;
          align-items: center;
        }
        .contact-left h1 { font-size: 32px; }
        .contact-left p { max-width: 100%; }
        .contact-card {
          max-width: 100%;
          padding: 30px 24px;
          border-radius: 16px;
        }
      }
    </style>
  </head>
  <body>
    <div id="landing-page">
      <div class="scanlines"></div>
      <div class="noise"></div>
      <div id="landing-particles"></div>
      <div class="scan-line-vertical"></div>
      <div class="chaos-overlay"></div>
      <section class="hero">
        <h1 class="hero-title glitch">RISHH</h1>
        <p class="hero-subtitle">
          MOBILE ENGINEER • REACT NATIVE • CROSS-PLATFORM
        </p>

        <button id="enter-world" class="enter-btn">UNDERSTAND WHAT I DO</button>

        <div class="scroll-indicator">
          <div class="scroll-line"></div>
        </div>
      </section>
    </div>
    <div id="scroll-container"></div>
    <div id="canvas-container"></div>

    <div id="custom-cursor"></div>
    <div id="cursor-trail"></div>

    <div id="ui-overlay">
      <div id="layer-title">SYSTEMS</div>
      <div id="narrative-text"></div>

      <button id="contact-cta" style="display: none;" onclick="showContactOverlay()">
        GET IN TOUCH
      </button>

      <div id="mini-map"></div>

      <div id="scroll-depth">
        <div id="scroll-depth-fill"></div>
      </div>

      <div id="control-panel">
        <div class="control-group">
          <label class="control-label">Particle Density</label>
          <input
            type="range"
            id="particle-density"
            min="0.2"
            max="1"
            step="0.1"
            value="1"
          />
        </div>
        <div class="control-group">
          <label class="control-label">Zoom Sensitivity</label>
          <input
            type="range"
            id="zoom-sensitivity"
            min="0.5"
            max="2"
            step="0.1"
            value="1"
          />
        </div>
        <div class="control-group">
          <button class="toggle-btn" id="performance-toggle">
            High Performance
          </button>
          <button class="toggle-btn" id="diagram-toggle">
            Architecture Mode
          </button>
        </div>
      </div>

      <div id="command-palette">
        <input
          type="text"
          id="command-input"
          placeholder="Navigate to layer..."
        />
        <div id="command-options"></div>
      </div>

      <div id="skill-focus"></div>

      <div id="keyboard-hints">
        <span class="hint-key">/</span> Navigate
        <span class="hint-key">SHIFT</span> X-Ray
        <span class="hint-key">SPACE</span> Freeze
        <span class="hint-key">A</span> Architecture
        <span class="hint-key">Double Click</span> Deep Dive
      </div>
    </div>

    <div id="architecture-diagram">
      <svg id="arch-svg" width="100%" height="100%"></svg>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

    <script>
      document.body.style.overflow = "hidden";
      const isMobile = /iPhone|iPad|iPod|Android/i.test(navigator.userAgent);
      const pixelRatio = isMobile ? 1 : Math.min(window.devicePixelRatio, 2);

      let scene, camera, renderer;
      let particleSystem;
      let currentLayer = 0;
      let scrollProgress = 0;
      let mouseX = 0,
        mouseY = 0;
      let targetCameraZ = 200;
      let targetFOV = 75;
      let particleDensityMultiplier = 1;
      let zoomSensitivity = 1;
      let isFrozen = false;
      let isXRayMode = false;

      const layers = [
        {
          name: "SYSTEMS",
          depth: 200,
          narrative: "I build systems that outlive their creators.",
          color: "#00ffff",
          bgColor: "#000a0f",
          particleShape: "settings",
          particleCount: 3000,
          cursorSize: 40,
          cursorShape: "reactor",
          identity: {
            title: "SYSTEMS THINKING",
            content:
              "Every component is a relationship. Every decision is a tradeoff. I design for emergence, not just execution.",
          },
        },
        {
          name: "MOBILE • ARCHITECTURE • SECURITY",
          depth: 150,
          narrative:
            "I operate end-to-end. From UI thread to memory allocation to VAPT hardening.",
          color: "#00ff88",
          bgColor: "#000f0a",
          particleShape: "mobile",
          particleCount: 2500,
          cursorSize: 50,
          cursorShape: "blob",
          skills: [
            "Mobile",
            "Architecture",
            "Security",
            "Performance",
            "Product",
          ],
          identity: {
            title: "PLATFORM MASTERY",
            content:
              "iOS, Android, Flutter, React Native. I speak in lifecycle hooks and memory graphs, not just features.",
          },
        },
        {
          name: "FLUTTER • REACT NATIVE • NATIVE",
          depth: 100,
          narrative:
            "Cross-platform is not a compromise. It's a strategic advantage when architected correctly.",
          color: "#0088ff",
          bgColor: "#00050f",
          particleShape: "frameworks",
          particleCount: 2000,
          cursorSize: 35,
          cursorShape: "crosshair",
          skills: ["Flutter", "React Native", "iOS Native", "Android Native"],
          identity: {
            title: "FRAMEWORK DEPTH",
            content:
              "I don't just use frameworks. I understand their constraints, their rendering pipelines, their failure modes.",
          },
        },
        {
          name: "STATE • ARCHITECTURE • PATTERNS",
          depth: 50,
          narrative:
            "BLoC. Provider. Clean Architecture. Modularization. These aren't buzzwords. They're survival strategies.",
          color: "#8800ff",
          bgColor: "#0a000f",
          particleShape: "state",
          particleCount: 1500,
          cursorSize: 30,
          cursorShape: "diagram",
          skills: ["BLoC", "Provider", "Clean Arch", "Modular Design"],
          identity: {
            title: "ARCHITECTURAL PRECISION",
            content:
              "State machines prevent chaos. Dependency injection enables testing. Separation of concerns enables scale.",
          },
        },
        {
          name: "THREADING • MEMORY • LIFECYCLE",
          depth: 20,
          narrative:
            "I debug crashes at 3 AM. I optimize render loops. I eliminate memory leaks before they reach production.",
          color: "#ff0088",
          bgColor: "#0f000a",
          particleShape: "engineering",
          particleCount: 1000,
          cursorSize: 25,
          cursorShape: "reticle",
          skills: [
            "Threading",
            "Memory",
            "ARC",
            "Lifecycle",
            "Crash Analytics",
          ],
          identity: {
            title: "ENGINEERING DEPTH",
            content:
              "I close the doors attackers don't know are open. I eliminate silent failures before users feel them.",
          },
        },
        {
          name: "IMPACT • VELOCITY • OWNERSHIP",
          depth: 5,
          narrative:
            "I ship fast without breaking trust. I reduce entropy in production systems. I stabilize chaos.",
          color: "#ffff00",
          bgColor: "#0f0f00",
          particleShape: "delivery",
          particleCount: 800,
          cursorSize: 45,
          cursorShape: "glow",
          identity: {
            title: "PRODUCT ENGINEERING",
            content:
              "Solo ownership. End-to-end delivery. From wireframe to monitoring dashboard to user impact metrics.",
          },
        },
      ];

      function initThree() {
        scene = new THREE.Scene();
        scene.fog = new THREE.FogExp2(0x000000, 0.002);

        camera = new THREE.PerspectiveCamera(
          75,
          window.innerWidth / window.innerHeight,
          0.1,
          5000
        );
        camera.position.z = 200;

        renderer = new THREE.WebGLRenderer({
          antialias: !isMobile,
          alpha: true,
        });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setPixelRatio(pixelRatio);
        document
          .getElementById("canvas-container")
          .appendChild(renderer.domElement);

        createParticleSystem();
        createLights();
      }

      function getSVGTexture(shape, color) {
        const svgMap = {
          mobile: `
      <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="100%" viewBox="0 0 204 192" enable-background="new 0 0 204 192" xml:space="preserve">
<path fill="#000000" opacity="0.000000" stroke="none" 
	d="
M205.000000,76.000000 
	C205.000000,115.308807 205.000000,154.117615 205.000000,192.963211 
	C137.067490,192.963211 69.134956,192.963211 1.101209,192.963211 
	C1.101209,129.108032 1.101209,65.215858 1.101209,1.161840 
	C68.999687,1.161840 136.999817,1.161840 205.000000,1.161840 
	C205.000000,25.864777 205.000000,50.682388 205.000000,76.000000 
M147.045471,36.029335 
	C147.045471,36.029335 147.062103,36.098740 147.621765,35.885208 
	C148.025818,35.256874 148.429855,34.628536 149.119171,33.366661 
	C158.092941,24.626413 167.066727,15.886163 176.695740,6.704184 
	C175.971893,6.468990 175.248474,6.030015 174.524124,6.028448 
	C157.037537,5.990605 139.549850,5.916763 122.065765,6.128810 
	C120.331032,6.149849 118.618088,7.967315 116.350220,9.127886 
	C115.880424,9.711654 115.410629,10.295423 114.385414,11.089188 
	C113.898315,11.696241 113.411224,12.303296 112.933655,12.962058 
	C112.933655,12.962058 112.889015,12.934273 112.269470,13.173605 
	C96.768631,28.680321 81.268433,44.187679 65.766678,59.693489 
	C57.823887,67.638359 49.801811,75.505936 41.964901,83.553864 
	C37.771355,87.860329 33.894688,92.475357 29.327000,97.232765 
	C31.534513,99.527435 33.742027,101.822098 36.095428,104.606750 
	C36.380424,104.779144 36.665421,104.951538 37.077068,105.586037 
	C37.262196,105.882065 37.529175,106.037392 38.063396,106.562721 
	C38.363251,106.750168 38.663105,106.937614 39.215168,107.737793 
	C44.292629,113.125275 49.233135,118.656227 54.580685,123.760765 
	C55.485020,124.624008 58.880032,124.399178 59.878685,123.414177 
	C74.747025,108.749001 89.405495,93.871048 104.667885,78.846901 
	C105.150108,78.245392 105.632339,77.643890 106.728462,76.793755 
	C109.190193,74.210358 111.651924,71.626953 114.694733,68.823242 
	C115.501244,67.896309 116.307762,66.969376 117.720917,65.800537 
	C119.494736,63.905300 121.268555,62.010063 123.652420,59.859154 
	C125.139854,58.253502 126.627289,56.647854 128.718155,54.803295 
	C130.184402,53.219101 131.650635,51.634911 133.606781,49.904572 
	C133.779160,49.619560 133.951553,49.334553 134.586014,48.922924 
	C134.882050,48.737823 135.037354,48.470856 135.562607,47.936661 
	C135.750366,47.636959 135.938110,47.337254 136.586136,46.914440 
	C136.881012,46.729473 137.033081,46.463009 137.608047,45.895336 
	C138.113113,45.280312 138.618179,44.665287 139.584518,43.924019 
	C139.880951,43.739864 140.035675,43.473427 140.648895,42.871487 
	C141.807526,41.597202 142.966156,40.322918 144.662170,38.863956 
	C145.125397,38.283344 145.588623,37.702728 146.560928,36.937805 
	C146.746017,36.638130 146.931122,36.338451 147.045471,36.029335 
M174.530258,186.945496 
	C174.035553,186.603806 173.540848,186.262115 172.714508,185.334396 
	C169.418060,182.022949 166.126205,178.706909 162.824326,175.400864 
	C152.476791,165.040298 142.089844,154.718567 131.820190,144.281403 
	C130.519135,142.959137 129.825241,141.039459 129.016052,138.684967 
	C134.044571,133.580750 139.119598,128.521271 144.087204,123.358437 
	C148.217285,119.066071 152.104996,114.536491 156.308258,110.319496 
	C162.490753,104.116791 168.858536,98.098778 175.825226,91.575485 
	C174.912720,91.050316 174.002655,90.072067 173.087357,90.067123 
	C156.040894,89.975090 138.993454,89.954865 121.947456,90.082764 
	C120.599808,90.092873 119.261131,91.300552 117.992775,91.974930 
	C117.992775,91.974930 117.943436,91.914467 117.340157,92.133751 
	C117.187439,92.742760 117.034721,93.351768 116.257317,94.226494 
	C110.828354,99.774025 105.399399,105.321548 99.347633,111.156136 
	C89.923866,120.590500 80.500107,130.024872 71.932518,138.602097 
	C81.338539,148.468933 90.652260,158.238953 100.125031,168.506393 
	C100.399910,168.710022 100.674789,168.913635 101.256065,169.704559 
	C105.767410,174.221634 110.259521,178.758163 114.800102,183.245651 
	C116.483543,184.909424 118.280739,186.458084 120.444122,188.814743 
	C139.152344,188.814743 157.860550,188.814743 177.591827,188.814743 
	C176.136490,187.876495 175.608917,187.536377 174.530258,186.945496 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M176.040512,7.145915 
	C167.066727,15.886163 158.092941,24.626413 148.690063,33.773979 
	C147.861343,34.820442 147.461716,35.459591 147.062103,36.098740 
	C147.062103,36.098740 147.045471,36.029335 146.866730,36.176704 
	C146.475922,36.590092 146.263885,36.856102 146.051834,37.122116 
	C145.588623,37.702728 145.125397,38.283344 144.035339,38.890236 
	C142.133057,38.724274 140.857620,38.532032 139.086090,38.265011 
	C139.509903,40.404591 139.779297,41.764645 140.048706,43.124702 
	C140.035675,43.473427 139.880951,43.739864 139.037567,44.053349 
	C138.007874,44.826801 137.525101,45.470924 137.042343,46.115047 
	C137.033081,46.463009 136.881012,46.729473 136.140747,47.118538 
	C135.480881,47.589100 135.266403,47.855564 135.051926,48.122025 
	C135.037354,48.470856 134.882050,48.737823 134.151154,48.996330 
	C133.516479,49.396729 133.316681,49.723724 133.116867,50.050720 
	C131.650635,51.634911 130.184402,53.219101 128.037262,54.914703 
	C122.945709,54.202263 123.379730,57.485516 123.042374,60.114826 
	C121.268555,62.010063 119.494736,63.905300 117.046661,65.853088 
	C114.774750,65.706245 113.177086,65.506851 111.579422,65.307457 
	C111.385559,65.765450 111.191696,66.223442 110.997833,66.681435 
	C112.036438,67.468811 113.075043,68.256180 114.113655,69.043556 
	C111.651924,71.626953 109.190193,74.210358 106.105408,76.867676 
	C104.570419,76.778481 103.658485,76.615356 101.638458,76.254036 
	C102.957138,77.740128 103.535332,78.391731 104.113533,79.043343 
	C89.405495,93.871048 74.747025,108.749001 59.878685,123.414177 
	C58.880032,124.399178 55.485020,124.624008 54.580685,123.760765 
	C49.233135,118.656227 44.292629,113.125275 38.946362,107.216324 
	C38.411041,106.480583 38.144527,106.266304 37.878014,106.052025 
	C37.529175,106.037392 37.262196,105.882065 37.003670,105.151176 
	C36.603363,104.516464 36.276455,104.316612 35.949543,104.116768 
	C33.742027,101.822098 31.534513,99.527435 30.003309,97.107651 
	C35.780380,97.814827 40.381237,99.901642 46.074986,99.287918 
	C58.965458,97.898453 70.536209,93.230194 80.381310,85.629044 
	C90.674217,77.682175 100.275696,68.610458 106.186615,56.378727 
	C112.894447,42.497871 118.230789,28.590405 112.889015,12.934273 
	C112.889015,12.934273 112.933655,12.962058 113.241730,12.876634 
	C114.013489,12.153872 114.477165,11.516533 114.940842,10.879192 
	C115.410629,10.295423 115.880424,9.711654 116.943581,9.005987 
	C118.341705,8.585891 119.146477,8.287693 120.424721,7.992557 
	C125.365898,7.997035 129.838226,8.126128 134.300018,7.964360 
	C138.863846,7.798892 143.417328,7.348272 148.445435,7.011352 
	C156.949799,7.008140 164.984100,7.016050 173.114563,7.132047 
	C173.210754,7.240134 173.605484,7.315855 173.605484,7.315855 
	C173.605484,7.315855 173.945374,7.073527 174.295380,7.076346 
	C175.110413,7.101416 175.575470,7.123666 176.040512,7.145915 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M112.579239,13.053939 
	C118.230789,28.590405 112.894447,42.497871 106.186615,56.378727 
	C100.275696,68.610458 90.674217,77.682175 80.381310,85.629044 
	C70.536209,93.230194 58.965458,97.898453 46.074986,99.287918 
	C40.381237,99.901642 35.780380,97.814827 30.277317,96.966835 
	C33.894688,92.475357 37.771355,87.860329 41.964901,83.553864 
	C49.801811,75.505936 57.823887,67.638359 65.766678,59.693489 
	C81.268433,44.187679 96.768631,28.680321 112.579239,13.053939 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M99.970436,110.869080 
	C105.399399,105.321548 110.828354,99.774025 116.822113,93.918106 
	C117.572418,93.044640 117.757927,92.479553 117.943436,91.914467 
	C117.943436,91.914467 117.992775,91.974930 118.377426,91.933105 
	C120.546631,91.591438 122.330048,91.039436 124.115913,91.031395 
	C139.355682,90.962677 154.596085,90.959785 169.835770,91.037537 
	C171.607910,91.046577 173.376907,91.665756 175.147369,92.002075 
	C168.858536,98.098778 162.490753,104.116791 156.308258,110.319496 
	C152.104996,114.536491 148.217285,119.066071 144.087204,123.358437 
	C139.119598,128.521271 134.044571,133.580750 128.681702,139.063080 
	C128.178284,139.429520 128.009216,139.417847 127.633865,139.139557 
	C118.275215,129.538315 109.122826,120.203690 99.970436,110.869080 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M127.840141,139.406189 
	C128.009216,139.417847 128.178284,139.429520 128.598709,139.418884 
	C129.825241,141.039459 130.519135,142.959137 131.820190,144.281403 
	C142.089844,154.718567 152.476791,165.040298 162.824326,175.400864 
	C166.126205,178.706909 169.418060,182.022949 172.549072,185.884735 
	C170.594101,186.622711 168.805115,186.966827 167.014938,186.973053 
	C153.617950,187.019653 140.220551,186.966110 126.823776,187.037537 
	C124.894264,187.047821 122.967422,187.559158 120.788567,187.905457 
	C120.367210,188.001266 120.196632,188.030258 120.026054,188.059235 
	C118.280739,186.458084 116.483543,184.909424 114.800102,183.245651 
	C110.259521,178.758163 105.767410,174.221634 101.105713,168.995178 
	C100.934479,167.730301 100.913589,167.174835 100.957741,166.452026 
	C101.163750,166.074875 101.357613,165.942520 102.034546,165.910614 
	C108.914169,163.846893 115.363594,161.760162 122.373199,159.492203 
	C119.633629,156.213440 117.740707,153.947952 116.015244,151.402893 
	C120.068504,147.217606 123.954323,143.311890 127.840141,139.406189 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M101.604355,165.887619 
	C101.357613,165.942520 101.163750,166.074875 100.736725,166.635437 
	C100.289101,167.327103 100.127541,167.668045 99.965981,168.008972 
	C90.652260,158.238953 81.338539,148.468933 71.932518,138.602097 
	C80.500107,130.024872 89.923866,120.590500 99.659035,111.012604 
	C109.122826,120.203690 118.275215,129.538315 127.633865,139.139557 
	C123.954323,143.311890 120.068504,147.217606 115.730347,151.590027 
	C110.720123,156.667038 106.162239,161.277328 101.604355,165.887619 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M176.368134,6.925050 
	C175.575470,7.123666 175.110413,7.101416 174.064423,7.055945 
	C173.483475,7.032724 173.018387,7.023960 173.018387,7.023960 
	C164.984100,7.016050 156.949799,7.008140 147.979767,7.003404 
	C142.572617,7.003355 138.096420,6.869758 133.631119,7.033175 
	C129.065613,7.200259 124.510757,7.658633 119.951241,7.989495 
	C119.146477,8.287693 118.341705,8.585891 117.215988,8.917549 
	C118.618088,7.967315 120.331032,6.149849 122.065765,6.128810 
	C139.549850,5.916763 157.037537,5.990605 174.524124,6.028448 
	C175.248474,6.030015 175.971893,6.468990 176.368134,6.925050 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M175.486298,91.788780 
	C173.376907,91.665756 171.607910,91.046577 169.835770,91.037537 
	C154.596085,90.959785 139.355682,90.962677 124.115913,91.031395 
	C122.330048,91.039436 120.546631,91.591438 118.340179,91.921471 
	C119.261131,91.300552 120.599808,90.092873 121.947456,90.082764 
	C138.993454,89.954865 156.040894,89.975090 173.087357,90.067123 
	C174.002655,90.072067 174.912720,91.050316 175.486298,91.788780 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M120.235092,188.436981 
	C120.196632,188.030258 120.367210,188.001266 121.252068,187.964767 
	C138.267212,187.970200 154.568130,188.002823 170.868851,187.961273 
	C172.273651,187.957687 173.677216,187.462860 175.081345,187.196243 
	C175.608917,187.536377 176.136490,187.876495 177.591827,188.814743 
	C157.860550,188.814743 139.152344,188.814743 120.235092,188.436981 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M174.805801,187.070862 
	C173.677216,187.462860 172.273651,187.957687 170.868851,187.961273 
	C154.568130,188.002823 138.267212,187.970200 121.502846,187.897934 
	C122.967422,187.559158 124.894264,187.047821 126.823776,187.037537 
	C140.220551,186.966110 153.617950,187.019653 167.014938,186.973053 
	C168.805115,186.966827 170.594101,186.622711 172.714905,186.177750 
	C173.540848,186.262115 174.035553,186.603806 174.805801,187.070862 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M114.404190,68.933395 
	C113.075043,68.256180 112.036438,67.468811 110.997833,66.681435 
	C111.191696,66.223442 111.385559,65.765450 111.579422,65.307457 
	C113.177086,65.506851 114.774750,65.706245 116.743347,65.974045 
	C116.307762,66.969376 115.501244,67.896309 114.404190,68.933395 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M140.348801,42.998093 
	C139.779297,41.764645 139.509903,40.404591 139.086090,38.265011 
	C140.857620,38.532032 142.133057,38.724274 143.766632,38.982574 
	C142.966156,40.322918 141.807526,41.597202 140.348801,42.998093 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M123.347397,59.986988 
	C123.379730,57.485516 122.945709,54.202263 127.735542,55.034157 
	C126.627289,56.647854 125.139854,58.253502 123.347397,59.986988 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M104.390709,78.945122 
	C103.535332,78.391731 102.957138,77.740128 101.638458,76.254036 
	C103.658485,76.615356 104.570419,76.778481 105.798462,76.991989 
	C105.632339,77.643890 105.150108,78.245392 104.390709,78.945122 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M137.325195,46.005192 
	C137.525101,45.470924 138.007874,44.826801 138.806946,44.116470 
	C138.618179,44.665287 138.113113,45.280312 137.325195,46.005192 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M114.663132,10.984191 
	C114.477165,11.516533 114.013489,12.153872 113.236969,12.850780 
	C113.411224,12.303296 113.898315,11.696241 114.663132,10.984191 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M147.341934,35.991974 
	C147.461716,35.459591 147.861343,34.820442 148.547424,34.090748 
	C148.429855,34.628536 148.025818,35.256874 147.341934,35.991974 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M117.641800,92.024109 
	C117.757927,92.479553 117.572418,93.044640 117.134460,93.785248 
	C117.034721,93.351768 117.187439,92.742760 117.641800,92.024109 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M100.045502,168.257690 
	C100.127541,167.668045 100.289101,167.327103 100.671677,166.802765 
	C100.913589,167.174835 100.934479,167.730301 100.952515,168.701508 
	C100.674789,168.913635 100.399910,168.710022 100.045502,168.257690 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M36.022484,104.361755 
	C36.276455,104.316612 36.603363,104.516464 36.940346,104.920128 
	C36.665421,104.951538 36.380424,104.779144 36.022484,104.361755 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M133.361816,49.977646 
	C133.316681,49.723724 133.516479,49.396729 133.920105,49.059639 
	C133.951553,49.334553 133.779160,49.619560 133.361816,49.977646 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M37.970703,106.307373 
	C38.144527,106.266304 38.411041,106.480583 38.820259,106.909958 
	C38.663105,106.937614 38.363251,106.750168 37.970703,106.307373 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M146.306381,37.029961 
	C146.263885,36.856102 146.475922,36.590092 146.902100,36.181427 
	C146.931122,36.338451 146.746017,36.638130 146.306381,37.029961 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M135.307266,48.029343 
	C135.266403,47.855564 135.480881,47.589100 135.910614,47.180092 
	C135.938110,47.337254 135.750366,47.636959 135.307266,48.029343 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M120.424721,7.992557 
	C124.510757,7.658633 129.065613,7.200259 133.631119,7.033175 
	C138.096420,6.869758 142.572617,7.003355 147.509674,7.014526 
	C143.417328,7.348272 138.863846,7.798892 134.300018,7.964360 
	C129.838226,8.126128 125.365898,7.997035 120.424721,7.992557 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M173.114563,7.132047 
	C173.018387,7.023960 173.483475,7.032724 173.714417,7.053125 
	C173.945374,7.073527 173.605484,7.315855 173.605484,7.315855 
	C173.605484,7.315855 173.210754,7.240134 173.114563,7.132047 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M102.034546,165.910614 
	C106.162239,161.277328 110.720123,156.667038 115.562897,151.869598 
	C117.740707,153.947952 119.633629,156.213440 122.373199,159.492203 
	C115.363594,161.760162 108.914169,163.846893 102.034546,165.910614 
z"/>
</svg>
    `,
          settings: `
      <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="100%" viewBox="0 0 153 159" enable-background="new 0 0 153 159" xml:space="preserve">
<path fill="${color}" opacity="0.000000" stroke="none" 
	d="
M95.000000,160.000000 
	C63.333336,160.000000 32.166676,160.000000 1.000008,160.000000 
	C1.000006,107.000008 1.000006,54.000019 1.000003,1.000023 
	C51.999985,1.000015 102.999969,1.000015 153.999969,1.000008 
	C153.999969,53.999981 153.999969,106.999962 153.999985,159.999969 
	C134.500000,160.000000 115.000000,160.000000 95.000000,160.000000 
M53.807533,30.716770 
	C50.271301,21.470644 48.680779,20.792175 38.884071,24.465328 
	C38.776028,25.373631 38.609928,26.348423 38.551289,27.329638 
	C38.079742,35.219929 32.560223,38.612869 25.785391,34.724056 
	C21.307673,32.153801 20.178356,35.860123 18.378489,38.027008 
	C16.627977,40.134472 13.868376,42.181076 17.055250,45.627659 
	C22.381207,51.387642 20.616497,57.421932 13.378883,59.845966 
	C12.084278,60.279560 10.174201,61.668999 10.164987,62.632557 
	C10.135213,65.745941 10.262703,69.153221 11.561244,71.855370 
	C12.151594,73.083832 15.618002,73.032295 17.809572,73.365868 
	C21.332478,73.902084 25.166546,80.349907 23.741896,83.507568 
	C20.743767,90.152756 20.862175,90.001167 26.432873,94.352554 
	C29.373329,96.649399 31.479305,96.801346 33.998894,93.860153 
	C35.044281,92.639839 36.868580,91.927208 38.474472,91.388756 
	C40.303490,90.775497 42.586433,91.110245 44.141182,90.162247 
	C48.491516,87.509666 52.634361,85.740913 56.162388,89.259003 
	C59.079887,87.781548 61.240402,86.317101 63.625599,85.569153 
	C66.932953,84.532051 70.409111,84.033257 75.053986,83.038094 
	C69.706337,78.409508 68.899658,74.594910 71.858543,69.983871 
	C76.248253,63.143089 77.713524,62.391953 86.063538,64.004791 
	C86.594879,61.982075 86.904091,59.861713 87.704086,57.946335 
	C89.663498,53.255013 88.444374,51.099121 83.508133,50.976154 
	C76.946701,50.812706 73.591301,44.692757 76.921783,38.767262 
	C78.204826,36.484516 78.829247,34.555012 76.235573,32.777557 
	C74.456367,31.558268 72.904480,29.942337 71.008011,28.985048 
	C69.977425,28.464830 67.674637,28.434389 67.249992,29.063473 
	C63.643326,34.406487 59.125717,32.866920 53.807533,30.716770 
M113.911308,108.529793 
	C115.979515,106.709412 118.066032,106.157738 120.605949,107.848022 
	C123.784927,109.963623 124.975578,107.059868 126.390488,105.162758 
	C127.799080,103.274139 129.043106,101.524223 126.634590,99.123138 
	C122.781662,95.282112 123.659714,90.788712 128.649185,88.981102 
	C132.523346,87.577538 131.502853,84.734840 130.817001,82.464989 
	C130.346497,80.907829 128.449753,78.894180 126.967705,78.688217 
	C121.419830,77.917244 118.928062,74.499710 121.314911,69.262978 
	C122.850998,65.892807 120.406120,65.159477 118.661873,63.906601 
	C116.871925,62.620911 115.251572,60.772720 112.662743,63.261654 
	C108.460869,67.301376 104.077423,66.476578 102.153374,61.263027 
	C100.806023,57.612133 98.282272,58.836227 96.002419,59.094257 
	C93.669579,59.358284 91.670753,59.865284 91.733238,63.267509 
	C91.831017,68.590706 87.894379,70.756554 82.806160,69.117165 
	C81.448151,68.679619 79.215576,69.413879 78.026085,70.391083 
	C76.578133,71.580627 75.808197,73.595474 74.803581,75.161949 
	C80.795753,82.092880 80.393913,85.700661 73.707298,88.460197 
	C74.267647,90.522530 74.823776,92.569321 75.438423,94.831505 
	C79.581093,93.185272 82.552040,94.870384 84.950554,98.450455 
	C87.731064,102.600700 89.428360,106.647598 84.936790,110.735039 
	C86.609940,112.191643 87.966309,113.372467 89.314240,114.545937 
	C93.947342,110.176056 99.242798,109.825279 100.689857,114.031189 
	C101.819572,117.314735 103.169235,118.646347 106.672852,117.998299 
	C110.326485,117.322517 112.407982,115.914589 111.598000,111.745354 
	C111.442940,110.947212 112.627800,109.888771 113.911308,108.529793 
M38.151722,113.083473 
	C42.620743,115.642944 42.905216,117.902466 40.050861,121.966347 
	C39.237598,123.124237 39.405544,125.643456 40.130428,127.000595 
	C40.729267,128.121750 42.907131,129.169403 44.221779,128.997665 
	C48.613041,128.424057 50.557037,129.789215 51.260902,133.855835 
	C51.517368,135.337570 53.151562,137.428360 54.445019,137.664474 
	C55.996284,137.947662 58.432102,137.024368 59.466228,135.778214 
	C61.972916,132.757553 64.446861,132.400665 67.745094,134.694855 
	C68.963890,135.542618 71.206421,135.557617 72.760040,135.135452 
	C75.097015,134.500397 76.006973,132.878967 75.046478,130.140961 
	C73.901695,126.877617 76.123146,123.722610 79.525681,123.936600 
	C82.461472,124.121231 83.810593,122.779213 83.787834,120.461739 
	C83.771088,118.755348 82.889778,116.551407 81.624321,115.467117 
	C78.865929,113.103630 78.000214,110.006523 80.686188,107.647392 
	C82.926392,105.679779 82.389534,104.206978 81.227737,102.089691 
	C79.962440,99.783798 78.584282,99.205612 76.002663,100.054108 
	C72.429413,101.228531 69.966591,99.207962 70.026993,95.811050 
	C70.082062,92.713959 68.882729,91.185585 66.336479,91.196762 
	C64.657654,91.204132 62.519779,92.268433 61.405796,93.563446 
	C59.006241,96.352936 56.323269,97.092743 53.888599,94.571770 
	C51.731255,92.337967 50.228706,92.588928 47.902500,93.903549 
	C45.478313,95.273544 46.008469,96.940308 45.950375,99.221207 
	C45.898453,101.259735 43.857986,104.489105 42.066723,105.002945 
	C37.204033,106.397850 36.443939,106.934441 38.151722,113.083473 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M54.152153,30.929287 
	C59.125717,32.866920 63.643326,34.406487 67.249992,29.063473 
	C67.674637,28.434389 69.977425,28.464830 71.008011,28.985048 
	C72.904480,29.942337 74.456367,31.558268 76.235573,32.777557 
	C78.829247,34.555012 78.204826,36.484516 76.921783,38.767262 
	C73.591301,44.692757 76.946701,50.812706 83.508133,50.976154 
	C88.444374,51.099121 89.663498,53.255013 87.704086,57.946335 
	C86.904091,59.861713 86.594879,61.982075 86.063538,64.004791 
	C77.713524,62.391953 76.248253,63.143089 71.858543,69.983871 
	C68.899658,74.594910 69.706337,78.409508 75.053986,83.038094 
	C70.409111,84.033257 66.932953,84.532051 63.625599,85.569153 
	C61.240402,86.317101 59.079887,87.781548 56.162388,89.259003 
	C52.634361,85.740913 48.491516,87.509666 44.141182,90.162247 
	C42.586433,91.110245 40.303490,90.775497 38.474472,91.388756 
	C36.868580,91.927208 35.044281,92.639839 33.998894,93.860153 
	C31.479305,96.801346 29.373329,96.649399 26.432873,94.352554 
	C20.862175,90.001167 20.743767,90.152756 23.741896,83.507568 
	C25.166546,80.349907 21.332478,73.902084 17.809572,73.365868 
	C15.618002,73.032295 12.151594,73.083832 11.561244,71.855370 
	C10.262703,69.153221 10.135213,65.745941 10.164987,62.632557 
	C10.174201,61.668999 12.084278,60.279560 13.378883,59.845966 
	C20.616497,57.421932 22.381207,51.387642 17.055250,45.627659 
	C13.868376,42.181076 16.627977,40.134472 18.378489,38.027008 
	C20.178356,35.860123 21.307673,32.153801 25.785391,34.724056 
	C32.560223,38.612869 38.079742,35.219929 38.551289,27.329638 
	C38.609928,26.348423 38.776028,25.373631 38.884071,24.465328 
	C48.680779,20.792175 50.271301,21.470644 54.152153,30.929287 
M41.592560,80.112076 
	C49.831974,83.667694 57.259964,82.193016 63.561287,76.019669 
	C69.310257,70.387466 70.752457,63.400982 68.180428,55.833061 
	C65.449783,47.798454 59.531761,43.487339 51.157196,42.620007 
	C42.223080,41.694721 33.773010,47.447681 30.895237,56.267803 
	C27.911743,65.411949 31.571880,74.082733 41.592560,80.112076 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M113.552895,108.740105 
	C112.627800,109.888771 111.442940,110.947212 111.598000,111.745354 
	C112.407982,115.914589 110.326485,117.322517 106.672852,117.998299 
	C103.169235,118.646347 101.819572,117.314735 100.689857,114.031189 
	C99.242798,109.825279 93.947342,110.176056 89.314240,114.545937 
	C87.966309,113.372467 86.609940,112.191643 84.936790,110.735039 
	C89.428360,106.647598 87.731064,102.600700 84.950554,98.450455 
	C82.552040,94.870384 79.581093,93.185272 75.438423,94.831505 
	C74.823776,92.569321 74.267647,90.522530 73.707298,88.460197 
	C80.393913,85.700661 80.795753,82.092880 74.803581,75.161949 
	C75.808197,73.595474 76.578133,71.580627 78.026085,70.391083 
	C79.215576,69.413879 81.448151,68.679619 82.806160,69.117165 
	C87.894379,70.756554 91.831017,68.590706 91.733238,63.267509 
	C91.670753,59.865284 93.669579,59.358284 96.002419,59.094257 
	C98.282272,58.836227 100.806023,57.612133 102.153374,61.263027 
	C104.077423,66.476578 108.460869,67.301376 112.662743,63.261654 
	C115.251572,60.772720 116.871925,62.620911 118.661873,63.906601 
	C120.406120,65.159477 122.850998,65.892807 121.314911,69.262978 
	C118.928062,74.499710 121.419830,77.917244 126.967705,78.688217 
	C128.449753,78.894180 130.346497,80.907829 130.817001,82.464989 
	C131.502853,84.734840 132.523346,87.577538 128.649185,88.981102 
	C123.659714,90.788712 122.781662,95.282112 126.634590,99.123138 
	C129.043106,101.524223 127.799080,103.274139 126.390488,105.162758 
	C124.975578,107.059868 123.784927,109.963623 120.605949,107.848022 
	C118.066032,106.157738 115.979515,106.709412 113.552895,108.740105 
M102.321304,74.202164 
	C100.522934,74.495659 98.641769,74.545853 96.940529,75.124786 
	C89.585899,77.627594 85.685379,86.188751 88.473808,93.422600 
	C91.360870,100.912331 100.206902,104.552658 107.442604,101.228661 
	C112.868889,98.735893 116.452904,92.705025 115.821381,87.129623 
	C115.071007,80.505074 110.845207,76.234718 102.321304,74.202164 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M37.774448,112.926445 
	C36.443939,106.934441 37.204033,106.397850 42.066723,105.002945 
	C43.857986,104.489105 45.898453,101.259735 45.950375,99.221207 
	C46.008469,96.940308 45.478313,95.273544 47.902500,93.903549 
	C50.228706,92.588928 51.731255,92.337967 53.888599,94.571770 
	C56.323269,97.092743 59.006241,96.352936 61.405796,93.563446 
	C62.519779,92.268433 64.657654,91.204132 66.336479,91.196762 
	C68.882729,91.185585 70.082062,92.713959 70.026993,95.811050 
	C69.966591,99.207962 72.429413,101.228531 76.002663,100.054108 
	C78.584282,99.205612 79.962440,99.783798 81.227737,102.089691 
	C82.389534,104.206978 82.926392,105.679779 80.686188,107.647392 
	C78.000214,110.006523 78.865929,113.103630 81.624321,115.467117 
	C82.889778,116.551407 83.771088,118.755348 83.787834,120.461739 
	C83.810593,122.779213 82.461472,124.121231 79.525681,123.936600 
	C76.123146,123.722610 73.901695,126.877617 75.046478,130.140961 
	C76.006973,132.878967 75.097015,134.500397 72.760040,135.135452 
	C71.206421,135.557617 68.963890,135.542618 67.745094,134.694855 
	C64.446861,132.400665 61.972916,132.757553 59.466228,135.778214 
	C58.432102,137.024368 55.996284,137.947662 54.445019,137.664474 
	C53.151562,137.428360 51.517368,135.337570 51.260902,133.855835 
	C50.557037,129.789215 48.613041,128.424057 44.221779,128.997665 
	C42.907131,129.169403 40.729267,128.121750 40.130428,127.000595 
	C39.405544,125.643456 39.237598,123.124237 40.050861,121.966347 
	C42.905216,117.902466 42.620743,115.642944 37.774448,112.926445 
M67.872444,105.483833 
	C59.495781,100.434044 50.214355,104.007957 49.045372,112.733398 
	C48.307846,118.238396 51.026031,123.065948 56.076191,125.220284 
	C60.944599,127.297089 66.719330,125.709053 69.897903,121.419327 
	C73.367058,116.737457 72.851326,111.306770 67.872444,105.483833 
z"/>
<path fill="${color}" opacity="0.000000" stroke="none" 
	d="
M41.227600,79.996231 
	C31.571880,74.082733 27.911743,65.411949 30.895237,56.267803 
	C33.773010,47.447681 42.223080,41.694721 51.157196,42.620007 
	C59.531761,43.487339 65.449783,47.798454 68.180428,55.833061 
	C70.752457,63.400982 69.310257,70.387466 63.561287,76.019669 
	C57.259964,82.193016 49.831974,83.667694 41.227600,79.996231 
M50.347076,47.829597 
	C40.093479,48.266685 33.462547,55.894058 35.402149,65.020317 
	C36.906433,72.098297 43.661762,77.350967 50.525440,76.779572 
	C57.852245,76.169617 63.688034,70.371201 64.072441,63.319324 
	C64.514885,55.202740 59.764324,49.508373 50.347076,47.829597 
z"/>
<path fill="${color}" opacity="0.000000" stroke="none" 
	d="
M102.718346,74.245918 
	C110.845207,76.234718 115.071007,80.505074 115.821381,87.129623 
	C116.452904,92.705025 112.868889,98.735893 107.442604,101.228661 
	C100.206902,104.552658 91.360870,100.912331 88.473808,93.422600 
	C85.685379,86.188751 89.585899,77.627594 96.940529,75.124786 
	C98.641769,74.545853 100.522934,74.495659 102.718346,74.245918 
M108.767570,83.010246 
	C104.173965,78.814278 99.265755,78.387749 95.567451,81.863144 
	C92.125183,85.097939 91.910660,90.867363 95.101372,94.397797 
	C97.860901,97.451141 102.951294,98.143623 106.458771,95.942810 
	C110.434929,93.447914 111.346352,89.376480 108.767570,83.010246 
z"/>
<path fill="${color}" opacity="0.000000" stroke="none" 
	d="
M68.153412,105.746071 
	C72.851326,111.306770 73.367058,116.737457 69.897903,121.419327 
	C66.719330,125.709053 60.944599,127.297089 56.076191,125.220284 
	C51.026031,123.065948 48.307846,118.238396 49.045372,112.733398 
	C50.214355,104.007957 59.495781,100.434044 68.153412,105.746071 
M63.490192,108.795670 
	C58.802292,107.484978 55.416950,108.807907 54.336815,112.602066 
	C53.260338,116.383362 54.803505,119.609138 58.391098,120.386604 
	C60.605034,120.866394 64.064034,119.781036 65.635719,118.132195 
	C68.484741,115.143295 67.301056,111.745186 63.490192,108.795670 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M50.769676,47.854916 
	C59.764324,49.508373 64.514885,55.202740 64.072441,63.319324 
	C63.688034,70.371201 57.852245,76.169617 50.525440,76.779572 
	C43.661762,77.350967 36.906433,72.098297 35.402149,65.020317 
	C33.462547,55.894058 40.093479,48.266685 50.769676,47.854916 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M108.981323,83.364883 
	C111.346352,89.376480 110.434929,93.447914 106.458771,95.942810 
	C102.951294,98.143623 97.860901,97.451141 95.101372,94.397797 
	C91.910660,90.867363 92.125183,85.097939 95.567451,81.863144 
	C99.265755,78.387749 104.173965,78.814278 108.981323,83.364883 
z"/>
<path fill="${color}" opacity="1.000000" stroke="none" 
	d="
M63.839066,108.975548 
	C67.301056,111.745186 68.484741,115.143295 65.635719,118.132195 
	C64.064034,119.781036 60.605034,120.866394 58.391098,120.386604 
	C54.803505,119.609138 53.260338,116.383362 54.336815,112.602066 
	C55.416950,108.807907 58.802292,107.484978 63.839066,108.975548 
z"/>
</svg>
    `,
          frameworks: `
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <polygon points="50,10 90,90 10,90" fill="${color}"/>
      </svg>
    `,
          state: `
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <circle cx="25" cy="50" r="8" fill="${color}"/>
        <circle cx="75" cy="50" r="8" fill="${color}"/>
        <line x1="33" y1="50" x2="67" y2="50" stroke="${color}" stroke-width="6"/>
      </svg>
    `,
          engineering: `
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <rect x="20" y="20" width="60" height="60" fill="${color}"/>
      </svg>
    `,
          delivery: `
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <polygon points="10,50 90,50 60,20 60,40 10,40" fill="${color}"/>
      </svg>
    `,
        };

        const svg = svgMap[shape] || svgMap.settings;

        const blob = new Blob([svg], { type: "image/svg+xml;charset=utf-8" });
        const url = URL.createObjectURL(blob);

        const texture = new THREE.TextureLoader().load(url);
        texture.needsUpdate = true;

        return texture;
      }

      function createParticleSystem() {
        if (particleSystem) {
          scene.remove(particleSystem);
          particleSystem.geometry.dispose();
          particleSystem.material.dispose();
        }

        const layer = layers[currentLayer];
        const baseCount = layer.particleCount;
        const particleCount = Math.floor(baseCount * particleDensityMultiplier);

        const texture = getSVGTexture(layer.particleShape, layer.color);

        const material = new THREE.MeshBasicMaterial({
          map: texture,
          transparent: true,
          depthWrite: false,
        });

        const geometry = new THREE.PlaneGeometry(
          isMobile ? 4 : 6,
          isMobile ? 4 : 6
        );

        particleSystem = new THREE.InstancedMesh(
          geometry,
          material,
          particleCount
        );

        const dummy = new THREE.Object3D();
        particleSystem.userData.velocities = [];

        for (let i = 0; i < particleCount; i++) {
          const pos = {
            x: (Math.random() - 0.5) * 120,
            y: (Math.random() - 0.5) * 120,
            z: (Math.random() - 0.5) * 40,
          };

          dummy.position.set(pos.x, pos.y, pos.z);
          dummy.rotation.z = Math.random() * Math.PI * 2;
          dummy.updateMatrix();

          particleSystem.setMatrixAt(i, dummy.matrix);

          particleSystem.userData.velocities.push({
            x: (Math.random() - 0.5) * 0.1,
            y: (Math.random() - 0.5) * 0.1,
            z: (Math.random() - 0.5) * 0.1,
          });
        }

        particleSystem.instanceMatrix.needsUpdate = true;

        scene.add(particleSystem);
      }

      function getShapePosition(shape, index, total) {
        const t = index / total;
        const angle = t * Math.PI * 2;

        switch (shape) {
          // ⚙ SETTINGS (Gear shape)
          case "settings":
            const teeth = 8;
            const r1 = 30;
            const r2 = 40;
            const toothAngle = Math.floor(t * teeth) % 2 === 0 ? r1 : r2;

            return {
              x: Math.cos(angle) * toothAngle,
              y: Math.sin(angle) * toothAngle,
              z: (Math.random() - 0.5) * 10,
            };

          // 📱 MOBILE (Random mix iOS + Android clusters)
          case "mobile":
            const mobileOffset = index % 2 === 0 ? -40 : 40;
            return {
              x: mobileOffset + (Math.random() - 0.5) * 25,
              y: (Math.random() - 0.5) * 50,
              z: (Math.random() - 0.5) * 10,
            };

          // 🦋 FLUTTER + ⚛ REACT
          case "frameworks":
            if (index % 2 === 0) {
              // Flutter triangle
              return {
                x: (Math.random() - 0.5) * 40,
                y: (Math.random() - 0.5) * 40,
                z: (Math.random() - 0.5) * 10,
              };
            } else {
              // React orbital
              const rx = 40;
              const ry = 15;
              return {
                x: Math.cos(angle) * rx,
                y: Math.sin(angle) * ry,
                z: (Math.random() - 0.5) * 10,
              };
            }

          // 🔁 STATE (Nodes in grid)
          case "state":
            const grid = Math.ceil(Math.sqrt(total));
            const gx = (index % grid) - grid / 2;
            const gy = Math.floor(index / grid) - grid / 2;

            return {
              x: gx * 10,
              y: gy * 10,
              z: (Math.random() - 0.5) * 10,
            };

          // 🧠 ENGINEERING (Threads + chip)
          case "engineering":
            const thread = Math.floor(index / (total / 5));
            return {
              x: t * 100 - 50,
              y: thread * 12 - 30 + Math.sin(t * Math.PI * 4) * 5,
              z: (Math.random() - 0.5) * 10,
            };

          // 🚀 DELIVERY (Arrow + bars mix)
          case "delivery":
            if (index < total / 2) {
              // Arrow
              return {
                x: t * 80 - 40,
                y: Math.abs(t - 0.5) * -60,
                z: 0,
              };
            } else {
              // Bar graph
              const bar = Math.floor((index - total / 2) / (total / 6));
              return {
                x: bar * 15 - 30,
                y: Math.random() * 40 - 20,
                z: 0,
              };
            }

          default:
            console.log("coming here");
            return {
              x: (Math.random() - 0.5) * 100,
              y: (Math.random() - 0.5) * 100,
              z: (Math.random() - 0.5) * 100,
            };
        }
      }

      function createLights() {
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.2);
        scene.add(ambientLight);

        const pointLight1 = new THREE.PointLight(0x00ffff, 0.8, 200);
        pointLight1.position.set(50, 50, 50);
        scene.add(pointLight1);

        const pointLight2 = new THREE.PointLight(0xff00ff, 0.8, 200);
        pointLight2.position.set(-50, -50, 50);
        scene.add(pointLight2);
      }

      window.addEventListener("scroll", () => {
        const currentScrollY = window.pageYOffset;
        const maxScroll =
          document.documentElement.scrollHeight - window.innerHeight;
        scrollProgress = currentScrollY / maxScroll;

        const logProgress = Math.log(1 + scrollProgress * 9) / Math.log(10);

        targetCameraZ = 200 - logProgress * 195 * zoomSensitivity;
        targetFOV = 75 + logProgress * 30;

        const newLayer = Math.min(
          Math.floor(logProgress * layers.length),
          layers.length - 1
        );

        if (newLayer !== currentLayer) {
          transitionToLayer(newLayer);
        }

        document.getElementById("scroll-depth-fill").style.height =
          scrollProgress * 100 + "%";
        scene.fog.density = 0.002 + logProgress * 0.008;
      });

      function transitionToLayer(newLayerIndex) {
        const oldLayer = currentLayer;
        currentLayer = newLayerIndex;
        const layer = layers[currentLayer];

        gsap.to("#layer-title", {
          opacity: 0,
          y: -30,
          duration: 0.4,
          onComplete: () => {
            document.getElementById("layer-title").textContent = layer.name;
            document.getElementById("layer-title").style.color = layer.color;
            gsap.to("#layer-title", {
              opacity: 1,
              y: 0,
              duration: 0.6,
              ease: "power2.out",
            });
          },
        });

        updateNarrative(layer.narrative);

        gsap.to(document.body, {
          backgroundColor: layer.bgColor,
          duration: 1.2,
        });

        updateCursor(layer);
        morphParticles(oldLayer, newLayerIndex);
        updateIdentityPanel(layer);
        updateMiniMap();

        // Show/Hide contact CTA at last layer
        const contactCta = document.getElementById('contact-cta');
        if (newLayerIndex === layers.length - 1) {
          contactCta.style.display = 'block';
          gsap.fromTo(contactCta, { opacity: 0, y: 30 }, { opacity: 1, y: 0, duration: 0.8, delay: 0.5, ease: 'back.out(1.5)' });
        } else {
          gsap.to(contactCta, { opacity: 0, y: 20, duration: 0.3, onComplete: () => { contactCta.style.display = 'none'; } });
        }

        gsap.to(scene.fog.color, {
          r: (parseInt(layer.color.slice(1, 3), 16) / 255) * 0.1,
          g: (parseInt(layer.color.slice(3, 5), 16) / 255) * 0.1,
          b: (parseInt(layer.color.slice(5, 7), 16) / 255) * 0.1,
          duration: 1,
        });
      }

      function morphParticles(fromLayer, toLayer) {
        if (!particleSystem) return;

        gsap.to(particleSystem.rotation, {
          y: particleSystem.rotation.y + Math.PI * 2,
          duration: 1.5,
          ease: "power2.inOut",
        });

        gsap.to(particleSystem.material, {
          opacity: 0,
          duration: 0.6,
          onComplete: () => {
            createParticleSystem();
            gsap.to(particleSystem.material, {
              opacity: 0.8,
              duration: 0.8,
              ease: "power2.out",
            });
          },
        });
      }

      function updateNarrative(text) {
        const narrativeEl = document.getElementById("narrative-text");

        gsap.to(narrativeEl, {
          opacity: 0,
          scale: 0.95,
          duration: 0.4,
          onComplete: () => {
            narrativeEl.textContent = text;
            narrativeEl.style.color = layers[currentLayer].color;
            gsap.to(narrativeEl, {
              opacity: 1,
              scale: 1,
              duration: 0.6,
              ease: "back.out(1.2)",
            });
          },
        });
      }

      const cursor = document.getElementById("custom-cursor");
      const cursorTrail = document.getElementById("cursor-trail");

      if (!isMobile) {
        let cursorX = 0,
          cursorY = 0;

        document.addEventListener("mousemove", (e) => {
          mouseX = (e.clientX / window.innerWidth) * 2 - 1;
          mouseY = -(e.clientY / window.innerHeight) * 2 + 1;

          const halfW = cursor.offsetWidth / 2;
          const halfH = cursor.offsetHeight / 2;

          gsap.to(cursor, {
            left: e.clientX - halfW,
            top: e.clientY - halfH,
            duration: 0.1,
          });

          gsap.to(cursorTrail, {
            left: e.clientX - 5,
            top: e.clientY - 5,
            duration: 0.3,
          });
        });

        // Set initial cursor SVG
        const initColor = layers[0].color;
        const initSize = layers[0].cursorSize;
        cursor.innerHTML = `<svg width="${initSize}" height="${initSize}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="30" cy="30" r="26" stroke="${initColor}" stroke-width="2" opacity="0.7"/>
          <circle cx="30" cy="30" r="18" stroke="${initColor}" stroke-width="1.5" stroke-dasharray="4 4" opacity="0.5">
            <animateTransform attributeName="transform" type="rotate" from="0 30 30" to="360 30 30" dur="3s" repeatCount="indefinite"/>
          </circle>
          <circle cx="30" cy="30" r="10" stroke="${initColor}" stroke-width="1" opacity="0.4">
            <animateTransform attributeName="transform" type="rotate" from="360 30 30" to="0 30 30" dur="2s" repeatCount="indefinite"/>
          </circle>
          <circle cx="30" cy="30" r="3" fill="${initColor}" opacity="0.9"/>
        </svg>`;
        cursor.style.width = initSize + 'px';
        cursor.style.height = initSize + 'px';
      }

      function updateCursor(layer) {
        if (isMobile) return;

        const color = layer.color;
        const size = layer.cursorSize;

        // SVG cursor designs per shape
        const svgCursors = {
          reactor: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="30" cy="30" r="26" stroke="${color}" stroke-width="2" opacity="0.7"/>
            <circle cx="30" cy="30" r="18" stroke="${color}" stroke-width="1.5" stroke-dasharray="4 4" opacity="0.5">
              <animateTransform attributeName="transform" type="rotate" from="0 30 30" to="360 30 30" dur="3s" repeatCount="indefinite"/>
            </circle>
            <circle cx="30" cy="30" r="10" stroke="${color}" stroke-width="1" opacity="0.4">
              <animateTransform attributeName="transform" type="rotate" from="360 30 30" to="0 30 30" dur="2s" repeatCount="indefinite"/>
            </circle>
            <circle cx="30" cy="30" r="3" fill="${color}" opacity="0.9"/>
          </svg>`,
          blob: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M30 6 C45 6, 54 15, 54 30 C54 45, 45 54, 30 54 C15 54, 6 45, 6 30 C6 15, 15 6, 30 6Z" stroke="${color}" stroke-width="2.5" fill="${color}" fill-opacity="0.1" opacity="0.8">
              <animate attributeName="d" dur="3s" repeatCount="indefinite" values="M30 6 C45 6, 54 15, 54 30 C54 45, 45 54, 30 54 C15 54, 6 45, 6 30 C6 15, 15 6, 30 6Z;M30 8 C48 4, 56 18, 52 30 C56 44, 44 56, 30 52 C16 56, 4 44, 8 30 C4 16, 16 4, 30 8Z;M30 6 C45 6, 54 15, 54 30 C54 45, 45 54, 30 54 C15 54, 6 45, 6 30 C6 15, 15 6, 30 6Z"/>
            </path>
            <circle cx="30" cy="30" r="4" fill="${color}" opacity="0.6"/>
          </svg>`,
          crosshair: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <line x1="30" y1="2" x2="30" y2="18" stroke="${color}" stroke-width="1.5" opacity="0.8"/>
            <line x1="30" y1="42" x2="30" y2="58" stroke="${color}" stroke-width="1.5" opacity="0.8"/>
            <line x1="2" y1="30" x2="18" y2="30" stroke="${color}" stroke-width="1.5" opacity="0.8"/>
            <line x1="42" y1="30" x2="58" y2="30" stroke="${color}" stroke-width="1.5" opacity="0.8"/>
            <circle cx="30" cy="30" r="12" stroke="${color}" stroke-width="1" opacity="0.4"/>
            <rect x="26" y="26" width="8" height="8" stroke="${color}" stroke-width="1" opacity="0.6"/>
            <circle cx="30" cy="30" r="2" fill="${color}" opacity="1"/>
          </svg>`,
          diagram: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="8" y="8" width="44" height="44" rx="8" stroke="${color}" stroke-width="1.5" opacity="0.6"/>
            <rect x="16" y="16" width="28" height="28" rx="4" stroke="${color}" stroke-width="1" stroke-dasharray="3 3" opacity="0.4"/>
            <circle cx="30" cy="30" r="5" fill="${color}" opacity="0.3"/>
            <line x1="30" y1="8" x2="30" y2="16" stroke="${color}" stroke-width="1" opacity="0.5"/>
            <line x1="30" y1="44" x2="30" y2="52" stroke="${color}" stroke-width="1" opacity="0.5"/>
            <circle cx="30" cy="30" r="2" fill="${color}" opacity="0.8"/>
          </svg>`,
          reticle: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="10" y="10" width="40" height="40" stroke="${color}" stroke-width="1" opacity="0.3"/>
            <line x1="10" y1="10" x2="20" y2="20" stroke="${color}" stroke-width="0.5" opacity="0.3"/>
            <line x1="50" y1="10" x2="40" y2="20" stroke="${color}" stroke-width="0.5" opacity="0.3"/>
            <line x1="10" y1="50" x2="20" y2="40" stroke="${color}" stroke-width="0.5" opacity="0.3"/>
            <line x1="50" y1="50" x2="40" y2="40" stroke="${color}" stroke-width="0.5" opacity="0.3"/>
            <circle cx="30" cy="30" r="1" fill="${color}" opacity="1"/>
          </svg>`,
          glow: `<svg width="${size}" height="${size}" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="30" cy="30" r="22" fill="${color}" fill-opacity="0.15"/>
            <circle cx="30" cy="30" r="14" fill="${color}" fill-opacity="0.2"/>
            <circle cx="30" cy="30" r="6" fill="${color}" fill-opacity="0.5"/>
          </svg>`
        };

        const svg = svgCursors[layer.cursorShape] || svgCursors.reactor;

        gsap.to(cursor, {
          width: size,
          height: size,
          border: 'none',
          borderRadius: '0',
          boxShadow: 'none',
          background: 'none',
          duration: 0.5,
          ease: "power2.out",
          onComplete: () => { cursor.innerHTML = svg; }
        });

        gsap.to(cursorTrail, {
          backgroundColor: color,
          duration: 0.5,
        });
      }

      let identityPanel = null;

      function updateIdentityPanel(layer) {
        if (!layer.identity) return;

        if (!identityPanel) {
          identityPanel = document.createElement("div");
          identityPanel.className = "identity-panel";
          identityPanel.style.top = "200px";
          identityPanel.style.left = "50px";
          document.getElementById("ui-overlay").appendChild(identityPanel);
        }

        gsap.to(identityPanel, {
          opacity: 0,
          x: -50,
          duration: 0.3,
          onComplete: () => {
            identityPanel.innerHTML = `
                        <h3>${layer.identity.title}</h3>
                        <p>${layer.identity.content}</p>
                    `;
            identityPanel.style.borderColor = layer.color;
            identityPanel.style.color = layer.color;

            gsap.to(identityPanel, {
              opacity: 1,
              x: 0,
              duration: 0.6,
              ease: "power2.out",
            });
          },
        });
      }

      function initMiniMap() {
        const miniMap = document.getElementById("mini-map");

        layers.forEach((layer, index) => {
          const node = document.createElement("div");
          node.className = "map-node";
          node.style.top = `${(index / (layers.length - 1)) * 85}%`;
          node.dataset.layer = index;

          const label = document.createElement("div");
          label.className = "map-label";
          label.textContent = layer.name.split(" ")[0];
          label.style.top = node.style.top;

          node.addEventListener("click", () => jumpToLayer(index));

          miniMap.appendChild(node);
          miniMap.appendChild(label);
        });

        updateMiniMap();
      }

      function updateMiniMap() {
        const nodes = document.querySelectorAll(".map-node");
        nodes.forEach((node, index) => {
          if (index === currentLayer) {
            node.classList.add("active");
          } else {
            node.classList.remove("active");
          }
        });
      }

      function jumpToLayer(index) {
        const targetScroll =
          (index / (layers.length - 1)) *
          (document.documentElement.scrollHeight - window.innerHeight);
        window.scrollTo({
          top: targetScroll,
          behavior: "smooth",
        });
      }

      const commandPalette = document.getElementById("command-palette");
      const commandInput = document.getElementById("command-input");
      const commandOptions = document.getElementById("command-options");

      document.addEventListener("keydown", (e) => {
        if (e.key === "/") {
          e.preventDefault();
          commandPalette.classList.add("active");
          commandInput.focus();
          populateCommandOptions();
        }

        if (e.key === "Escape") {
          commandPalette.classList.remove("active");
          commandInput.value = "";
        }

        if (e.key === "Shift" && !isXRayMode) {
          activateXRayMode(true);
        }

        if (e.code === "Space" && e.target === document.body) {
          e.preventDefault();
          toggleFreeze();
        }

        if (e.key === "a" || e.key === "A") {
          toggleArchitectureDiagram();
        }
      });

      document.addEventListener("keyup", (e) => {
        if (e.key === "Shift" && isXRayMode) {
          activateXRayMode(false);
        }
      });

      function populateCommandOptions() {
        commandOptions.innerHTML = "";

        layers.forEach((layer, index) => {
          const option = document.createElement("div");
          option.className = "command-option";
          option.innerHTML = `
                    <span>${layer.name}</span>
                    <span class="command-option-desc">Layer ${index + 1}</span>
                `;
          option.addEventListener("click", () => {
            jumpToLayer(index);
            commandPalette.classList.remove("active");
            commandInput.value = "";
          });
          commandOptions.appendChild(option);
        });
      }

      commandInput.addEventListener("input", () => {
        const query = commandInput.value.toLowerCase();
        const options = commandOptions.querySelectorAll(".command-option");

        options.forEach((option) => {
          const text = option.textContent.toLowerCase();
          if (text.includes(query)) {
            option.style.display = "flex";
          } else {
            option.style.display = "none";
          }
        });
      });

      document
        .getElementById("particle-density")
        .addEventListener("input", (e) => {
          particleDensityMultiplier = parseFloat(e.target.value);
          createParticleSystem();
        });

      document
        .getElementById("zoom-sensitivity")
        .addEventListener("input", (e) => {
          zoomSensitivity = parseFloat(e.target.value);
        });

      document
        .getElementById("performance-toggle")
        .addEventListener("click", (e) => {
          const btn = e.target;
          if (btn.classList.contains("active")) {
            btn.classList.remove("active");
            btn.textContent = "High Performance";
            particleDensityMultiplier = 1;
          } else {
            btn.classList.add("active");
            btn.textContent = "Low Performance";
            particleDensityMultiplier = 0.3;
          }
          document.getElementById("particle-density").value =
            particleDensityMultiplier;
          createParticleSystem();
        });

      document
        .getElementById("diagram-toggle")
        .addEventListener("click", () => {
          toggleArchitectureDiagram();
        });

      function toggleFreeze() {
        isFrozen = !isFrozen;
        if (isFrozen) {
          document.body.classList.add("frozen");
        } else {
          document.body.classList.remove("frozen");
        }
      }

      function activateXRayMode(active) {
        isXRayMode = active;
        if (active) {
          document.body.classList.add("xray");
          initArchitectureDiagram();
        } else {
          document.body.classList.remove("xray");
        }
      }

      let architectureDiagramInitialized = false;

      function toggleArchitectureDiagram() {
        const diagram = document.getElementById("architecture-diagram");

        if (diagram.classList.contains("active")) {
          diagram.classList.remove("active");
        } else {
          if (!architectureDiagramInitialized) {
            initArchitectureDiagram();
          }
          diagram.classList.add("active");
        }
      }

      function initArchitectureDiagram() {
        if (architectureDiagramInitialized) return;
        architectureDiagramInitialized = true;

        const diagram = document.getElementById("architecture-diagram");
        diagram.innerHTML =
          '<svg id="arch-svg" width="100%" height="100%"></svg>';

        const nodes = [
          { id: "client", label: "CLIENT", x: "50%", y: "10%" },
          { id: "state", label: "STATE", x: "30%", y: "30%" },
          { id: "network", label: "NETWORK", x: "70%", y: "30%" },
          { id: "security", label: "SECURITY", x: "20%", y: "50%" },
          { id: "persistence", label: "PERSISTENCE", x: "50%", y: "50%" },
          { id: "monitoring", label: "MONITORING", x: "80%", y: "50%" },
          { id: "impact", label: "IMPACT", x: "50%", y: "70%" },
        ];

        const connections = [
          ["client", "state"],
          ["client", "network"],
          ["state", "security"],
          ["state", "persistence"],
          ["network", "persistence"],
          ["network", "monitoring"],
          ["security", "impact"],
          ["persistence", "impact"],
          ["monitoring", "impact"],
        ];

        const svg = document.getElementById("arch-svg");
        connections.forEach(([from, to]) => {
          const fromNode = nodes.find((n) => n.id === from);
          const toNode = nodes.find((n) => n.id === to);

          const line = document.createElementNS(
            "http://www.w3.org/2000/svg",
            "line"
          );
          line.setAttribute("x1", fromNode.x);
          line.setAttribute("y1", fromNode.y);
          line.setAttribute("x2", toNode.x);
          line.setAttribute("y2", toNode.y);
          line.setAttribute("stroke", "rgba(0, 255, 255, 0.3)");
          line.setAttribute("stroke-width", "2");
          svg.appendChild(line);
        });

        nodes.forEach((node) => {
          const nodeEl = document.createElement("div");
          nodeEl.className = "arch-node";
          nodeEl.textContent = node.label;
          nodeEl.style.left = node.x;
          nodeEl.style.top = node.y;
          nodeEl.style.transform = "translate(-50%, -50%)";

          nodeEl.addEventListener("click", () => {
            gsap.to(nodeEl, {
              scale: 1.2,
              duration: 0.2,
              yoyo: true,
              repeat: 1,
            });
          });

          diagram.appendChild(nodeEl);
        });
      }

      document.addEventListener("dblclick", () => {
        const targetLayer = layers.length - 1;
        jumpToLayer(targetLayer);

        gsap.to(camera.position, {
          z: 5,
          duration: 2,
          ease: "power2.inOut",
        });

        setTimeout(() => {
          gsap.to(camera.position, {
            z: targetCameraZ,
            duration: 1.5,
            ease: "power2.out",
          });
        }, 2000);
      });

      function animate() {
        requestAnimationFrame(animate);

        if (isFrozen) {
          renderer.render(scene, camera);
          return;
        }

        camera.position.z += (targetCameraZ - camera.position.z) * 0.05;
        camera.fov += (targetFOV - camera.fov) * 0.05;
        camera.updateProjectionMatrix();

        if (particleSystem) {
          const dummy = new THREE.Object3D();
          const velocities = particleSystem.userData.velocities;

          for (let i = 0; i < particleSystem.count; i++) {
            particleSystem.getMatrixAt(i, dummy.matrix);
            dummy.matrix.decompose(
              dummy.position,
              dummy.quaternion,
              dummy.scale
            );

            dummy.position.x += velocities[i].x;
            dummy.position.y += velocities[i].y;
            dummy.position.z += velocities[i].z;

            const bound = 120;
            if (Math.abs(dummy.position.x) > bound) velocities[i].x *= -1;
            if (Math.abs(dummy.position.y) > bound) velocities[i].y *= -1;
            if (Math.abs(dummy.position.z) > bound) velocities[i].z *= -1;

            dummy.updateMatrix();
            particleSystem.setMatrixAt(i, dummy.matrix);
          }

          particleSystem.instanceMatrix.needsUpdate = true;
        }

        if (!isMobile) {
          camera.position.x += (mouseX * 3 - camera.position.x) * 0.02;
          camera.position.y += (mouseY * 3 - camera.position.y) * 0.02;
        }

        renderer.render(scene, camera);
      }

      let resizeTimeout;
      window.addEventListener("resize", () => {
        clearTimeout(resizeTimeout);
        resizeTimeout = setTimeout(() => {
          camera.aspect = window.innerWidth / window.innerHeight;
          camera.updateProjectionMatrix();
          renderer.setSize(window.innerWidth, window.innerHeight);
        }, 250);
      });

      window.addEventListener("load", () => {
        initThree();
        initMiniMap();

        const firstLayer = layers[0];
        document.body.style.backgroundColor = firstLayer.bgColor;
        document.getElementById("layer-title").textContent = firstLayer.name;
        document.getElementById("layer-title").style.color = firstLayer.color;
        updateCursor(firstLayer);
        updateNarrative(firstLayer.narrative);
        updateIdentityPanel(firstLayer);

        animate();

        gsap.from(camera.position, {
          z: 400,
          duration: 2.5,
          ease: "power2.out",
        });

        gsap.from("#layer-title", {
          opacity: 0,
          y: -100,
          duration: 1,
          delay: 0.5,
        });
      });

      let frameCount = 0;
      let lastFPSUpdate = Date.now();

      setInterval(() => {
        const now = Date.now();
        const delta = now - lastFPSUpdate;
        const fps = Math.round((frameCount * 1000) / delta);

        if (fps < 30 && particleDensityMultiplier > 0.3) {
          console.log("Auto-reducing particle density for performance");
          particleDensityMultiplier *= 0.8;
          createParticleSystem();
        }

        frameCount = 0;
        lastFPSUpdate = now;
      }, 2000);

      const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
          if (!entry.isIntersecting && particleSystem) {
            particleSystem.material.opacity = 0;
          } else if (entry.isIntersecting && particleSystem) {
            particleSystem.material.opacity = 0.8;
          }
        });
      });

      document.getElementById("enter-world").addEventListener("click", () => {
        gsap.to("#landing-page", {
          opacity: 0,
          scale: 1.1,
          duration: 1,
          ease: "power3.inOut",
          onComplete: () => {
            document.getElementById("landing-page").style.display = "none";
            document.body.style.overflow = "auto";
          },
        });

        gsap.from(camera.position, {
          z: 600,
          duration: 2.5,
          ease: "power4.out",
        });
      });

      class TextScramble {
        constructor(el) {
          this.el = el;
          this.chars = "!<>-_\\/[]{}—=+*^?#________";
          this.update = this.update.bind(this);
        }

        setText(newText) {
          const oldText = this.el.innerText;
          const length = Math.max(oldText.length, newText.length);
          const promise = new Promise((resolve) => (this.resolve = resolve));
          this.queue = [];

          for (let i = 0; i < length; i++) {
            const from = oldText[i] || "";
            const to = newText[i] || "";
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
          let output = "";
          let complete = 0;

          for (let i = 0; i < this.queue.length; i++) {
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
      const heroTitle = document.querySelector(".hero-title");
      if (heroTitle) {
        const scramble = new TextScramble(heroTitle);
        setTimeout(() => {
          scramble.setText("RISHH");
        }, 500);
      }

      // Landing Page Particles (Chaotic)
      function createLandingParticles() {
        const container = document.getElementById("landing-particles");
        const particleCount = 60;

        for (let i = 0; i < particleCount; i++) {
          const particle = document.createElement("div");
          particle.classList.add("landing-particle");
          
          const size = Math.random() * 4 + 1;
          particle.style.width = `${size}px`;
          particle.style.height = `${size}px`;
          
          // Initial position
          const startX = Math.random() * 100;
          const startY = Math.random() * 100;
          particle.style.left = `${startX}%`;
          particle.style.top = `${startY}%`;
          
          // Random opacity
          particle.style.opacity = Math.random() * 0.6 + 0.2;
          
          container.appendChild(particle);

          // Chaotic Animation
          const duration = Math.random() * 5 + 3; // Faster
          const yMove = Math.random() * 200 - 100;
          const xMove = Math.random() * 200 - 100;

          gsap.to(particle, {
            x: xMove,
            y: yMove,
            duration: duration,
            repeat: -1,
            yoyo: true,
            ease: "rough({ template: none.out, strength: 1, points: 20, taper: 'none', randomize: true, clamp: false })"
          });
        }
      }
      createLandingParticles();

      function spawnChaos() {
        if (Math.random() > 0.05) { // Control frequency
            requestAnimationFrame(spawnChaos);
            return;
        }

        const container = document.querySelector('.chaos-overlay');
        if (!container) return;

        const el = document.createElement('div');
        el.classList.add('chaos-element');
        
        // Random Content
        const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789<>/[]{}!@#$%^&*";
        let text = "";
        for(let i=0; i<5; i++) text += chars[Math.floor(Math.random() * chars.length)];
        el.innerText = text;

        // Random Position
        el.style.left = Math.random() * 100 + '%';
        el.style.top = Math.random() * 100 + '%';
        el.style.opacity = Math.random() * 0.5 + 0.2;
        el.style.fontSize = (Math.random() * 20 + 10) + 'px';

        container.appendChild(el);

        // Glitch Animation
        gsap.to(el, {
            opacity: 0,
            duration: 0.5,
            x: (Math.random() - 0.5) * 50,
            onComplete: () => el.remove()
        });

        requestAnimationFrame(spawnChaos);
      }
      spawnChaos();

      // Scan Line Particles
      function spawnScanLineParticles() {
        if (Math.random() > 0.3) { 
           requestAnimationFrame(spawnScanLineParticles);
           return;
        }

        const scanLine = document.querySelector('.scan-line-vertical');
        const container = document.getElementById('landing-page');
        if (!scanLine || !container) return;

        const rect = scanLine.getBoundingClientRect();
        
        // Spawn multiple particles at once for a trail effect
        const particleCount = Math.floor(Math.random() * 3) + 1;

        for(let i=0; i<particleCount; i++) {
            const particle = document.createElement('div');
            particle.classList.add('scan-particle');
            
            // Position at scan line
            // Reset left relative to container if needed, but here fixed usually works
            particle.style.left = (rect.left + Math.random() * 4) + 'px';
            particle.style.top = (Math.random() * window.innerHeight) + 'px';
            
            container.appendChild(particle);

            // Fall and Fade
            gsap.to(particle, {
                y: Math.random() * 50 + 20,
                opacity: 0,
                duration: Math.random() * 1 + 0.5,
                ease: "power1.in",
                onComplete: () => particle.remove()
            });
        }
        
        requestAnimationFrame(spawnScanLineParticles);
      }
      spawnScanLineParticles();

      observer.observe(document.body);

      // Contact Overlay
      function showContactOverlay() {
        const overlay = document.getElementById('contact-overlay');
        overlay.classList.add('active');
        gsap.fromTo(overlay, { opacity: 0 }, { opacity: 1, duration: 0.4 });
        gsap.fromTo('.contact-card', { y: 40, opacity: 0 }, { y: 0, opacity: 1, duration: 0.6, delay: 0.15, ease: 'back.out(1.5)' });
        gsap.fromTo('.contact-left', { x: -30, opacity: 0 }, { x: 0, opacity: 1, duration: 0.5, delay: 0.1 });
      }

      function hideContactOverlay() {
        const overlay = document.getElementById('contact-overlay');
        gsap.to(overlay, { opacity: 0, duration: 0.3, onComplete: () => overlay.classList.remove('active') });
      }
    </script>

    <!-- Contact Overlay -->
    <div id="contact-overlay">
      <div class="contact-bg-grid"></div>
      <div class="contact-glow contact-glow-1"></div>
      <div class="contact-glow contact-glow-2"></div>

      <div class="contact-container">
        <div class="contact-left">
          <button class="contact-close" onclick="hideContactOverlay()">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M19 12H5M12 19l-7-7 7-7"/>
            </svg>
            Back
          </button>
          <h1>Let's Build<br/>Something.</h1>
          <p>Have a project in mind? Want to collaborate? Drop me a message and I'll get back to you.</p>
        </div>

        <div class="contact-card">
          <div class="contact-brand">
            <div class="contact-brand-icon">R</div>
            <span class="contact-brand-text">RISHH</span>
          </div>
          <h2>Get in Touch</h2>
          <p class="subtitle">Fill in the details and I'll reach out soon.</p>

          <form action="https://formsubmit.co/mittal.risheek@gmail.com" method="POST">
            <input type="hidden" name="_subject" value="New Contact from Portfolio" />
            <input type="hidden" name="_captcha" value="false" />
            <input type="text" name="_honey" style="display:none" />

            <div class="form-group">
              <label>Name</label>
              <input type="text" name="name" placeholder="Enter your name" required />
            </div>

            <div class="form-group">
              <label>Email</label>
              <input type="email" name="email" placeholder="Enter your email" required />
            </div>

            <div class="form-group">
              <label>Subject</label>
              <select name="subject" required>
                <option value="" disabled selected>Select a topic</option>
                <option value="Project Inquiry">Project Inquiry</option>
                <option value="Collaboration">Collaboration</option>
                <option value="Freelance Work">Freelance Work</option>
                <option value="Just Saying Hi">Just Saying Hi</option>
                <option value="Other">Other</option>
              </select>
            </div>

            <div class="form-group">
              <label>Message</label>
              <textarea name="message" placeholder="Tell me about your project..." required></textarea>
            </div>

            <button type="submit" class="contact-submit">SEND MESSAGE</button>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
