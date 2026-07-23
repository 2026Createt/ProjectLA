<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Los Angeles | FiveM Roleplay</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #ff6b00;
            --primary-glow: rgba(255, 107, 0, 0.4);
            --secondary: #ffaa00;
            --bg-base: #090d16;
            --bg-card: rgba(18, 24, 38, 0.7);
            --border-color: rgba(255, 107, 0, 0.15);
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

        /* LA Sunset Glow Effects */
        .bg-glow {
            position: absolute;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, var(--primary-glow) 0%, rgba(0,0,0,0) 70%);
            top: -100px;
            left: -100px;
            z-index: -1;
            filter: blur(90px);
            opacity: 0.6;
        }

        .bg-glow-2 {
            position: absolute;
            width: 700px;
            height: 700px;
            background: radial-gradient(circle, rgba(255, 170, 0, 0.15) 0%, rgba(0,0,0,0) 70%);
            top: 35%;
            right: -200px;
            z-index: -1;
            filter: blur(110px);
            opacity: 0.5;
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
            background: rgba(9, 13, 22, 0.85);
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

        /* Hero Section with LA Sunset Vibe */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            background: linear-gradient(rgba(9, 13, 22, 0.65), rgba(9, 13, 22, 0.95)), url('https://images.unsplash.com/photo-1534447677768-be436bb09401?q=80&w=1920&auto=format&fit=crop') no-repeat center center/cover;
            position: relative;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 107, 0, 0.1);
            border: 1px solid rgba(255, 107, 0, 0.3);
            padding: 6px 16px;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--primary);
            margin-bottom: 25px;
            box-shadow: 0 0 20px rgba(255, 107, 0, 0.15);
        }

        .hero h1 {
            font-size: 4.2rem;
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
            color: #090d16;
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
            border-color: rgba(255, 107, 0, 0.4);
            transform: translateY(-3px);
        }

        /* Server Stats Bar */
        .stats-bar {
            background: rgba(18, 24, 38, 0.8);
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 30px 8%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
        }

        .stat-item h3 {
            font-size: 2rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 5px;
        }

        .stat-item p {
            color: var(--text-muted);
            font-size: 0.9rem;
            font-weight: 500;
        }

        /* Generic Section Styling */
        section {
            padding: 100px 8%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
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
            max-width: 550px;
            margin: 0 auto;
        }

        /* Features Section (Deine 3 Kernpunkte) */
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
            border-color: rgba(255, 107, 0, 0.4);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
        }

        .feature-card:hover::before {
            opacity: 1;
        }

        .icon-box {
            width: 70px;
            height: 70px;
            background: rgba(255, 107, 0, 0.08);
            border: 1px solid rgba(255, 107, 0, 0.2);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: var(--primary);
            margin-bottom: 25px;
            box-shadow: 0 0 20px rgba(255, 107, 0, 0.1);
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

        /* Factions / Berufe Section */
        .factions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .faction-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 30px;
            text-align: center;
            transition: var(--transition);
        }

        .faction-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .faction-card i {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .faction-card h3 {
            font-size: 1.25rem;
            margin-bottom: 10px;
        }

        .faction-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Guide / How-to-Join Section */
        .steps-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .step-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 35px;
            position: relative;
        }

        .step-number {
            font-size: 3rem;
            font-weight: 800;
            color: rgba(255, 107, 0, 0.15);
            position: absolute;
            top: 20px;
            right: 25px;
        }

        .step-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: var(--text-main);
        }

        .step-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Footer */
        footer {
            background: rgba(6, 9, 15, 0.95);
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

        /* Responsive */
        @media (max-width: 968px) {
            header {
                padding: 15px 5%;
            }
            nav ul {
                display: none;
            }
            .hero h1 {
                font-size: 3rem;
            }
            .hero-buttons {
                flex-direction: column;
                width: 100%;
                max-width: 320px;
            }
            section {
                padding: 70px 5%;
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
            <i class="fa-solid fa-fire"></i>
            Project <span>LA</span>
        </a>
        <nav>
            <ul>
                <li><a href="#home">Startseite</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#factions">Fraktionen</a></li>
                <li><a href="#join">Join Guide</a></li>
            </ul>
        </nav>
        <a href="https://discord.gg/yzsHbpgwVu" target="_blank" class="nav-discord-btn">
            <i class="fa-brands fa-discord"></i> Discord
        </a>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-badge">
            <i class="fa-solid fa-circle-dot" style="font-size: 0.6rem;"></i> Server Online & Bereit
        </div>
        <h1>Project <span>Los Angeles</span></h1>
        <p>Dein ultimatives FiveM Roleplay-Erlebnis mit kalifornischem Vibe. Erlebe einzigartige Systeme, eine faire Wirtschaft und unendliche Möglichkeiten.</p>
        <div class="hero-buttons">
            <a href="fivem://connect/IP_HIER_EINFUEGEN" class="btn btn-primary">
                <i class="fa-solid fa-play"></i> Jetzt Verbinden
            </a>
            <a href="https://discord.gg/yzsHbpgwVu" class="btn btn-secondary" target="_blank">
                <i class="fa-brands fa-discord"></i> Discord Beitreten
            </a>
        </div>
    </section>

    <!-- Stats Bar -->
    <div class="stats-bar">
        <div class="stat-item">
            <h3>64 / 64</h3>
            <p>Server Slots</p>
        </div>
        <div class="stat-item">
            <h3>0.0ms</h3>
            <p>Optimierter Ping</p>
        </div>
        <div class="stat-item">
            <h3>100%</h3>
            <p>Custom Scripts</p>
        </div>
        <div class="stat-item">
            <h3>24/7</h3>
            <p>Aktiver Support</p>
        </div>
    </div>

    <!-- Features Section (Deine 3 Kernpunkte) -->
    <section id="features">
        <div class="section-header">
            <h2>Was uns auszeichnet</h2>
            <p>Kompromisslose Performance und handgemachte Features für maximalen Spielspaß.</p>
        </div>
        <div class="features-grid">
            
            <!-- Punkt 1 -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-code"></i>
                </div>
                <h3>Hauseigene Developer</h3>
                <p>Erfahrene Entwickler in jedem Bereich kümmern sich tagtäglich um individuelle Wünsche, Bugfixes und innovative Neuerungen direkt auf dem Server.</p>
            </div>

            <!-- Punkt 2 -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-gauge-high"></i>
                </div>
                <h3>Hoch Performanter Server</h3>
                <p>Spüre flüssiges Gameplay ohne lästige Drops oder Lags. Unsere Hardware und Code-Struktur sind auf maximale Leistung ausgelegt.</p>
            </div>

            <!-- Punkt 3 -->
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-microchip"></i>
                </div>
                <h3>Selbst entwickelt & Performance</h3>
                <p>Jedes Script ist bis ins Detail optimiert. Ein Großteil unserer Features stammt aus eigener Hand – exklusiv nur bei uns.</p>
            </div>

        </div>
    </section>

    <!-- Factions / Berufe Section -->
    <section id="factions">
        <div class="section-header">
            <h2>Staat & Wirtschaft</h2>
            <p>Werde Teil des Geschehens – egal ob Gesetzeshüter, Lebensretter oder Geschäftsmann.</p>
        </div>
        <div class="factions-grid">
            <div class="faction-card">
                <i class="fa-solid fa-shield-halved"></i>
                <h3>Los Angeles Police</h3>
                <p>Sorge für Recht und Ordnung in den Straßen von LA mit modernster Ausrüstung und Taktik.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-suitcase-medical"></i>
                <h3>Medical Center</h3>
                <p>Rette Leben bei Einsätzen und halte die Bevölkerung gesund. Werde Teil des Rettungsdienstes.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-wrench"></i>
                <h3>Mechaniker & Tuner</h3>
                <p>Pimp die krassesten Karren auf, repariere Unfallschäden und leite deine eigene Werkstatt.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-user-tie"></i>
                <h3>Zivilleben & Wirtschaft</h3>
                <p>Baue dir ein Imperium auf, gründe Unternehmen oder starte eine ehrliche Karriere im Staat.</p>
            </div>
        </div>
    </section>

    <!-- Join Guide Section -->
    <section id="join">
        <div class="section-header">
            <h2>So startest du durch</h2>
            <p>In drei einfachen Schritten bist du bereit für dein neues Abenteuer auf Project Los Angeles.</p>
        </div>
        <div class="steps-container">
            <div class="step-card">
                <div class="step-number">01</div>
                <h3>Discord beitreten</h3>
                <p>Klicke auf den Discord-Button, trete unserer Community bei und lies dir in Ruhe das Regelwerk durch.</p>
            </div>
            <div class="step-card">
                <div class="step-number">02</div>
                <h3>FiveM öffnen</h3>
                <p>Starte FiveM und nutze entweder unseren Direktverbindungs-Link oder suche nach "Project Los Angeles".</p>
            </div>
            <div class="step-card">
                <div class="step-number">03</div>
                <h3>Charakter erstellen</h3>
                <p>Erstelle deinen eigenen Charakter, reise nach Los Angeles ein und schreibe deine eigene Geschichte.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <span>Project Los Angeles</span>. Alle Rechte vorbehalten. Dieser Server steht in keiner Verbindung zu Take-Two Interactive oder Rockstar Games.</p>
    </footer>

</body>
</html>
