<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>TV Premium CL | Televisión Digital Premium</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800;14..32,900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
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
            background-color: #0a0a0a;
            color: #ffffff;
            line-height: 1.5;
            overflow-x: hidden;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(12px);
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1280px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 24px;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.5rem;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .logo i {
            color: #e50914;
            font-size: 1.6rem;
        }

        .logo .cl {
            color: #e50914;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            text-decoration: none;
            color: #f0f0f0;
            font-weight: 500;
            transition: color 0.3s;
            font-size: 0.95rem;
        }

        .nav-menu a:hover, .nav-contact {
            color: #e50914;
        }

        .hamburger {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: white;
        }

        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            overflow: hidden;
            padding: 120px 20px 80px;
            background: linear-gradient(135deg, #0a0a0a 0%, #141414 100%);
        }

        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(229,9,20,0.15) 0%, rgba(0,0,0,0.9) 80%);
            pointer-events: none;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
            margin: 0 auto;
        }

        .hero-badge {
            background: rgba(229, 9, 20, 0.15);
            backdrop-filter: blur(4px);
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            font-size: 0.85rem;
            font-weight: 500;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(229,9,20,0.3);
            color: #e50914;
        }

        .hero h1 {
            font-size: 3.8rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 1rem;
        }

        .gradient-text {
            background: linear-gradient(90deg, #e50914, #ff6b6b);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .hero p {
            font-size: 1.2rem;
            color: #ccc;
            margin-bottom: 1.8rem;
        }

        .hero-features {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .hero-features span {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            font-size: 0.9rem;
            color: #aaa;
        }

        .hero-features i {
            color: #e50914;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary, .btn-secondary {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 1rem 2rem;
            border-radius: 40px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1rem;
        }

        .btn-primary {
            background: #e50914;
            color: white;
            box-shadow: 0 8px 20px rgba(229,9,20,0.3);
        }

        .btn-primary:hover {
            background: #b81d24;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: rgba(255,255,255,0.08);
            color: white;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .btn-secondary:hover {
            background: rgba(255,255,255,0.15);
            transform: translateY(-2px);
        }

        .hero-scroll {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;
            color: #888;
            font-size: 0.8rem;
            animation: bounce 2s infinite;
        }

        .animate-up {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 0.8s ease forwards;
        }

        .delay-1 { animation-delay: 0.2s; }
        .delay-2 { animation-delay: 0.4s; }
        .delay-3 { animation-delay: 0.6s; }
        .delay-4 { animation-delay: 0.8s; }

        @keyframes fadeUp {
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(10px); }
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-tag {
            color: #e50914;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-weight: 600;
            font-size: 0.8rem;
            display: inline-block;
            margin-bottom: 1rem;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .featured-content {
            padding: 80px 0;
            background: #0a0a0a;
        }

        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .content-card {
            background: #111;
            border-radius: 24px;
            padding: 2rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.05);
            position: relative;
            text-align: center;
        }

        .content-card:hover {
            transform: translateY(-5px);
            border-color: rgba(229,9,20,0.3);
        }

        .card-badge {
            position: absolute;
            top: -12px;
            left: 20px;
            background: #e50914;
            color: white;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.7rem;
            font-weight: bold;
        }

        .content-card i {
            font-size: 2.5rem;
            color: #e50914;
            margin-bottom: 1rem;
        }

        .content-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.8rem;
        }

        .content-card p {
            color: #aaa;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .card-tag {
            color: #e50914;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .stats-row {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 2rem;
            background: linear-gradient(135deg, #111, #0a0a0a);
            padding: 2rem;
            border-radius: 40px;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            display: block;
            font-size: 2rem;
            font-weight: 800;
            color: #e50914;
        }

        .stat-label {
            font-size: 0.85rem;
            color: #aaa;
        }

        .why-us {
            padding: 80px 0;
            background: #0f0f0f;
        }

        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .benefit-card {
            text-align: center;
            padding: 2rem;
            background: #111;
            border-radius: 24px;
        }

        .benefit-card i {
            font-size: 2.5rem;
            color: #e50914;
            margin-bottom: 1rem;
        }

        .benefit-card h3 {
            margin-bottom: 0.8rem;
        }

        .benefit-card p {
            color: #aaa;
            font-size: 0.9rem;
        }

        .stats-banner {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 2rem;
            background: linear-gradient(90deg, #e50914, #ff6b6b);
            padding: 2rem;
            border-radius: 30px;
        }

        .banner-item {
            text-align: center;
        }

        .banner-number {
            display: block;
            font-size: 2rem;
            font-weight: 800;
            color: white;
        }

        .banner-text {
            color: rgba(255,255,255,0.9);
            font-size: 0.9rem;
        }

        .plans {
            padding: 80px 0;
            background: #0a0a0a;
        }

        .plans-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .plan-card {
            background: #111;
            border-radius: 28px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            border: 1px solid rgba(255,255,255,0.05);
            text-align: center;
        }

        .plan-card:hover {
            transform: translateY(-8px);
            border-color: rgba(229,9,20,0.3);
        }

        .featured {
            border: 1px solid #e50914;
            background: linear-gradient(145deg, #151515, #0e0e0e);
            box-shadow: 0 0 20px rgba(229,9,20,0.2);
        }

        .recommended-badge {
            position: absolute;
            top: -12px;
            left: 50%;
            transform: translateX(-50%);
            background: #e50914;
            color: white;
            padding: 5px 15px;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: bold;
            white-space: nowrap;
        }

        .plan-icon i {
            font-size: 2rem;
            color: #e50914;
            margin-bottom: 1rem;
        }

        .plan-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .plan-duration {
            color: #e50914;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .price {
            font-size: 2.2rem;
            font-weight: 800;
            margin: 1rem 0;
        }

        .currency {
            font-size: 1.3rem;
            vertical-align: super;
        }

        .period {
            font-size: 0.9rem;
            font-weight: 400;
            color: #aaa;
        }

        .plan-features {
            list-style: none;
            margin: 1.5rem 0;
            text-align: left;
        }

        .plan-features li {
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            color: #ccc;
        }

        .plan-features i {
            color: #e50914;
            width: 20px;
        }

        .plan-btn {
            display: block;
            text-align: center;
            background: transparent;
            border: 1px solid #e50914;
            padding: 12px;
            border-radius: 40px;
            text-decoration: none;
            color: white;
            font-weight: 600;
            transition: all 0.3s;
            margin-top: 20px;
        }

        .plan-btn:hover {
            background: #e50914;
            color: white;
        }

        .featured-btn {
            background: #e50914;
        }

        .payment-methods {
            text-align: center;
            padding: 1rem;
            color: #aaa;
            font-size: 0.85rem;
        }

        .devices {
            padding: 80px 0;
            background: #0f0f0f;
        }

        .devices-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
            gap: 20px;
            margin-bottom: 50px;
        }

        .device-item {
            background: #111;
            padding: 1.5rem;
            border-radius: 20px;
            text-align: center;
            border: 1px solid #222;
        }

        .device-item i {
            font-size: 2rem;
            color: #e50914;
            margin-bottom: 0.8rem;
            display: block;
        }

        .device-item span {
            font-size: 0.9rem;
        }

        .requirements {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
            margin-top: 40px;
        }

        .req-card {
            text-align: center;
            background: #111;
            padding: 1.5rem;
            border-radius: 20px;
            min-width: 180px;
        }

        .req-card i {
            font-size: 1.8rem;
            color: #e50914;
            margin-bottom: 0.8rem;
        }

        .req-card h4 {
            margin-bottom: 0.5rem;
        }

        .req-card p {
            color: #aaa;
            font-size: 0.85rem;
        }

        .how-to {
            padding: 80px 0;
            background: #0a0a0a;
        }

        .steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .step {
            text-align: center;
            padding: 2rem;
            background: #111;
            border-radius: 24px;
        }

        .step-number {
            width: 50px;
            height: 50px;
            background: #e50914;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
            margin: 0 auto 1rem;
        }

        .step h3 {
            margin-bottom: 0.5rem;
        }

        .step p {
            color: #aaa;
            font-size: 0.9rem;
        }

        .cta-banner {
            text-align: center;
            background: linear-gradient(90deg, #e50914, #ff6b6b);
            padding: 1rem;
            border-radius: 50px;
            max-width: 500px;
            margin: 0 auto;
        }

        .cta-banner p {
            font-weight: 600;
        }

        footer {
            background: #030303;
            padding: 60px 0 20px;
            border-top: 1px solid #1f1f1f;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-brand .logo {
            margin-bottom: 1rem;
        }

        .footer-brand p {
            color: #aaa;
            font-size: 0.85rem;
            margin-bottom: 1rem;
        }

        .social {
            display: flex;
            gap: 15px;
        }

        .social a {
            color: #aaa;
            font-size: 1.2rem;
            transition: color 0.3s;
        }

        .social a:hover {
            color: #e50914;
        }

        .footer-info h4 {
            margin-bottom: 1rem;
            font-size: 1rem;
        }

        .footer-info p {
            color: #aaa;
            font-size: 0.85rem;
            line-height: 1.5;
        }

        .legal-notice {
            background: #0f0f0f;
            padding: 25px;
            border-radius: 16px;
            margin: 30px 0;
            border-left: 4px solid #e50914;
        }

        .legal-notice h4 {
            margin-bottom: 12px;
            color: #e50914;
        }

        .legal-notice p {
            font-size: 0.8rem;
            color: #aaa;
            line-height: 1.5;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #1f1f1f;
            font-size: 0.75rem;
            color: #666;
        }

        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: #25d366;
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
            z-index: 1000;
            transition: all 0.3s;
            text-decoration: none;
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
            background-color: #128C7E;
        }

        .tooltip {
            position: absolute;
            right: 70px;
            background: #1f1f1f;
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            white-space: nowrap;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }

        .whatsapp-float:hover .tooltip {
            opacity: 1;
            visibility: visible;
            right: 80px;
        }

        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background: #0a0a0a;
                width: 100%;
                text-align: center;
                transition: 0.3s;
                padding: 2rem 0;
                gap: 1.5rem;
                border-top: 1px solid #222;
            }
            .nav-menu.active {
                left: 0;
            }
            .hamburger {
                display: block;
            }
            .hero h1 {
                font-size: 2.2rem;
            }
            .hero p {
                font-size: 1rem;
            }
            .hero-features {
                gap: 1rem;
            }
            .section-header h2 {
                font-size: 1.8rem;
            }
            .content-grid {
                grid-template-columns: 1fr;
            }
            .plans-grid {
                grid-template-columns: 1fr;
            }
            .devices-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .steps {
                grid-template-columns: 1fr;
            }
            .whatsapp-float {
                width: 50px;
                height: 50px;
                font-size: 1.5rem;
            }
        }

        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <a href="https://wa.me/56995958036?text=Hola%2C%20quiero%20contratar%20TV%20Premium%20CL" class="whatsapp-float" target="_blank">
        <i class="fab fa-whatsapp"></i>
        <span class="tooltip">+56 9 9595 8036</span>
    </a>

    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">
                <i class="fas fa-tv"></i>
                <span>TV Premium <span class="cl">CL</span></span>
            </div>
            <ul class="nav-menu">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#destacado">Contenido</a></li>
                <li><a href="#porque">Beneficios</a></li>
                <li><a href="#planes">Planes</a></li>
                <li><a href="#dispositivos">Dispositivos</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
            <div class="hamburger">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </nav>

    <section id="inicio" class="hero">
        <div class="hero-bg"></div>
        <div class="hero-content">
            <div class="hero-badge animate-up">
                <i class="fas fa-play-circle"></i> Servicio Premium de Streaming
            </div>
            <h1 class="animate-up delay-1">TV PREMIUM CL<br><span class="gradient-text">Televisión Digital Premium</span></h1>
            <p class="animate-up delay-2">Más de 15.000 contenidos entre películas, series, infantil y deportes.</p>
            <div class="hero-features animate-up delay-3">
                <span><i class="fas fa-bolt"></i> Activación inmediata</span>
                <span><i class="fas fa-headset"></i> Soporte 24/7</span>
                <span><i class="fas fa-file-signature"></i> Sin contratos</span>
            </div>
            <div class="hero-buttons animate-up delay-4">
                <a href="#planes" class="btn-primary">Probar Demo <i class="fas fa-arrow-right"></i></a>
                <a href="https://wa.me/56995958036" class="btn-secondary" target="_blank"><i class="fab fa-whatsapp"></i> WhatsApp +56 9 9595 8036</a>
            </div>
        </div>
        <div class="hero-scroll">
            <span>Descubre más</span>
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <section id="destacado" class="featured-content">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">Contenido Destacado</span>
                <h2>Lo mejor del entretenimiento <span class="gradient-text">al alcance de tu mano</span></h2>
            </div>
            <div class="content-grid">
                <div class="content-card"><div class="card-badge">NUEVO</div><i class="fas fa-film"></i><h3>Películas de Estreno</h3><p>Los últimos estrenos de Hollywood y cine internacional disponibles en HD y Full HD.</p><span class="card-tag">Actualizaciones semanales</span></div>
                <div class="content-card"><div class="card-badge">TRENDING</div><i class="fas fa-tv"></i><h3>Series Populares</h3><p>Las series más vistas del momento. Drama, comedia, thriller y mucho más.</p><span class="card-tag">Catálogo completo</span></div>
                <div class="content-card"><div class="card-badge">EN VIVO</div><i class="fas fa-futbol"></i><h3>Deportes en Vivo</h3><p>Todas las ligas de fútbol, NBA, UFC, tenis y más deportes en tiempo real.</p><span class="card-tag">Transmisión 24/7</span></div>
                <div class="content-card"><div class="card-badge">KIDS</div><i class="fas fa-child"></i><h3>Contenido Infantil</h3><p>Caricaturas, películas animadas y programas educativos para toda la familia.</p><span class="card-tag">Contenido seguro</span></div>
                <div class="content-card"><div class="card-badge">HD</div><i class="fas fa-camera"></i><h3>Documentales</h3><p>Naturaleza, historia, ciencia y cultura. Contenido educativo de alta calidad.</p><span class="card-tag">Aprende y disfruta</span></div>
                <div class="content-card"><div class="card-badge">GLOBAL</div><i class="fas fa-globe-americas"></i><h3>Canales Internacionales</h3><p>Más de 2.000 canales de todo el mundo. Noticias, entretenimiento y más.</p><span class="card-tag">Cobertura mundial</span></div>
            </div>
            <div class="stats-row">
                <div class="stat-item"><span class="stat-number">5.000+</span><span class="stat-label">Películas</span></div>
                <div class="stat-item"><span class="stat-number">3.000+</span><span class="stat-label">Series</span></div>
                <div class="stat-item"><span class="stat-number">2.000+</span><span class="stat-label">Canales</span></div>
                <div class="stat-item"><span class="stat-number">5.000+</span><span class="stat-label">Contenido Infantil</span></div>
            </div>
        </div>
    </section>

    <section id="porque" class="why-us">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">¿Por qué elegir TV PREMIUM CL?</span>
                <h2>Todo el entretenimiento que necesitas <span class="gradient-text">en un solo lugar</span></h2>
            </div>
            <div class="benefits-grid">
                <div class="benefit-card"><i class="fas fa-hd"></i><h3>HD & Full HD</h3><p>Más de 2.000 canales nacionales e internacionales con la mejor calidad de imagen.</p></div>
                <div class="benefit-card"><i class="fas fa-film"></i><h3>Películas y Series</h3><p>Estrenos, contenido reciente, infantil y mucho más. Catálogo actualizado constantemente.</p></div>
                <div class="benefit-card"><i class="fas fa-futbol"></i><h3>Deportes y Fútbol en vivo</h3><p>Todas las ligas principales, campeonatos internacionales y repeticiones disponibles.</p></div>
            </div>
            <div class="stats-banner">
                <div class="banner-item"><span class="banner-number">15.000+</span><span class="banner-text">Contenidos</span></div>
                <div class="banner-item"><span class="banner-number">2.000+</span><span class="banner-text">Canales</span></div>
                <div class="banner-item"><span class="banner-number">24/7</span><span class="banner-text">Soporte</span></div>
                <div class="banner-item"><span class="banner-number">100%</span><span class="banner-text">Garantía</span></div>
            </div>
        </div>
    </section>

    <section id="planes" class="plans">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">Planes y Precios</span>
                <h2>Elige el plan que mejor se adapte a <span class="gradient-text">tus necesidades</span></h2>
            </div>
            <div class="plans-grid">
                <div class="plan-card"><div class="plan-icon"><i class="fas fa-tv"></i></div><h3>Plan Básico</h3><div class="plan-duration">1 mes</div><div class="price"><span class="currency">$</span>5.490<span class="period"> CLP</span></div><ul class="plan-features"><li><i class="fas fa-check-circle"></i> Acceso completo</li><li><i class="fas fa-check-circle"></i> 2.000+ canales</li><li><i class="fas fa-check-circle"></i> HD & Full HD</li><li><i class="fas fa-check-circle"></i> Soporte incluido</li></ul><a href="https://wa.me/56995958036?text=Quiero%20contratar%20Plan%20Básico" class="plan-btn" target="_blank">Contratar ahora</a></div>
                <div class="plan-card"><div class="plan-icon"><i class="fas fa-signal"></i></div><h3>Plan Plus</h3><div class="plan-duration">3 meses</div><div class="price"><span class="currency">$</span>14.990<span class="period"> CLP</span></div><ul class="plan-features"><li><i class="fas fa-check-circle"></i> Todo lo del Plan Básico</li><li><i class="fas fa-check-circle"></i> Ahorro del 16%</li><li><i class="fas fa-check-circle"></i> Prioridad en soporte</li><li><i class="fas fa-check-circle"></i> Actualizaciones premium</li></ul><a href="https://wa.me/56995958036?text=Quiero%20contratar%20Plan%20Plus" class="plan-btn" target="_blank">Contratar ahora</a></div>
                <div class="plan-card featured"><div class="recommended-badge">🔥 Más Popular</div><div class="plan-icon"><i class="fas fa-rocket"></i></div><h3>Plan Avanzado</h3><div class="plan-duration">6 meses + 2 GRATIS</div><div class="price"><span class="currency">$</span>25.990<span class="period"> CLP</span></div><ul class="plan-features"><li><i class="fas fa-check-circle"></i> Todo lo del Plan Plus</li><li><i class="fas fa-check-circle"></i> 2 meses de regalo</li><li><i class="fas fa-check-circle"></i> Total 8 meses</li><li><i class="fas fa-check-circle"></i> Soporte prioritario</li></ul><a href="https://wa.me/56995958036?text=Quiero%20contratar%20Plan%20Avanzado" class="plan-btn featured-btn" target="_blank">Contratar ahora</a></div>
                <div class="plan-card"><div class="plan-icon"><i class="fas fa-crown"></i></div><h3>Plan Premium</h3><div class="plan-duration">12 meses + 3 GRATIS</div><div class="price"><span class="currency">$</span>45.990<span class="period"> CLP</span></div><ul class="plan-features"><li><i class="fas fa-check-circle"></i> Todo lo del Plan Avanzado</li><li><i class="fas fa-check-circle"></i> 3 meses de regalo</li><li><i class="fas fa-check-circle"></i> Total 15 meses</li><li><i class="fas fa-check-circle"></i> Soporte VIP 24/7</li></ul><a href="https://wa.me/56995958036?text=Quiero%20contratar%20Plan%20Premium" class="plan-btn" target="_blank">Contratar ahora</a></div>
            </div>
            <div class="payment-methods"><p>Métodos de pago: Transferencia bancaria, Mercado Pago, WebPay</p></div>
        </div>
    </section>

    <section id="dispositivos" class="devices">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">Compatible con todos tus dispositivos</span>
                <h2>Funciona en cualquier dispositivo <span class="gradient-text">con Internet</span></h2>
            </div>
            <div class="devices-grid">
                <div class="device-item"><i class="fas fa-tv"></i><span>Smart TV</span></div>
                <div class="device-item"><i class="fab fa-android"></i><span>Android TV</span></div>
                <div class="device-item"><i class="fab fa-android"></i><span>Android</span></div>
                <div class="device-item"><i class="fab fa-apple"></i><span>iPhone</span></div>
                <div class="device-item"><i class="fas fa-tablet-alt"></i><span>Tablets</span></div>
                <div class="device-item"><i class="fas fa-microchip"></i><span>TV Box</span></div>
                <div class="device-item"><i class="fas fa-laptop"></i><span>PC</span></div>
                <div class="device-item"><i class="fas fa-laptop-code"></i><span>Notebook</span></div>
            </div>
            <div class="requirements">
                <div class="req-card"><i class="fas fa-wifi"></i><h4>Conexión a Internet</h4><p>Mínimo 10 Mbps para HD</p></div>
                <div class="req-card"><i class="fas fa-download"></i><h4>Aplicación</h4><p>Instalación simple y rápida</p></div>
                <div class="req-card"><i class="fas fa-clock"></i><h4>Activación</h4><p>En menos de 3 minutos</p></div>
            </div>
        </div>
    </section>

    <section class="how-to">
        <div class="container">
            <div class="section-header">
                <span class="section-tag">¿Cómo contratar?</span>
                <h2>Proceso simple y rápido <span class="gradient-text">en 4 pasos</span></h2>
            </div>
            <div class="steps">
                <div class="step"><div class="step-number">1</div><h3>Elige tu plan</h3><p>Selecciona el plan que mejor se adapte a tus necesidades y presupuesto.</p></div>
                <div class="step"><div class="step-number">2</div><h3>Envíame un mensaje</h3><p>Contáctame por WhatsApp y te responderé de inmediato.</p></div>
                <div class="step"><div class="step-number">3</div><h3>Recibe tu usuario</h3><p>En menos de 3 minutos tendrás tu acceso listo para usar.</p></div>
                <div class="step"><div class="step-number">4</div><h3>Soporte garantizado</h3><p>Asistencia técnica durante todo el periodo contratado.</p></div>
            </div>
            <div class="cta-banner"><p><i class="fas fa-bolt"></i> Respuesta inmediata • Activación en minutos</p></div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand"><div class="logo"><i class="fas fa-tv"></i><span>TV Premium <span class="cl">CL</span></span></div><p>Televisión Digital Premium. Más de 15.000 contenidos en un solo lugar.</p><div class="social"><a href="#"><i class="fab fa-facebook"></i></a><a href="#"><i class="fab fa-instagram"></i></a><a href="#"><i class="fab fa-twitter"></i></a></div></div>
                <div class="footer-info"><h4>Horario de atención</h4><p>Lunes a Domingo<br>9:00 AM - 11:00 PM</p></div>
                <div class="footer-info"><h4>Soporte técnico</h4><p>Disponible 24/7<br>Respuesta inmediata</p></div>
                <div class="footer-info"><h4>Garantía</h4><p>100% satisfacción<br>Reembolso disponible</p></div>
            </div>
            <div class="legal-notice">
                <h4>Nota Legal</h4>
                <p>No alojamos, almacenamos ni distribuimos contenido audiovisual. Nuestro servicio se limita exclusivamente al soporte técnico y a la configuración de aplicaciones disponibles públicamente. Toda la programación, canales, series y películas son proporcionadas por terceros ajenos a nuestra empresa. No somos responsables del origen, disponibilidad, funcionamiento ni legalidad del contenido entregado por dichos proveedores externos.</p>
            </div>
            <div class="footer-bottom"><p>&copy; 2025 TV Premium CL - Todos los derechos reservados.</p></div>
        </div>
    </footer>

    <script>
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('.nav-menu');
        if (hamburger) {
            hamburger.addEventListener('click', () => {
                navMenu.classList.toggle('active');
            });
        }
        document.querySelectorAll('.nav-menu a').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
            });
        });
        const revealElements = document.querySelectorAll('.content-card, .benefit-card, .plan-card, .device-item, .step, .stat-item, .banner-item, .req-card');
        function checkReveal() {
            revealElements.forEach(el => {
                const windowHeight = window.innerHeight;
                const revealTop = el.getBoundingClientRect().top;
                const revealPoint = 100;
                if (revealTop < windowHeight - revealPoint) {
                    el.classList.add('active');
                }
            });
        }
        revealElements.forEach(el => {
            el.classList.add('reveal');
        });
        window.addEventListener('scroll', checkReveal);
        window.addEventListener('load', checkReveal);
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.background = 'rgba(10, 10, 10, 0.98)';
            } else {
                navbar.style.background = 'rgba(10, 10, 10, 0.95)';
            }
        });
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if(target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
    </script>
</body>
</html>
