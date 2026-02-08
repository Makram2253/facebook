<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>روز ماربل | متجر مستحضرات التجميل الفاخرة</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #d4a5a5;
            --secondary: #9d8189;
            --accent: #f4acb7;
            --dark: #2d3436;
            --light: #faf7f7;
            --gold: #d4af37;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background: linear-gradient(135deg, #faf7f7 0%, #f5f0f0 100%);
            color: var(--dark);
            overflow-x: hidden;
        }

        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes shimmer {
            0% { background-position: -200% 0; }
            100% { background-position: 200% 0; }
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

        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 20px rgba(212, 165, 165, 0.4); }
            50% { box-shadow: 0 0 40px rgba(212, 165, 165, 0.8); }
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(212, 165, 165, 0.2);
        }

        .header-top {
            background: linear-gradient(90deg, var(--primary), var(--accent));
            color: white;
            text-align: center;
            padding: 8px;
            font-size: 14px;
            font-weight: 500;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 32px;
            font-weight: 800;
            background: linear-gradient(45deg, var(--primary), var(--gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -1px;
        }

        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            position: relative;
            transition: all 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            right: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-icons {
            display: flex;
            gap: 25px;
            align-items: center;
        }

        .icon-btn {
            background: none;
            border: none;
            cursor: pointer;
            position: relative;
            font-size: 20px;
            color: var(--dark);
            transition: transform 0.3s;
        }

        .icon-btn:hover {
            transform: scale(1.1);
            color: var(--primary);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--accent);
            color: white;
            font-size: 10px;
            padding: 2px 6px;
            border-radius: 50%;
            font-weight: bold;
        }

        /* Hero Section */
        .hero {
            margin-top: 100px;
            min-height: 90vh;
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            padding: 0 5%;
            max-width: 1400px;
            margin-left: auto;
            margin-right: auto;
            gap: 60px;
        }

        .hero-content {
            animation: fadeInUp 1s ease;
        }

        .hero-badge {
            display: inline-block;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            color: white;
            padding: 8px 20px;
            border-radius: 30px;
            font-size: 14px;
            margin-bottom: 20px;
            font-weight: 600;
        }

        .hero h1 {
            font-size: 56px;
            line-height: 1.2;
            margin-bottom: 20px;
            font-weight: 800;
            color: var(--dark);
        }

        .hero h1 span {
            color: var(--primary);
            position: relative;
        }

        .hero p {
            font-size: 18px;
            color: var(--secondary);
            margin-bottom: 30px;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 20px;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--primary), var(--accent));
            color: white;
            padding: 15px 40px;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(212, 165, 165, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(212, 165, 165, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: var(--dark);
            padding: 15px 40px;
            border: 2px solid var(--primary);
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-secondary:hover {
            background: var(--primary);
            color: white;
        }

        .hero-image {
            position: relative;
            animation: float 6s ease-in-out infinite;
        }

        .hero-image img {
            width: 100%;
            max-width: 600px;
            border-radius: 30px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.15);
        }

        .floating-card {
            position: absolute;
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            animation: fadeInUp 1s ease 0.5s both;
        }

        .card-1 {
            top: 10%;
            left: -30px;
        }

        .card-2 {
            bottom: 20%;
            right: -20px;
        }

        .floating-card img {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            object-fit: cover;
        }

        /* Categories */
        .categories {
            padding: 80px 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 40px;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .section-title p {
            color: var(--secondary);
            font-size: 18px;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .category-card {
            background: white;
            border-radius: 25px;
            overflow: hidden;
            position: relative;
            cursor: pointer;
            transition: all 0.4s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .category-card img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            transition: transform 0.4s;
        }

        .category-card:hover img {
            transform: scale(1.1);
        }

        .category-info {
            padding: 25px;
            text-align: center;
        }

        .category-info h3 {
            font-size: 22px;
            margin-bottom: 10px;
        }

        .category-info span {
            color: var(--primary);
            font-weight: 600;
        }

        /* Products */
        .products {
            padding: 80px 5%;
            background: white;
        }

        .products-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .products-filter {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 10px 25px;
            border: 2px solid #eee;
            background: white;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
            font-family: inherit;
            font-weight: 500;
        }

        .filter-btn.active,
        .filter-btn:hover {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: white;
            border-radius: 25px;
            overflow: hidden;
            position: relative;
            transition: all 0.4s;
            border: 1px solid #f0f0f0;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: var(--accent);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 700;
            z-index: 10;
        }

        .product-wishlist {
            position: absolute;
            top: 15px;
            right: 15px;
            background: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            transition: all 0.3s;
            z-index: 10;
        }

        .product-wishlist:hover {
            background: var(--accent);
            color: white;
        }

        .product-image {
            position: relative;
            overflow: hidden;
            height: 300px;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.1);
        }

        .quick-view {
            position: absolute;
            bottom: -50px;
            left: 50%;
            transform: translateX(-50%);
            background: white;
            padding: 12px 30px;
            border-radius: 30px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            opacity: 0;
            white-space: nowrap;
        }

        .product-card:hover .quick-view {
            bottom: 20px;
            opacity: 1;
        }

        .product-info {
            padding: 25px;
        }

        .product-brand {
            color: var(--primary);
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 8px;
        }

        .product-name {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--dark);
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 5px;
            margin-bottom: 15px;
        }

        .stars {
            color: #ffc107;
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 15px;
        }

        .current-price {
            font-size: 24px;
            font-weight: 800;
            color: var(--dark);
        }

        .old-price {
            font-size: 16px;
            color: #999;
            text-decoration: line-through;
        }

        .add-to-cart {
            width: 100%;
            padding: 15px;
            background: var(--dark);
            color: white;
            border: none;
            border-radius: 15px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .add-to-cart:hover {
            background: var(--primary);
            animation: pulse-glow 1s infinite;
        }

        /* Features */
        .features {
            padding: 80px 5%;
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
            color: white;
        }

        .features-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .feature-item {
            text-align: center;
            padding: 30px;
        }

        .feature-icon {
            font-size: 50px;
            margin-bottom: 20px;
        }

        .feature-item h3 {
            font-size: 22px;
            margin-bottom: 10px;
        }

        .feature-item p {
            opacity: 0.9;
            line-height: 1.6;
        }

        /* Newsletter */
        .newsletter {
            padding: 100px 5%;
            text-align: center;
            background: white;
        }

        .newsletter-content {
            max-width: 600px;
            margin: 0 auto;
        }

        .newsletter h2 {
            font-size: 36px;
            margin-bottom: 20px;
            color: var(--dark);
        }

        .newsletter p {
            color: var(--secondary);
            margin-bottom: 30px;
            font-size: 18px;
        }

        .newsletter-form {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .newsletter-input {
            flex: 1;
            min-width: 300px;
            padding: 18px 25px;
            border: 2px solid #eee;
            border-radius: 50px;
            font-family: inherit;
            font-size: 16px;
            outline: none;
            transition: border-color 0.3s;
        }

        .newsletter-input:focus {
            border-color: var(--primary);
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 60px 5% 30px;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            font-size: 20px;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 12px;
        }

        .footer-section a {
            color: #aaa;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--primary);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #aaa;
        }

        /* Cart Sidebar */
        .cart-sidebar {
            position: fixed;
            top: 0;
            left: -400px;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: 10px 0 30px rgba(0,0,0,0.1);
            transition: left 0.4s;
            z-index: 2000;
            padding: 30px;
            overflow-y: auto;
        }

        .cart-sidebar.open {
            left: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid #f0f0f0;
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--dark);
        }

        .cart-item {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid #f0f0f0;
        }

        .cart-item img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 15px;
        }

        .cart-item-info h4 {
            font-size: 16px;
            margin-bottom: 5px;
        }

        .cart-item-price {
            color: var(--primary);
            font-weight: 700;
        }

        .cart-total {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 2px solid #f0f0f0;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 18px;
        }

        .total-row.final {
            font-size: 24px;
            font-weight: 800;
            color: var(--dark);
        }

        .checkout-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            margin-top: 20px;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            z-index: 1500;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* Responsive */
        @media (max-width: 968px) {
            .hero {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-image {
                order: -1;
            }

            .nav-links {
                display: none;
            }

            .cart-sidebar {
                width: 100%;
                left: -100%;
            }
        }

        /* Loading Animation */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: opacity 0.5s;
        }

        .loader.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .loader-content {
            text-align: center;
        }

        .loader-logo {
            font-size: 48px;
            font-weight: 800;
            background: linear-gradient(45deg, var(--primary), var(--gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
    </style>
</head>
<body>
    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="loader-content">
            <div class="loader-logo">روز ماربل</div>
            <p style="color: var(--secondary); margin-top: 20px;">جاري تحميل التجميل الفاخر...</p>
        </div>
    </div>

    <!-- Overlay -->
    <div class="overlay" id="overlay"></div>

    <!-- Cart Sidebar -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h2>سلة التسوق 🛍️</h2>
            <button class="close-cart" onclick="toggleCart()">✕</button>
        </div>
        <div id="cartItems">
            <!-- Cart items will be added here dynamically -->
        </div>
        <div class="cart-total">
            <div class="total-row">
                <span>المجموع الفرعي:</span>
                <span id="subtotal">0 ر.س</span>
            </div>
            <div class="total-row">
                <span>الشحن:</span>
                <span>مجاني</span>
            </div>
            <div class="total-row final">
                <span>الإجمالي:</span>
                <span id="total">0 ر.س</span>
            </div>
            <button class="checkout-btn">إتمام الشراء</button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="header-top">
            🎁 شحن مجاني للطلبات أكثر من 300 ر.س | كود خصم: ROSE20
        </div>
        <nav>
            <div class="logo">روز ماربل</div>
            <ul class="nav-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#products">المنتجات</a></li>
                <li><a href="#categories">التصنيفات</a></li>
                <li><a href="#offers">العروض</a></li>
                <li><a href="#contact">تواصل معنا</a></li>
            </ul>
            <div class="nav-icons">
                <button class="icon-btn">🔍</button>
                <button class="icon-btn">👤</button>
                <button class="icon-btn" onclick="toggleCart()">
                    🛒
                    <span class="cart-count" id="cartCount">0</span>
                </button>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <span class="hero-badge">✨ جديد 2024</span>
            <h1>اكتشفي جمالك <span>الطبيعي</span> مع روز ماربل</h1>
            <p>مستحضرات تجميل فاخرة، عضوية، وخالية من القسوة. نقدم لكِ أفضل الماركات العالمية بعناية فائقة لبشرة نضرة وجميلة.</p>
            <div class="hero-buttons">
                <button class="btn-primary">تسوقي الآن</button>
                <button class="btn-secondary">اكتشفي المزيد</button>
            </div>
        </div>
        <div class="hero-image">
            <img src="https://images.unsplash.com/photo-1596462502278-27bfdc403348?w=800" alt="مستحضرات تجميل فاخرة">
            <div class="floating-card card-1">
                <div style="display: flex; align-items: center; gap: 15px;">
                    <img src="https://images.unsplash.com/photo-1571781926291-c477ebfd024b?w=200" alt="منتج">
                    <div>
                        <div style="font-weight: 700;">كريم الليل</div>
                        <div style="color: var(--primary); font-weight: 700;">199 ر.س</div>
                    </div>
                </div>
            </div>
            <div class="floating-card card-2">
                <div style="text-align: center;">
                    <div style="font-size: 24px; font-weight: 800; color: var(--primary);">50K+</div>
                    <div style="font-size: 14px; color: var(--secondary);">عميلة سعيدة</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories -->
    <section class="categories" id="categories">
        <div class="section-title">
            <h2>تصنيفاتنا المميزة</h2>
            <p>اختر ما يناسبك من مجموعتنا الواسعة</p>
        </div>
        <div class="category-grid">
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1512496015851-a90fb38ba796?w=400" alt="عناية بالبشرة">
                <div class="category-info">
                    <h3>العناية بالبشرة</h3>
                    <span>120 منتج</span>
                </div>
            </div>
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1487412912498-0447578fcca8?w=400" alt="مكياج">
                <div class="category-info">
                    <h3>المكياج</h3>
                    <span>85 منتج</span>
                </div>
            </div>
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1527799820374-dcf8d9d4a388?w=400" alt="عطور">
                <div class="category-info">
                    <h3>العطور الفاخرة</h3>
                    <span>45 منتج</span>
                </div>
            </div>
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1585652757141-8837edd4ba38?w=400" alt="شعر">
                <div class="category-info">
                    <h3>العناية بالشعر</h3>
                    <span>67 منتج</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Products -->
    <section class="products" id="products">
        <div class="products-container">
            <div class="section-title">
                <h2>منتجاتنا الأكثر مبيعاً</h2>
                <p>اخترنا لكِ بعناية أفضل المنتجات</p>
            </div>
            
            <div class="products-filter">
                <button class="filter-btn active" onclick="filterProducts('all')">الكل</button>
                <button class="filter-btn" onclick="filterProducts('skin')">البشرة</button>
                <button class="filter-btn" onclick="filterProducts('makeup')">المكياج</button>
                <button class="filter-btn" onclick="filterProducts('perfume')">العطور</button>
                <button class="filter-btn" onclick="filterProducts('hair')">الشعر</button>
            </div>

            <div class="products-grid" id="productsGrid">
                <!-- Products will be rendered here -->
            </div>
        </div>
    </section>

    <!-- Features -->
    <section class="features">
        <div class="features-grid">
            <div class="feature-item">
                <div class="feature-icon">🚚</div>
                <h3>شحن سريع</h3>
                <p>توصيل خلال 24-48 ساعة لجميع المدن</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">✨</div>
                <h3>منتجات أصلية</h3>
                <p>100% أصلية مع ضمان الجودة</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">🎁</div>
                <h3>هدايا مجانية</h3>
                <p>مع كل طلب أكثر من 200 ر.س</p>
            </div>
            <div class="feature-item">
                <div class="feature-icon">💳</div>
                <h3>دفع آمن</h3>
                <p>طرق دفع متعددة وآمنة 100%</p>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="newsletter-content">
            <h2>اشتركي في نشرتنا الجميلة 💌</h2>
            <p>احصلي على آخر العروض والنصائح الجمالية مباشرة إلى بريدك</p>
            <form class="newsletter-form" onsubmit="event.preventDefault(); alert('شكراً للاشتراك! 🌸');">
                <input type="email" class="newsletter-input" placeholder="بريدك الإلكتروني" required>
                <button type="submit" class="btn-primary">اشتركي الآن</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>روز ماربل</h3>
                <p style="color: #aaa; line-height: 1.8; margin-bottom: 20px;">
                    وجهتك الأولى للجمال الفاخر. نقدم لكِ أفضل المنتجات بعناية فائقة.
                </p>
                <div class="social-links">
                    <a href="#">📘</a>
                    <a href="#">📸</a>
                    <a href="#">🐦</a>
                    <a href="#">💬</a>
                </div>
            </div>
            <div class="footer-section">
                <h3>روابط سريعة</h3>
                <ul>
                    <li><a href="#">من نحن</a></li>
                    <li><a href="#">المنتجات</a></li>
                    <li><a href="#">العروض</a></li>
                    <li><a href="#">المدونة</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>خدمة العملاء</h3>
                <ul>
                    <li><a href="#">تواصل معنا</a></li>
                    <li><a href="#">الشحن والتوصيل</a></li>
                    <li><a href="#">سياسة الإرجاع</a></li>
                    <li><a href="#">الأسئلة الشائعة</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>تواصل معنا</h3>
                <ul>
                    <li>📧 hello@rosemarble.com</li>
                    <li>📞 9200XXXXX</li>
                    <li>📍 الرياض، المملكة العربية السعودية</li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© 2024 روز ماربل. جميع الحقوق محفوظة. صنع ب❤️ في السعودية</p>
        </div>
    </footer>

    <script>
        // Products Data
        const products = [
            {
                id: 1,
                name: "سيروم فيتامين سي النقي",
                brand: "The Ordinary",
                price: 89,
                oldPrice: 120,
                image: "https://images.unsplash.com/photo-1620916566398-39f1143ab7be?w=400",
                category: "skin",
                badge: "الأكثر مبيعاً",
                rating: 4.9
            },
            {
                id: 2,
                name: "كريم أساس هيدرا",
                brand: "Fenty Beauty",
                price: 199,
                oldPrice: 250,
                image: "https://images.unsplash.com/photo-1631730486784-5d9b1f5d3e0a?w=400",
                category: "makeup",
                badge: "جديد",
                rating: 4.8
            },
            {
                id: 3,
                name: "عطر روز الذهب",
                brand: "Rose Marble",
                price: 450,
                image: "https://images.unsplash.com/photo-1541643600914-78b084683601?w=400",
                category: "perfume",
                badge: "حصري",
                rating: 5.0
            },
            {
                id: 4,
                name: "شامبو البروتين المعالج",
                brand: "Olaplex",
                price: 155,
                oldPrice: 180,
                image: "https://images.unsplash.com/photo-1527799820374-dcf8d9d4a388?w=400",
                category: "hair",
                badge: "-15%",
                rating: 4.7
            },
            {
                id: 5,
                name: "باليت ظلال عيون نود",
                brand: "Huda Beauty",
                price: 275,
                image: "https://images.unsplash.com/photo-1512496015851-a90fb38ba796?w=400",
                category: "makeup",
                badge: "محدود",
                rating: 4.9
            },
            {
                id: 6,
                name: "ماسك الطين المغربي",
                brand: "Rhode",
                price: 129,
                oldPrice: 160,
                image: "https://images.unsplash.com/photo-1571781926291-c477ebfd024b?w=400",
                category: "skin",
                badge: "طبيعي 100%",
                rating: 4.8
            },
            {
                id: 7,
                name: "زيت الأرغان النقي",
                brand: "Moroccan Oil",
                price: 189,
                image: "https://images.unsplash.com/photo-1608248597279-f99d160bfcbc?w=400",
                category: "hair",
                badge: "أفضل تقييم",
                rating: 4.9
            },
            {
                id: 8,
                name: "أحمر شفاه مخملي",
                brand: "Rare Beauty",
                price: 145,
                image: "https://images.unsplash.com/photo-1586495777744-4413f21062fa?w=400",
                category: "makeup",
                badge: "جديد",
                rating: 4.6
            }
        ];

        let cart = [];
        let currentFilter = 'all';

        // Initialize
        window.onload = function() {
            setTimeout(() => {
                document.getElementById('loader').classList.add('hidden');
            }, 1500);
            renderProducts();
        };

        // Render Products
        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            const filtered = currentFilter === 'all' 
                ? products 
                : products.filter(p => p.category === currentFilter);
            
            grid.innerHTML = filtered.map(product => `
                <div class="product-card" data-category="${product.category}">
                    <span class="product-badge">${product.badge}</span>
                    <button class="product-wishlist">♡</button>
                    <div class="product-image">
                        <img src="${product.image}" alt="${product.name}">
                        <button class="quick-view" onclick="quickView(${product.id})">عرض سريع</button>
                    </div>
                    <div class="product-info">
                        <div class="product-brand">${product.brand}</div>
                        <h3 class="product-name">${product.name}</h3>
                        <div class="product-rating">
                            <span class="stars">${'★'.repeat(Math.floor(product.rating))}</span>
                            <span>(${product.rating})</span>
                        </div>
                        <div class="product-price">
                            <span class="current-price">${product.price} ر.س</span>
                            ${product.oldPrice ? `<span class="old-price">${product.oldPrice} ر.س</span>` : ''}
                        </div>
                        <button class="add-to-cart" onclick="addToCart(${product.id})">
                            <span>🛒</span> أضفي إلى السلة
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Filter Products
        function filterProducts(category) {
            currentFilter = category;
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
                if(btn.textContent.includes(getCategoryName(category))) {
                    btn.classList.add('active');
                }
            });
            renderProducts();
        }

        function getCategoryName(cat) {
            const names = {
                'all': 'الكل',
                'skin': 'البشرة',
                'makeup': 'المكياج',
                'perfume': 'العطور',
                'hair': 'الشعر'
            };
            return names[cat] || 'الكل';
        }

        // Cart Functions
        function toggleCart() {
            document.getElementById('cartSidebar').classList.toggle('open');
            document.getElementById('overlay').classList.toggle('active');
        }

        document.getElementById('overlay').addEventListener('click', toggleCart);

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existing = cart.find(item => item.id === productId);
            
            if(existing) {
                existing.quantity++;
            } else {
                cart.push({...product, quantity: 1});
            }
            
            updateCart();
            toggleCart();
            
            // Animation feedback
            const btn = event.target;
            btn.innerHTML = '<span>✓</span> تمت الإضافة';
            setTimeout(() => {
                btn.innerHTML = '<span>🛒</span> أضفي إلى السلة';
            }, 2000);
        }

        function updateCart() {
            const cartItems = document.getElementById('cartItems');
            const cartCount = document.getElementById('cartCount');
            const subtotal = document.getElementById('subtotal');
            const total = document.getElementById('total');
            
            cartCount.textContent = cart.reduce((sum, item) => sum + item.quantity, 0);
            
            if(cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; color: #999; padding: 40px;">السلة فارغة 🛍️</p>';
            } else {
                cartItems.innerHTML = cart.map(item => `
                    <div class="cart-item">
                        <img src="${item.image}" alt="${item.name}">
                        <div class="cart-item-info">
                            <h4>${item.name}</h4>
                            <div class="cart-item-price">${item.price} ر.س × ${item.quantity}</div>
                        </div>
                        <button onclick="removeFromCart(${item.id})" style="background: none; border: none; cursor: pointer; font-size: 20px; color: #ff6b6b;">🗑️</button>
                    </div>
                `).join('');
            }
            
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            subtotal.textContent = totalPrice + ' ر.س';
            total.textContent = totalPrice + ' ر.س';
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
        }

        function quickView(productId) {
            const product = products.find(p => p.id === productId);
            alert(`
                ${product.name}
                ${product.brand}
                ${product.price} ر.س
                التقييم: ${product.rating} ⭐
            `);
        }

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if(target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if(window.scrollY > 100) {
                header.style.boxShadow = '0 2px 20px rgba(0,0,0,0.1)';
            } else {
                header.style.boxShadow = 'none';
            }
        });
    </script>
</body>
</html>
