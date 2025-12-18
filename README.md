
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mya's Lash Lab | Luxury Lash Studio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;500;600;700&family=Poppins:wght@300;400;500&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        :root {
            --hot-pink: #FF1493;
            --pink-glow: rgba(255, 20, 147, 0.7);
            --pink-light: rgba(255, 20, 147, 0.15);
            --pink-extra-light: rgba(255, 20, 147, 0.08);
            --black: #000000;
            --dark: #0a0a0a;
            --text-light: #fff;
            --text-gray: #eee;
            --cursive-font: 'Dancing Script', cursive;
            --elegant-font: 'Playfair Display', serif;
            --sans-font: 'Poppins', sans-serif;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
            scroll-padding-top: 80px;
        }
        
        body {
            font-family: var(--sans-font);
            background-color: var(--black);
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        /* FIXED HEADER - CLEAN */
        header {
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            background: rgba(0, 0, 0, 0.9);
            border-bottom: 2px solid transparent;
            padding: 15px 0;
            transition: all 0.3s;
            height: 80px;
            display: flex;
            align-items: center;
            backdrop-filter: blur(10px);
        }
        
        header.scrolled {
            border-bottom: 2px solid var(--hot-pink);
            box-shadow: 0 5px 20px rgba(255, 20, 147, 0.2);
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 40px;
        }
        
        .logo {
            font-family: var(--cursive-font);
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--text-light);
            white-space: nowrap;
            line-height: 1;
        }
        
        .logo span {
            color: var(--hot-pink);
            text-shadow: 0 0 15px var(--pink-glow);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }
        
        .nav-links a {
            font-family: var(--cursive-font);
            font-size: 1.8rem;
            font-weight: 600;
            text-decoration: none;
            color: var(--text-light);
            transition: all 0.3s;
            white-space: nowrap;
            padding: 5px 0;
            position: relative;
        }
        
        .nav-links a:hover {
            color: var(--hot-pink);
            text-shadow: 0 0 10px var(--pink-glow);
        }
        
        .nav-links a.active {
            color: var(--hot-pink);
            text-shadow: 0 0 10px var(--pink-glow);
        }
        
        .nav-links a:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--hot-pink);
            transition: width 0.3s;
        }
        
        .nav-links a:hover:after,
        .nav-links a.active:after {
            width: 100%;
        }
        
        /* HERO SECTION - LIGHT OVERLAY, NO CARDS */
        .hero-section {
            min-height: 100vh;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 100px 40px 40px;
            margin-top: 80px;
            background: var(--black);
            text-align: center;
        }
        
        .hero-image-container {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
            overflow: hidden;
        }
        
        .hero-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
            filter: brightness(0.7);
        }
        
        /* LIGHT LIGHT OVERLAY */
        .hero-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                to bottom,
                rgba(255, 255, 255, 0.1) 0%,
                rgba(255, 255, 255, 0.05) 50%,
                rgba(0, 0, 0, 0.8) 100%
            );
            z-index: 2;
        }
        
        /* HERO CONTENT - NO CARD, DIRECT ON OVERLAY */
        .hero-content {
            max-width: 900px;
            position: relative;
            z-index: 3;
            padding: 60px;
        }
        
        .hero-title {
            font-family: var(--cursive-font);
            font-size: 6rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 30px;
            color: var(--text-light);
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.8);
        }
        
        .hero-title span {
            color: var(--hot-pink);
            text-shadow: 0 0 40px var(--pink-glow), 2px 2px 10px rgba(0, 0, 0, 0.8);
        }
        
        .hero-subtitle {
            font-family: var(--elegant-font);
            font-size: 2rem;
            color: var(--text-light);
            margin-bottom: 40px;
            line-height: 1.7;
            text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
        }
        
        /* SPECIAL BANNER - NO CARD, DIRECT CONTENT */
        .special-banner {
            position: relative;
            padding: 80px 40px;
            margin: 40px 0;
            text-align: center;
            background: linear-gradient(135deg, 
                rgba(255, 20, 147, 0.15) 0%, 
                rgba(255, 20, 147, 0.05) 100%);
            border-top: 3px solid rgba(255, 20, 147, 0.3);
            border-bottom: 3px solid rgba(255, 20, 147, 0.3);
            backdrop-filter: blur(5px);
        }
        
        .special-title {
            font-family: var(--cursive-font);
            font-size: 4.5rem;
            color: var(--hot-pink);
            margin-bottom: 20px;
            text-shadow: 0 0 30px var(--pink-glow);
        }
        
        .special-price {
            font-family: var(--cursive-font);
            font-size: 7rem;
            font-weight: 700;
            color: var(--text-light);
            margin-bottom: 20px;
            text-shadow: 0 0 50px var(--hot-pink);
        }
        
        /* MAIN CONTENT - NO CARDS, DIRECT CONTENT */
        .main-content {
            padding: 60px 40px;
            position: relative;
            background: var(--black);
        }
        
        .section-title {
            font-family: var(--cursive-font);
            font-size: 4.5rem;
            text-align: center;
            margin: 60px 0 40px;
            color: var(--hot-pink);
            text-shadow: 0 0 20px var(--pink-glow);
            position: relative;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--hot-pink), transparent);
        }
        
        /* PRICING - NO CARDS, DIRECT LAYOUT */
        .pricing-list {
            max-width: 800px;
            margin: 50px auto;
            padding: 0;
        }
        
        .price-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 30px 0;
            border-bottom: 1px solid rgba(255, 20, 147, 0.2);
            transition: all 0.3s;
        }
        
        .price-item:hover {
            padding-left: 20px;
            border-bottom-color: var(--hot-pink);
        }
        
        .price-item:last-child {
            border-bottom: none;
        }
        
        .lash-name {
            font-family: var(--cursive-font);
            font-size: 3rem;
            color: var(--text-light);
            text-shadow: 0 0 10px rgba(255, 20, 147, 0.3);
        }
        
        .lash-price {
            font-family: var(--cursive-font);
            font-size: 3.5rem;
            font-weight: 700;
            color: var(--hot-pink);
            text-shadow: 0 0 20px var(--pink-glow);
        }
        
        /* POLICIES - NO CARDS, DIRECT LAYOUT */
        .policies-section {
            max-width: 900px;
            margin: 60px auto;
            padding: 0;
        }
        
        .policy-group {
            margin-bottom: 50px;
            padding: 40px 0;
            border-bottom: 1px solid rgba(255, 20, 147, 0.1);
        }
        
        .policy-group:last-child {
            border-bottom: none;
        }
        
        .policy-title {
            font-family: var(--cursive-font);
            font-size: 3rem;
            color: var(--hot-pink);
            margin-bottom: 30px;
            text-shadow: 0 0 15px var(--pink-glow);
        }
        
        .policy-list {
            list-style: none;
            padding-left: 20px;
        }
        
        .policy-list li {
            font-family: var(--sans-font);
            color: var(--text-gray);
            padding: 15px 0;
            font-size: 1.2rem;
            line-height: 1.7;
            position: relative;
            padding-left: 40px;
        }
        
        .policy-list li:before {
            content: '❀';
            color: var(--hot-pink);
            position: absolute;
            left: 0;
            top: 15px;
            font-size: 1.5rem;
            text-shadow: 0 0 10px var(--hot-pink);
        }
        
        /* BOOKING SECTION - NO CARD, DIRECT STYLING */
        .booking-section {
            position: relative;
            padding: 80px 40px;
            margin: 80px 0;
            background: linear-gradient(135deg, 
                rgba(255, 20, 147, 0.1) 0%, 
                rgba(0, 0, 0, 0.95) 100%);
            border-top: 3px solid var(--hot-pink);
            border-bottom: 3px solid var(--hot-pink);
        }
        
        .booking-title {
            font-family: var(--cursive-font);
            font-size: 4rem;
            color: var(--text-light);
            margin-bottom: 50px;
            text-align: center;
            text-shadow: 0 0 20px var(--hot-pink);
        }
        
        .booking-form {
            max-width: 1000px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
        }
        
        .form-label {
            font-family: var(--cursive-font);
            font-size: 2rem;
            color: var(--hot-pink);
            margin-bottom: 15px;
            text-shadow: 0 0 10px var(--pink-glow);
        }
        
        .form-input, .form-select, .form-textarea {
            padding: 18px;
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid rgba(255, 20, 147, 0.3);
            border-radius: 12px;
            color: var(--text-light);
            font-family: var(--sans-font);
            font-size: 1.1rem;
            transition: all 0.3s;
        }
        
        .form-input:focus, .form-select:focus, .form-textarea:focus {
            outline: none;
            border-color: var(--hot-pink);
            box-shadow: 0 0 30px rgba(255, 20, 147, 0.4);
            background: rgba(0, 0, 0, 0.8);
        }
        
        .form-submit {
            grid-column: 1 / -1;
            background: linear-gradient(45deg, var(--hot-pink), #ff69b4);
            color: black;
            border: none;
            padding: 25px;
            border-radius: 15px;
            font-family: var(--cursive-font);
            font-size: 2.5rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 40px;
            box-shadow: 0 0 40px rgba(255, 20, 147, 0.6);
        }
        
        .form-submit:hover {
            transform: translateY(-8px);
            box-shadow: 0 0 60px rgba(255, 20, 147, 0.9);
            letter-spacing: 2px;
        }
        
        .form-message {
            grid-column: 1 / -1;
            padding: 25px;
            background: rgba(255, 20, 147, 0.1);
            border-radius: 12px;
            border: 2px solid var(--hot-pink);
            margin: 20px 0;
            display: none;
        }
        
        /* FOOTER - DIRECT STYLING */
        footer {
            background: rgba(0, 0, 0, 0.97);
            border-top: 3px solid var(--hot-pink);
            padding: 60px 40px 30px;
            margin-top: 80px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-section {
            flex: 1;
            min-width: 250px;
        }
        
        .footer-title {
            font-family: var(--cursive-font);
            font-size: 2.8rem;
            color: var(--hot-pink);
            margin-bottom: 25px;
            text-shadow: 0 0 15px var(--pink-glow);
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .contact-icon {
            color: var(--hot-pink);
            font-size: 1.5rem;
            text-shadow: 0 0 10px var(--hot-pink);
        }
        
        .contact-text {
            font-family: var(--sans-font);
            color: var(--text-gray);
            font-size: 1.1rem;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 20, 147, 0.3);
            font-family: var(--sans-font);
            color: var(--text-gray);
            font-size: 1.1rem;
        }
        
        /* RESPONSIVE */
        @media (max-width: 1100px) {
            .nav-container {
                padding: 0 30px;
            }
            
            .nav-links {
                gap: 20px;
            }
            
            .nav-links a {
                font-size: 1.6rem;
            }
            
            .logo {
                font-size: 2.2rem;
            }
            
            .hero-title {
                font-size: 5rem;
            }
            
            .special-price {
                font-size: 6rem;
            }
        }
        
        @media (max-width: 900px) {
            .nav-container {
                flex-direction: column;
                gap: 15px;
                padding: 15px;
                height: auto;
                min-height: 80px;
            }
            
            header {
                height: auto;
                min-height: 80px;
                padding: 10px 0;
            }
            
            .hero-section {
                margin-top: 120px;
                padding: 40px 30px;
            }
            
            .nav-links {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .nav-links a {
                font-size: 1.5rem;
                padding: 3px 8px;
            }
            
            .logo {
                font-size: 2rem;
            }
            
            .hero-content {
                padding: 40px 30px;
            }
            
            .hero-title {
                font-size: 4rem;
            }
            
            .special-price {
                font-size: 5rem;
            }
            
            .lash-name {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 768px) {
            .hero-title {
                font-size: 3.5rem;
            }
            
            .section-title {
                font-size: 3.5rem;
            }
            
            .special-title {
                font-size: 3.5rem;
            }
            
            .special-price {
                font-size: 4.5rem;
            }
            
            .main-content {
                padding: 40px 30px;
            }
            
            .hero-section {
                margin-top: 140px;
            }
            
            .price-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
        }
        
        @media (max-width: 600px) {
            .nav-container {
                padding: 10px;
            }
            
            .nav-links {
                gap: 12px;
            }
            
            .nav-links a {
                font-size: 1.4rem;
            }
            
            .logo {
                font-size: 1.8rem;
            }
            
            .hero-title {
                font-size: 3rem;
            }
            
            .hero-section {
                margin-top: 130px;
                padding: 30px 20px;
            }
            
            .booking-form {
                grid-template-columns: 1fr;
            }
            
            .special-banner, .booking-section {
                padding: 60px 25px;
            }
            
            .hero-content {
                padding: 30px 20px;
            }
            
            .lash-name {
                font-size: 2.2rem;
            }
            
            .lash-price {
                font-size: 2.8rem;
            }
        }
        
        @media (max-width: 480px) {
            .nav-links {
                gap: 10px;
            }
            
            .nav-links a {
                font-size: 1.3rem;
            }
            
            .logo {
                font-size: 1.6rem;
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-section {
                margin-top: 120px;
            }
        }
    </style>
</head>
<body>
    <!-- HEADER -->
    <header id="header">
        <div class="nav-container">
            <div class="logo">Mya's <span>Lash Lab</span></div>
            <nav class="nav-links">
                <a href="#home" class="active">Home</a>
                <a href="#pricing">Services</a>
                <a href="#policies">Policies</a>
                <a href="#booking">Booking</a>
            </nav>
        </div>
    </header>
    
    <!-- HERO SECTION - LIGHT OVERLAY, NO CARDS -->
    <section class="hero-section" id="home">
        <div class="hero-image-container">
            <!-- YOUR IMAGE -->
            <img src="https://i.postimg.cc/vHqVsCTT/DE1320C0-441F-4DCA-B88C-366CB77F58A0.jpg" alt="Mya's Lash Lab" class="hero-image">
            <!-- LIGHT LIGHT OVERLAY -->
            <div class="hero-overlay"></div>
        </div>
        <!-- CONTENT DIRECTLY ON OVERLAY -->
        <div class="hero-content">
            <h1 class="hero-title">Welcome to <span>Mya's</span><br>Lash Sanctuary</h1>
            <p class="hero-subtitle">Step into a world of luxury lash artistry where every detail is crafted for perfection. Experience premium extensions in our exclusive studio sanctuary.</p>
        </div>
    </section>
    
    <!-- MAIN CONTENT - NO CARDS -->
    <div class="main-content">
        
        <!-- SPECIAL BANNER - NO CARD -->
        <div class="special-banner">
            <h2 class="special-title">Holiday Magic</h2>
            <div class="special-price">$20</div>
            <p style="font-family: var(--sans-font); font-size: 1.3rem; color: var(--text-light); max-width: 700px; margin: 0 auto; text-shadow: 1px 1px 5px rgba(0,0,0,0.8);">
                Celebrate the season with our exclusive Christmas special! Every lash style at this incredible price. Limited time only—book before December 24th.
            </p>
        </div>
        
        <!-- PRICING - NO CARDS -->
        <h2 class="section-title" id="pricing">Signature Services</h2>
        
        <div class="pricing-list">
            <div class="price-item">
                <div class="lash-name">Classic Natural</div>
                <div class="lash-price">$25</div>
            </div>
            
            <div class="price-item">
                <div class="lash-name">Dramatic Cat Eye</div>
                <div class="lash-price">$35</div>
            </div>
            
            <div class="price-item">
                <div class="lash-name">Textured Hybrid</div>
                <div class="lash-price">$40</div>
            </div>
            
            <div class="price-item">
                <div class="lash-name">Luxury Volume</div>
                <div class="lash-price">$55</div>
            </div>
            
            <div class="price-item">
                <div class="lash-name">Mega Volume</div>
                <div class="lash-price">$60</div>
            </div>
        </div>
        
        <!-- POLICIES - NO CARDS -->
        <h2 class="section-title" id="policies">Studio Experience</h2>
        
        <div class="policies-section">
            <div class="policy-group">
                <h3 class="policy-title">Before Your Visit</h3>
                <ul class="policy-list">
                    <li>Arrive with completely clean lashes and face—free of all makeup, skincare products, and oils</li>
                    <li>Avoid caffeine consumption 3-4 hours before your appointment for optimal comfort</li>
                    <li>Bring your favorite headphones for a personalized, relaxing experience</li>
                    <li>Communicate any allergies or sensitivities before we begin</li>
                    <li>Late arrivals beyond 15 minutes will be rescheduled to maintain quality</li>
                    <li>Photography may be taken for artistic portfolio with expressed consent only</li>
                </ul>
            </div>
            
            <div class="policy-group">
                <h3 class="policy-title">Aftercare Ritual</h3>
                <ul class="policy-list">
                    <li>Avoid all moisture, steam, and humidity for the first 24 hours</li>
                    <li>Gently brush lashes morning and evening with a clean spoolie</li>
                    <li>Cleanse daily with specialized foaming lash shampoo</li>
                    <li>Sleep on your back or side using a silk pillowcase</li>
                    <li>Avoid all oil-based products near the eye area</li>
                    <li>Never pull, pick, or rub your eyelash extensions</li>
                    <li>Schedule infill appointments every 2-3 weeks for maintenance</li>
                    <li>Use only water-based, extension-safe makeup products</li>
                </ul>
            </div>
            
            <div class="policy-group">
                <h3 class="policy-title">Studio Policies</h3>
                <ul class="policy-list">
                    <li>24-hour cancellation notice required for all appointments</li>
                    <li>Infill appointments require at least 40% of extensions remaining</li>
                    <li>First-time clients please arrive 10 minutes early for consultation</li>
                    <li>All services include a detailed aftercare guide and demonstration</li>
                    <li>Patch tests available for clients with sensitivity concerns</li>
                    <li>We maintain the highest sanitation standards with disposable tools</li>
                    <li>Gift certificates available for special occasions</li>
                    <li>Contact for questions: Direct message via preferred platform</li>
                </ul>
            </div>
        </div>
        
        <!-- BOOKING - NO CARD -->
        <div class="booking-section" id="booking">
            <h2 class="booking-title">Reserve Your Session</h2>
            
            <form class="booking-form" id="bookingForm" action="https://getform.io/f/bllgyywb" method="POST">
                <!-- Getform required fields -->
                <input type="hidden" name="_gotcha" style="display:none !important">
                
                <div class="form-group">
                    <label class="form-label" for="name">Full Name</label>
                    <input type="text" id="name" name="name" class="form-input" placeholder="Your full name" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone" class="form-input" placeholder="Your phone number" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="email">Email Address</label>
                    <input type="email" id="email" name="email" class="form-input" placeholder="Your email address">
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="contact">Contact Preference</label>
                    <select id="contact" name="contact_preference" class="form-select" required>
                        <option value="">Preferred contact method</option>
                        <option value="text">Text Message</option>
                        <option value="email">Email</option>
                        <option value="dm">Direct Message</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="service">Lash Service</label>
                    <select id="service" name="service" class="form-select" required>
                        <option value="">Select service</option>
                        <option value="Classic Natural">Classic Natural - $25</option>
                        <option value="Dramatic Cat Eye">Dramatic Cat Eye - $35</option>
                        <option value="Textured Hybrid">Textured Hybrid - $40</option>
                        <option value="Luxury Volume">Luxury Volume - $55</option>
                        <option value="Mega Volume">Mega Volume - $60</option>
                        <option value="Christmas Special">Christmas Special - $20</option>
                        <option value="infill">Infill Appointment</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="date">Preferred Date</label>
                    <input type="date" id="date" name="preferred_date" class="form-input" required>
                </div>
                
                <div class="form-group">
                    <label class="form-label" for="time">Time Preference</label>
                    <select id="time" name="preferred_time" class="form-select" required>
                        <option value="">Select time</option>
                        <option value="9:00 AM">Morning (9:00 AM)</option>
                        <option value="11:00 AM">Late Morning (11:00 AM)</option>
                        <option value="1:00 PM">Afternoon (1:00 PM)</option>
                        <option value="3:00 PM">Mid-Afternoon (3:00 PM)</option>
                        <option value="5:00 PM">Evening (5:00 PM)</option>
                    </select>
                </div>
                
                <div class="form-group" style="grid-column: 1 / -1;">
                    <label class="form-label" for="notes">Special Requests & Notes</label>
                    <textarea id="notes" name="notes" class="form-textarea" rows="4" placeholder="Any preferences, concerns, allergies, or questions..."></textarea>
                </div>
                
                <!-- Form Submission Message -->
                <div class="form-message" id="formMessage" style="display: none;">
                    <p style="font-family: var(--sans-font); color: var(--text-light); text-align: center; font-size: 1.2rem;">
                        <i class="fas fa-check-circle" style="color: var(--hot-pink); margin-right: 10px; font-size: 1.5rem;"></i>
                        <span id="messageText">Thank you! Your booking request has been submitted.</span>
                    </p>
                </div>
                
                <button type="submit" class="form-submit">
                    <i class="fas fa-paper-plane" style="margin-right: 15px;"></i>
                    Submit Booking Request
                </button>
            </form>
            
            <p style="text-align: center; margin-top: 40px; font-family: var(--sans-font); color: var(--text-gray); font-size: 1.1rem;">
                <i class="fas fa-info-circle" style="color: var(--hot-pink); margin-right: 10px;"></i>
                You'll receive a confirmation within 24 hours. For urgent questions, please direct message.
            </p>
        </div>
    </div>
    
    <!-- FOOTER -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3 class="footer-title">Mya's Lash Lab</h3>
                <p style="color: var(--text-gray); font-family: var(--sans-font); font-size: 1.2rem; line-height: 1.7; margin-bottom: 25px;">
                    A sanctuary for luxury lash artistry. Where precision meets passion, and every client receives personalized attention.
                </p>
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt contact-icon"></i>
                        <span class="contact-text">Exclusive Studio by Appointment</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-clock contact-icon"></i>
                        <span class="contact-text">Tuesday - Saturday: 10AM - 7PM</span>
                    </div>
                </div>
            </div>
            
            <div class="footer-section">
                <h3 class="footer-title">Connect</h3>
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-comment-dots contact-icon"></i>
                        <span class="contact-text">Direct message for inquiries</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope-open-text contact-icon"></i>
                        <span class="contact-text">Booking confirmation sent</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-gift contact-icon"></i>
                        <span class="contact-text">Gift certificates available</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 Mya's Lash Lab. All rights reserved.</p>
            <p style="margin-top: 15px; font-size: 1rem; color: rgba(255,255,255,0.6);">Please direct message for any questions or concerns</p>
        </div>
    </footer>
    
    <script>
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Smooth scrolling for navigation
        document.querySelectorAll('.nav-links a').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    // Update active nav link
                    document.querySelectorAll('.nav-links a').forEach(link => {
                        link.classList.remove('active');
                    });
                    this.classList.add('active');
                    
                    // Calculate offset
                    const headerHeight = document.querySelector('header').offsetHeight;
                    const targetPosition = targetElement.offsetTop - headerHeight;
                    
                    // Scroll to target
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Form submission with Getform
        document.getElementById('bookingForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            // Show loading state
            const submitBtn = this.querySelector('.form-submit');
            const originalText = submitBtn.innerHTML;
            submitBtn.innerHTML = '<i class="fas fa-spinner fa-spin" style="margin-right: 15px;"></i> Processing...';
            submitBtn.disabled = true;
            
            // Hide any previous message
            document.getElementById('formMessage').style.display = 'none';
            
            try {
                // Get form data
                const formData = new FormData(this);
                const name = formData.get('name');
                
                // Send to Getform
                const response = await fetch(this.action, {
                    method: 'POST',
                    body: formData,
                    headers: {
                        'Accept': 'application/json'
                    }
                });
                
                if (response.ok) {
                    // Show success message
                    const messageDiv = document.getElementById('formMessage');
                    const messageText = document.getElementById('messageText');
                    messageText.textContent = `Thank you ${name}! Your booking request has been submitted successfully. We'll contact you within 24 hours.`;
                    messageDiv.style.display = 'block';
                    
                    // Reset form
                    this.reset();
                    
                    // Set minimum date to today
                    const today = new Date().toISOString().split('T')[0];
                    document.getElementById('date').setAttribute('min', today);
                    
                    // Scroll to show success message
                    messageDiv.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
                    
                } else {
                    throw new Error('Form submission failed');
                }
                
            } catch (error) {
                // Show error message
                const messageDiv = document.getElementById('formMessage');
                const messageText = document.getElementById('messageText');
                messageText.textContent = 'Oops! There was an issue submitting your request. Please try again or direct message us.';
                messageDiv.style.display = 'block';
                messageDiv.style.background = 'rgba(255, 0, 0, 0.1)';
                messageDiv.style.border = '2px solid #ff0000';
                
            } finally {
                // Reset button state
                submitBtn.innerHTML = originalText;
                submitBtn.disabled = false;
            }
        });
        
        // Set minimum date to today
        const today = new Date().toISOString().split('T')[0];
        document.getElementById('date').setAttribute('min', today);
        
        // Update active nav link on scroll
        window.addEventListener('scroll', function() {
            const sections = document.querySelectorAll('section, .section-title');
            const navLinks = document.querySelectorAll('.nav-links a');
            
            let current = '';
            const headerHeight = document.querySelector('header').offsetHeight;
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                
                if (window.scrollY >= (sectionTop - headerHeight - 100)) {
                    current = section.getAttribute('id');
                }
            });
            
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
