<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Travel Scout | Современные путешествия</title>
    <style>
        :root {
            --primary-color: #2a9d8f;
            --secondary-color: #e9c46a;
            --accent-color: #f4a261;
            --dark-bg: #264653;
            --light-bg: #f8f9fa;
            --text-dark: #2c3e2f;
            --text-light: #ffffff;
            --font-main: 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            --shadow-sm: 0 8px 20px rgba(0,0,0,0.05);
            --transition-default: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-main);
            background-color: var(--light-bg);
            color: var(--text-dark);
            line-height: 1.5;
        }

        .header {
            background: var(--dark-bg);
            color: var(--text-light);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .nav-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            list-style: none;
            flex-wrap: wrap;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition-default);
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0%;
            height: 2px;
            background: var(--secondary-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::before {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--secondary-color);
        }

        .hero {
            background: linear-gradient(135deg, #2a9d8f, #264653);
            color: white;
            text-align: center;
            padding: 5rem 2rem;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 0.5rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 1rem auto;
            opacity: 0.9;
        }

        .hero::after {
            font-size: 12rem;
            position: absolute;
            bottom: -40px;
            right: 10px;
            opacity: 0.08;
            pointer-events: none;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .grid-destinations {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .card {
            background: white;
            border-radius: 24px;
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: var(--transition-default);
            position: relative;
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 30px rgba(0,0,0,0.1);
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
        }

        .card-content {
            padding: 1.2rem;
        }

        .card h3 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
        }

        .flex-features {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 2rem;
            margin: 3rem 0;
        }

        .feature-item {
            flex: 1;
            min-width: 180px;
            background: #eef2f1;
            border-radius: 32px;
            padding: 1.5rem;
            text-align: center;
            transition: var(--transition-default);
        }

        .feature-item:hover {
            background: var(--primary-color);
            color: white;
            transform: scale(1.02);
        }

        .feature-item h4 {
            margin-bottom: 0.5rem;
        }

        .subscribe-section {
            background: var(--dark-bg);
            color: white;
            border-radius: 48px;
            padding: 2rem;
            margin: 3rem 0;
            text-align: center;
        }

        .form-group {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .form-group input {
            flex: 1;
            min-width: 220px;
            padding: 0.8rem 1.2rem;
            border: none;
            border-radius: 60px;
            font-size: 1rem;
            background: #fff;
            transition: var(--transition-default);
        }

        .form-group input:focus {
            outline: none;
            box-shadow: 0 0 0 3px var(--secondary-color);
            transform: scale(1.01);
        }

        .form-group input:valid {
            border-left: 4px solid var(--primary-color);
        }

        .form-group button {
            background: var(--secondary-color);
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 60px;
            font-weight: bold;
            color: var(--dark-bg);
            cursor: pointer;
            transition: var(--transition-default);
        }

        .form-group button:hover {
            background: var(--accent-color);
            transform: translateY(-2px);
        }

        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.4rem;
            }
            .grid-destinations {
                gap: 1.5rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
            }
            .hero {
                padding: 3rem 1rem;
            }
            .hero h1 {
                font-size: 1.8rem;
            }
            .flex-features {
                flex-direction: column;
            }
            .form-group {
                flex-direction: column;
                align-items: stretch;
            }
            .form-group button {
                width: 100%;
            }
            .container {
                padding: 1rem;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.5rem;
            }
            .card img {
                height: 160px;
            }
        }

        .card:nth-child(odd) .card-content {
            background: #fffef7;
        }

        .footer {
            background: var(--dark-bg);
            color: #dddddd;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            position: relative;
        }

        .footer a {
            color: var(--secondary-color);
            text-decoration: none;
        }

        .scroll-top {
            position: fixed;
            bottom: 25px;
            right: 25px;
            background: var(--primary-color);
            color: white;
            padding: 10px 14px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            transition: var(--transition-default);
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
            z-index: 99;
        }

        .scroll-top:hover {
            background: var(--accent-color);
            transform: scale(1.05);
        }
    </style>
</head>
<body>

<header class="header">
    <nav>
        <ul class="nav-links">
            <li><a href="#home">Главная</a></li>
            <li><a href="#destinations">Направления</a></li>
            <li><a href="#features">Преимущества</a></li>
            <li><a href="#subscribe">Подписка</a></li>
        </ul>
    </nav>
</header>

<main>
    <section id="home" class="hero">
        <h1>Travel Scout</h1>
        <p>Откройте мир с комфортом — уникальные маршруты, лучшие гиды и яркие впечатления.</p>
        <p style="font-size: 0.95rem;"> Путешествуйте осознанно, отдыхайте ярко</p>
    </section>

    <div class="container">
        <section id="destinations">
            <h2 style="color: var(--primary-color); margin-bottom: 1rem;">🌍 Популярные направления</h2>
            <div class="grid-destinations">
                <article class="card">
                    <img src="https://avatars.mds.yandex.net/i?id=beb39e3fa7949d9e550bc3098873b494_l-5231332-images-thumbs&n=13" alt="Пляж с бирюзовой водой" loading="lazy">
                    <div class="card-content">
                        <h3>Мальдивы</h3>
                        <p>Белый песок, лагуны, идеальный отдых для души.</p>
                        <span><strong>от 300 000р</strong></span>
                    </div>
                </article>
                <article class="card">
                    <img src="https://i.pinimg.com/originals/56/fc/fb/56fcfb804e829afd4070b093ff9c0f50.jpg" alt="Горы и альпийские луга" loading="lazy">
                    <div class="card-content">
                        <h3>Швейцарские Альпы</h3>
                        <p>Горные вершины, свежий воздух и незабываемые тропы.</p>
                        <span><strong>от 200 000р</strong></span>
                    </div>
                </article>
                <article class="card">
                    <img src="https://avatars.mds.yandex.net/i?id=03a5146aeb7dfcff5438a24fe3c9eaeb_l-2411671-images-thumbs&n=13" alt="Улицы старого города" loading="lazy">
                    <div class="card-content">
                        <h3>Тоскана, Италия</h3>
                        <p>Виноградники, кухня и искусство Возрождения.</p>
                        <span><strong>от 100 000р</strong></span>
                    </div>
                </article>
                <article class="card">
                    <img src="https://media.gettyimages.com/id/1176802435/photo/tokyo-japan-cityscape-at-tokyo-station.jpg?s=1024x1024&w=gi&k=20&c=rhBrsuZ48Xe5E0LUq0topGOSK-if_-mzqiEzc4RZIAU=" alt="Футуристический мегаполис" loading="lazy">
                    <div class="card-content">
                        <h3>Токио</h3>
                        <p>Технологии, традиции и неоновая эстетика.</p>
                        <span><strong>от 150 000р</strong></span>
                    </div>
                </article>
            </div>
        </section>

        <section id="features">
            <h2 style="color: var(--primary-color); margin-bottom: 1rem;"> Почему выбирают нас</h2>
            <div class="flex-features">
                <div class="feature-item">
                    <h4> Лучшие отели</h4>
                    <p>Проверенные апартаменты и виллы с отзывами.</p>
                </div>
                <div class="feature-item">
                    <h4> Индивидуальные туры</h4>
                    <p>Маршруты под ваш стиль и бюджет.</p>
                </div>
                <div class="feature-item">
                    <h4> Поддержка 24/7</h4>
                    <p>Русскоязычная помощь в любой точке мира.</p>
                </div>
            </div>
        </section>

        <!-- Форма подписки с валидацией и псевдоклассами -->
        <section id="subscribe" class="subscribe-section">
            <h3> Получайте горячие предложения</h3>
            <form action="#" method="post" class="form-group">
                <input type="email" placeholder="Ваш e-mail" required aria-label="Email для подписки">
                <input type="text" placeholder="Как к вам обращаться?" required aria-label="Имя">
                <button type="submit">Подписаться</button>
            </form>
        </section>
    </div>
</main>

<footer class="footer">
    <p>© 2025 Travel Scout</p>
    </p>
    <p style="margin-top: 0.5rem;"> Ваши мечты - наша профессия</p>
</footer>

<a href="#" class="scroll-top" aria-label="Наверх">↑ Наверх</a>

</body>
</html>
