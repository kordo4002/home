# home
우리회사 홈페이지
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>N E TECH - Automotive Parts Innovation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Helvetica Neue', 'Segoe UI', 'Apple SD Gothic Neo', sans-serif;
            color: #111;
            overflow-x: hidden;
            background: #000;
        }
        
        /* Header */
        header {
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(20px);
            transition: all 0.3s;
        }
        
        header.scrolled {
            background: rgba(0, 0, 0, 0.98);
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.3);
        }
        
        nav {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 3rem;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 4px;
            color: #fff;
            background: linear-gradient(135deg, #00d4ff 0%, #0099ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .nav-menu {
            display: flex;
            list-style: none;
            gap: 3rem;
        }
        
        .nav-menu a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 0.5px;
            transition: all 0.3s;
            position: relative;
        }
        
        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #00d4ff, #0099ff);
            transition: width 0.3s;
        }
        
        .nav-menu a:hover::after {
            width: 100%;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            background: #000;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(0, 212, 255, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(0, 153, 255, 0.1) 0%, transparent 50%),
                linear-gradient(180deg, #000 0%, #0a0a0a 100%);
            animation: pulse 10s ease-in-out infinite;
        }
        
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.8; }
        }
        
        .hero-grid {
            position: absolute;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 212, 255, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 212, 255, 0.05) 1px, transparent 1px);
            background-size: 100px 100px;
            animation: gridMove 20s linear infinite;
        }
        
        @keyframes gridMove {
            0% { transform: translateY(0); }
            100% { transform: translateY(100px); }
        }
        
        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            color: #fff;
            max-width: 1200px;
            padding: 0 2rem;
        }
        
        .hero-content h1 {
            font-size: 5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            line-height: 1.1;
            letter-spacing: -2px;
            background: linear-gradient(135deg, #fff 0%, #00d4ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: fadeInUp 1s ease;
        }
        
        .hero-subtitle {
            font-size: 1.8rem;
            font-weight: 300;
            margin-bottom: 1rem;
            color: rgba(255, 255, 255, 0.9);
            animation: fadeInUp 1s ease 0.2s backwards;
        }
        
        .hero-description {
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.6);
            margin-bottom: 3rem;
            line-height: 1.8;
            animation: fadeInUp 1s ease 0.4s backwards;
        }
        
        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            animation: fadeInUp 1s ease 0.6s backwards;
        }
        
        .btn-primary {
            padding: 1.2rem 3rem;
            background: linear-gradient(135deg, #00d4ff 0%, #0099ff 100%);
            color: #000;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 1rem;
            letter-spacing: 0.5px;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        
        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s;
        }
        
        .btn-primary:hover::before {
            left: 100%;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.4);
        }
        
        .btn-secondary {
            padding: 1.2rem 3rem;
            background: transparent;
            color: #fff;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            letter-spacing: 0.5px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            transition: all 0.3s;
        }
        
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: #00d4ff;
            transform: translateY(-3px);
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 3rem;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(10px); }
        }
        
        /* Features Section */
        .features {
            background: #fff;
            padding: 8rem 2rem;
            position: relative;
        }
        
        .section-header {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 5rem;
        }
        
        .section-label {
            color: #0099ff;
            font-size: 0.9rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 1rem;
        }
        
        .section-title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            letter-spacing: -1px;
        }
        
        .section-description {
            font-size: 1.2rem;
            color: #666;
            line-height: 1.8;
        }
        
        .features-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 3rem;
        }
        
        .feature-card {
            background: #fff;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.05);
            transition: all 0.4s;
            border: 1px solid rgba(0, 0, 0, 0.05);
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.05) 0%, rgba(0, 153, 255, 0.05) 100%);
            opacity: 0;
            transition: opacity 0.4s;
        }
        
        .feature-card:hover::before {
            opacity: 1;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 153, 255, 0.15);
        }
        
        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #00d4ff 0%, #0099ff 100%);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            margin-bottom: 2rem;
            position: relative;
        }
        
        .feature-card h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
            color: #111;
            position: relative;
        }
        
        .feature-card p {
            color: #666;
            line-height: 1.8;
            font-size: 1.05rem;
            position: relative;
        }
        
        /* Technology Section */
        .technology {
            background: linear-gradient(180deg, #0a0a0a 0%, #000 100%);
            padding: 8rem 2rem;
            color: #fff;
        }
        
        .technology .section-title,
        .technology .section-label {
            color: #fff;
        }
        
        .tech-showcase {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
        }
        
        .tech-image {
            width: 100%;
            height: 500px;
            background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
            border-radius: 20px;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6rem;
            box-shadow: 0 20px 60px rgba(0, 212, 255, 0.2);
        }
        
        .tech-content h3 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            line-height: 1.3;
        }
        
        .tech-features {
            list-style: none;
        }
        
        .tech-features li {
            padding: 1.5rem 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.8);
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .tech-features li::before {
            content: '✓';
            color: #00d4ff;
            font-weight: bold;
            font-size: 1.5rem;
        }
        
        /* Products Section */
        .products {
            background: #f8f9fa;
            padding: 8rem 2rem;
        }
        
        .products-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2rem;
        }
        
        .product-card {
            background: #fff;
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.4s;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
        }
        
        .product-image {
            height: 250px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            position: relative;
            overflow: hidden;
        }
        
        .product-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }
        
        .product-card:hover .product-image::after {
            left: 100%;
        }
        
        .product-info {
            padding: 2rem;
        }
        
        .product-info h3 {
            font-size: 1.4rem;
            margin-bottom: 0.8rem;
            color: #111;
        }
        
        .product-info p {
            color: #666;
            line-height: 1.6;
        }
        
        /* Stats Section */
        .stats {
            background: linear-gradient(135deg, #00d4ff 0%, #0099ff 100%);
            padding: 6rem 2rem;
            color: #fff;
        }
        
        .stats-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 3rem;
            text-align: center;
        }
        
        .stat-item h3 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        
        .stat-item p {
            font-size: 1.2rem;
            font-weight: 300;
        }
        
        /* Contact Section */
        .contact {
            background: #fff;
            padding: 8rem 2rem;
        }
        
        .contact-container {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
        }
        
        .contact-info h2 {
            font-size: 3rem;
            margin-bottom: 2rem;
            line-height: 1.2;
        }
        
        .contact-details {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        
        .contact-item {
            padding: 2rem;
            background: #f8f9fa;
            border-radius: 15px;
            transition: all 0.3s;
        }
        
        .contact-item:hover {
            background: #e9ecef;
            transform: translateX(10px);
        }
        
        .contact-item h4 {
            font-size: 0.9rem;
            color: #0099ff;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 0.5rem;
        }
        
        .contact-item p {
            font-size: 1.3rem;
            color: #111;
            font-weight: 500;
        }
        
        .contact-form {
            background: #f8f9fa;
            padding: 3rem;
            border-radius: 20px;
        }
        
        .form-group {
            margin-bottom: 2rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #111;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
            background: #fff;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #00d4ff;
        }
        
        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: #000;
            color: rgba(255, 255, 255, 0.6);
            padding: 3rem 2rem;
            text-align: center;
        }
        
        footer p {
            font-size: 0.95rem;
        }
        
        /* Responsive */
        @media (max-width: 1200px) {
            .features-grid,
            .products-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .tech-showcase,
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 3rem;
            }
            
            .hero-subtitle {
                font-size: 1.3rem;
            }
            
            .section-title {
                font-size: 2.5rem;
            }
            
            .features-grid,
            .products-grid,
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .nav-menu {
                display: none;
            }
            
            .cta-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header id="header">
        <nav>
            <div class="logo">N E TECH</div>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Technology</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-bg"></div>
        <div class="hero-grid"></div>
        <div class="hero-content">
            <h1>Innovation in Motion</h1>
            <p class="hero-subtitle">플라스틱 사출금형의 새로운 기준</p>
            <p class="hero-description">
                자동차 산업의 미래를 선도하는 정밀 제조 기술과 혁신적인 솔루션으로<br>
                글로벌 자동차 부품 산업의 새로운 지평을 열어갑니다
            </p>
            <div class="cta-buttons">
                <a href="#contact" class="btn-primary">문의하기</a>
                <a href="#features" class="btn-secondary">자세히 보기</a>
            </div>
        </div>
        <div class="scroll-indicator">
            Scroll ↓
        </div>
    </section>

    <section id="features" class="features">
        <div class="section-header">
            <div class="section-label">Core Competencies</div>
            <h2 class="section-title">차별화된 기술력</h2>
            <p class="section-description">
                최첨단 사출금형 기술과 자동화 시스템으로 최고 품질의 자동차 부품을 생산합니다
            </p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">⚙️</div>
                <h3>정밀 사출금형</h3>
                <p>마이크로미터 단위의 정밀도를 자랑하는 최첨단 사출금형 기술로 완벽한 제품을 생산합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🔬</div>
                <h3>품질 보증</h3>
                <p>ISO 인증 기반의 철저한 품질관리 시스템과 전수검사로 최상의 품질을 보증합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🚀</div>
                <h3>혁신 기술</h3>
                <p>지속적인 R&D 투자로 업계를 선도하는 혁신적인 제조 기술을 개발합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🏭</div>
                <h3>자동화 생산</h3>
                <p>스마트 팩토리 기반의 자동화 생산 시스템으로 효율성과 생산성을 극대화합니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">♻️</div>
                <h3>친환경</h3>
                <p>환경을 생각하는 친환경 제조 공정으로 지속 가능한 미래를 만들어갑니다.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🤝</div>
                <h3>파트너십</h3>
                <p>글로벌 완성차 업체와의 긴밀한 협력으로 최적의 솔루션을 제공합니다.</p>
            </div>
        </div>
    </section>

    <section class="technology">
        <div class="section-header">
            <div class="section-label">Technology</div>
            <h2 class="section-title">자동차 펌프 전문 기술</h2>
        </div>
        <div class="tech-showcase">
            <div class="tech-image">🔧</div>
            <div class="tech-content">
                <h3>최첨단 펌프 제조 시스템</h3>
                <ul class="tech-features">
                    <li>고압 사출 성형 기술</li>
                    <li>정밀 조립 자동화 라인</li>
                    <li>실시간 품질 모니터링</li>
                    <li>무결점 생산 시스템</li>
                    <li>글로벌 품질 인증</li>
                </ul>
            </div>
        </div>
    </section>

    <section id="products" class="products">
        <div class="section-header">
            <div class="section-label">Products</div>
            <h2 class="section-title">주요 제품</h2>
            <p class="section-description">
                자동차 산업을 위한 프리미엄 플라스틱 부품 솔루션
            </p>
        </div>
        <div class="products-grid">
            <div class="product-card">
                <div class="product-image">💧</div>
                <div class="product-info">
                    <h3>워터 펌프</h3>
                    <p>엔진 냉각 시스템용 고효율 워터 펌프</p>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image">⛽</div>
                <div class="product-info">
                    <h3>연료 펌프</h3>
                    <p>정밀 연료 공급 시스템용 펌프</p>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image">🌊</div>
                <div class="product-info">
                    <h3>오일 펌프</h3>
                    <p>엔진 윤활 시스템용 고성능 펌프</p>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image">🔩</div>
                <div class="product-info">
                    <h3>맞춤형 금형</h3>
                    <p>고객 요구사항 맞춤 설계 제작</p>
                </div>
            </div>
        </div>
    </section>

    <section class="stats">
        <div class="stats-grid">
            <div class="stat-item">
                <h3>20+</h3>
                <p>Years of Experience</p>
            </div>
            <div class="stat-item">
                <h3>500+</h3>
                <p>Projects Completed</p>
            </div>
            <div class="stat-item">
                <h3>99.9%</h3>
                <p>Quality Rate</p>
            </div>
            <div class="stat-item">
                <h3>50+</h3>
                <p>Global Partners</p>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="contact-container">
            <div class="contact-info">
                <h2>함께 성장할<br>파트너를 찾습니다</h2>
                <div class="contact-details">
                    <div class="contact-item">
                        <h4>Phone</h4>
                        <p>02-XXXX-XXXX</p>
                    </div>
                    <div class="contact-item">
                        <h4>Email</h4>
                        <p>info@netech.co.kr</p>
                    </div>
                    <div class="contact-item">
                        <h4>Address</h4>
                        <p>경기도 부천시</p>
                    </div>
                    <div class="contact-item">
                        <h4>Business Hours</h4>
                        <p>평일 09:00 - 18:00</p>
                    </div>
                </div>
            </div>
            <div class="contact-form">
                <form>
                    <div class="form-group">
                        <label>회사명</label>
                        <input type="text" placeholder="회사명을 입력하세요">
                    </div>
                    <div class="form-group">
                        <label>담당자명</label>
                        <input type="text" placeholder="성함을 입력하세요">
                    </div>
                    <div class="form-group">
                        <label>이메일</label>
                        <input type="email" placeholder="이메일을 입력하세요">
                    </div>
                    <div class="form-group">
                        <label>문의내용</label>
                        <textarea placeholder="문의하실 내용을 입력하세요"></textarea>
                    </div>
                    <button type="submit" class="btn-primary" style="width: 100%;">문의 보내기</button>
                </form>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 N E TECH. All Rights Reserved. | Automotive Parts Manufacturing Excellence</p>
    </footer>

    <script>
        // Header scroll effect
        const header = document.getElementById('header');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList
