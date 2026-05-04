# Hygieclean
Safe public washroom 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HygieClean - Smart Washroom Solutions</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { 
            font-family: 'Poppins', sans-serif; 
            line-height: 1.6; 
            color: #333;
            overflow-x: hidden;
        }
        
        /* Adorable Gradient Background */
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(135deg, #e3f2fd 0%, #f3e5f5 50%, #e8f5e8 100%);
            z-index: -1;
        }
        
        /* Header */
        header {
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: fixed; width: 100%; top: 0; z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }
        nav { max-width: 1200px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center; padding: 0 2rem; }
        .logo { font-size: 1.8rem; font-weight: 700; background: linear-gradient(45deg, #2196f3, #ff4081); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .nav-links { display: flex; list-style: none; gap: 2rem; }
        .nav-links a { color: #333; text-decoration: none; font-weight: 500; transition: color 0.3s; }
        .nav-links a:hover { color: #ff4081; }
        .cta-btn { background: linear-gradient(45deg, #4caf50, #81c784); color: white; padding: 0.8rem 2rem; border-radius: 50px; text-decoration: none; font-weight: 600; transition: transform 0.3s; }
        .cta-btn:hover { transform: scale(1.05); }
        
        /* Hero Section */
        .hero {
            height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; padding: 0 2rem; position: relative;
        }
        .hero-content h1 { 
            font-size: clamp(2.5rem, 5vw, 4rem); font-weight: 700; margin-bottom: 1rem; 
            background: linear-gradient(45deg, #2196f3, #ff4081); -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        .hero p { font-size: 1.3rem; margin-bottom: 2rem; color: #555; max-width: 600px; }
        .hero-stats { display: flex; justify-content: center; gap: 3rem; margin-top: 2rem; flex-wrap: wrap; }
        .stat { text-align: center; }
        .stat i { font-size: 2.5rem; color: #4caf50; margin-bottom: 0.5rem; animation: bounce 2s infinite; }
        @keyframes bounce { 0%, 20%, 50%, 80%, 100% { transform: translateY(0); } 40% { transform: translateY(-10px); } 60% { transform: translateY(-5px); } }
        
        /* Features Section */
        .features { padding: 5rem 2rem; max-width: 1200px; margin: 0 auto; }
        .section-title { text-align: center; font-size: 2.5rem; margin-bottom: 3rem; color: #333; }
        .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .feature-card {
            background: rgba(255,255,255,0.9); padding: 2rem; border-radius: 20px; text-align: center; box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s; position: relative; overflow: hidden;
        }
        .feature-card::before {
            content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent); transition: 0.5s;
        }
        .feature-card:hover::before { left: 100%; }
        .feature-card:hover { transform: translateY(-10px); box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
        .feature-icon { font-size: 3rem; margin-bottom: 1rem; }
        .feature-card:nth-child(1) .feature-icon { color: #2196f3; }
        .feature-card:nth-child(2) .feature-icon { color: #ff9800; }
        .feature-card:nth-child(3) .feature-icon { color: #4caf50; }
        .feature-card:nth-child(4) .feature-icon { color: #9c27b0; }
        .feature-card:nth-child(5) .feature-icon { color: #f44336; }
        .feature-card:nth-child(6) .feature-icon { color: #00bcd4; }
        
        /* Tech Features */
        .feature-card h3 { font-size: 1.5rem; margin-bottom: 1rem; }
        .feature-card p { color: #666; }
        
        /* Contact */
        .contact { padding: 5rem 2rem; background: rgba(255,255,255,0.5); text-align: center; }
        .contact form { max-width: 600px; margin: 2rem auto; display: flex; flex-direction: column; gap: 1rem; }
        .contact input, .contact textarea { padding: 1rem; border: 2px solid #e0e0e0; border-radius: 10px; font-family: inherit; transition: border 0.3s; }
        .contact input:focus, .contact textarea:focus { outline: none; border-color: #2196f3; }
        .submit-btn { background: linear-gradient(45deg, #ff4081, #f48fb1); color: white; padding: 1rem; border: none; border-radius: 10px; font-size: 1.1rem; font-weight: 600; cursor: pointer; transition: transform 0.3s; }
        .submit-btn:hover { transform: scale(1.02); }
        
        /* Footer */
        footer { background: rgba(51,51,51,0.9); color: white; text-align: center; padding: 2rem; }
        
        /* Responsive */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero-stats { gap: 1rem; }
            .features-grid { grid-template-columns: 1fr; }
        }
        
        /* Floating bubbles animation */
        .bubble { position: absolute; border-radius: 50%; background: rgba(255,255,255,0.3); animation: float 6s infinite; }
        .bubble:nth-child(1) { width: 80px; height: 80px; left: 10%; animation-delay: 0s; }
        .bubble:nth-child(2) { width: 50px; height: 50px; right: 10%; animation-delay: 2s; }
        .bubble:nth-child(3) { width: 120px; height: 120px; left: 20%; animation-delay: 4s; }
        @keyframes float { 0%, 100% { transform: translateY(0px) rotate(0deg); } 50% { transform: translateY(-20px) rotate(180deg); } }
    </style>
</head>
<body>
    <!-- Floating Bubbles -->
    <div class="bubble" style="top: 20%;"></div>
    <div class="bubble" style="top: 60%;"></div>
    <div class="bubble" style="top: 80%;"></div>
    
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">🧼 HygieClean</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <a href="#contact" class="cta-btn">Get Quote</a>
        </nav>
    </header>

    <!-- Hero -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Smart Washrooms, Sparkling Clean! ✨</h1>
            <p>Touchless technology meets adorable design. Hygienic, sustainable, and 100% public-friendly solutions for modern spaces.</p>
            <div class="hero-stats">
                <div class="stat">
                    <i class="fas fa-shield-alt"></i>
                    <h3>99.9% Germ-Free</h3>
                </div>
                <div class="stat">
                    <i class="fas fa-bolt"></i>
                    <h3>Touchless Tech</h3>
                </div>
                <div class="stat">
                    <i class="fas fa-leaf"></i>
                    <h3>100% Eco-Friendly</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Features -->
    <section id="features" class="features">
        <h2 class="section-title">🌟 Cutting-Edge Technology Features</h2>
        <div class="features-grid">
            <div class="feature-card">
                <i class="fas fa-hand-paper feature-icon"></i>
                <h3>Touchless Everything</h3>
                <p>Sensor-activated faucets, doors, soap dispensers. Zero contact, maximum hygiene.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-eye feature-icon"></i>
                <h3>AI Cleanliness Monitor</h3>
                <p>Smart cameras detect dirt instantly. Auto-alerts cleaning teams 24/7.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-tint feature-icon"></i>
                <h3>UV-C Disinfection</h3>
                <p>Ultraviolet light kills 99.99% germs on surfaces every hour. Chemical-free!</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-wind feature-icon"></i>
                <h3>Smart Ventilation</h3>
                <p>Air quality sensors adjust airflow. Fresh, odor-free air always.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-mobile-alt feature-icon"></i>
                <h3>Usage Analytics</h3>
                <p>Real-time data dashboard. Optimize cleaning schedules, reduce waste.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-recycle feature-icon"></i>
                <h3>Water-Saving Tech</h3>
                <p>50% less water usage. Eco-sensors + low-flow systems = planet-friendly.</p>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="contact">
        <h2 class="section-title">Ready for Sparkling Clean? 🧽</h2>
        <p style="font-size: 1.2rem; margin-bottom: 2rem;">Get your free consultation today!</p>
        <form>
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <input type="tel" placeholder="Phone Number">
            <textarea rows="5" placeholder="Tell us about your space..." required></textarea>
            <button type="submit" class="submit-btn">Get Free Quote <i class="fas fa-paper-plane"></i></button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 HygieClean. Making washrooms adorable, hygienic & smart. | <a href="#" style="color: #ccc;">Privacy Policy</a></p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Form submission (demo)
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you! Your quote request has been sent. We\'ll contact you in 24 hours! ✨');
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            document.querySelector('header').style.background = window.scrollY > 100 ? 'rgba(255,255,255,0.98)' : 'rgba(255,255,255,0.95)';
        });
    </script>
</body>
</html>
