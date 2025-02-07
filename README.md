<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Agri Cultro Gaurav - Sustainable Farming Solutions</title>
  <!-- Google Fonts & Font Awesome -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&family=Open+Sans:wght@300;400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <!-- AOS Animation Library -->
  <link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css" />

  <style>
    :root {
      --primary-green: #5cb85c;
      --secondary-green: #449d44;
      --dark-green: #2d672d;
      --light-bg: #f9f9f9;
      --text-dark: #333;
      --accent: #ff7b29;
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Open Sans', sans-serif;
      line-height: 1.6;
      color: var(--text-dark);
      overflow-x: hidden;
      background: var(--light-bg);
    }
    
    /* Sticky Navigation */
    .nav-container {
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.95);
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      transition: background 0.3s ease;
    }
    
    nav {
      max-width: 1200px;
      margin: 0 auto;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .logo {
      font-family: 'Roboto', sans-serif;
      font-size: 1.8rem;
      color: var(--dark-green);
      font-weight: 700;
      text-decoration: none;
      transition: transform 0.3s ease;
    }
    
    /* Hamburger Menu for Mobile */
    .hamburger {
      display: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--dark-green);
    }
    
    .nav-links {
      display: flex;
      gap: 2rem;
    }
    
    .nav-links a {
      color: var(--text-dark);
      text-decoration: none;
      font-weight: 500;
      position: relative;
      padding: 0.5rem 0;
      transition: color 0.3s ease;
    }
    
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--primary-green);
      transition: width 0.3s ease;
    }
    
    .nav-links a:hover::after {
      width: 100%;
    }
    
    /* Header / Hero Section */
    header {
      background: linear-gradient(rgba(92, 184, 92, 0.85), rgba(44, 103, 45, 0.85)),
        url('https://images.unsplash.com/photo-1625246333195-78d9c38ad449?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80');
      background-size: cover;
      background-position: center;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
      color: #fff;
      padding: 0 2rem;
    }
    
    .hero-content h1 {
      font-size: 3.5rem;
      margin-bottom: 1.5rem;
      text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
      animation: fadeInUp 1s ease-out;
    }
    
    .hero-content p {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      opacity: 0;
      animation: fadeInUp 1s ease-out 0.3s forwards;
    }
    
    .cta-btn {
      background: var(--accent);
      color: #fff;
      padding: 0.8rem 2rem;
      border: none;
      border-radius: 4px;
      text-decoration: none;
      font-size: 1.1rem;
      cursor: pointer;
      transition: transform 0.3s ease, background 0.3s ease;
    }
    
    .cta-btn:hover {
      background: var(--secondary-green);
      transform: scale(1.05);
    }
    
    /* Keyframe for hero fadeInUp */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    /* Main Content Sections */
    section {
      padding: 6rem 2rem;
      background: var(--light-bg);
    }
    
    .section-title {
      text-align: center;
      font-size: 2.5rem;
      margin-bottom: 3rem;
      color: var(--dark-green);
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
      background: var(--primary-green);
    }
    
    /* About Section */
    .about-content {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 4rem;
      align-items: center;
    }
    
    .about-image {
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
      transition: transform 0.3s ease;
    }
    
    .about-image img {
      width: 100%;
      height: auto;
      display: block;
    }
    
    .about-image:hover img {
      transform: scale(1.05);
    }
    
    .about-text h3 {
      font-size: 1.8rem;
      margin-bottom: 1rem;
      color: var(--dark-green);
    }
    
    .achievements-list {
      list-style: none;
      margin-top: 1rem;
    }
    
    .achievements-list li {
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    
    .achievements-list li i {
      color: var(--primary-green);
    }
    
    /* Services Section */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .service-card {
      background: #fff;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
      text-align: center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .service-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.15);
    }
    
    .service-icon {
      font-size: 2.5rem;
      color: var(--primary-green);
      margin-bottom: 1rem;
    }
    
    /* Testimonials Section */
    .testimonials {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2rem;
    }
    
    .testimonial {
      background: #fff;
      padding: 1.5rem;
      border-radius: 8px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.05);
      text-align: center;
      transition: transform 0.3s ease;
    }
    
    .testimonial p {
      font-style: italic;
      margin-bottom: 1rem;
    }
    
    .testimonial h4 {
      margin-top: 0.5rem;
      color: var(--dark-green);
    }
    
    /* Contact Section */
    .contact-container {
      max-width: 800px;
      margin: 0 auto;
      background: #fff;
      padding: 3rem;
      border-radius: 10px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    }
    
    .contact-form {
      display: grid;
      gap: 1.5rem;
    }
    
    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
    }
    
    input, textarea {
      padding: 0.8rem;
      border: 1px solid #ddd;
      border-radius: 5px;
      font-size: 1rem;
      outline: none;
      transition: border-color 0.3s ease;
    }
    
    input:focus, textarea:focus {
      border-color: var(--primary-green);
    }
    
    .submit-btn {
      background: var(--primary-green);
      color: white;
      border: none;
      padding: 1rem 2rem;
      border-radius: 5px;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background 0.3s ease, transform 0.3s ease;
    }
    
    .submit-btn:hover {
      background: var(--secondary-green);
      transform: scale(1.03);
    }
    
    /* Footer Styles */
    footer {
      background: var(--dark-green);
      color: white;
      padding: 4rem 2rem;
    }
    
    .footer-content {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 3rem;
    }
    
    .footer-section h3 {
      margin-bottom: 1.5rem;
    }
    
    .social-links {
      display: flex;
      gap: 1rem;
    }
    
    .social-links a {
      color: white;
      font-size: 1.5rem;
      transition: color 0.3s ease;
    }
    
    .social-links a:hover {
      color: var(--primary-green);
    }
    
    .footer-bottom {
      text-align: center;
      margin-top: 2rem;
    }
    
    /* Media Queries */
    @media (max-width: 768px) {
      .about-content, .testimonials {
        grid-template-columns: 1fr;
      }
      
      .nav-links {
        display: none;
        flex-direction: column;
        background: rgba(255, 255, 255, 0.95);
        position: absolute;
        top: 60px;
        right: 0;
        width: 200px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      }
      
      .nav-links.active {
        display: flex;
      }
      
      .hamburger {
        display: block;
      }
    }
    
    /* Smooth scroll back-to-top button */
    #back-to-top {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background: var(--primary-green);
      color: #fff;
      border: none;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      font-size: 1.5rem;
      cursor: pointer;
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 1000;
      transition: background 0.3s ease;
    }
    
    #back-to-top:hover {
      background: var(--secondary-green);
    }
  </style>
</head>
<body>
  <!-- Navigation -->
  <div class="nav-container" id="nav-container">
    <nav>
      <a href="#" class="logo">AgriCultro</a>
      <div class="hamburger" id="hamburger"><i class="fas fa-bars"></i></div>
      <div class="nav-links" id="nav-links">
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#testimonials">Testimonials</a>
        <a href="#contact">Contact</a>
      </div>
    </nav>
  </div>
  
  <!-- Hero Section -->
  <header>
    <div class="hero-content" data-aos="fade-up">
      <h1>Sustainable Agriculture Solutions</h1>
      <p>Empowering Farmers Through Innovation & Tradition</p>
      <a href="#contact" class="cta-btn">Get Started</a>
    </div>
  </header>
  
  <!-- About Section -->
  <section id="about">
    <h2 class="section-title" data-aos="fade-up">About Us</h2>
    <div class="about-content">
      <div class="about-image" data-aos="zoom-in">
        <img src="https://images.unsplash.com/photo-1625246333195-78d9c38ad449?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Farmers working">
      </div>
      <div class="about-text" data-aos="fade-left">
        <h3>25+ Years of Agricultural Excellence</h3>
        <p>At Agri Cultro Gaurav, we blend traditional farming wisdom with modern sustainable practices to create holistic solutions for the agricultural community. Our team of experts works directly with farmers to improve yields while maintaining ecological balance.</p>
        <ul class="achievements-list">
          <li><i class="fas fa-check"></i> 5000+ Farmers Trained</li>
          <li><i class="fas fa-check"></i> 45% Average Yield Increase</li>
          <li><i class="fas fa-check"></i> 100% Organic Solutions</li>
        </ul>
      </div>
    </div>
  </section>
  
  <!-- Services Section -->
  <section id="services">
    <h2 class="section-title" data-aos="fade-up">Our Services</h2>
    <div class="services-grid">
      <div class="service-card" data-aos="fade-up">
        <i class="fas fa-seedling service-icon"></i>
        <h3>Crop Management</h3>
        <p>Soil analysis, crop rotation, and sustainable practices to boost yield.</p>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="100">
        <i class="fas fa-tractor service-icon"></i>
        <h3>Modern Equipment</h3>
        <p>Access to state-of-the-art machinery with comprehensive training programs.</p>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="200">
        <i class="fas fa-graduation-cap service-icon"></i>
        <h3>Farmer Education</h3>
        <p>Workshops and certification courses in sustainable agriculture practices.</p>
      </div>
    </div>
  </section>
  
  <!-- Testimonials Section -->
  <section id="testimonials">
    <h2 class="section-title" data-aos="fade-up">Testimonials</h2>
    <div class="testimonials">
      <div class="testimonial" data-aos="fade-up">
        <p>"Agri Cultro Gaurav transformed our yield – their expertise is unmatched!"</p>
        <h4>- Ramesh Kumar, Farmer</h4>
      </div>
      <div class="testimonial" data-aos="fade-up" data-aos-delay="100">
        <p>"Their sustainable approach not only boosted our production but also preserved our land."</p>
        <h4>- Sunita Devi, Farm Owner</h4>
      </div>
      <div class="testimonial" data-aos="fade-up" data-aos-delay="200">
        <p>"The training workshops were insightful and practical. I learned a lot!"</p>
        <h4>- Mohan Singh, Agricultural Consultant</h4>
      </div>
    </div>
  </section>
  
  <!-- Contact Section -->
  <section id="contact">
    <h2 class="section-title" data-aos="fade-up">Contact Us</h2>
    <div class="contact-container" data-aos="fade-up">
      <form class="contact-form">
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" required>
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" required>
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" rows="5" required></textarea>
        </div>
        <button type="submit" class="submit-btn">Send Message</button>
      </form>
    </div>
  </section>
  
  <!-- Footer -->
  <footer>
    <div class="footer-content">
      <div class="footer-section">
        <h3>AgriCultro</h3>
        <p>Committed to sustainable agricultural development since 1998.</p>
      </div>
      <div class="footer-section">
        <h3>Quick Links</h3>
        <ul>
          <li><a href="#about" style="color:inherit; text-decoration:none;">About</a></li>
          <li><a href="#services" style="color:inherit; text-decoration:none;">Services</a></li>
          <li><a href="#contact" style="color:inherit; text-decoration:none;">Contact</a></li>
        </ul>
      </div>
      <div class="footer-section">
        <h3>Connect With Us</h3>
        <div class="social-links">
          <a href="#"><i class="fab fa-facebook-f"></i></a>
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-linkedin-in"></i></a>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2025 Agri Cultro Gaurav. All rights reserved.</p>
    </div>
  </footer>
  
  <!-- Back to Top Button -->
  <button id="back-to-top"><i class="fas fa-chevron-up"></i></button>
  
  <!-- Scripts -->
  <script src="https://unpkg.com/aos@next/dist/aos.js"></script>
  <script>
    // Initialize AOS
    AOS.init({
      duration: 1000,
      once: true,
      easing: 'ease-in-out'
    });
    
    // Mobile Navigation Toggle
    const hamburger = document.getElementById('hamburger');
    const navLinks = document.getElementById('nav-links');
    hamburger.addEventListener('click', () => {
      navLinks.classList.toggle('active');
    });
    
    // Change nav background on scroll
    const navContainer = document.getElementById('nav-container');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navContainer.style.background = "#fff";
      } else {
        navContainer.style.background = "rgba(255, 255, 255, 0.95)";
      }
    });
    
    // Back-to-Top Button Functionality
    const backToTopBtn = document.getElementById('back-to-top');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 400) {
        backToTopBtn.style.display = "flex";
      } else {
        backToTopBtn.style.display = "none";
      }
    });
    
    backToTopBtn.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });
  </script>
</body>
</html>
