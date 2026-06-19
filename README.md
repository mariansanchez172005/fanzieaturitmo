<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>No tienes que tener todo resuelto - Marian Sánchez Flores</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400..700;1,400..700&family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
    
    <style>
        /* CSS RESET & VARIABLES */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        :root {
            --color-black: #1E1E1E;
            --color-cream: #FAF8F5;
            --color-yellow: #F5E45A;
            --color-blue: #D6E2F0;
            --color-lila: #D7B8E8;
            --color-grey: #CFCFD4;
            --font-title: 'Sour Gummy', sans-serif;
            --font-body: 'Lora', serif;
        }

        body {
            font-family: var(--font-body);
            background-color: var(--color-cream);
            color: var(--color-black);
            line-height: 1.6;
            overflow-x: hidden;
            /* Fondo decorativo que emula de manera limpia manchas abstractas */
            background-image: 
                radial-gradient(circle at 10% 15%, rgba(214, 226, 240, 0.4) 0%, transparent 20%),
                radial-gradient(circle at 85% 20%, rgba(215, 184, 232, 0.4) 0%, transparent 25%),
                radial-gradient(circle at 90% 75%, rgba(245, 228, 90, 0.3) 0%, transparent 20%),
                radial-gradient(circle at 15% 85%, rgba(207, 207, 212, 0.4) 0%, transparent 20%);
            background-attachment: fixed;
        }

        /* TIPOGRAFÍAS */
        h1, h2, h3, .nav-links a, .btn-primary {
            font-family: var(--font-title);
            font-weight: 600;
        }

        /* HEADER & NAVEGACIÓN */
        header {
            position: sticky;
            top: 0;
            background-color: rgba(250, 248, 245, 0.9);
            backdrop-filter: blur(5px);
            z-index: 1000;
            border-bottom: 2px dashed var(--color-grey);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            display: table;
            width: 100%;
        }

        .nav-logo {
            display: table-cell;
            vertical-align: middle;
            font-family: var(--font-title);
            font-size: 1.4rem;
            color: var(--color-black);
            text-decoration: none;
        }

        .nav-links {
            display: table-cell;
            text-align: right;
            vertical-align: middle;
        }

        .nav-links a {
            color: var(--color-black);
            text-decoration: none;
            margin-left: 25px;
            font-size: 1.1rem;
            position: relative;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #555;
        }

        .nav-links a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 4px;
            background-color: var(--color-lila);
            border-radius: 2px;
        }

        /* ELEMENTOS COMUNES */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 10%;
            width: 80%;
            height: 8px;
            background-color: var(--color-yellow);
            z-index: -1;
            border-radius: 4px;
        }

        /* HERO SECTION */
        .hero {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .grid-hero {
            display: table;
            width: 100%;
            table-layout: fixed;
        }

        .col-hero-left {
            display: table-cell;
            width: 55%;
            vertical-align: middle;
            padding-right: 40px;
            position: relative;
        }

        .col-hero-right {
            display: table-cell;
            width: 45%;
            vertical-align: middle;
            padding-left: 20px;
        }

        /* Maquetación del Mockup Visual */
        .mockup-container {
            position: relative;
            width: 100%;
            height: 380px;
        }

        .mockup-book {
            position: absolute;
            width: 240px;
            height: 290px;
            background-color: #fff;
            border: 3px solid var(--color-black);
            box-shadow: 12px 12px 0px rgba(0,0,0,0.08);
            transform: rotate(-10deg);
            top: 30px;
            left: 20px;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
        }

        .mockup-envelope {
            position: absolute;
            width: 260px;
            height: 220px;
            background-color: #fff;
            border: 3px solid var(--color-black);
            box-shadow: 15px 15px 0px rgba(0,0,0,0.05);
            transform: rotate(12deg);
            top: 70px;
            right: 40px;
            border-radius: 4px;
            padding: 20px;
        }

        .tag-autor {
            margin-top: 25px;
            font-size: 1.1rem;
            font-weight: bold;
            color: var(--color-black);
        }

        .hero-tagline {
            font-size: 2.2rem;
            line-height: 1.3;
            margin-bottom: 25px;
            color: var(--color-black);
        }

        .btn-primary {
            display: inline-block;
            background-color: var(--color-lila);
            color: var(--color-black);
            padding: 15px 35px;
            font-size: 1.3rem;
            text-decoration: none;
            border: 3px solid var(--color-black);
            border-radius: 12px;
            box-shadow: 5px 5px 0px var(--color-black);
            transition: all 0.2s ease;
            cursor: pointer;
        }

        .btn-primary:hover {
            transform: translate(-2px, -2px);
            box-shadow: 7px 7px 0px var(--color-black);
        }

        /* SOBRE EL PROYECTO */
        .sobre-proyecto {
            background-color: rgba(214, 226, 240, 0.4); 
            border-top: 2px dashed var(--color-grey);
            border-bottom: 2px dashed var(--color-grey);
        }

        .sobre-content {
            display: table;
            width: 100%;
        }

        .sobre-text {
            display: table-cell;
            width: 60%;
            vertical-align: middle;
            padding-right: 40px;
            font-size: 1.15rem;
        }

        .sobre-text p {
            margin-bottom: 20px;
        }

        .sobre-features {
            display: table-cell;
            width: 40%;
            vertical-align: middle;
        }

        .feature-box {
            background: #fff;
            padding: 20px;
            border: 2px solid var(--color-black);
            border-radius: 8px;
            margin-bottom: 15px;
            box-shadow: 4px 4px 0px var(--color-grey);
        }

        .feature-box h3 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }

        /* GALERÍA / INTERIOR DEL FANZIE */
        .gallery-grid {
            display: block;
            text-align: center;
        }

        .gallery-item {
            display: inline-block;
            width: 31%;
            margin: 1%;
            background-color: #fff;
            border: 2px solid var(--color-black);
            border-radius: 8px;
            padding: 10px;
            box-shadow: 5px 5px 0px rgba(0,0,0,0.05);
            vertical-align: top;
        }

        .gallery-placeholder {
            width: 100%;
            height: 220px;
            background-color: var(--color-grey);
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #555;
            font-size: 0.9rem;
            font-style: italic;
        }

        .gallery-item p {
            margin-top: 10px;
            font-size: 0.95rem;
        }

        /* TIENDA */
        .tienda-section {
            background-color: rgba(245, 228, 90, 0.15); 
            border-top: 2px dashed var(--color-grey);
            border-bottom: 2px dashed var(--color-grey);
        }

        .product-card {
            background: #fff;
            border: 3px solid var(--color-black);
            border-radius: 16px;
            max-width: 750px;
            margin: 0 auto;
            box-shadow: 8px 8px 0px var(--color-black);
            display: table;
            width: 100%;
            overflow: hidden;
        }

        .product-img-col {
            display: table-cell;
            width: 45%;
            background-color: var(--color-blue);
            vertical-align: middle;
            text-align: center;
            padding: 40px 20px;
        }

        .product-info-col {
            display: table-cell;
            width: 55%;
            padding: 40px;
            vertical-align: middle;
        }

        .price {
            font-family: var(--font-title);
            font-size: 2rem;
            margin: 15px 0;
        }

        .price span {
            background-color: var(--color-yellow);
            padding: 2px 8px;
            border-radius: 4px;
        }

        .product-meta {
            margin-top: 20px;
            font-size: 0.9rem;
            color: #666;
            border-top: 1px solid #ddd;
            padding-top: 15px;
        }

        /* FOOTER & REDES SOCIALES */
        footer {
            background-color: var(--color-black);
            color: var(--color-cream);
            padding: 60px 20px;
            text-align: center;
        }

        .footer-title {
            font-family: var(--font-title);
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--color-lila);
        }

        .footer-text {
            font-size: 1.05rem;
            max-width: 600px;
            margin: 0 auto 30px auto;
            opacity: 0.9;
        }

        .social-links a {
            display: inline-block;
            color: var(--color-black);
            background-color: var(--color-cream);
            width: 45px;
            height: 45px;
            line-height: 45px;
            border-radius: 50%;
            margin: 0 10px;
            font-family: var(--font-title);
            font-weight: bold;
            text-decoration: none;
            transition: transform 0.2s, background-color 0.2s;
        }

        .social-links a:hover {
            transform: scale(1.1);
            background-color: var(--color-yellow);
        }

        .copyright {
            margin-top: 40px;
            font-size: 0.85rem;
            opacity: 0.6;
            border-top: 1px solid #444;
            padding-top: 20px;
        }

        /* RESPONSIVO MÓVIL (Media Queries) */
        @media screen and (max-width: 768px) {
            .nav-container, .nav-logo, .nav-links {
                display: block;
                text-align: center;
                width: 100%;
            }
            .nav-links {
                margin-top: 15px;
            }
            .nav-links a {
                margin: 0 10px;
                font-size: 1rem;
            }

            .grid-hero, .col-hero-left, .col-hero-right,
            .sobre-content, .sobre-text, .sobre-features,
            .product-card, .product-img-col, .product-info-col {
                display: block;
                width: 100% !important;
                padding-left: 0 !important;
                padding-right: 0 !important;
            }

            .col-hero-left {
                margin-bottom: 40px;
            }

            .mockup-container {
                height: 320px;
                max-width: 400px;
                margin: 0 auto;
            }
            .mockup-book {
                width: 180px;
                height: 220px;
            }
            .mockup-envelope {
                width: 200px;
                height: 170px;
                top: 60px;
                right: 10px;
            }

            .hero-tagline {
                font-size: 1.6rem;
                text-align: center;
            }
            .hero-text-box {
                text-align: center;
            }

            .section-title {
                font-size: 2rem;
            }

            .gallery-item {
                width: 94%;
                margin: 15px 3%;
            }

            .product-info-col, .product-img-col {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="nav-container">
            <a href="#" class="nav-logo">Marian S.F.</a>
            <nav class="nav-links">
                <a href="#" class="active">Inicio</a>
                <a href="#fanzie">El fanzie</a>
                <a href="#sobre-el-proyecto">Sobre el proyecto</a>
                <a href="#tienda">Tienda</a>
                <a href="#contacto">Contacto</a>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="grid-hero">
            <div class="col-hero-left">
                <div class="mockup-container">
                    <div class="mockup-book">
                        <div style="border: 1px dashed var(--color-grey); height: 100%; padding: 10px; background-image: radial-gradient(var(--color-grey) 1px, transparent 1px); background-size: 10px 10px;">
                            <span style="font-size: 0.8rem; text-transform: uppercase;">Fanzie Ilustrado</span>
                            <h2 style="font-size: 1.3rem; margin-top: 15px; line-height: 1.1;">No tienes que tener <span style="background-color: var(--color-yellow); padding: 0 4px;">todo</span> resuelto</h2>
                        </div>
                    </div>
                    <div class="mockup-envelope">
                        <div style="border-top: 2px dashed var(--color-lila); margin-top: 40px; text-align: center; padding-top: 20px;">
                            <div style="width: 50px; height: 50px; background-color: var(--color-blue); border-radius: 50%; margin: 0 auto 10px auto;"></div>
                            <p style="font-size: 0.75rem;">Proceso & Crecimiento</p>
                        </div>
                    </div>
                </div>
                <div class="tag-autor" style="text-align: center;">
                    <p style="font-family: var(--font-body); font-weight: normal; font-style: italic; color: #666;">Una obra por:</p>
                    <p style="font-size: 1.3rem;">Marian Sánchez Flores</p>
                </div>
            </div>

            <div class="col-hero-right">
                <div class="hero-text-box">
                    <h1 class="hero-tagline">Un fanzie ilustrado para jóvenes que están aprendiendo a crecer sin tener todas las respuestas.</h1>
                    <div style="margin-top: 35px;">
                        <a href="#tienda" class="btn-primary">Descubrir el proyecto &rarr;</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="container" id="fanzie">
        <h2 class="section-title">Hojas del Fanzie</h2>
        <p style="text-align: center; max-width: 600px; margin: -20px auto 40px auto; font-size: 1.1rem; color: #555;">
            Un vistazo al interior de las páginas cargadas de arte lineal, reflexiones sutiles y espacios de auto-descubrimiento.
        </p>
        
        <div class="gallery-grid">
            <div class="gallery-item">
                <div class="gallery-placeholder">
                    <span>[ Inserta aquí: foto_fanzie_1.jpg ]</span>
                </div>
                <p><b>Aceptar tu proceso:</b> Ilustraciones sobre el tiempo y la paciencia personal.</p>
            </div>
            <div class="gallery-item">
                <div class="gallery-placeholder">
                    <span>[ Inserta aquí: foto_fanzie_2.jpg ]</span>
                </div>
                <p><b>Herramientas creativas:</b> Arte interactivo y dinámicas visuales.</p>
            </div>
            <div class="gallery-item">
                <div class="gallery-placeholder">
                    <span>[ Inserta aquí: foto_fanzie_3.jpg ]</span>
                </div>
                <p><b>Detalles del empaque:</b> Calidad de impresión sobre papel de alta gama.</p>
            </div>
        </div>
    </section>

    <section class="sobre-proyecto" id="sobre-el-proyecto">
        <div class="container">
            <h2 class="section-title">Sobre el Proyecto</h2>
            <div class="sobre-content">
                <div class="sobre-text">
                    <p><b>"No tienes que tener todo resuelto"</b> nace como un refugio visual y literario para esos momentos de transición donde la incertidumbre parece ganarle al futuro.</p>
                    <p>A través de una narrativa gráfica honesta, limpia y sumamente cuidada, Marian Sánchez Flores explora los pilares de la salud mental, la auto-compasión y la evolución artística. No pretende ser una guía definitiva, sino un recordatorio amigable de que crecer es un camino flexible y personal.</p>
                </div>
                <div class="sobre-features">
                    <div class="feature-box">
                        <h3>🎨 Enfoque Creativo</h3>
                        <p style="font-size: 0.95rem; color:#444;">Ilustraciones conceptuales detalladas bajo una estética contemporánea y madura.</p>
                    </div>
                    <div class="feature-box">
                        <h3>🌱 Introspección Sana</h3>
                        <p style="font-size: 0.95rem; color:#444;">Contenido pensado para validar tus emociones sin presiones de productividad.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="tienda-section" id="tienda">
        <div class="container">
            <h2 class="section-title">Lleva tu Fanzie</h2>
            <div class="product-card">
                <div class="product-img-col">
                    <div style="border: 2px dashed var(--color-black); background: #fff; padding: 40px 10px; border-radius: 8px;">
                        <span style="font-family: var(--font-title); font-size: 1.2rem; display: block;">EDICIÓN IMPRESA</span>
                        <div style="width: 70px; height: 70px; background-color: var(--color-yellow); border-radius: 50%; margin: 15px auto; border: 2px solid var(--color-black);"></div>
                        <p style="font-size: 0.85rem; color:#555;">Incluye sobre protector y set de stickers.</p>
                    </div>
                </div>
                <div class="product-info-col">
                    <h3 style="font-family: var(--font-title); font-size: 1.8rem;">Fanzie Físico + Kit de Crecimiento</h3>
                    <p style="margin-top: 10px;">Consigue la edición impresa limitada. Cada ejemplar viene empaquetado individualmente con materiales de primera calidad.</p>
                    <div class="price">
                        <span>$250 MXN</span>
                    </div>
                    <button class="btn-primary" style="width: 100%; margin-top: 10px; font-size: 1.1rem;" onclick="alert('¡Enlace de pago simulado! Aquí puedes colocar tu link de PayPal, Stripe o Mercado Pago.')">
                        🛒 Comprar Ahora
                    </button>
                    <div class="product-meta">
                        <p>📍 Envíos disponibles a toda la república.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer id="contacto">
        <div class="container" style="padding: 0;">
            <h2 class="footer-title">Marian Sánchez Flores</h2>
            <p class="footer-text">Gracias por acompañarme en este espacio de crecimiento. Si quieres conocer más de mi portafolio, escribirme una duda o seguir mis procesos diarios, te espero en redes.</p>
            <div class="social-links">
                <a href="https://instagram.com" target="_blank" title="Instagram">IG</a>
                <a href="https://behance.net" target="_blank" title="Behance">Bh</a>
                <a href="mailto:tu-correo@ejemplo.com" title="Correo">✉</a>
            </div>
            <p class="copyright">&copy; 2026 Marian Sánchez Flores. Todos los derechos reservados.</p>
        </div>
    </footer>

</body>
</html>
