<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Los Angeles | FiveM Roleplay</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #f39c12;
            --primary-hover: #e67e22;
            --bg-color: #0b0f19;
            --card-bg: #131b2e;
            --text-main: #ffffff;
            --text-muted: #94a3b8;
            --border-color: #1e293b;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            line-height: 1.6;
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
            padding: 20px 50px;
            background: rgba(11, 15, 25, 0.85);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--text-main);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
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
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--primary);
        }

        .nav-btn {
            background: var(--primary);
            color: #fff;
            padding: 10px 20px;
            border-radius: 8px;
            font-weight: 600;
            text-decoration: none;
            transition: background 0.3s, transform 0.2s;
        }

        .nav-btn:hover {
            background: var(--primary-hover);
            transform: translateY(-2px);
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
            background: linear-gradient(rgba(11, 15, 25, 0.7), rgba(11, 15, 25, 0.9)), url('https://images.unsplash.com/photo-1542314831-068cd1dbfeeb?q=80&w=1920&auto=format&fit=crop') no-repeat center center/cover;
            position: relative;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 15px;
            letter-spacing: 1px;
        }

        .hero h1 span {
            color: var(--primary);
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            max-width: 600px;
            margin-bottom: 30px;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 12px 25px;
            border-radius: 8px;
            font-weight: 600;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s;
        }

        .btn-primary {
            background: var(--primary);
            color: #fff;
        }

        .btn-primary:hover {
            background: var(--primary-hover);
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.05);
            color: #fff;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(5px);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-2px);
        }

        /* Features Section */
        .features {
            padding: 100px 50px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .section-title p {
            color: var(--text-muted);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 30px;
            border-radius: 12px;
            transition: transform 0.3s, border-color 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
        }

        .feature-card i {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Footer */
        footer {
            background: #070a10;
            border-top: 1px solid var(--border-color);
            padding: 30px 50px;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        footer span {
            color: var(--primary);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                padding: 15px 20px;
            }
            nav ul {
                display: none;
            }
            .hero h1 {
                font-size: 2.5rem;
            }
            .hero-buttons {
                flex-direction: column;
                width: 100%;
                max-width: 300px;
            }
            .features {
                padding: 60px 20px;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <header>
        <a href="#" class="logo"><i class="fa-solid fa-city"></i>Project <span>LA</span></a>
        <nav>
            <ul>
                <li><a href="#home">Startseite</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#" target="_blank">Regelwerk</a></li>
                <li><a href="#" target="_blank">Forum</a></li>
            </ul>
        </nav>
        <a href="discord://..." class="nav-btn"><i class="fa-brands fa-discord"></i> Discord</a>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <h1>Project <span>Los Angeles</span></h1>
        <p>Erlebe erstklassiges Hardcore- und Midcore-Roleplay auf dem modernsten FiveM-Server Deutschlands. Deine Geschichte beginnt hier.</p>
        <div class="hero-buttons">
            <a href="fivem://connect/IP_HIER_EINFUEGEN" class="btn btn-primary"><i class="fa-solid fa-play"></i> Jetzt Verbinden</a>
            <a href="https://discord.gg/DEIN_DISCORD" class="btn btn-secondary" target="_blank"><i class="fa-brands fa-discord"></i> Discord beitreten</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="section-title">
            <h2>Was uns auszeichnet</h2>
            <p>Entdecke die Highlights, die unseren Server so einzigartig machen.</p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <i class="fa-solid fa-users-gear"></i>
                <h3>Aktives Team</h3>
                <p>Ein engagiertes und kompetentes Admin- und Supportteam kümmert sich zügig um deine Anliegen und sorgt für faires RP.</p>
            </div>
            <div class="feature-card">
                <i class="fa-solid fa-car-tunnel"></i>
                <h3>Custom Content</h3>
                <p>Maßgeschneiderte Fahrzeuge, einzigartige Kleidung und exklusive Mappings sorgen für ein realistisches Spielerlebnis.</p>
            </div>
            <div class="feature-card">
                <i class="fa-solid fa-scale-balanced"><h3>Fair Economy</h3></h3>
                <p>Eine perfekt ausbalancierte Wirtschaft sorgt für langanhaltenden Spielspaß und realistische Karrierewege im Staat.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 <span>Project Los Angeles</span>. Alle Rechte vorbehalten. Dieser Server steht in keiner Verbindung zu Take-Two Interactive oder Rockstar Games.</p>
    </footer>

</body>
</html>
