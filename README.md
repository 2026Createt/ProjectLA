<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Los Angeles | FiveM Roleplay</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2563eb;
            --primary-hover: #1d4ed8;
            --bg-base: #090d16;
            --bg-card: #0f172a;
            --border-color: rgba(255, 255, 255, 0.08);
            --border-focus: rgba(37, 99, 235, 0.4);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --transition: all 0.2s ease-in-out;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Plus Jakarta Sans', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-base);
            color: var(--text-main);
            overflow-x: hidden;
            line-height: 1.5;
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
            padding: 18px 6%;
            background: rgba(9, 13, 22, 0.9);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
        }

        .logo {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--text-main);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            color: var(--primary);
            font-size: 1.4rem;
        }

        .logo span {
            color: var(--primary);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
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
            color: var(--text-main);
        }

        .nav-discord-btn {
            background: #5865F2;
            color: #fff;
            padding: 9px 18px;
            border-radius: 8px;
            font-weight: 600;
            font-size: 0.9rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: var(--transition);
        }

        .nav-discord-btn:hover {
            background: #4752c4;
        }

        /* Hero Section */
        .hero {
            min-height: 85vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 120px 20px 60px 20px;
            background-color: var(--bg-base);
            background-image: radial-gradient(circle at 50% 15%, rgba(37, 99, 235, 0.08) 0%, transparent 55%);
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(37, 99, 235, 0.1);
            border: 1px solid rgba(37, 99, 235, 0.25);
            padding: 5px 14px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            color: var(--primary);
            margin-bottom: 24px;
        }

        .hero h1 {
            font-size: 3.8rem;
            font-weight: 800;
            margin-bottom: 16px;
            letter-spacing: -1.5px;
            line-height: 1.1;
        }

        .hero h1 span {
            color: var(--primary);
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--text-muted);
            max-width: 580px;
            margin-bottom: 36px;
            font-weight: 400;
        }

        .hero-buttons {
            display: flex;
            gap: 12px;
        }

        .btn {
            padding: 12px 24px;
            border-radius: 8px;
            font-weight: 600;
            font-size: 0.95rem;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: var(--transition);
            cursor: pointer;
        }

        .btn-primary {
            background: var(--primary);
            color: #fff;
        }

        .btn-primary:hover {
            background: var(--primary-hover);
        }

        .btn-secondary {
            background: var(--bg-card);
            color: var(--text-main);
            border: 1px solid var(--border-color);
        }

        .btn-secondary:hover {
            border-color: rgba(255, 255, 255, 0.2);
            background: rgba(255, 255, 255, 0.03);
        }

        /* Stats Bar */
        .stats-bar {
            background: var(--bg-card);
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 24px 6%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            text-align: center;
        }

        .stat-item h3 {
            font-size: 1.75rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 2px;
        }

        .stat-item p {
            color: var(--text-muted);
            font-size: 0.85rem;
            font-weight: 500;
        }

        /* Generic Sections */
        section {
            padding: 90px 6%;
            max-width: 1300px;
            margin: 0 auto;
        }

        .section-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-header h2 {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 10px;
            letter-spacing: -0.5px;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 1rem;
            max-width: 500px;
            margin: 0 auto;
        }

        /* Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 24px;
        }

        .feature-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 32px;
            border-radius: 12px;
            transition: var(--transition);
        }

        .feature-card:hover {
            border-color: var(--border-focus);
            transform: translateY(-3px);
        }

        .icon-box {
            width: 48px;
            height: 48px;
            background: rgba(37, 99, 235, 0.1);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.25rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Factions Section */
        .factions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
        }

        .faction-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 24px;
            transition: var(--transition);
        }

        .faction-card:hover {
            border-color: var(--border-focus);
        }

        .faction-card i {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 16px;
        }

        .faction-card h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
        }

        .faction-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Guide / Steps */
        .steps-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
        }

        .step-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 28px;
            position: relative;
        }

        .step-number {
            font-size: 2rem;
            font-weight: 800;
            color: rgba(255, 255, 255, 0.04);
            position: absolute;
            top: 20px;
            right: 24px;
        }

        .step-card h3 {
            font-size: 1.15rem;
            margin-bottom: 10px;
        }

        .step-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
            line-height: 1.5;
        }

        /* Unsere Bilder Section */
        .pictures-grid {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .picture-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 16px;
            max-width: 700px;
            width: 100%;
            transition: var(--transition);
        }

        .picture-card:hover {
            border-color: var(--border-focus);
        }

        .picture-card img {
            width: 100%;
            border-radius: 8px;
            display: block;
        }

        /* Footer */
        <footer>
            <p>&copy; 2026 <span>Project Los Angeles</span>. Alle Rechte vorbehalten. Steht in keiner Verbindung zu Take-Two Interactive oder Rockstar Games.</p>
        </footer>

        /* Responsive */
        @media (max-width: 768px) {
            header {
                padding: 15px 5%;
            }
            nav ul {
                display: none;
            }
            .hero h1 {
                font-size: 2.6rem;
            }
            .hero-buttons {
                flex-direction: column;
                width: 100%;
                max-width: 280px;
            }
            section {
                padding: 60px 5%;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <header>
        <a href="#" class="logo">
            <i class="fa-solid fa-shield-cat"></i>
            Project <span>LA</span>
        </a>
        <nav>
            <ul>
                <li><a href="#home">Startseite</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#factions">Fraktionen</a></li>
                <li><a href="#join">Join Guide</a></li>
                <li><a href="#pictures">Bilder</a></li>
            </ul>
        </nav>
        <a href="https://discord.gg/yzsHbpgwVu" target="_blank" class="nav-discord-btn">
            <i class="fa-brands fa-discord"></i> Discord
        </a>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-badge">
            <i class="fa-solid fa-circle" style="font-size: 0.5rem; color: #22c55e;"></i> Server Online
        </div>
        <h1>Project <span>Los Angeles</span></h1>
        <p>Dein neues FiveM Roleplay-Zuhause. Erlebe eine performante Umgebung, maßgeschneiderte Systeme und eine aktive Community.</p>
        <div class="hero-buttons">
            <a href="fivem://connect/IP_HIER_EINFUEGEN" class="btn btn-primary">
                <i class="fa-solid fa-play"></i> Verbinden
            </a>
            <a href="https://discord.gg/yzsHbpgwVu" class="btn btn-secondary" target="_blank">
                <i class="fa-brands fa-discord"></i> Community
            </a>
        </div>
    </section>

    <!-- Stats Bar -->
    <div class="stats-bar">
        <div class="stat-item">
            <h3>48 / 48</h3>
            <p>Slots</p>
        </div>
        <div class="stat-item">
            <h3>0.0ms</h3>
            <p>Ping</p>
        </div>
        <div class="stat-item">
            <h3>Custom</h3>
            <p>Script-Architektur</p>
        </div>
        <div class="stat-item">
            <h3>24/7</h3>
            <p>Support</p>
        </div>
    </div>

    <!-- Features Section -->
    <section id="features">
        <div class="section-header">
            <h2>Server Features</h2>
            <p>Technisch optimiert für ein flüssiges und stabiles Spielerlebnis.</p>
        </div>
        <div class="features-grid">
            
            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-code"></i>
                </div>
                <h3>Hauseigene Developer</h3>
                <p>Erfahrene Entwickler mit Fachwissen in jedem Bereich sorgen für stetige Updates, reibungslose Abläufe und schnelle Hilfe bei technischen Fragen.</p>
            </div>

            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-gauge-high"></i>
                </div>
                <h3>High-Performanter Server</h3>
                <p>Genieße deinen Spielspaß ohne Ruckler oder Performance-Einbrüche. Unsere Infrastruktur ist exakt auf Spitzenwerte ausgelegt.</p>
            </div>

            <div class="feature-card">
                <div class="icon-box">
                    <i class="fa-solid fa-microchip"></i>
                </div>
                <h3>Selbst entwickelt & Performant</h3>
                <p>Jedes Script ist auf maximale Effizienz optimiert. Ein Großteil unserer Features wurde komplett in Eigenregie für euch programmiert.</p>
            </div>

        </div>
    </section>

    <!-- Factions Section -->
    <section id="factions">
        <div class="section-header">
            <h2>Staat & Wirtschaft</h2>
            <p>Finde deinen Weg im Staat – vom Gesetzeshüter bis zum Unternehmer.</p>
        </div>
        <div class="factions-grid">
            <div class="faction-card">
                <i class="fa-solid fa-shield-halved"></i>
                <h3>Los Angeles Police</h3>
                <p>Sorge für Sicherheit und rechtmäßige Ordnung im Staat.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-suitcase-medical"></i>
                <h3>Medical Center</h3>
                <p>Rette Menschenleben und sorge für die medizinische Versorgung.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-wrench"></i>
                <h3>Mechaniker & Tuner</h3>
                <p>Repariere Fahrzeuge und gestalte individuelle Custom-Setups.</p>
            </div>
            <div class="faction-card">
                <i class="fa-solid fa-user-tie"></i>
                <h3>Zivilleben & Business</h3>
                <p>Gründe Unternehmen und baue dir deine eigene Karriere auf.</p>
            </div>
        </div>
    </section>

    <!-- Join Guide Section -->
    <section id="join">
        <div class="section-header">
            <h2>Dein Einstieg</h2>
            <p>In wenigen Schritten bist du bereit für Project Los Angeles.</p>
        </div>
        <div class="steps-container">
            <div class="step-card">
                <div class="step-number">01</div>
                <h3>Discord beitreten</h3>
                <p>Klicke auf den Discord-Link, lies das Regelwerk und registriere dich.</p>
            </div>
            <div class="step-card">
                <div class="step-number">02</div>
                <h3>FiveM starten</h3>
                <p>Öffne FiveM, nutze unseren Direktlink oder suche nach dem Servernamen.</p>
            </div>
            <div class="step-card">
                <div class="step-number">03</div>
                <h3>Loslegen</h3>
                <p>Erstelle deinen Ingame-Charakter und starte deine Rolle im Staat.</p>
            </div>
        </div>
    </section>

    <!-- Unsere Bilder Section -->
    <section id="pictures">
        <div class="section-header">
            <h2>Unsere Bilder</h2>
            <p>Ein visueller Einblick in das Geschehen und die Atmosphäre auf unserem Server.</p>
        </div>
        <div class="pictures-grid">
            <div class="picture-card">
                <img src="Pictur1.png" alt="Project Los Angeles Impression">
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <span>Project Los Angeles</span>. Alle Rechte vorbehalten. Steht in keiner Verbindung zu Take-Two Interactive oder Rockstar Games.</p>
    </footer>

</body>
</html>
