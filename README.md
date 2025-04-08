<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safety Tracker Pro | Advanced Workplace Safety Monitoring</title>
    <meta name="description" content="Comprehensive workplace safety monitoring platform with real-time analytics, predictive hazard detection, and compliance management.">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #1a4673;
            --secondary-color: #ff9800;
            --accent-color: #4caf50;
            --dark-color: #0d2b4e;
            --light-color: #f4f4f4;
            --danger-color: #e53935;
            --warning-color: #ffb300;
            --success-color: #43a047;
            --text-color: #333;
            --text-light: #777;
            --white: #ffffff;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        
        /* Reset and base styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--light-color);
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header with sticky navigation */
        header {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 15px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        header.scrolled {
            padding: 10px 0;
            background-color: rgba(26, 70, 115, 0.95);
        }
        
        header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 28px;
            font-weight: 700;
            text-decoration: none;
            color: var(--white);
        }
        
        .logo i {
            color: var(--secondary-color);
            margin-right: 10px;
            font-size: 32px;
        }
        
        .highlight {
            color: var(--secondary-color);
        }
        
        /* Navigation */
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav li {
            position: relative;
            padding: 0 15px;
        }
        
        nav a {
            color: var(--white);
            text-decoration: none;
            text-transform: uppercase;
            font-size: 15px;
            font-weight: 600;
            letter-spacing: 1px;
            transition: var(--transition);
            padding: 10px 0;
            position: relative;
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background-color: var(--secondary-color);
            transition: var(--transition);
        }
        
        nav a:hover::after,
        nav a.current::after {
            width: 100%;
        }
        
        nav a:hover {
            color: var(--secondary-color);
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 24px;
            cursor: pointer;
        }
        
        /* Showcase with animated gradient */
        .showcase {
            min-height: 100vh;
            background: linear-gradient(135deg, rgba(26, 70, 115, 0.8) 0%, rgba(13, 43, 78, 0.9) 100%), 
                        url('https://images.unsplash.com/photo-1581093196270-1a1d1dfc3a28?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80') no-repeat center center/cover;
            color: var(--white);
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 120px 20px 80px;
            position: relative;
            overflow: hidden;
        }
        
        .showcase::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(255, 152, 0, 0.2) 0%, transparent 30%);
            animation: pulse 8s infinite alternate;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
                opacity: 0.3;
            }
            100% {
                transform: scale(1.1);
                opacity: 0.1;
            }
        }
        
        .showcase h1 {
            font-size: 3.5rem;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-weight: 800;
            position: relative;
            z-index: 1;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .showcase p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 40px;
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }
        
        .btn {
            display: inline-block;
            background: var(--secondary-color);
            color: var(--white);
            padding: 15px 35px;
            border: none;
            cursor: pointer;
            text-decoration: none;
            font-size: 1rem;
            border-radius: 50px;
            text-transform: uppercase;
            font-weight: 700;
            letter-spacing: 1px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
            box-shadow: 0 4px 15px rgba(255, 152, 0, 0.3);
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background-color: var(--primary-color);
            transition: var(--transition);
            z-index: -1;
        }
        
        .btn:hover::before {
            width: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 152, 0, 0.4);
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid var(--white);
            margin-left: 15px;
        }
        
        .btn-outline:hover {
            background: var(--white);
            color: var(--primary-color);
        }
        
        /* Stats counter */
        .stats {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            background: var(--primary-color);
            padding: 30px 0;
            margin-top: -50px;
            position: relative;
            z-index: 10;
            border-radius: 10px;
            box-shadow: var(--shadow);
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .stat-item {
            text-align: center;
            padding: 20px;
            color: var(--white);
            flex: 1;
            min-width: 200px;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .stat-label {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        /* Features with icons */
        .features {
            padding: 100px 0;
            background: var(--white);
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            text-transform: uppercase;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--secondary-color);
            margin: 0 auto;
        }
        
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-box {
            padding: 40px 30px;
            background: var(--light-color);
            text-align: center;
            border-radius: 10px;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            position: relative;
            overflow: hidden;
            border-top: 5px solid var(--primary-color);
        }
        
        .feature-box:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            transition: var(--transition);
        }
        
        .feature-box:hover .feature-icon {
            color: var(--secondary-color);
            transform: scale(1.1);
        }
        
        .feature-box h3 {
            margin-bottom: 20px;
            color: var(--primary-color);
            font-size: 1.5rem;
        }
        
        .feature-box p {
            margin-bottom: 20px;
            color: var(--text-light);
        }
        
        .feature-link {
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            transition: var(--transition);
        }
        
        .feature-link i {
            margin-left: 5px;
            transition: var(--transition);
        }
        
        .feature-link:hover {
            color: var(--primary-color);
        }
        
        .feature-link:hover i {
            transform: translateX(5px);
        }
        
        /* About section with tabs */
        .about {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--light-color) 0%, #e6eef5 100%);
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }
        
        .about-image {
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        .about-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(26, 70, 115, 0.1) 0%, rgba(26, 70, 115, 0.3) 100%);
        }
        
        .about-text h2 {
            font-size: 2.2rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }
        
        .about-text p {
            margin-bottom: 20px;
            color: var(--text-color);
            line-height: 1.8;
        }
        
        .tabs {
            margin-top: 30px;
        }
        
        .tab-header {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: 20px;
        }
        
        .tab-btn {
            padding: 10px 20px;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--text-light);
            position: relative;
            transition: var(--transition);
        }
        
        .tab-btn.active {
            color: var(--primary-color);
        }
        
        .tab-btn.active::after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 100%;
            height: 3px;
            background: var(--secondary-color);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Testimonials */
        .testimonials {
            padding: 100px 0;
            background: var(--primary-color);
            color: var(--white);
        }
        
        .testimonial-slider {
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
        }
        
        .testimonial-slide {
            text-align: center;
            padding: 30px;
            display: none;
        }
        
        .testimonial-slide.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        .testimonial-quote {
            font-size: 1.3rem;
            font-style: italic;
            margin-bottom: 30px;
            line-height: 1.8;
            position: relative;
        }
        
        .testimonial-quote::before,
        .testimonial-quote::after {
            content: '"';
            font-size: 3rem;
            color: var(--secondary-color);
            opacity: 0.3;
            position: absolute;
        }
        
        .testimonial-quote::before {
            top: -20px;
            left: -30px;
        }
        
        .testimonial-quote::after {
            bottom: -40px;
            right: -30px;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 30px;
        }
        
        .author-image {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 20px;
            border: 3px solid var(--secondary-color);
        }
        
        .author-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .author-info h4 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .author-info p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }
        
        .slider-controls {
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }
        
        .slider-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            margin: 0 5px;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .slider-dot.active {
            background: var(--secondary-color);
            transform: scale(1.2);
        }
        
        /* Pricing */
        .pricing {
            padding: 100px 0;
            background: var(--white);
        }
        
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }
        
        .pricing-card {
            background: var(--light-color);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }
        
        .pricing-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .pricing-header {
            background: var(--primary-color);
            color: var(--white);
            padding: 30px;
            text-align: center;
        }
        
        .pricing-popular {
            position: absolute;
            top: 0;
            right: 30px;
            background: var(--secondary-color);
            color: var(--white);
            padding: 5px 15px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            border-radius: 0 0 5px 5px;
        }
        
        .pricing-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        .pricing-price {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .pricing-price span {
            font-size: 1rem;
            font-weight: 400;
        }
        
        .pricing-period {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .pricing-body {
            padding: 30px;
        }
        
        .pricing-features {
            list-style: none;
            margin-bottom: 30px;
        }
        
        .pricing-features li {
            padding: 10px 0;
            border-bottom: 1px solid #eee;
            display: flex;
            align-items: center;
        }
        
        .pricing-features li i {
            color: var(--accent-color);
            margin-right: 10px;
        }
        
        .pricing-btn {
            display: block;
            text-align: center;
            padding: 15px;
            background: var(--secondary-color);
            color: var(--white);
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            transition: var(--transition);
        }
        
        .pricing-btn:hover {
            background: var(--primary-color);
        }
        
        /* Contact Form */
        .contact {
            padding: 100px 0;
            background: linear-gradient(135deg, var(--light-color) 0%, #e6eef5 100%);
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }
        
        .contact-info {
            padding: 30px;
        }
        
        .contact-info h3 {
            font-size: 1.8rem;
            color: var(--primary-color);
            margin-bottom: 30px;
        }
        
        .contact-details {
            margin-bottom: 40px;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }
        
        .contact-icon {
            font-size: 1.2rem;
            color: var(--secondary-color);
            margin-right: 15px;
            margin-top: 5px;
        }
        
        .contact-text h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
            color: var(--primary-color);
        }
        
        .contact-text p, 
        .contact-text a {
            color: var(--text-light);
            text-decoration: none;
            transition: var(--transition);
        }
        
        .contact-text a:hover {
            color: var(--secondary-color);
        }
        
        .social-links {
            display: flex;
            margin-top: 30px;
        }
        
        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: var(--primary-color);
            color: var(--white);
            border-radius: 50%;
            margin-right: 15px;
            transition: var(--transition);
        }
        
        .social-link:hover {
            background: var(--secondary-color);
            transform: translateY(-3px);
        }
        
        .contact-form {
            background: var(--white);
            padding: 40px;
            border-radius: 10px;
            box-shadow: var(--shadow);
        }
        
        .contact-form h2 {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 30px;
            text-align: center;
        }
        
        .form-group {
            margin-bottom: 25px;
            position: relative;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
            font-size: 1rem;
            transition: var(--transition);
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 3px rgba(255, 152, 0, 0.2);
        }
        
        .form-group textarea {
            height: 150px;
            resize: vertical;
        }
        
        .form-status {
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 5px;
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        /* Footer */
        footer {
            background: var(--dark-color);
            color: var(--white);
            padding: 70px 0 0;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 25px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: var(--secondary-color);
        }
        
        .footer-column p {
            margin-bottom: 20px;
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.8;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 15px;
        }
        
        .footer-links a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
        }
        
        .footer-links a i {
            margin-right: 10px;
            color: var(--secondary-color);
            font-size: 0.8rem;
        }
        
        .footer-links a:hover {
            color: var(--secondary-color);
            transform: translateX(5px);
        }
        
        .footer-newsletter input {
            width: 100%;
            padding: 12px 15px;
            border: none;
            border-radius: 5px;
            margin-bottom: 15px;
            font-family: inherit;
        }
        
        .footer-bottom {
            background: rgba(0, 0, 0, 0.2);
            padding: 20px 0;
            text-align: center;
        }
        
        .footer-bottom p {
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }
        
        /* Back to top button */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--secondary-color);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 999;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }
        
        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }
        
        .back-to-top:hover {
            background: var(--primary-color);
            transform: translateY(-5px);
        }
        
        /* Responsive styles */
        @media (max-width: 1200px) {
            .showcase h1 {
                font-size: 3rem;
            }
        }
        
        @media (max-width: 992px) {
            .about-content,
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .about-image {
                order: -1;
                max-width: 600px;
                margin: 0 auto;
            }
            
            .contact-info {
                text-align: center;
            }
            
            .social-links {
                justify-content: center;
            }
        }
        
        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            nav {
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background: var(--primary-color);
                padding: 0 20px;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
                max-height: 0;
                overflow: hidden;
                transition: max-height 0.5s ease;
            }
            
            nav.active {
                max-height: 500px;
                padding: 20px;
            }
            
            nav ul {
                flex-direction: column;
            }
            
            nav li {
                padding: 10px 0;
                border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            }
            
            .showcase h1 {
                font-size: 2.5rem;
            }
            
            .showcase p {
                font-size: 1.1rem;
            }
            
            .btn-container {
                display: flex;
                flex-direction: column;
                align-items: center;
            }
            
            .btn-outline {
                margin-left: 0;
                margin-top: 15px;
            }
            
            .stats {
                flex-direction: column;
                margin-top: 0;
                border-radius: 0;
            }
            
            .stat-item {
                padding: 15px 0;
            }
        }
        
        @media (max-width: 576px) {
            .showcase h1 {
                font-size: 2rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .pricing-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* Animations */
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        .floating {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container">
            <a href="#" class="logo">
                <i class="fas fa-shield-alt"></i>
                Safety<span class="highlight">Tracker</span>Pro
            </a>
            <button class="mobile-menu-btn" id="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            <nav id="nav">
                <ul>
                    <li><a href="#home" class="current">Home</a></li>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#testimonials">Testimonials</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Showcase -->
    <section id="home" class="showcase">
        <h1>Next-Gen Workplace Safety</h1>
        <p>AI-powered safety monitoring platform that predicts hazards before they occur, ensuring compliance and protecting your workforce with real-time analytics and actionable insights.</p>
        <div class="btn-container">
            <a href="#pricing" class="btn">Get Started</a>
            <a href="#features" class="btn btn-outline">Explore Features</a>
        </div>
    </section>

    <!-- Stats -->
    <div class="stats">
        <div class="stat-item">
            <div class="stat-number" id="stat1">0</div>
            <div class="stat-label">Incidents Prevented</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" id="stat2">0</div>
            <div class="stat-label">Happy Clients</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" id="stat3">0</div>
            <div class="stat-label">Safety Hours</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" id="stat4">0</div>
            <div class="stat-label">Countries</div>
        </div>
    </div>

    <!-- Features -->
    <section id="features" class="features">
        <div class="container">
            <div class="section-title">
                <h2>Advanced Safety Features</h2>
                <p>Our comprehensive suite of tools helps you maintain the highest safety standards</p>
            </div>
            <div class="feature-grid">
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-bell"></i>
                    </div>
                    <h3>Real-time Alerts</h3>
                    <p>Instant notifications for safety violations, hazardous conditions, and equipment malfunctions with location-based precision.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>Predictive Analytics</h3>
                    <p>Our AI models analyze historical data and real-time inputs to forecast potential safety incidents before they occur.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-clipboard-check"></i>
                    </div>
                    <h3>Compliance Automation</h3>
                    <p>Automated reporting for OSHA, ISO 45001, and other regulatory standards with audit-ready documentation.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-vr-cardboard"></i>
                    </div>
                    <h3>VR Training</h3>
                    <p>Immersive safety training simulations for high-risk scenarios without exposing workers to actual danger.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-robot"></i>
                    </div>
                    <h3>IoT Integration</h3>
                    <p>Connect wearable devices, environmental sensors, and equipment monitors for comprehensive safety coverage.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">
                        <i class="fas fa-project-diagram"></i>
                    </div>
                    <h3>Root Cause Analysis</h3>
                    <p>Advanced incident investigation tools that identify underlying causes and recommend corrective actions.</p>
                    <a href="#" class="feature-link">Learn more <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- About -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2>Why Choose SafetyTracker Pro?</h2>
                    <p>Developed by safety experts and data scientists, SafetyTracker Pro combines deep industry knowledge with cutting-edge technology to deliver unparalleled workplace protection.</p>
                    
                    <div class="tabs">
                        <div class="tab-header">
                            <button class="tab-btn active" data-tab="mission">Mission</button>
                            <button class="tab-btn" data-tab="technology">Technology</button>
                            <button class="tab-btn" data-tab="team">Team</button>
                        </div>
                        
                        <div class="tab-content active" id="mission">
                            <p>Our mission is to eliminate preventable workplace injuries through intelligent technology. We believe that every worker deserves to return home safely, and that safety management should be proactive, not reactive.</p>
                            <p>By combining IoT sensors, AI analytics, and human factors engineering, we're creating safer work environments across industries worldwide.</p>
                        </div>
                        
                        <div class="tab-content" id="technology">
                            <p>SafetyTracker Pro leverages machine learning algorithms trained on millions of safety data points to identify patterns and predict hazards with 92% accuracy.</p>
                            <p>Our platform integrates with existing enterprise systems and supports a wide range of IoT devices for comprehensive environmental and personnel monitoring.</p>
                        </div>
                        
                        <div class="tab-content" id="team">
                            <p>Founded by a team of occupational safety professionals and data scientists, our company brings together decades of hands-on safety experience with advanced technical expertise.</p>
                            <p>We've worked in the field and understand the real challenges of maintaining safety in complex work environments.</p>
                        </div>
                    </div>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3
