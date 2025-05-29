<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FONG | Cambodian Music Artist</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #D4AF37;
            --dark-gold: #B8860B;
            --black: #0A0A0A;
            --dark-gray: #1A1A1A;
            --light-gray: #F5F5F5;
            --white: #FFFFFF;
            --transition: all 0.5s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--black);
            color: var(--white);
            overflow-x: hidden;
            line-height: 1.7;
            perspective: 1000px; /* Added for 3D effect */
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center; /* Center content vertically */
            flex-direction: column; /* Align title and content */
            padding: 8rem 0;
            position: relative;
            overflow: hidden;
        }

        .section-title {
            font-size: 3.5rem;
            margin-bottom: 4rem;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 0;
            width: 80px;
            height: 4px;
            background: var(--gold);
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: transparent;
            color: var(--white);
            border: 2px solid var(--gold);
            border-radius: 0;
            text-decoration: none;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.9rem;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: var(--gold);
            transition: width 0.5s ease;
            z-index: -1;
        }

        .btn:hover::before {
            width: 100%;
        }

        .btn:hover {
            color: var(--black);
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 0;
            z-index: 1000;
            transition: var(--transition);
        }

        nav.scrolled {
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--gold);
            text-decoration: none;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2.5rem;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            padding: 0.5rem 0;
            transition: var(--transition);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--gold);
        }

        /* Hero Section */
        #hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('images/hero-bg.jpg') center/cover no-repeat;
            background-attachment: fixed;
        }

        .hero-content {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
        }

        .hero-title {
            font-size: 5.5rem;
            margin-bottom: 1.5rem;
            line-height: 1.1;
        }

        .hero-subtitle {
            font-size: 1.8rem;
            font-weight: 300;
            margin-bottom: 2.5rem;
            color: var(--gold);
        }

        .hero-text {
            font-size: 1.2rem;
            margin-bottom: 3rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        /* About Section */
        #about {
            background: var(--dark-gray) url('images/about-bg.jpg') center/cover;
            position: relative;
        }

        #about::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(26, 26, 26, 0.9);
            z-index: 1;
        }

        #about .container {
            position: relative;
            z-index: 2;
        }
        
        .about-container {
            display: flex;
            align-items: center;
            gap: 5rem;
        }
        
        .about-image {
            flex: 1;
            position: relative;
        }

        .about-image-grid {
            position: relative;
            width: 100%;
            height: auto; 
            margin-top: 2rem;
            display: grid; 
            grid-template-columns: 1fr;
            gap: 1.5rem; 
        }

        .about-image-grid img {
            width: 100%;
            height: auto;
            object-fit: cover;
            border: 3px solid var(--gold);
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            transition: transform 0.3s ease-in-out;
            position: relative; 
        }

        @media (min-width: 769px) {
            .about-image-grid {
                height: 450px; 
                gap: 0; 
            }
            .about-image-grid img {
                position: absolute; 
            }
            .about-image-grid .about-img-1 {
                width: 70%;
                top: 0;
                left: 0;
                z-index: 1;
            }
            .about-image-grid .about-img-2 {
                width: 50%;
                bottom: 0;
                right: 0;
                z-index: 2;
            }
            .about-image-grid .about-img-3 {
                width: 40%;
                top: 25%;
                left: 45%;
                z-index: 3;
                transform: rotate(5deg);
            }
            .about-image-grid:hover .about-img-1 {
                transform: translate(-10px, -10px) rotate(-3deg);
            }
            .about-image-grid:hover .about-img-2 {
                transform: translate(10px, 10px) rotate(3deg);
            }
            .about-image-grid:hover .about-img-3 {
                transform: scale(1.1) rotate(0deg);
            }
        }
        
        .about-content {
            flex: 1;
        }
        
        .about-text {
            margin-bottom: 2rem;
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
        }
        
        .khmer-text {
            font-style: italic;
            margin-top: 2rem;
            padding: 1rem;
            border-left: 3px solid var(--gold);
            background: rgba(212, 175, 55, 0.1);
        }
        
        /* Music Section */
        #music {
            /* Make sure you have 'music-bg.jpg' in your images folder, or change the name here */
            background: linear-gradient(rgba(0, 0, 0, 0.85), rgba(0, 0, 0, 0.85)), url('images/music-bg.jpg') center/cover fixed;
        }
        
        .music-header {
            text-align: center;
            margin-bottom: 4rem;
        }
        
        .albums-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
        }
        
        .album-card {
            background: rgba(26, 26, 26, 0.8);
            border: 1px solid rgba(212, 175, 55, 0.3);
            padding: 2rem;
            text-align: center;
            transition: var(--transition);
        }
        
        .album-card:hover {
            transform: translateY(-10px);
            border-color: var(--gold);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .album-cover {
            width: 100%;
            margin-bottom: 1.5rem;
            aspect-ratio: 1/1;
            object-fit: cover;
        }
        
        .album-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--gold);
        }
        
        .album-year {
            font-size: 0.9rem;
            margin-bottom: 1rem;
            opacity: 0.7;
        }
        
        .album-tracks {
            list-style: none;
            margin-bottom: 1.5rem;
            text-align: left;
        }
        
        .album-tracks li {
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Gallery Section */
        #gallery {
            /* Make sure you have 'gallery-bg.jpg' in your images folder, or change the name here */
            background: linear-gradient(rgba(10, 10, 10, 0.9), rgba(10, 10, 10, 0.9)), url('images/gallery-bg.jpg') center/cover no-repeat;
            background-attachment: fixed; 
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
        }
        
        .gallery-item {
            position: relative;
            height: 300px;
            overflow: hidden;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(212, 175, 55, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: var(--transition);
        }
        
        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }
        
        /* Contact Section */
        #contact {
            background: linear-gradient(rgba(10, 10, 10, 0.9), rgba(10, 10, 10, 0.9)), url('images/contact-bg.jpg') center/cover fixed;
        }
        
        .contact-container {
            display: flex;
            gap: 5rem;
        }
        
        .contact-info, .contact-form {
            flex: 1;
        }
        
        .info-item {
            display: flex;
            margin-bottom: 2rem;
            align-items: center;
        }
        
        .info-icon {
            width: 60px;
            height: 60px;
            background: var(--gold);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1.5rem;
            flex-shrink: 0;
        }
        
        .info-content h4 {
            margin-bottom: 0.5rem;
            color: var(--gold);
        }
        
        .social-links {
            display: flex;
            gap: 1.5rem;
            margin-top: 3rem;
        }
        
        .social-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            border: 1px solid var(--gold);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--gold);
            font-size: 1.2rem;
            transition: var(--transition);
        }
        
        .social-icon:hover {
            background: var(--gold);
            color: var(--black);
            transform: translateY(-5px);
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-control {
            width: 100%;
            padding: 1rem;
            background: transparent;
            border: 1px solid rgba(255, 255, 255, 0.2);
            color: var(--white);
            font-family: 'Montserrat', sans-serif;
            font-size: 1rem;
            transition: var(--transition);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--gold);
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: var(--dark-gray);
            padding: 4rem 0 2rem;
            text-align: center;
        }
        
        .footer-logo {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: var(--gold);
            margin-bottom: 1.5rem;
            display: inline-block;
        }
        
        .copyright {
            font-size: 0.9rem;
            opacity: 0.7;
            margin-top: 2rem;
        }
        
        /* NEW 3D Animation on Scroll */
        .scroll-animate {
            opacity: 0;
            transform: rotateY(30deg) scale(0.9);
            transition: all 1s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        .scroll-animate.animate {
            opacity: 1;
            transform: rotateY(0) scale(1);
        }

        /* Responsive */
        @media (max-width: 992px) {
            .about-container,
            .contact-container {
                flex-direction: column;
                gap: 3rem;
                text-align: center;
            }
        
            .section-title {
                font-size: 3rem;
            }
        
            .hero-title {
                font-size: 4rem;
            }
        
            .nav-links li {
                margin-left: 1.5rem;
            }
        
            .admin-panel {
                display: none;
            }
        }
        
        @media (max-width: 768px) {
            .section {
                padding: 6rem 0;
            }
        
            .hero-title {
                font-size: 3rem;
            }
        
            .hero-subtitle {
                font-size: 1.5rem;
            }
        
            .nav-links {
                display: none;
            }
        }
    </style>
</head>

<body>

    <nav id="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">FONG</a>
            <ul class="nav-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#music">Music</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="hero" class="section">
        <div class="container scroll-animate">
            <div class="hero-content">
                <h1 class="hero-title">FONG</h1>
                <h2 class="hero-subtitle">CAMBODIAN MUSIC ARTIST</h2>
                <p class="hero-text">Blending traditional Khmer melodies with contemporary sounds to create a unique musical experience that resonates globally.</p>
                <a href="#music" class="btn">Explore Music</a>
            </div>
        </div>
    </section>

    <section id="about" class="section">
        <div class="container">
            <div class="scroll-animate">
                <h2 class="section-title" style="text-align: center; display: block;">About FONG</h2>
            </div>
            <div class="about-container scroll-animate">
                <div class="about-image">
                    <div class="about-image-grid">
                        <img src="images/about.jpg" alt="A portrait of the artist FONG" class="about-img-1">
                        <img src="images/about-2.jpg" alt="FONG playing a traditional instrument" class="about-img-2">
                        <img src="images/about-1.jpg" alt="FONG on stage" class="about-img-3">
                    </div>
                </div>
                <div class="about-content">
                    <div class="about-text">
                        <p>FONG is a rising artist from Takhmao, Cambodia, known for his heartfelt approach to music and a vision that breaks the mold. From a young age, he stood out — not just for his passion, but for the way he hears music differently. With a sound rooted in emotion and authenticity, FONG creates music that speaks directly to the soul.

What sets him apart is his ability to blend raw feeling with a uniquely creative perspective, turning life experiences into soundscapes that resonate far beyond borders. He's not just an artist — he's a storyteller, a visionary, and a reflection of a new generation of Cambodian talent. With a big heart and a fearless drive, FONG is on a mission to share his voice with the world.</p>
                        <p></p>
                        <div class="khmer-text">
                            <p>FONG គឺជាសិល្បករខ្មែរមួយរូប ពេញដោយទេពកោសល្យ និងចក្ខុវិស័យបែបសិល្បៈបច្ចេកវិទ្យា ដែលបាននាំយកសម្លេងតន្ត្រីសម័យទំនើប រួមបញ្ចូល សម្លេងតន្ត្រីប្រពៃណីខ្មែរ។
FONG មិនត្រឹមតែជាសិល្បករដែលចេះសរសេរបទ និងផលិតបទភ្លេងដោយខ្លួនឯងទេ ប៉ុន្តែគាត់ក៏ជាអ្នកប្រាប់រឿងតាមសម្លេង ម្នាក់ដែលនាំយកអារម្មណ៍ពិតប្រាកដក្នុងជីវិត ប្រកបដោយភាពស្មោះត្រង់ និងច្នៃប្រឌិត។ គាត់ជឿជាក់ថា តន្ត្រីគឺជាភាសាដែលអាចភ្ជាប់មនុស្សគ្រប់គ្នា ពីគ្រប់ជ្រុងជ្រោយពិភពលោក។

បើសិនជាអ្នកស្ដាប់កំពុងស្វែងរកសម្លេងថ្មីៗ ដែលទាក់ទងអារម្មណ៍ និងបញ្ចេញភាពជាខ្លួនឯង ស្នាដៃរបស់FONGនឹងនាំអ្នកទៅរកការចាប់អារម្មណ៍ថ្មីមួយទៀតក្នុងភពតន្ត្រីខ្មែរ។</p>
                        </div>
                    </div>
                    <a href="#" class="btn">View Full Biography</a>
                </div>
            </div>
        </div>
    </section>

    <section id="music" class="section">
        <div class="container">
            <div class="music-header scroll-animate">
                <h2 class="section-title" style="text-align: center; display: block;">Discography</h2>
                <p>A journey through FONG's musical evolution</p>
            </div>
            <div class="albums-grid scroll-animate">
                <div class="album-card">
                    <img src="images/album1.jpg" alt="Album cover for The first" class="album-cover">
                    <h3 class="album-title">The First</h3>
                    <div class="album-year">2025 • Album</div>
                    <a href="#" class="btn">Listen Now</a>
                </div>
                <div class="album-card">
                    <img src="images/album2.jpg" alt="Album cover for Emerald Forest" class="album-cover"> <h3 class="album-title">Emerald Forest</h3>
                    <div class="album-year">2021 • Album</div>
                    <a href="#" class="btn">Listen Now</a>
                </div>
                <div class="album-card">
                    <img src="images/album3.jpg" alt="Album cover for Khmer Soul" class="album-cover">
                    <h3 class="album-title">Khmer Soul</h3>
                    <div class="album-year">2019 • Album</div>
                    <a href="#" class="btn">Listen Now</a>
                </div>
            </div>
        </div>
    </section>

    <section id="gallery" class="section">
        <div class="container scroll-animate"> <h2 class="section-title" style="text-align: center; display: block;">Gallery</h2>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="images/gallery1.jpg" alt="FONG performing live in Siem Reap">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/gallery2.jpg" alt="FONG in the studio">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/gallery3.jpg" alt="Khmer musical instruments">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/gallery4.jpg" alt="FONG at Bonn Om Touk">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/gallery5.jpg" alt="FONG collaborating">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/gallery6.jpg" alt="FONG with award">
                    <div class="gallery-overlay"><h3></h3></div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <div class="scroll-animate">
                <h2 class="section-title" style="text-align: center; display: block;">Contact</h2>
            </div>
            <div class="contact-container scroll-animate">
                <div class="contact-info">
                    <h3>Booking & Management</h3>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-envelope"></i></div>
                        <div class="info-content">
                            <h4>Email</h4>
                            <p>contact@fongmusic.com</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-phone"></i></div>
                        <div class="info-content">
                            <h4>Phone</h4>
                            <p>+855 23 456 7890</p>
                        </div>
                    </div>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-map-marker-alt"></i></div>
                        <div class="info-content">
                            <h4>Location</h4>
                            <p>Phnom Penh, Cambodia</p>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="#" class="social-icon"><i class="fab fa-spotify"></i></a>
                        <a href="#" class="social-icon"><i class="fab fa-apple"></i></a>
                        <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="social-icon"><i class="fab fa-youtube"></i></a>
                        <a href="#" class="social-icon"><i class="fab fa-tiktok"></i></a>
                    </div>
                </div>
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Full Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <a href="#" class="footer-logo">FONG</a>
            <p>Preserving Khmer heritage through contemporary soundscapes</p>
            <p class="copyright">© 2025 FONG Music. All rights reserved. | Phnom Penh, Cambodia</p>
        </div>
    </footer>

    <script>
        // Navigation scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // NEW: Scroll animation for sections
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.25 // Trigger when 25% of the element is visible
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate');
                    observer.unobserve(entry.target); // Optional: stop observing once animated
                }
            });
        }, observerOptions);

        // Observe elements with the .scroll-animate class
        document.querySelectorAll('.scroll-animate').forEach(el => {
            observer.observe(el);
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            });
        });

        // Form submission
        const form = document.querySelector('form');
        if (form) { // Check if the form exists before adding event listener
             form.addEventListener('submit', function(e) {
                e.preventDefault();
                alert('Thank you for your message! FONG will get back to you soon.');
                form.reset();
            });
        }
    </script>
</body>
</html>
