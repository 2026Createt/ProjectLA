<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Los Angeles | Next-Gen FiveM Roleplay</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #00f2fe;
            --primary-glow: rgba(0, 242, 254, 0.4);
            --secondary: #4facfe;
            --bg-base: #07090f;
            --bg-card: rgba(15, 23, 42, 0.6);
            --border-color: rgba(255, 255, 255, 0.08);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Outfit', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-base);
            color: var(--text-main);
            overflow-x: hidden;
            position: relative;
        }

        /* Background Glow Effects */
        .bg-glow {
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, var(--primary-glow) 0%, rgba(0,0,0,0) 70%);
            top: -100px;
            left: -100px;
            z-index: -1;
            filter: blur(80px);
            opacity: 0.5;
        }

        .bg-glow-2 {
            position: absolute;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(79, 172, 254, 0.2) 0%, rgba(0,0,0,0) 70%);
            top: 40%;
            right: -200px;
            z-index: -1;
            filter: blur(100px);
            opacity: 0.4;
        }

        /* Navbar */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            background: rgba(7, 9, 15, 0.8);
            backdrop-filter: blur(16px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
        }

        .logo {
            font-size: 1.4rem;
            font-weight: 800;
            color: var(--text-main);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 12px;
            letter-spacing: 0.5px;
        }

        .logo i {
            color: var(--primary);
            font-size: 1.6rem;
            filter: drop-shadow(0 0 10px var(--primary-glow));
        }

        .logo span {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 35px;
            align-items: center;
        }

        nav a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
        }

        nav a:hover {
            color: var(--primary);
            text-shadow: 0 0 10px var(--primary-glow);
        }

        .nav-discord-btn {
            background: linear-gradient(135deg, #5865F2, #4752C4);
            color: #fff;
            padding: 10px 22px;
            border-radius: 12px;
            font-weight: 600;
            font-size: 0.9rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 4px 20px rgba(88, 101, 242, 0.3);
            transition: var(--transition);
        }

        .nav-discord-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(88, 101, 242, 0.5);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            background: linear-gradient(rgba(7, 9, 15, 0.5), rgba(7, 9, 15, 0.95)), url('https://images.unsplash.com/photo-1514565131-fce0801e5785?q=80&w=1920&auto=format&fit=crop') no-repeat center center/cover;
            position: relative;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(0, 242, 254, 0.1);
            border: 1px solid rgba(0, 242, 254, 0.3);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 25px;
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.15);
            animation: pulse-badge 2s infinite;
        }

        @keyframes pulse-badge {
            0% { box-shadow: 0 0 0 0 rgba(0, 242, 254, 0.4); }
            70% { box-shadow: 0 0 0 10px rgba(0, 242, 254, 0); }
            100% { box-shadow: 0 0 0 0 rgba(0, 242, 254, 0); }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 20px;
            letter-spacing: -1px;
            line-height: 1.1;
        }

        .hero h1 span {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.15rem;
            color: var(--text-muted);
            max-width: 650px;
            margin-bottom: 40px;
            font-weight: 400;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
        }

        .btn {
            padding: 14px 28px;
            border-radius: 12px;
            font-weight: 600;
            font-size: 1rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition);
            cursor: pointer;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: #07090f;
            font-weight: 700;
            box-shadow: 0 4px 25px var(--primary-glow);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 35px var(--primary-glow);
        }

        .btn-secondary {
            background: var(--bg-card);
            color: #fff;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        /* Features Section (USP) */
        .features {
            padding: 120px 8%;
            max-width: 1350px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 70px;
        }

        .section-header h2 {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 15px;
            letter-spacing: -0.5px;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 500px;
            margin: 0 auto;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 40px 35px;
            border-radius: 20px;
            backdrop-filter: blur(20px);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-8px);
            border-color: rgba(0, 242, 254, 0.3);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        .feature-card:hover::before {
            opacity: 1;
        }

        .icon-box {
            width: 70px;
            height: 70px;
            background: rgba(0, 242, 254, 0.08);
            border: 1px solid rgba(0, 242, 254, 0.2);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: var(--primary);
            margin-bottom: 25px;
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.1);
        }

        .feature-card h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 1rem;
            line-height: 1.7;
        }

        /* Footer */
        footer {
            background: rgba(4, 6, 10, 0.95);
            border-top: 1px solid var(--border-color);
            padding: 40px 8%;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 15px;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        footer span {
            color: var(--primary);
        }

        /* Responsive Design */
        @media (max-width: 968px) {
            header {
                padding: 15px 5%;
            }
            nav ul {
                display: none;
            }
            .hero h1 {
                font-size: 2.8rem;
            }
            .hero-buttons {
                flex-direction: column;
                width: 100%;
                max-width: 320px;
            }
            .features {
                padding: 80px 5%;
            }
        }
    </style>
</head>
<body>

    <div class="bg-glow"></div>
    <div class="bg-glow-2"></div>

    <!-- Header / Navbar -->
    <header>
        <a href="#" class="logo">
            <i class="fa-solid fa-cube"></i>
            Project <span>LA</span>
        </a>
        <nav>
            <ul>
                <li><a href="#home">Startseite</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="https://discord.gg/yzsHbpgwVu" target="_blank">Regelwerk</a></li>
                <li><a href="https://discord.gg/yzsHbpgwVu" target="_blank">Forum</a></li>
            </ul>
        </nav>
        <a href="https://discord.gg/yzsHbpgwVu" target="_blank" class="nav-discord-btn">
            <i class="fa-brands fa-discord"></i> Discord
        </a>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-badge">
            <i class="fa-solid fa-circle-dot" style="font-size: 0.6rem;"></i> Next-Gen FiveM Experience
        </div>
        <h1>Project <span>Los Angeles</span></h1>
        <p>Tauche ein in eine realistische Welt mit perfekten Performance-Werten, exklusiven Systemen und einer aktiven Community. Dein neues Roleplay-Zuhause wartet.</p>
        <div class="hero-buttons">
            <a href="fivem://connect/IP_HIER_EINFUEGEN" class="btn btn-primary">
                <i class="fa-solid fa-play"></i> Jetzt Verbinden
            </a>
            <a href="https://discord.gg/yzsHbpgwVu" class="btn btn-secondary" target="_blank">
                <i class="fa-brands fa-discord"></i> Discord Beitreten
            </a>
        </div>
    </section>

    <!-- Features Section (Basierend auf deinen Stichpunkten) -->
    <section class="features" id="features">
        <div class="section-header">
            <h2>Was uns auszeichnet</h2>
            <p>Entdecke die Säulen unseres Servers, die kompromisslosen Spielspaß garantieren.</p>
        </div>
        <div class="features-grid">
            
            <!-- Punkt 1: Hauseigene Developer -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-code"></i>
                </div>
                <h3>Hauseigene Developer</h3>
                <p>Erfahrene Entwickler in jedem Bereich sorgen dafür, dass Custom-Anfragen, Updates und Bugs blitzschnell bearbeitet werden – für ein reibungsloses Spielerlebnis.</p>
            </div>

            <!-- Punkt 2: Hoch performanter Server -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-gauge-high"></i>
                </div>
                <h3>High-Performanter Server</h3>
                <p>Maximaler Spielspaß ohne störende Lags oder Performance-Einbrüche dank modernster Server-Hardware und konstanter Optimierung im Hintergrund.</p>
            </div>

            <!-- Punkt 3: Performance & Eigenentwicklung -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-microchip"></i>
                </div>
                <h3>Selbst entwickelt & Performance</h3>
                <p>Jedes Script ist extrem performant optimiert. Ein Großteil unserer Features und Systeme wurde eigens von Grund auf neu für euch entwickelt.</p>
            </div>

        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <span>Project Los Angeles</span>. Alle Rechte vorbehalten. Dieser Server steht in keiner Verbindung zu Take-Two Interactive oder Rockstar Games.</p>
    </footer>

</body>
</html>
