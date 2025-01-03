<html><head><html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amelia Zhu | Interactive Designer</title>
    <style>
        :root {
            --primary: #0F0F13;
            --accent: #FF3366;
            --light: #FFFFFF;
            --secondary: #2A2A38;
            --gradient-1: linear-gradient(145deg, #FF3366, #FF8C42);
            --gradient-2: linear-gradient(145deg, #1A1A24, #0F0F13);
        }
        
        body {
            margin: 0;
            padding: 0;
            font-family: 'Inter', sans-serif;
            background: linear-gradient(145deg, #1E90FF, #FFD700);
            color: var(--light);
            cursor: none;
        }

        .custom-cursor {
            mix-blend-mode: difference;
            background: var(--gradient-1);
            border: none;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.2s ease;
            backdrop-filter: invert(1);
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            padding: 0 2rem;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        .hero-content {
            text-align: center;
            z-index: 2;
            transition: all 0.5s ease;
            max-width: 800px;
            margin: 0 auto;
        }

        h1 {
            font-size: clamp(3rem, 8vw, 4rem);
            margin: 0;
            opacity: 0;
            transform: translateY(50px);
            animation: fadeUp 1s ease forwards;
            letter-spacing: 0.1em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .subtitle {
            font-size: clamp(1rem, 3vw, 1.5rem);
            color: var(--light);
            opacity: 0;
            transform: translateY(50px);
            animation: fadeUp 1s ease 0.3s forwards;
            margin-top: 1rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .interactive-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            padding: 4rem;
            opacity: 0;
            transform: translateY(50px);
            animation: fadeUp 1s ease 0.6s forwards;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }

        .project-card {
            aspect-ratio: 1;
            background: rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            transition: transform 0.3s ease;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 12px 48px rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--light);
        }

        .project-description {
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.9);
            line-height: 1.5;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tag {
            background: rgba(255, 255, 255, 0.2);
            color: var(--light);
            padding: 0.25rem 0.75rem;
            border-radius: 100px;
            font-size: 0.875rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            backdrop-filter: blur(5px);
        }

        @keyframes fadeUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="custom-cursor"></div>

    <section class="hero">
        <div class="hero-content">
            <h1>AMELIA ZHU</h1>
            <p class="subtitle">Interactive Designer & Creative Developer</p>
        </div>
    </section>

    <div class="interactive-grid">
        <div class="project-card">
            <div>
                <h3 class="project-title">Immersive Gallery</h3>
                <p class="project-description">A WebGL-powered virtual art gallery featuring interactive 3D sculptures and paintings.</p>
            </div>
            <div class="project-tags">
                <span class="tag">WebGL</span>
                <span class="tag">Three.js</span>
                <span class="tag">Interactive</span>
            </div>
        </div>
        <div class="project-card">
            <div>
                <h3 class="project-title">Sound Visualizer</h3>
                <p class="project-description">Real-time audio visualization using Web Audio API and custom shader effects.</p>
            </div>
            <div class="project-tags">
                <span class="tag">Web Audio</span>
                <span class="tag">GLSL</span>
                <span class="tag">Canvas</span>
            </div>
        </div>
        <div class="project-card">
            <div>
                <h3 class="project-title">Data Poetry</h3>
                <p class="project-description">Converting live data streams into generative visual poetry using machine learning.</p>
            </div>
            <div class="project-tags">
                <span class="tag">ML</span>
                <span class="tag">SVG</span>
                <span class="tag">Data Art</span>
            </div>
        </div>
        <div class="project-card">
            <div>
                <h3 class="project-title">Kinetic Typography</h3>
                <p class="project-description">Interactive text animations responding to user gestures and device motion.</p>
            </div>
            <div class="project-tags">
                <span class="tag">JavaScript</span>
                <span class="tag">Animation</span>
                <span class="tag">Typography</span>
            </div>
        </div>
        <div class="project-card">
            <div>
                <h3 class="project-title">AR Experiences</h3>
                <p class="project-description">Browser-based augmented reality installations for cultural institutions.</p>
            </div>
            <div class="project-tags">
                <span class="tag">WebXR</span>
                <span class="tag">AR.js</span>
                <span class="tag">3D</span>
            </div>
        </div>
        <div class="project-card">
            <div>
                <h3 class="project-title">Digital Garden</h3>
                <p class="project-description">Procedurally generated botanical scenes with environmental data integration.</p>
            </div>
            <div class="project-tags">
                <span class="tag">P5.js</span>
                <span class="tag">API</span>
                <span class="tag">Generative</span>
            </div>
        </div>
    </div>

    <script>
        const cursor = document.querySelector('.custom-cursor');
        let mouseX = 0, mouseY = 0, cursorX = 0, cursorY = 0;

        document.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });

        function updateCursor() {
            const dx = mouseX - cursorX;
            const dy = mouseY - cursorY;

            cursorX += dx * 0.1;
            cursorY += dy * 0.1;

            cursor.style.left = (cursorX - 10) + 'px';
            cursor.style.top = (cursorY - 10) + 'px';

            requestAnimationFrame(updateCursor);
        }

        updateCursor();
    </script>
</body>
</html>
