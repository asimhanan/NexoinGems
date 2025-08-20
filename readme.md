<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Royal Gems - Trusted Gemstones Dealer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #d4af37;
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-menu a:hover {
            color: #d4af37;
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #d4af37;
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: white;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('gemstones-hero-bg.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            padding: 2rem;
            animation: fadeInUp 1s ease;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
            color: #d4af37;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
        }

        .cta-button {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, #d4af37, #f4d03f);
            color: #333;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.4);
        }

        /* Section Styling */
        .section {
            padding: 80px 0;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(45deg, #d4af37, #f4d03f);
        }

        /* Gemstones Section */
        .gemstones {
            background: #f8f9fa;
        }

        .gemstone-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .gemstone-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .gemstone-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .gemstone-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .ruby { background: linear-gradient(45deg, #e74c3c, #c0392b); }
        .sapphire { background: linear-gradient(45deg, #3498db, #2980b9); }
        .emerald { background: linear-gradient(45deg, #27ae60, #229954); }
        .diamond { background: linear-gradient(45deg, #ecf0f1, #bdc3c7); }

        .gemstone-content {
            padding: 1.5rem;
        }

        .gemstone-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .gemstone-content p {
            color: #666;
            line-height: 1.6;
        }

        .price {
            font-size: 1.2rem;
            font-weight: bold;
            color: #d4af37;
            margin-top: 1rem;
        }

        /* About Section */
        .about {
            background: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #555;
        }

        .about-features {
            display: grid;
            gap: 1.5rem;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .feature:hover {
            background: #e9ecef;
            transform: translateX(10px);
        }

        .feature-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #d4af37, #f4d03f);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .contact .section-title {
            color: white;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            background: white;
            box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.3);
        }

        .form-group textarea {
            height: 120px;
            resize: vertical;
        }

        .submit-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(45deg, #d4af37, #f4d03f);
            color: #333;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.4);
        }

        /* Footer */
        .footer {
            background: #1a1a1a;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Animations */
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

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: rgba(0, 0, 0, 0.95);
                width: 100%;
                text-align: center;
                transition: 0.3s;
                padding: 2rem 0;
            }

            .nav-menu.active {
                left: 0;
            }

            .mobile-menu {
                display: flex;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .gemstone-grid {
                grid-template-columns: 1fr;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .nav-container {
                padding: 0 1rem;
            }

            .container {
                padding: 0 1rem;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            .section {
                padding: 60px 0;
            }

            .contact-form {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="#home" class="logo">Royal Gems</a>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Royal Gems</h1>
            <p>Trusted Gemstones Dealer</p>
            <p>Discover the world's finest precious stones, carefully selected for their exceptional quality, authenticity, and natural beauty.</p>
            <a href="#products" class="cta-button">Explore Our Collection</a>
        </div>
    </section>

    <!-- Gemstones Section -->
    <section id="products" class="section gemstones">
        <div class="container">
            <h2 class="section-title">Our Premium Gemstones</h2>
            <div class="gemstone-grid">
                <div class="gemstone-card">
                    <div class="gemstone-image ruby">💎</div>
                    <div class="gemstone-content">
                        <h3>Ruby</h3>
                        <p>The king of precious stones, rubies symbolize passion and power. Our collection features the finest Burmese and Thai rubies with exceptional clarity and deep red color.</p>
                        <div class="price">Starting from $2,500</div>
                    </div>
                </div>
                <div class="gemstone-card">
                    <div class="gemstone-image sapphire">💎</div>
                    <div class="gemstone-content">
                        <h3>Sapphire</h3>
                        <p>Renowned for their stunning blue hues, our sapphires come from the legendary mines of Kashmir and Ceylon, offering unmatched brilliance and durability.</p>
                        <div class="price">Starting from $1,800</div>
                    </div>
                </div>
                <div class="gemstone-card">
                    <div class="gemstone-image emerald">💎</div>
                    <div class="gemstone-content">
                        <h3>Emerald</h3>
                        <p>The epitome of luxury and elegance, our Colombian emeralds showcase the most vibrant green color with minimal inclusions, perfect for fine jewelry.</p>
                        <div class="price">Starting from $3,200</div>
                    </div>
                </div>
                <div class="gemstone-card">
                    <div class="gemstone-image diamond">💎</div>
                    <div class="gemstone-content">
                        <h3>Diamond</h3>
                        <p>Timeless and brilliant, our diamonds are ethically sourced and certified, featuring exceptional cut, clarity, and carat weight for maximum sparkle.</p>
                        <div class="price">Starting from $4,500</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
        <div class="container">
            <h2 class="section-title">About Royal Gems</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>For over three decades, Royal Gems has been the premier destination for discerning collectors and jewelry enthusiasts seeking the world's finest gemstones. Our commitment to excellence, authenticity, and ethical sourcing has established us as a trusted name in the industry.</p>
                    
                    <p>Every gemstone in our collection is carefully hand-selected by our expert gemologists, ensuring that only stones of exceptional quality and beauty reach our clients. We maintain direct relationships with mines and suppliers worldwide, guaranteeing the authenticity and provenance of each precious stone.</p>
                    
                    <p>Our state-of-the-art facility features advanced testing equipment and certification processes, providing our customers with complete confidence in their investment. Whether you're seeking a centerpiece for a custom jewelry design or adding to your collection, Royal Gems offers unparalleled expertise and service.</p>
                </div>
                <div class="about-features">
                    <div class="feature">
                        <div class="feature-icon">🔍</div>
                        <div>
                            <h4>Certified Authenticity</h4>
                            <p>Every gemstone comes with detailed certification from internationally recognized laboratories.</p>
                        </div>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">🌍</div>
                        <div>
                            <h4>Ethical Sourcing</h4>
                            <p>We maintain strict ethical standards and work only with responsible suppliers worldwide.</p>
                        </div>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">⭐</div>
                        <div>
                            <h4>Expert Curation</h4>
                            <p>Our master gemologists personally select each stone for exceptional quality and beauty.</p>
                        </div>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">🛡️</div>
                        <div>
                            <h4>Lifetime Guarantee</h4>
                            <p>We stand behind every gemstone with our comprehensive lifetime authenticity guarantee.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact">
        <div class="container">
            <h2 class="section-title">Contact Us</h2>
            <form class="contact-form" onsubmit="handleSubmit(event)">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" placeholder="Tell us about your gemstone interests or any questions you may have..." required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2024 Royal Gems. All rights reserved. | Trusted Gemstones Dealer Since 1990</p>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        function toggleMenu() {
            const navMenu = document.querySelector('.nav-menu');
            navMenu.classList.toggle('active');
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
                // Close mobile menu if open
                document.querySelector('.nav-menu').classList.remove('active');
            });
        });

        // Form submission handler
        function handleSubmit(event) {
            event.preventDefault();
            const formData = new FormData(event.target);
            const name = formData.get('name');
            const email = formData.get('email');
            const message = formData.get('message');
            
            // Simple form validation and feedback
            if (name && email && message) {
                alert(`Thank you, ${name}! Your message has been received. We'll contact you at ${email} within 24 hours.`);
                event.target.reset();
            } else {
                alert('Please fill in all required fields.');
            }
        }

        // Navbar background change on scroll
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.background = 'rgba(0, 0, 0, 0.95)';
            } else {
                navbar.style.background = 'rgba(0, 0, 0, 0.9)';
            }
        });

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all cards and features for animation
        document.querySelectorAll('.gemstone-card, .feature').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>

