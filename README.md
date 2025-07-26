<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kalay Portfolio</title>
  <style>
    :root {
      --primary: #a3aeea;
      --text-dark: #222;
      --text-light: #fff;
      --accent: #000;
      --muted: #f6f6fa;
      --gray: #888;
      --radius: 18px;
      --transition: 0.3s cubic-bezier(.4, 2, .6, 1);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      background: #fff;
      color: var(--text-dark);
      line-height: 1.6;
    }

    header {
      background: #fff;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .navbar {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.2rem 2rem;
    }

    .navbar .logo {
      font-size: 1.6rem;
      font-weight: bold;
      letter-spacing: 1px;
    }

    .navbar nav a {
      color: var(--text-dark);
      text-decoration: none;
      margin-left: 2rem;
      font-size: 1.1rem;
      transition: color var(--transition);
    }

    .navbar nav a:hover {
      color: var(--primary);
    }

    .hero {
      background: url('https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=1200&q=80') center/cover no-repeat;
      min-height: 60vh;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
    }

    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background: rgba(60, 80, 180, 0.35);
      z-index: 1;
    }

    .hero-content {
      position: relative;
      z-index: 2;
      text-align: center;
      color: var(--text-light);
      max-width: 700px;
      margin: 0 auto;
    }

    .hero-content h1 {
      font-size: 2.8rem;
      font-weight: bold;
      margin-bottom: 1rem;
    }

    .hero-content p {
      font-size: 1.2rem;
      margin-bottom: 2rem;
    }

    .hero-content .btn {
      background: var(--accent);
      color: var(--text-light);
      border: none;
      padding: 0.9rem 2.2rem;
      border-radius: 30px;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background var(--transition), color var(--transition);
    }

    .hero-content .btn:hover {
      background: var(--primary);
      color: var(--accent);
    }

    .services {
      background: #fff;
      padding: 4rem 1rem 2rem 1rem;
      text-align: center;
    }

    .services h2 {
      font-size: 2rem;
      margin-bottom: 0.5rem;
      font-weight: 600;
    }

    .services>p {
      color: var(--gray);
      margin-bottom: 2.5rem;
    }

    .service-list {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      margin-bottom: 1rem;
    }

    .service {
      background: var(--muted);
      border-radius: var(--radius);
      flex: 1 1 220px;
      min-width: 220px;
      max-width: 260px;
      padding: 2.2rem 1.2rem 1.6rem 1.2rem;
      box-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);
      transition: background var(--transition), color var(--transition), box-shadow var(--transition);
      display: flex;
      flex-direction: column;
      align-items: center;
      cursor: pointer;
      color: var(--text-dark);
      position: relative;
    }

    .service .icon {
      font-size: 2.5rem;
      margin-bottom: 1.1rem;
      color: var(--primary);
      transition: color var(--transition);
    }

    .service h3 {
      font-size: 1.2rem;
      font-weight: 500;
      margin-bottom: 0.7rem;
    }

    .service p {
      font-size: 1rem;
      color: var(--gray);
    }

    .service.active,
    .service:hover {
      background: var(--accent);
      color: var(--text-light);
      box-shadow: 0 4px 24px rgba(0, 0, 0, 0.10);
    }

    .service.active .icon,
    .service:hover .icon {
      color: var(--text-light);
    }

    .about {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      gap: 3rem;
      padding: 4rem 1rem 2rem 1rem;
      background: #fff;
    }

    .about-img {
      flex: 0 0 260px;
      max-width: 260px;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 2px 16px rgba(0, 0, 0, 0.07);
    }

    .about-img img {
      width: 100%;
      display: block;
    }

    .about-content {
      flex: 1 1 320px;
      max-width: 600px;
    }

    .about-content h2 {
      font-size: 2rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .about-content h4 {
      color: var(--gray);
      font-weight: 400;
      margin-bottom: 1.2rem;
    }

    .about-content p {
      color: var(--text-dark);
      margin-bottom: 1.5rem;
    }

    .about-social {
      display: flex;
      gap: 1.2rem;
      margin-top: 1rem;
    }

    .about-social a {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      background: var(--muted);
      border-radius: 50%;
      color: var(--accent);
      font-size: 1.2rem;
      text-decoration: none;
      transition: background var(--transition), color var(--transition);
    }

    .about-social a:hover {
      background: var(--primary);
      color: var(--text-light);
    }

    .gallery {
      background: #fff;
      padding: 4rem 1rem 2rem 1rem;
      text-align: center;
    }

    .gallery h2 {
      font-size: 2rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .gallery>p {
      color: var(--gray);
      margin-bottom: 2.5rem;
    }

    .gallery-list {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
    }

    .gallery-item {
      background: var(--muted);
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: 0 2px 12px rgba(0, 0, 0, 0.04);
      flex: 1 1 260px;
      min-width: 220px;
      max-width: 320px;
      transition: transform var(--transition), box-shadow var(--transition);
      cursor: pointer;
    }

    .gallery-item img {
      width: 100%;
      display: block;
      aspect-ratio: 1/1;
      object-fit: cover;
      transition: transform var(--transition);
    }

    .gallery-item:hover {
      transform: translateY(-10px) scale(1.03);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.13);
    }

    .gallery-item:hover img {
      transform: scale(1.07);
    }

    .contact {
      background: #fff;
      padding: 4rem 1rem 2rem 1rem;
      display: flex;
      flex-wrap: wrap;
      gap: 3rem;
      justify-content: center;
      align-items: flex-start;
    }

    .contact-form {
      flex: 1 1 320px;
      max-width: 400px;
    }

    .contact-form h2 {
      font-size: 2rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .contact-form>p {
      color: var(--gray);
      margin-bottom: 2rem;
    }

    .contact-form form {
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
    }

    .contact-form input,
    .contact-form textarea {
      padding: 0.8rem 1rem;
      border: none;
      border-bottom: 2px solid var(--muted);
      background: #fafbfc;
      border-radius: 6px 6px 0 0;
      font-size: 1rem;
      resize: none;
      transition: border-color var(--transition);
    }

    .contact-form input:focus,
    .contact-form textarea:focus {
      outline: none;
      border-bottom: 2px solid var(--primary);
    }

    .contact-form button {
      background: var(--accent);
      color: var(--text-light);
      border: none;
      padding: 0.9rem 2.2rem;
      border-radius: 30px;
      font-size: 1.1rem;
      cursor: pointer;
      margin-top: 1rem;
      transition: background var(--transition), color var(--transition);
    }

    .contact-form button:hover {
      background: var(--primary);
      color: var(--accent);
    }

    .contact-info {
      flex: 1 1 260px;
      max-width: 340px;
    }

    .contact-info h3 {
      font-size: 1.3rem;
      font-weight: 600;
      margin-bottom: 1rem;
    }

    .contact-info p {
      color: var(--gray);
      margin-bottom: 1.2rem;
    }

    .contact-info ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    .contact-info li {
      display: flex;
      align-items: center;
      gap: 0.7rem;
      margin-bottom: 0.7rem;
      color: var(--text-dark);
      font-size: 1rem;
    }

    .contact-info li .icon {
      font-size: 1.1rem;
      color: var(--primary);
    }

    footer {
      background: var(--primary);
      color: var(--text-light);
      text-align: center;
      padding: 2rem 1rem 1.2rem 1rem;
      margin-top: 2rem;
    }

    .footer-social {
      display: flex;
      justify-content: center;
      gap: 1.2rem;
      margin: 1.2rem 0 0.5rem 0;
    }

    .footer-social a {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      background: #fff;
      border-radius: 50%;
      color: var(--accent);
      font-size: 1.2rem;
      text-decoration: none;
      transition: background var(--transition), color var(--transition);
    }

    .footer-social a:hover {
      background: var(--accent);
      color: var(--text-light);
    }

    @media (max-width: 900px) {

      .about,
      .contact {
        flex-direction: column;
        gap: 2rem;
        align-items: stretch;
      }

      .service-list,
      .gallery-list {
        gap: 1.2rem;
      }
    }

    @media (max-width: 600px) {
      .navbar {
        flex-direction: column;
        gap: 0.7rem;
        padding: 1rem 0.5rem;
      }

      .hero-content h1 {
        font-size: 2rem;
      }

      .about-img {
        max-width: 100%;
      }

      .service-list,
      .gallery-list {
        flex-direction: column;
        gap: 1.2rem;
      }

      .service,
      .gallery-item {
        max-width: 100%;
      }

      .contact {
        padding: 2rem 0.5rem;
      }

      .about,
      .gallery,
      .services {
        padding: 2rem 0.5rem;
      }
    }
  </style>

</head>

<body>
  <header>
    <div class="navbar">
      <div class="logo">Kalay</div>
      <nav>
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#services">Blog</a>
        <a href="#gallery">Designs</a>
        <a href="#contact">Contact Us</a>
      </nav>
    </div>
  </header>
  <section class="hero" id="home">
    <div class="hero-content">
      <h1>Hello, I am Kalay.</h1>
      <p>Praesent eleifend tristique nisl, nec finibus urna posuere nec. Quisque vel nunc eget arcu maximus facilisis
        non eu nisi. Aliquam ullamcorper est a nisl imperdiet luctus. imperdiet luctus.</p>
      <button class="btn">Discover More</button>
    </div>
  </section>
  <section class="services" id="services">
    <h2>what things i am doing...</h2>
    <p>Lorem ipsum dolor sit amet, consectetur venenatis tincidunt.</p>
    <div class="service-list">
      <div class="service">
        <span class="icon">😊</span>
        <h3>Graphic Design</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing morbi venenatis.</p>
      </div>
      <div class="service active">
        <span class="icon">

          <svg width="32" height="32" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="6" y="10" width="20" height="14" rx="3" stroke="currentColor" stroke-width="2" />
            <circle cx="16" cy="17" r="4" stroke="currentColor" stroke-width="2" />
            <rect x="12" y="6" width="8" height="4" rx="2" stroke="currentColor" stroke-width="2" />
          </svg>
        </span>
        <h3>Photography</h3>
        <p>Duis sed arcu sed nunc maximus tempor. Maecenas et enim laoreet, pharetra risus vel.</p>
      </div>
      <div class="service">
        <span class="icon">💡</span>
        <h3>Graphic Design</h3>
        <p>Sed tristique, nunc sit amet pellentesque pharetra, sapien urna.</p>
      </div>
      <div class="service">
        <span class="icon">

          <svg width="32" height="32" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="8" y="8" width="16" height="16" rx="4" stroke="currentColor" stroke-width="2" />
            <rect x="12" y="12" width="8" height="8" rx="2" stroke="currentColor" stroke-width="2" />
          </svg>
        </span>
        <h3>illustration</h3>
        <p>Cras ut urna quis nisi luctus molestie tincidunt sed ipsum. Donec gravida laoreet erat.</p>
      </div>
    </div>
  </section>
  <section class="about" id="about">
    <div class="about-img">
      <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=400&q=80"
        alt="Kalay profile">
    </div>
    <div class="about-content">
      <h2>a little more about Kalay</h2>
      <h4>Graphic Designer, Creative Photographer & Front-end Developer</h4>
      <p>Praesent eleifend tristique nisl, nec finibus urna posuere nec. Quisque vel nunc eget arcu maximus facilisis
        non eu nisi. Aliquam ullamcorper est a nisl imperdiet luctus. Sed sed convallis odio. Nulla scelerisque libero
        efficitur diam fermentum, quis tincidunt urna placerat. Maecenas sed tortor sed nisi semper ultricies. Nulla
        ornare metus in massa mollis scelerisque.</p>
      <div class="about-social">
        <a href="#" title="Facebook"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M22 12c0-5.522-4.477-10-10-10S2 6.478 2 12c0 4.991 3.657 9.128 8.438 9.877v-6.987h-2.54v-2.89h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.242 0-1.632.771-1.632 1.562v1.875h2.773l-.443 2.89h-2.33v6.987C18.343 21.128 22 16.991 22 12z" />
          </svg></a>
        <a href="#" title="Twitter"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M24 4.557a9.93 9.93 0 0 1-2.828.775 4.932 4.932 0 0 0 2.165-2.724c-.951.564-2.005.974-3.127 1.195a4.92 4.92 0 0 0-8.384 4.482C7.691 8.095 4.066 6.13 1.64 3.161c-.542.929-.856 2.01-.857 3.17 0 2.188 1.115 4.117 2.823 5.247a4.904 4.904 0 0 1-2.229-.616c-.054 2.281 1.581 4.415 3.949 4.89a4.936 4.936 0 0 1-2.224.084c.627 1.956 2.444 3.377 4.6 3.417A9.867 9.867 0 0 1 0 19.54a13.94 13.94 0 0 0 7.548 2.209c9.057 0 14.009-7.496 14.009-13.986 0-.21-.005-.423-.015-.633A9.936 9.936 0 0 0 24 4.557z" />
          </svg></a>
        <a href="#" title="Instagram"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M12 2.163c3.204 0 3.584.012 4.85.07 1.366.062 2.633.334 3.608 1.308.974.974 1.246 2.241 1.308 3.608.058 1.266.069 1.646.069 4.85s-.012 3.584-.07 4.85c-.062 1.366-.334 2.633-1.308 3.608-.974.974-2.241 1.246-3.608 1.308-1.266.058-1.646.069-4.85.069s-3.584-.012-4.85-.07c-1.366-.062-2.633-.334-3.608-1.308-.974-.974-1.246-2.241-1.308-3.608C2.175 15.647 2.163 15.267 2.163 12s.012-3.584.07-4.85c.062-1.366.334-2.633 1.308-3.608.974-.974 2.241-1.246 3.608-1.308C8.416 2.175 8.796 2.163 12 2.163zm0-2.163C8.741 0 8.332.013 7.052.072 5.775.131 4.602.425 3.635 1.392 2.668 2.359 2.374 3.532 2.315 4.809 2.256 6.089 2.243 6.498 2.243 12c0 5.502.013 5.911.072 7.191.059 1.277.353 2.45 1.32 3.417.967.967 2.14 1.261 3.417 1.32 1.28.059 1.689.072 7.191.072s5.911-.013 7.191-.072c1.277-.059 2.45-.353 3.417-1.32.967-.967 1.261-2.14 1.32-3.417.059-1.28.072-1.689.072-7.191s-.013-5.911-.072-7.191c-.059-1.277-.353-2.45-1.32-3.417C21.45.425 20.277.131 19 .072 17.721.013 17.312 0 14.053 0h-4.106z" />
            <circle cx="12" cy="12" r="3.5" />
          </svg></a>
        <a href="#" title="Behance"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
            <path
              d="M22.162 9.656c-1.019 0-1.803.334-2.353.998-.551.664-.826 1.664-.826 2.998 0 1.334.275 2.334.826 2.998.55.664 1.334.998 2.353.998 1.019 0 1.803-.334 2.353-.998.551-.664.826-1.664.826-2.998 0-1.334-.275-2.334-.826-2.998-.55-.664-1.334-.998-2.353-.998zm0 5.334c-.55 0-.963-.184-1.238-.553-.275-.369-.413-.953-.413-1.749 0-.796.138-1.38.413-1.749.275-.369.688-.553 1.238-.553.55 0 .963.184 1.238.553.275.369.413.953.413 1.749 0 .796-.138 1.38-.413 1.749-.275.369-.688.553-1.238.553zM8.5 10.5c0-.796-.138-1.38-.413-1.749-.275-.369-.688-.553-1.238-.553-.55 0-.963.184-1.238.553-.275.369-.413.953-.413 1.749 0 .796.138 1.38.413 1.749.275.369.688.553 1.238.553.55 0 .963-.184 1.238-.553.275-.369.413-.953.413-1.749zm-2.5 0c0-.796.138-1.38.413-1.749.275-.369.688-.553 1.238-.553.55 0 .963.184 1.238.553.275.369.413.953.413 1.749 0 .796-.138 1.38-.413 1.749-.275.369-.688.553-1.238.553-.55 0-.963-.184-1.238-.553-.275-.369-.413-.953-.413-1.749zM0 12c0-5.522 4.477-10 10-10s10 4.478 10 10-4.477 10-10 10S0 17.522 0 12zm2 0c0 4.418 3.582 8 8 8s8-3.582 8-8-3.582-8-8-8-8 3.582-8 8z" />
          </svg></a>
      </div>
    </div>
  </section>
  <section class="gallery" id="gallery">
    <h2>Seleted Designs</h2>
    <p>Lorem ipsum dolor sit amet, consectetur venenatis tincidunt.</p>
    <div class="gallery-list">
      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=400&q=80"
          alt="Donuts">
      </div>
      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1465101046530-73398c7f28ca?auto=format&fit=crop&w=400&q=80"
          alt="Cactus">
      </div>
      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=400&q=80"
          alt="Coffee cup">
      </div>
    </div>
  </section>
  <section class="contact" id="contact">
    <div class="contact-form">
      <h2>Get in touch</h2>
      <p>Lorem ipsum dolor sit amet, consectetur venenatis tincidunt.</p>
      <form id="contactForm" autocomplete="off">
        <input type="text" id="name" name="name" placeholder="Name" required>
        <input type="email" id="email" name="email" placeholder="Email" required>
        <textarea id="message" name="message" rows="4" placeholder="Message" required></textarea>
        <button type="submit">Send Message</button>
        <div id="formMessage" style="display:none;margin-top:1rem;"></div>
      </form>
    </div>
    <div class="contact-info">
      <h3>Contact Info</h3>
      <p>Lorem ipsum sit consectetur adipiscing morbi venenatis et tortor consectetur adipiscing lacinia tortor morbi
        ultricies.</p>
      <ul>
        <li><span class="icon">📍</span> 456 New Street 22000, New York City, USA</li>
        <li><span class="icon">✉️</span> info@company.com</li>
        <li><span class="icon">📞</span> 0109988742</li>
      </ul>
    </div>
  </section>
  <footer>
    <div>Copyright © 2024 Your Company | Design: By Moharam</div>
    <div class="footer-social">
      <a href="#" title="Facebook"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
          <path
            d="M22 12c0-5.522-4.477-10-10-10S2 6.478 2 12c0 4.991 3.657 9.128 8.438 9.877v-6.987h-2.54v-2.89h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.242 0-1.632.771-1.632 1.562v1.875h2.773l-.443 2.89h-2.33v6.987C18.343 21.128 22 16.991 22 12z" />
        </svg></a>
      <a href="#" title="Twitter"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
          <path
            d="M24 4.557a9.93 9.93 0 0 1-2.828.775 4.932 4.932 0 0 0 2.165-2.724c-.951.564-2.005.974-3.127 1.195a4.92 4.92 0 0 0-8.384 4.482C7.691 8.095 4.066 6.13 1.64 3.161c-.542.929-.856 2.01-.857 3.17 0 2.188 1.115 4.117 2.823 5.247a4.904 4.904 0 0 1-2.229-.616c-.054 2.281 1.581 4.415 3.949 4.89a4.936 4.936 0 0 1-2.224.084c.627 1.956 2.444 3.377 4.6 3.417A9.867 9.867 0 0 1 0 19.54a13.94 13.94 0 0 0 7.548 2.209c9.057 0 14.009-7.496 14.009-13.986 0-.21-.005-.423-.015-.633A9.936 9.936 0 0 0 24 4.557z" />
        </svg></a>
      <a href="#" title="Instagram"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
          <path
            d="M12 2.163c3.204 0 3.584.012 4.85.07 1.366.062 2.633.334 3.608 1.308.974.974 1.246 2.241 1.308 3.608.058 1.266.069 1.646.069 4.85s-.012 3.584-.07 4.85c-.062 1.366-.334 2.633-1.308 3.608-.974.974-2.241 1.246-3.608 1.308-1.266.058-1.646.069-4.85.069s-3.584-.012-4.85-.07c-1.366-.062-2.633-.334-3.608-1.308-.974-.974-1.246-2.241-1.308-3.608C2.175 15.647 2.163 15.267 2.163 12s.012-3.584.07-4.85c.062-1.366.334-2.633 1.308-3.608.974-.974 2.241-1.246 3.608-1.308C8.416 2.175 8.796 2.163 12 2.163zm0-2.163C8.741 0 8.332.013 7.052.072 5.775.131 4.602.425 3.635 1.392 2.668 2.359 2.374 3.532 2.315 4.809 2.256 6.089 2.243 6.498 2.243 12c0 5.502.013 5.911.072 7.191.059 1.277.353 2.45 1.32 3.417.967.967 2.14 1.261 3.417 1.32 1.28.059 1.689.072 7.191.072s5.911-.013 7.191-.072c1.277-.059 2.45-.353 3.417-1.32.967-.967 1.261-2.14 1.32-3.417.059-1.28.072-1.689.072-7.191s-.013-5.911-.072-7.191c-.059-1.277-.353-2.45-1.32-3.417C21.45.425 20.277.131 19 .072 17.721.013 17.312 0 14.053 0h-4.106z" />
          <circle cx="12" cy="12" r="3.5" />
        </svg></a>
      <a href="#" title="Behance"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
          <path
            d="M22.162 9.656c-1.019 0-1.803.334-2.353.998-.551.664-.826 1.664-.826 2.998 0 1.334.275 2.334.826 2.998.55.664 1.334.998 2.353.998 1.019 0 1.803-.334 2.353-.998.551-.664.826-1.664.826-2.998 0-1.334-.275-2.334-.826-2.998-.55-.664-1.334-.998-2.353-.998zm0 5.334c-.55 0-.963-.184-1.238-.553-.275-.369-.413-.953-.413-1.749 0-.796.138-1.38.413-1.749.275-.369.688-.553 1.238-.553.55 0 .963.184 1.238.553.275.369.413.953.413 1.749 0 .796-.138 1.38-.413 1.749-.275.369-.688.553-1.238.553zM8.5 10.5c0-.796-.138-1.38-.413-1.749-.275-.369-.688-.553-1.238-.553-.55 0-.963.184-1.238.553-.275.369-.413.953-.413 1.749 0 .796.138 1.38.413 1.749.275.369.688.553 1.238.553.55 0 .963-.184 1.238-.553.275-.369.413-.953.413-1.749zm-2.5 0c0-.796.138-1.38.413-1.749.275-.369.688-.553 1.238-.553.55 0 .963.184 1.238.553.275.369.413.953.413 1.749 0 .796-.138 1.38-.413 1.749-.275.369-.688.553-1.238.553-.55 0-.963-.184-1.238-.553-.275-.369-.413-.953-.413-1.749zM0 12c0-5.522 4.477-10 10-10s10 4.478 10 10-4.477 10-10 10S0 17.522 0 12zm2 0c0 4.418 3.582 8 8 8s8-3.582 8-8-3.582-8-8-8-8 3.582-8 8z" />
        </svg></a>
      <a href="#" title="GitHub"><svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
          <path
            d="M12 2C6.477 2 2 6.484 2 12.021c0 4.428 2.865 8.186 6.839 9.504.5.092.682-.217.682-.482 0-.237-.009-.868-.014-1.703-2.782.605-3.369-1.342-3.369-1.342-.454-1.157-1.11-1.465-1.11-1.465-.908-.62.069-.608.069-.608 1.004.07 1.532 1.032 1.532 1.032.892 1.53 2.341 1.088 2.91.832.091-.647.35-1.088.636-1.339-2.221-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.025A9.564 9.564 0 0 1 12 6.844c.85.004 1.705.115 2.504.337 1.909-1.295 2.748-1.025 2.748-1.025.546 1.378.202 2.397.1 2.65.64.7 1.028 1.595 1.028 2.688 0 3.847-2.337 4.695-4.566 4.944.359.309.678.919.678 1.852 0 1.336-.012 2.417-.012 2.747 0 .267.18.579.688.481C19.138 20.204 22 16.447 22 12.021 22 6.484 17.523 2 12 2z" />
        </svg></a>
    </div>
  </footer>
  <script>

    document.getElementById('contactForm').addEventListener('submit', function (e) {
      e.preventDefault();
      var name = document.getElementById('name').value.trim();
      var email = document.getElementById('email').value.trim();
      var message = document.getElementById('message').value.trim();
      var formMessage = document.getElementById('formMessage');
      if (!name || !email || !message) {
        formMessage.style.display = 'block';
        formMessage.style.color = 'red';
        formMessage.textContent = 'Please fill in all fields.';
        return;
      }

      var emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailPattern.test(email)) {
        formMessage.style.display = 'block';
        formMessage.style.color = 'red';
        formMessage.textContent = 'Please enter a valid email address.';
        return;
      }
      formMessage.style.display = 'block';
      formMessage.style.color = 'green';
      formMessage.textContent = 'Thank you for contacting us! We will get back to you soon.';
      this.reset();
    });
  </script>
</body>

</html>
