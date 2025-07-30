<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Google Fonts: Diphylleia for titles, Noto Serif KR for body -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Diphylleia&family=Noto+Serif+KR:wght@300;400;700&display=swap" rel="stylesheet">

    <style>
        /* CSS Design by a Human Designer, with care. */

        /* ------------------------- */
        /* --- 1. Core & Setup --- */
        /* ------------------------- */
        :root {
            --color-bg-dark: #0c1412;
            --color-green-medium: #1a2b28;
            --color-green-glow: #a8ff89;
            --color-gold-accent: #e6d3a8;
            --color-purple-dark: #2d1b3d;
            --color-purple-light: #764ba2;
            --font-magic: 'Diphylleia', serif; /* Title Font Changed */
            --font-body: 'Noto Serif KR', sans-serif; /* Body Font Changed */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            height: 100%;
        }

        body {
            background-color: var(--color-bg-dark);
            font-family: var(--font-body);
            color: #fff;
            min-height: 100vh;
            background-image: url('https://i.pinimg.com/originals/3b/87/26/3b8726191a35528459487676752317b6.gif');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            position: relative;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(ellipse at center, rgba(12, 20, 18, 0.4) 0%, rgba(12, 20, 18, 0.9) 80%);
            z-index: 1;
            pointer-events: none;
        }

        /* ------------------------- */
        /* --- 2. Main Container --- */
        /* ------------------------- */

        .page-wrapper {
            position: relative;
            z-index: 2;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem;
        }

        .main-container {
            display: none;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 100%;
            max-width: 600px;
        }
        
        .main-container.active {
            display: flex;
        }
        
        .profile-header {
            margin-bottom: 2rem;
            animation: fadeInDown 1s ease-out forwards;
        }

        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--color-gold-accent);
            box-shadow: 0 0 15px var(--color-gold-accent), 0 0 25px rgba(230, 211, 168, 0.5);
            margin-bottom: 1rem;
            background-image: url('https://i.pinimg.com/564x/7a/17/99/7a1799718b5c90b852f2008e330f65b1.jpg');
            background-size: cover;
            background-position: center;
        }

        .profile-name {
            font-family: var(--font-magic);
            font-size: 2.5rem;
            color: #fff;
            text-shadow: 0 0 5px var(--color-green-glow), 0 0 10px var(--color-green-glow);
            margin-bottom: 10px; /* <<< [변경] 제목 아래 여백 추가 */
        }

        .profile-tagline {
            font-size: 1rem;
            color: var(--color-gold-accent);
            opacity: 0.9;
        }

        /* --------------------------------- */
        /* --- 3. Magical Button Links --- */
        /* --------------------------------- */
        
        .links-container {
            width: 100%;
            max-width: 500px;
        }
        
        .magic-button {
            display: block;
            text-decoration: none;
            color: #fff;
            background-color: rgba(26, 43, 40, 0.85);
            font-family: var(--font-magic);
            font-size: 1.25rem;
            padding: 15px 60px;
            margin: 1rem 0;
            border: 2px solid var(--color-gold-accent);
            border-radius: 15px;
            position: relative;
            transition: all 0.3s ease;
            box-shadow: 0 0 5px rgba(230, 211, 168, 0.4);
            animation: fadeInUp 0.5s ease-out forwards;
            animation-delay: var(--delay);
            cursor: pointer;
            overflow: visible; /* Allow decorations to show outside button */
        }
        
        /* Left and Right decorations */
        .magic-button::after {
            content: '✧';
            font-family: serif;
            position: absolute;
            font-size: 1.5rem;
            color: var(--color-gold-accent);
            opacity: 0.8;
            transition: all 0.3s ease;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
        }
        
        /* Right decoration - moved to far right edge */
        .magic-button span::after {
            content: '✧';
            font-family: serif;
            position: absolute;
            font-size: 1.5rem;
            color: var(--color-gold-accent);
            opacity: 0.8;
            transition: all 0.3s ease;
            right: -40px;
            top: 50%;
            transform: translateY(-50%);
        }
        
        .magic-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-radius: 15px;
            border: 2px solid transparent;
            box-shadow: inset 0 0 10px var(--color-green-glow);
            opacity: 0.7;
            transition: all 0.3s ease;
        }
        
        .magic-button:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 0 15px var(--color-gold-accent);
            color: var(--color-gold-accent);
        }
        
        .magic-button:hover::before {
            opacity: 1;
            box-shadow: inset 0 0 15px var(--color-green-glow), 0 0 15px var(--color-green-glow);
        }
        
        .magic-button:hover::after {
            opacity: 1;
            text-shadow: 0 0 10px var(--color-gold-accent);
            transform: translateY(-50%) rotate(360deg);
        }
        
        .magic-button span {
            position: relative;
            display: block;
        }

        /* --------------------------------- */
        /* --- 4. Page Content Styles --- */
        /* --------------------------------- */
        
        .page-content {
            display: none;
            width: 100%;
            max-width: 900px;
            margin: 0 auto;
            animation: fadeIn 0.8s ease-out;
        }
        
        .page-content.active {
            display: block;
        }
        
        .back-button {
            display: inline-block;
            margin-bottom: 2rem;
            padding: 10px 30px;
            background-color: rgba(26, 43, 40, 0.85);
            border: 2px solid var(--color-gold-accent);
            border-radius: 10px;
            color: var(--color-gold-accent);
            text-decoration: none;
            font-family: var(--font-magic);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .back-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 10px var(--color-gold-accent);
            background-color: rgba(26, 43, 40, 1);
        }
        
        .content-header {
            font-family: var(--font-magic);
            font-size: 2.5rem;
            color: var(--color-gold-accent);
            margin-bottom: 2rem;
            text-shadow: 0 0 5px var(--color-green-glow);
            text-align: center;
        }
        
        .content-text {
            background-color: rgba(26, 43, 40, 0.8);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid var(--color-gold-accent);
            line-height: 1.8;
            margin-bottom: 2rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
        }
        
        .content-text h3 {
            color: var(--color-gold-accent);
            margin-bottom: 1rem;
            font-family: var(--font-magic);
        }
        
        .content-text p {
            margin-bottom: 1rem;
        }
        
        .content-text ul {
            list-style: none;
            padding-left: 0;
            margin-top: 1rem;
        }
        
        .content-text li {
            margin-bottom: 0.8rem;
            padding-left: 1.5rem;
        }
        
        .character-grid {
            display: grid;
            gap: 2rem;
            margin-top: 2rem;
        }
        
        /* Main character - full width */
        .character-card.main-character {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: 200px 1fr;
            gap: 2rem;
            padding: 2.5rem;
            background: linear-gradient(135deg, rgba(26, 43, 40, 0.95), rgba(45, 70, 60, 0.9));
            border: 3px solid var(--color-gold-accent);
        }
        
        .main-character .character-avatar {
            width: 180px;
            height: 180px;
            margin: 0;
        }
        
        .main-character .character-info {
            text-align: left;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .main-character .character-name {
            font-size: 2rem;
            margin-bottom: 1rem;
        }
        
        .main-character .character-role {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
        }
        
        .main-character .character-description {
            font-size: 1rem;
            line-height: 1.8;
        }
        
        /* Supporting characters grid */
        .supporting-characters {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }
        
        .supporting-characters .character-card:nth-child(4),
        .supporting-characters .character-card:nth-child(5) {
            grid-column: span 1;
        }
        
        /* Make last row center aligned */
        .bottom-row {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 2rem;
            max-width: 66.66%;
            margin: 0 auto;
        }
        
        .character-card {
            background-color: rgba(26, 43, 40, 0.9);
            border: 2px solid var(--color-gold-accent);
            border-radius: 15px;
            padding: 2rem 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
            cursor: pointer;
        }
        
        .character-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(168, 255, 137, 0.3);
            border-color: var(--color-green-glow);
        }
        
        .character-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            background-size: cover;
            background-position: center;
            border: 3px solid var(--color-green-glow);
            box-shadow: 0 0 20px rgba(168, 255, 137, 0.4);
        }
        
        .character-name {
            font-family: var(--font-magic);
            font-size: 1.4rem;
            color: var(--color-gold-accent);
            margin-bottom: 0.5rem;
        }
        
        .character-role {
            color: var(--color-green-glow);
            font-size: 0.95rem;
            margin-bottom: 1rem;
            font-style: italic;
        }
        
        .character-description {
            font-size: 0.9rem;
            line-height: 1.8; 
            color: #ddd;
        }

        /* --------------------------------- */
        /* --- Character Profile Page --- */
        /* --------------------------------- */
        
        .profile-detail-container {
            background: rgba(26, 43, 40, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            padding: 40px;
            width: 100%;
            max-width: 1000px;
            position: relative;
            overflow: hidden;
            border: 2px solid var(--color-gold-accent);
        }

        .profile-detail-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, var(--color-green-glow), var(--color-gold-accent), var(--color-green-glow));
        }

        .quote-section {
            text-align: center;
            margin-bottom: 30px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(168, 255, 137, 0.2), rgba(230, 211, 168, 0.2));
            border-radius: 15px;
            border: 1px solid var(--color-gold-accent);
            color: var(--color-gold-accent);
            position: relative;
        }

        .quote-section::before {
            content: '"';
            font-size: 4rem;
            position: absolute;
            top: -10px;
            left: 20px;
            opacity: 0.3;
            color: var(--color-green-glow);
        }

        .quote-text {
            font-size: 1.1rem;
            font-weight: 300;
            line-height: 1.8;
            font-style: italic;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 40px;
            margin-bottom: 30px;
        }

        .character-image-large {
            background: linear-gradient(135deg, var(--color-purple-dark), var(--color-green-medium));
            border-radius: 20px;
            aspect-ratio: 3/4;
            position: relative;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
            border: 3px solid var(--color-gold-accent);
        }

        .character-image-large img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .character-title-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
            color: white;
            padding: 30px 20px 20px;
            text-align: center;
        }

        .character-title-overlay h1 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            color: var(--color-gold-accent);
            font-family: var(--font-magic);
        }

        .character-subtitle {
            font-size: 1rem;
            opacity: 0.9;
            font-weight: 300;
            color: var(--color-green-glow);
        }

        .profile-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .info-section {
            background: rgba(26, 43, 40, 0.6);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            border-left: 5px solid var(--color-green-glow);
            border: 1px solid var(--color-gold-accent);
        }

        .info-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--color-gold-accent);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: var(--font-magic);
        }

        .info-title::before {
            content: '✦';
            color: var(--color-green-glow);
        }

        .info-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .info-item {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .info-label {
            font-size: 0.9rem;
            color: var(--color-green-glow);
            font-weight: 500;
        }

        .info-value {
            font-size: 1rem;
            color: #fff;
            font-weight: 400;
            padding: 8px 12px;
            background: rgba(168, 255, 137, 0.1);
            border-radius: 8px;
            border: 1px solid rgba(168, 255, 137, 0.3);
        }

        .personality-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 10px;
        }

        .tag {
            background: linear-gradient(135deg, var(--color-green-glow), var(--color-gold-accent));
            color: var(--color-bg-dark);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
            box-shadow: 0 5px 10px rgba(168, 255, 137, 0.3);
        }

        .features-section {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }

        .feature-card {
            background: rgba(26, 43, 40, 0.8);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
            border: 1px solid var(--color-gold-accent);
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(168, 255, 137, 0.3);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--color-green-glow), var(--color-gold-accent));
            border-radius: 50%;
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
        }

        .feature-title {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--color-gold-accent);
            margin-bottom: 10px;
            font-family: var(--font-magic);
        }

        .feature-desc {
            font-size: 0.9rem;
            color: #ddd;
            line-height: 1.8;
        }

        .description-section {
            background: rgba(26, 43, 40, 0.8);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
            border: 1px solid var(--color-gold-accent);
        }

        .description-title {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--color-gold-accent);
            margin-bottom: 20px;
            text-align: center;
            font-family: var(--font-magic);
        }

        .description-text {
            font-size: 1rem;
            line-height: 1.8;
            color: #ddd;
            text-align: justify;
        }

        /* ----------------------------- */
        /* --- 5. Animations & FX --- */
        /* ----------------------------- */
        
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* ----------------------------- */
        /* --- 6. Responsiveness --- */
        /* ----------------------------- */

        @media (max-width: 768px) {
            .page-wrapper {
                padding: 1rem;
                align-items: flex-start;
            }
            
            .content-header {
                font-size: 2rem;
            }
            
            .character-card.main-character {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .main-character .character-avatar {
                margin: 0 auto 1.5rem;
            }
            
            .main-character .character-info {
                text-align: center;
            }
            
            .supporting-characters {
                grid-template-columns: 1fr;
            }
            
            .bottom-row {
                grid-template-columns: 1fr;
                max-width: 100%;
            }
            
            .content-text {
                padding: 1.5rem;
            }
            
            .main-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .info-grid {
                grid-template-columns: 1fr;
            }
            
            .features-section {
                grid-template-columns: 1fr;
            }
            
            .profile-detail-container {
                padding: 20px;
            }
        }

        @media (max-width: 600px) {
            .profile-avatar {
                width: 120px;
                height: 120px;
            }
            .profile-name {
                font-size: 2rem;
            }
            .magic-button {
                font-size: 1.1rem;
                padding: 12px 50px;
            }
            .character-avatar {
                width: 100px;
                height: 100px;
            }
        }
    </style>
</head>
<body>

    <div class="page-wrapper">
        <!-- Main Hub -->
        <div id="main-hub" class="main-container active">
            <header class="profile-header">
                <div class="profile-avatar"></div>
                <h1 class="profile-name">하렘의 남자들</h1>
                <p class="profile-tagline">정확히는 담이의 도파민 생성제들</p>
            </header>

            <nav class="links-container">
                <a class="magic-button" style="--delay: 0.6s;" onclick="showPage('worldbuilding')"><span>Universe</span></a>
                <a class="magic-button" style="--delay: 0.7s;" onclick="showPage('characters')"><span>Character</span></a>
                <a href="https://www.band.us/band/99216051" target="_blank" class="magic-button" style="--delay: 0.8s;"><span>Band</span></a>
                <a href="https://open.kakao.com/o/gHx0LMFh" target="_blank" class="magic-button" style="--delay: 0.9s;"><span>Kakao talk</span></a>
            </nav>
        </div>

        <!-- Worldbuilding Page -->
        <div id="worldbuilding" class="page-content">
            <a class="back-button" onclick="showPage('main')">← Back</a>
            <h2 class="content-header">세계관</h2>
            
            <div class="content-text">
                <h3>현대 판타지</h3>
                <p>한때 인류는 농업과 산업의 효율을 높이기 위해 식물과 동물의 유전자를 대대적으로 개조했지만, 그 부작용으로 변형된 생명체들은 `마물`이라 불리며 폭력적으로 진화했다. 이 마물들이 지구 곳곳을 파괴하면서 인간이 안전하게 생존할 수 있는 땅은 갈수록 줄어들었다.</p>
                
                <p>그러나 아이러니하게도 인간 역시 유전자 조작의 영향을 받아 특별한 이능력을 지닌 이들이 속속 등장했다. 이능력자들 덕에 인간들은 멸종하지 않을 수 있었고, 땅덩어리 또한 탈환할 수 있었다.</p>
				
				<p>이 세계에서 최고의 가치는 곧 ‘힘’이다. 부가 곧 권력을 의미하기도 하지만 진정한 강자는 어떤 재산보다 물리적·초능력적 우위를 가진 자다. 재력으로 모든 것을 통제할 수 있다 해도 더 강력한 존재가 나타나면 한순간에 빼앗길 수밖에 없기 때문이다.</p>
            </div>
            
            <div class="content-text">
                <h3>6 영토</h3>
                <p>지구는 이제 여섯 개의 거대 영토로 나뉘며 각 지역에는 국적이 뒤섞인 인간들이 거주한다.</p>
                <ul>
                    <li>🌿 <strong>기역</strong> - 한국쪽</li>
                    <li>🌙 <strong>반</strong> - 미정 / 조지아어</li>
                    <li>🍄 <strong>고 카이</strong> - 미정 / 태국어</li>
                    <li>💎 <strong>하</strong> - 미정 / 암하라어</li>
                    <li>🌊 <strong>알파</strong> - 미정 / 그리스어</li>
                    <li>🌺 <strong>카</strong> - 미정 / 티베트어</li>
                </ul>
            </div>
            
            <div class="content-text">
                <h3>기역 영토</h3>
                <p>현재 무대가 되는 영토</p>
                <p style="font-style: italic; text-align: center; margin-top: 1.5rem; color: var(--color-green-glow);">
                    "규칙은 아직<br>
                    미정이라<br>
                    비워둡니다"
                </p>
            </div>
        </div>

        <!-- Characters Page -->
        <div id="characters" class="page-content">
            <a class="back-button" onclick="showPage('main')">← Back</a>
            <h2 class="content-header">황보 담의 하렘</h2>
            
            <div class="character-grid">
                <!-- Main Character -->
                <div class="character-card main-character" onclick="showCharacterProfile('dam')">
                    <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FdY0wwm%2FbtsPD2to4r6%2FAAAAAAAAAAAAAAAAAAAAAHzuPPkZL9E4bebd4KhJomJNV8347KoJeLD34PUFypVO%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D%252BgWZEARs4fn1DV%252BM4NUr0vAL2eU%253D');"></div>
                    <div class="character-info">
                        <h3 class="character-name">황보 담</h3>
                        <p class="character-role">34세 :: 177cm :: 마른 근육질 :: B</p>
                        <p class="character-description">전 영주를 제끼고 <i>기역 영토</i>의 영주가 되었다. 영토 사람들의 생존에 도움이 되는 능력을 가진 덕에 영토 내에서의 위상은 높다.</p>
                    </div>
                </div>
                
                <!-- Supporting Characters - First Row -->
                <div class="supporting-characters">
                    <div class="character-card" onclick="showCharacterProfile('fos')">
                        <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbKfHho%2FbtsPCnMi3ki%2FAAAAAAAAAAAAAAAAAAAAACxsxS2G83bg8jNOcFYgaqagipMNWfjnns7QHeKUj5g1%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3DUlyhCqS9B%252F1fpf2diMw0aVvbWSY%253D');"></div>
                        <h3 class="character-name">필포스</h3>
                        <p class="character-role">55세 :: 190cm :: 근육+살집  근육 40% 살 60% :: M</p>
                        <p class="character-description">강약약강의 권력추구자. 황보 담의 곁에서 권력을 추구한다.</p>
                    </div>
                    
                    <div class="character-card" onclick="showCharacterProfile('kara')">
                        <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FboNyCq%2FbtsPDOa6I4g%2FAAAAAAAAAAAAAAAAAAAAAAoEB1J56SOlKerrUVOc5XyhCVxJfdr0DmLkk6s0q5sh%2Fimg.webp%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D%252FpvWrTnO6KqmMota5uO5kd0dHxw%253D');"></div>
                        <h3 class="character-name">에브 카라</h3>
                        <p class="character-role">26세 :: 182cm :: 평균 :: T</p>
                        <p class="character-description">자존심 없는 기회주의자. 악과 자신감, 의심만큼은 넘친다.</p>
                    </div>
                    
                    <div class="character-card" onclick="showCharacterProfile('uk')">
                        <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbH9xGx%2FbtsPCqbcGBj%2FAAAAAAAAAAAAAAAAAAAAAP9eWP7ZP5zdcSlGYVgd89DKHe3-BYF6_WI0nzSQuOD-%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3DwAfwt8au4jQghhLoQPpc9AkBOyY%253D'); background-position: 50% 20%;"></div>
                        <h3 class="character-name">한 현욱</h3>
                        <p class="character-role">44세 :: 192cm :: 근육질 :: M</p>
                        <p class="character-description">사회적으로는 서글서글하지만 실제로는 계산적이고 자기중심적인 이기주의자.</p>
                    </div>
                </div>
                
                <!-- Supporting Characters - Second Row -->
                <div class="bottom-row">
                    <div class="character-card" onclick="showCharacterProfile('sol')">
                        <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FSCOmx%2FbtsPCKN8A8H%2FAAAAAAAAAAAAAAAAAAAAALQlPU2HBQZbZwxRXjVXnfjsPxv4FVP3VURl6S5nKP2-%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3DaZtdEi9OCh7Nef0dGbrikj6BTpc%253D');"></div>
                        <h3 class="character-name">이 솔</h3>
                        <p class="character-role">21세 :: 188cm :: 87kg :: M</p>
                        <p class="character-description">누구에게나 손길을 허락하는 대형 견. 사교성도 좋아 남들에게 쉽게 사랑받는다.</p>
                    </div>
                    
                    <div class="character-card" onclick="showCharacterProfile('il')">
                        <div class="character-avatar" style="background-image: url('https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FdFGfU6%2FbtsPDMRViVy%2FAAAAAAAAAAAAAAAAAAAAABqGcFi9x4FxbdP5bMgAv7U4s7MNajMBCt43hk-_nALe%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D%252Bhc6q6Vwzbi72WSmAyttIx%252FpPTo%253D');"></div>
                        <h3 class="character-name">최명일</h3>
                        <p class="character-role">36세 :: 186cm :: 근육질 :: T</p>
                        <p class="character-description">한 명(황보 담)을 제외한 상대에게는 언제까지나 상식인. 강한 열등감을 가지고 있다.</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Character Profile Detail -->
        <div id="character-profile" class="page-content">
            <a class="back-button" onclick="showPage('characters')">← Back</a>
            
            <div class="profile-detail-container">
                <div class="quote-section">
                    <div class="quote-text" id="character-quote">
                        "The forest speaks to those who listen with their hearts."
                    </div>
                </div>

                <div class="main-content">
                    <div class="character-image-large">
                        <img id="character-image" src="https://i.pinimg.com/564x/7a/17/99/7a1799718b5c90b852f2008e330f65b1.jpg" alt="Character">
                        <div class="character-title-overlay">
                            <h1 id="character-detail-name">Character Name</h1>
                            <div class="character-subtitle" id="character-detail-role">Role</div>
                        </div>
                    </div>

                    <div class="profile-info">
                        <div class="info-section">
                            <div class="info-title">기본 정보</div>
                            <div class="info-grid">
                                <div class="info-item">
                                    <div class="info-label">나이</div>
                                    <div class="info-value" id="character-age">Unknown</div>
                                </div>
                                <div class="info-item">
                                    <div class="info-label">신장/체형</div>
                                    <div class="info-value" id="character-height">Unknown</div>
                                </div>
                                <div class="info-item">
                                    <div class="info-label">포지션</div>
                                    <div class="info-value" id="character-born">Unknown</div>
                                </div>
                                <div class="info-item">
                                    <div class="info-label">능력</div>
                                    <div class="info-value" id="character-element">Unknown</div>
                                </div>
                            </div>
                        </div>

                        <div class="info-section">
                            <div class="info-title">성격</div>
                            <div class="personality-tags" id="character-traits">
                                <span class="tag">Wise</span>
                                <span class="tag">Mystical</span>
                                <span class="tag">Protective</span>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="features-section">
                    <div class="feature-card">
                        <div class="feature-icon">🌿</div>
                        <div class="feature-title">외형</div>
                        <div class="feature-desc" id="character-appearance">
                            Mystical appearance with flowing robes
                        </div>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">✨</div>
                        <div class="feature-title">능력</div>
                        <div class="feature-desc" id="character-abilities">
                            Magical powers and ancient wisdom
                        </div>
                    </div>
                    <div class="feature-card">
                        <div class="feature-icon">🔮</div>
                        <div class="feature-title">성향</div>
                        <div class="feature-desc" id="character-tool">
                            Mystical artifact or familiar
                        </div>
                    </div>
                </div>

                <div class="description-section">
                    <div class="description-title">캐릭터 이야기</div>
                    <div class="description-text" id="character-story">
                        A detailed background story of the character...
                    </div>
                </div>
            </div>
        </div>

    <script>
        // Character data
        const characterData = {
            fos: {
                name: "필포스",
                role: "아첨의 달인",
                image: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fwed80%2FbtsPBMFKPOu%2FAAAAAAAAAAAAAAAAAAAAADaqQEJkczir3GxYTnEqS6SPtyflEiMLkY_BbX65ZS4j%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D71YJ3KMS5BD2FXr5yfd1cU7%252BhM8%253D",
                quote: "치료해달라고? 맨입으로? 기합으로 이겨내라.",
                age: "55 세",
                height: "190cm / 근육+살집  근육 40% 살 60%",
                born: "Multi",
                element: "회복, 복원, 재생",
                traits: ["강약약강", "권력추구자", "절대 손해보지않을 것이다(나보다 상급자 빼고)"],
                appearance: "좋지 않은 성격 탓에 왼쪽 눈을 이능력으로 공격받아 눈 색이 탁하고 시야가 흐리다.\n\n큰 덩치, 화려한 옷과 행동을 할 때마다 금속이 부딪치는 소리가 날 정도로 금 장신구를 잔뜩 둘렀다\n\n흰색과 금색상의 옷을 선호, 더러워지면 바로 갈아입는다.\n\n체모가 많은 편, 남성성이 강해 보여 자부심을 느끼고 있다.",
                abilities: "골드타임 안에 능력을 쓴다면 목이 잘려도 소생 가능\n\n너무 오래된 절단 부위나 상처는 회복하지 못한다.\n\n잘린 부위 재생시키기 가능 (영구 상해 방지 차원)\n\n본인이 다쳐, 기절할 정도라면 무의식의 생존 본능에 의해 회복한다 (살고 싶어요)",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호:  일상대화 , 브레스 컨트롤, 오르가즘 컨트롤 ...등 가학적인 플레이\n불호:  아픈 거 당하는 거 싫어!!! (존심상함 이슈) ,더러운 거 싫어!! (내가하면 ㄱㅊ음)\n\n<b>오너 성향</b>\n성행위: O\n\n R19, G19 모두 환영하나 R19쪽으로 가게 되면 수줍음에 폭력적인 행동을 하게 될 수 있습니다.\n\n호: 캐 동일, R19,G19…뭘 써야할지 모르겠어요 대충 거의 다 먹긴함 \n불호: 스캇(골든 제외),방치플?",
                story: "- 20대부터 자신의 이능력으로 이득을 볼 수 있는 무리를 찾아 돌아다녔다.\n- 분위기의 흐름을 잘 읽거나, 운이 좋아 타이밍에 맞게 발을 뺌으로 크게 화를 당한 적은 없다.\n- 인생을 무난하게 살아온 탓에 자존감과 자신감이 가득하다…\n- 권력을 탐하지만, 세력을 얻기엔 힘든 이능력과 한 무리의 보스가 하극상 당하는 모습을 많이 봐와서 그런지 일인자보다는 2~3인자를 선호한다.\n- 공격 특화가 아닌 이능력을 무시하는 대상에게 치유 능력이 얼마나 좋은 건지 알게 해주겠다며, 인체 해부학 책의 이미지에 가까운 모습으로 고문하고 치유해 준 적이 있다…  이후 그 대상에게 무시당한 적이 없으며, 필포스는 대상의 고통스러워하는 반응에 새로운 취향에 눈을 뜨게 된다… (가학 취향에 눈을 뜨게 됐지만 이미지관리 차원으로 자제하는 편… 하지만 기회가 온다면 즐기겠죠?)\n- 일인자의 명령이 아니라면 거래를 통해 능력을 써준다. (현금, 화폐가치가 있는 사치품, 줄 게 없다면 인체 공부 겸 +아파하는 모습을 볼 수 있도록 환부를 헤집거나, 고문에 가까운 행위를 즐기고 치료해 준다는… 몸으로 때우라는 거래 형식, 기분이 좋을 땐 흔쾌히 아무 조건 없이 치료할 때도 있다.)\n- 복식은 속한 무리에 따라서 달라진다. 이번 보스가 하렘을 차린다고 하니 상체를 반을 깠지만,,, 보통 단정히 입거나 잘 여미고 다닌다…"
            },
            uk: {
                name: "한현욱",
                role: "고개 숙이고 꼴아보기",
                image: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbH9xGx%2FbtsPCqbcGBj%2FAAAAAAAAAAAAAAAAAAAAAP9eWP7ZP5zdcSlGYVgd89DKHe3-BYF6_WI0nzSQuOD-%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3DwAfwt8au4jQghhLoQPpc9AkBOyY%253D",
                quote: "안녕하세요! 날씨가 좋죠?",
                age: "44 세",
                height: "192cm / 근육질",
                born: "Multi",
                element: "매혹",
                traits: ["복흑", "이기주의", "현실적"],
                appearance: "짙은 회색 머리, 손 발이 제법 큰 편.\n가벼운 슬리퍼나 크록스를 자주 신고, 옷은 긴팔 긴 바지 위주로 입는다. 직업상 앞치마나 보호 장구를 자주 입는다.",
                abilities: "눈을 마주친 상대방에게 이 상황에서 가장 감정적으로 중요한 인물로 인식되도록 한다. 사람과 동물을 가리지 않는다.\n사람이 애정을 바란다면 그 애정을 줄 수 있는 사람으로 인식하는 식. 다만 상대방이 극단적인 성향일 경우에나, 자신에게 성욕을 가지고 있는 경우라면 이 능력을 사용할 시 어떻게 될 지 모르기 때문에 다짜고짜 능력을 사용하지는 않는 편이다.",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호:  자신이 주도권을 가지는 행위. 결박. 재갈. 도구플\n불호: 자신이 주도권을 잃는 행위. 특히 주도권을 가지는 게 어린 놈이면 더\n\n<b>오너 성향</b>\n성행위: O\n\n호: 딱히 따지는건 없는 듯? 그냥 제 기력이 없어요. \n불호: 더티플 (브라운)",
                story: "직업은… … 정육점 사장님. 사실 플로리스트를 고민했는데 정육점이 괜찮은 것 같음. 좀 쎄하잖아요."
            },
            dam: {
                name: "황보 담",
                role: "하렘의 주인",
                image: "https://smoggy-calcium-684.notion.site/image/attachment%3Ac12f5b41-c0e4-4214-b7cc-17bdff0400fc%3A93L6gL9tvArX8rkbUiIxO227WEUiJk8s3.png?table=block&id=22e9934d-5da6-8072-a665-e459de10a328&spaceId=b4b209e1-1b82-4cd6-bea4-14e59a65ed24&width=1420&userId=&cache=v2",
                quote: "왜? 네 얼굴도 찢어줘?",
                age: "34 세",
                height: "177 cm / 마른 근육질",
                born: "Bottom",
                element: "변화",
                traits: ["제멋대로", "도파민 추구자", "거만한", "오만함"],
                appearance: "흉터가 생기며 오른쪽 눈의 색이 조금 탁해졌다. 딱히 시력에 이상은 없지만 사람들이 오해하게 두는 중. 약점인 줄 알고 지능 있는 적들이 달려들 때가 즐거워서라는 이유다.\n\n전신에 흉터가 있다. 몸매는 마른 근육으로 매끈하게 다져졌다.\n\n옷을 좀 지 꼴리는 대로 입는다. 주로 입는 건 검은색 계통. 피에 젖어도 크게 티가 안나서다.",
                abilities: "<b>변화</b> 외부 물질을 변환하는 능력. 자신에게 닿은 물질을 다른 것으로 재가공이 가능하다. 능력의 한계는 거의 없지만 할 수 있는 난도를 따지자면 아래와 같다. \n\n- <b>下 상태 변화:</b> 공기 중의 수분을 얼리거나 지면에 주변 수분이나 지하수를 끌어와 늪처럼 변화 시키는 등 크게 개입하지 않아도 되는 변화. 온도, 압력 등 자연적으로도 가능한 변화를 빠르게 당겨올 수 있다. \n- <b>中 구조 변성:</b> 같은 원소로 이루어진 물질의 분자 구조를 바꾼다. 평범한 흙을 단단한 암석으로, 일반 철을 합금으로 바꿀 수 있다. \n- <b>上 원소 변환:</b> 공기 중의 질소나 흙 속의 규소 등을 다른 원소로 변환할 수 있다. 납을 금으로 바꾸거나, 공기를 독으로 만드는 등 다양한 변환이 가능하지만 고도의 집중을 필요로 한다.",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호: 도파민 넘치는 자극적인거\n불호: 허락되지 않은 하극상\n\n<b>오너 성향</b>\n성행위: O\n\n호:\n<b>가하는 것:</b> 더티토크(자보드립 등), 브레스컨트롤, 가스라이팅 및 세뇌, 요도플, 연속 절정 시키기, 약물, 컴컨트롤, 강압적인 플레이, 풋잡, 방치플\n<b>당하는 것:</b> 더티토크(자보드립 등), 골든플(장내방뇨, 골든샤워 등), 도구 취급, 인격 모욕, 가스라이팅\n불호: 브라운 스캇, 조율되지 않은 영구 상해",
                story: "- 전 영주를 제끼고 기역 영토의 영주됨\n- 졸라셈\n- 맘에 드는 녀석들은 하렘으로 데려옴\n- 뒤만 쓰는 이유: 그쪽이 더 도파민 터지더라"
            },
            sol: {
                name: "이 솔",
                role: "뇌 맑은 개",
                image: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FSCOmx%2FbtsPCKN8A8H%2FAAAAAAAAAAAAAAAAAAAAALQlPU2HBQZbZwxRXjVXnfjsPxv4FVP3VURl6S5nKP2-%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3DaZtdEi9OCh7Nef0dGbrikj6BTpc%253D",
                quote: "멍멍!",
                age: "21 세",
                height: "188cm / 87kg",
                born: "Multi",
                element: "야수화",
                traits: ["활발한", "충성심깊은", "맹목적인", "사교성 좋은"],
                appearance: "- 투블럭 숏컷 핑발\n- 색색별의 후드를 즐겨입음\n- 데미지 진\n- 발목까지 올라오는 워커\n- (보는사람기준) 오른쪽에 하늘색 피어싱",
                abilities: "<b>야수화</b>\n완전의태 부터 일부변환(수인)까지 알고있는 종류의 동물로의 전환이 가능합니다.\n\n완전의태(100%) 상태일 경우 크기는 원 동물보다 크고 강하지만 인간의 자아가 거의 사라져 말 잘듣는 동물정도의 수준입니다.\n\n주로 사용하는 동물은 보더콜리, 독수리, 보아뱀 입니다.\n\n색상은 머리털 색을 따라갑니다.\n\n반의태(50%) 흔히 수인화한 모습입니다. 완전의태 상태보다 힘이 강하진 않지만 일반적인 능력자들의 완력보단 강합니다.",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호: 시키는거 다함\n불호: 방치\n\n<b>오너 성향</b>\n성행위: O\n\n호:\n불호제외\n불호: 이건좀.. 정도의 더티플, 관절단위의 절단은 조율 필요",
                story: "- 담의 강함에 반해 스스로 하렘에 입성\n다만 뇌가 좀 맑아서 하렘을 개인 용병단 쯤으로 인식하고 들어옴\n- 이곳저곳 돌아다니는걸 좋아함"
            },
            il: {
                name: "최명일",
                role: "#널죽일끼다",
                image: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FdFGfU6%2FbtsPDMRViVy%2FAAAAAAAAAAAAAAAAAAAAABqGcFi9x4FxbdP5bMgAv7U4s7MNajMBCt43hk-_nALe%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D%252Bhc6q6Vwzbi72WSmAyttIx%252FpPTo%253D",
                quote: "……악취미도 정도가 있지.",
                age: "36 세",
                height: "186cm / 근육질",
                born: "Top",
                element: "빗줄기",
                traits: ["묵중한", "외골수", "책임감이 강하고 보수적인", "약간은 비관적인 면도", "요령 없음"],
                appearance: "흑발, 눈동자는 갈색이다. 대충 자른 머리카락은 길이가 정돈되지 않아 제멋대로 뻗쳐있다. 수염 역시 마찬가지. 시종일관 주름진 미간, 굳게 다문 입술은 과묵하다기 보다 까칠한 인상을 준다. 보기에 따라서는 추레해보이기도. 하지만 자세히 들여다보면 조금 투박할 뿐 나름대로 단정한 차림을 유지하기 위해 노력하고 있다는 것을 알 수 있다. 대부분의 사람들은 팔 한쪽이 없는 것을 보고 적당히 납득하고는 한다. 절단된 왼팔은 아문 자리를 가리기 위해 검은 천으로 감싸두었다. 남아있는 부위는 완쪽 어깨를 기준으로 한뼘 정도.\n\n옷.. 을 생각을 안해봤는데 하의만 입고 있고 왼팔 부분은 넓고 긴 천 걸쳐서 가려놓지 않았을까.. 장신구는 딱히 없음",
                abilities: "비를 내릴 수 있다. 단, 제물이 필요(몬스터의 핵이라든가 처치하면 나오는 부산물? 같은 거)",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호: 끈질길만큼 진득하고 거친 행위, 동물, 조용하고 평화로운 분위기, 작고 어리고 약하고 말랑말랑한 것\n불호: 서툴거나 소극적인 혹은 처음인 상대, 요란한 분위기 및 그런 사람\n\n<b>오너 성향</b>\n성행위: O\n\n호:\탑, 가벼운 스킨십, 패팅, 사사로운 스몰토크, 유혈, 영구상해, 불호외 딱히 가리는 것 없음. 상해 같은 것도 조율 없이 그냥 던지셔도 괜찮아요.\n불호: 대변과 관련된 모든 플레이(스캇, 관장 등)",
                story: "1. 능력의 도움도 있었지만 지역을 통솔하는 위치에 오를 만큼 무력에도 자신이 있는 편. 물론 지금은 과거의 이야기가 되었다.\n2. 특별히 리더가 되려고 했다기보다는 모이는 사람들을 내버려두다 보니 어느새 세력이 커진 느낌? 요령없고 무뚝뚝한 성격이 더해져 무관심하다는 인상이 강했으나 나름대로는 최선을 다했음. 인망은 좋지 못했을지도. 그 탓에 큰 반발 없이 세력 통합이 가능하지 않았을지… \n3. 왼팔이 절단되어 없다. 주로 사용하던 손이 없어진 탓에 어느 정도 익숙해진 지금도 여러모로 애를 먹고 있다.\n4. 성격상 남의 손을 빌리지 못해-도와달라는 말을 못함- 대부분 자신의 힘으로 처리한다. 이발, 면도 등도 마찬가지. 때문에 종종 얼굴에 베인 자국이 생기기도.\n5. 담배를 피게 된 것은 팔이 없어진 이후부터. 날이 흐려 통증이 올라오거나 그날의 일이 떠오르거나 할 때면 피는 양이 많아진다.\n6. 죽고 싶어 하지만 스스로 목숨을 끊을 만큼의 용기-이걸 용기라고 해도 될 지는 모르겠지만-는 없어서 죽지못해 살아가는 중. 내심 죽여주기를 바라고 있기 때문에 태도나 말투가 거침없다.이길 수 없다는 것을 알면서도 달려드는 것을 멈추지 않는 이유도 이 때문이다.\n7. 위와 같은 이유로 막 살 것 같지만 의외로 규칙적이고 건강한 생활을 유지하고 있다.\n8. 단련도 꾸준히."
            },
            kara: {
                name: "에브 카라",
                role: "Stone Keeper",
                image: "https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FboNyCq%2FbtsPDOa6I4g%2FAAAAAAAAAAAAAAAAAAAAAAoEB1J56SOlKerrUVOc5XyhCVxJfdr0DmLkk6s0q5sh%2Fimg.webp%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1753973999%26allow_ip%3D%26allow_referer%3D%26signature%3D%252FpvWrTnO6KqmMota5uO5kd0dHxw%253D",
                quote: "내가 사람 볼 줄 알거든.",
                age: "26 세",
                height: "182cm / 평균",
                born: "Top",
                element: "스캐닝",
                traits: ["기회주의자", "이간꾼", "의심병", "남의 고통은 나의 행복", "누구보다도 가벼운 무릎", "자신감과 악 빼면 시체"],
                appearance: "프린팅 티셔츠에 6부 길이의 통이 넓은 반바지. 주로 채도 높은 노란색, 녹색, 검은색이 들어간 옷을 자주 입는다. 보라색 신발끈과 뒷축이 엉망으로 꺾인 검은색 운동화. 왼손에는 하늘색 장식이 있는 얇은 보라색 팔찌를 착용했다.",
                abilities: "마음을 읽을 수 있는 정도의 능력\n\n마음을 읽고자 하는 상대방의 동의가 반드시 필요하다. 처음 능력을 사용할 때는 신체적 접촉이 있어야만 하고 제한 시간이 있다. 접촉은 단순히 손가락 끝을 잡는 정도여도 된다. \n대상의 허가만 있으면 능력의 시간을 늘릴 수도 있고, 상대방이 현재 느끼는 감각이나 몸의 상태, 기억까지도 그대로 전해 받을 수 있다. 대상과 멀리 떨어져도 능력을 계속 사용할 수는 있지만 까다로워서 연결이 끊기기 쉽다.\n\n능력을 사용하는 동안에는 눈의 흰자위 색이 남색으로 변한다.",
                tool: "<b>캐릭터 성향</b>\n성행위: O\n\n호: 강압, 결박, 수치플\n불호: 호에 있는 것을 자기가 당하는 것 전부\n\n<b>오너 성향</b>\n성행위: O\n\n호:\더티토크, 덥콘(동의 여부가 애매한 상황)\n불호: 브라운 스캇",
                story: "- 진작 철이 들었어야 할 무렵부터 영토의 작은 세력들을 전전하며 지냈다. 세력을 차지하거나 관리할 만한 깜냥은 되지 않아 세력에서 중요한 지위에 있다거나 했던 적은 거의 없다. 손가락을 접어가며 세어야 할 정도로 여러 세력을 옮겨 다녔는데 그 이유는 다양한 것 같으면서도 한결같다. 약해진 세력에는 있을 필요가 없다. 무너진 세력에는 있을 수도 없다. 제 이득 조금 보려고 말 몇번 옮기다가 그렇게 허무하게 망해버린 세력 정도야 원래부터 가망없던 집단이라고 생각한다. \n- 현재 이름은 2년 전, 꽤 마음에 들어서 오래 있어도 좋겠다고 생각했던 세력에 있었을 때 받은 것이다.  \n- 이능력을 써본 적은 많지 않다. 정말 필요할 때가 아니면 이능력이 있다는 사실을 남에게 알리지 않기 때문에 능력이 있다는 것을 아는 사람도 얼마 없다.  \n- 맷집이 좋다. 평균 정도의 체형과는 다르게 몸이 매우 튼튼하다. 큰 상처가 생겨도 금방 낫는 편. 여러 의미로 회복이 빠르다. 물리적이든 정신적이든… \n- 가끔 즐기는 취미는 작곡. 악기를 잘 다룬다."
            }
        };

        function showPage(page) {
            // Hide all content
            document.querySelectorAll('.main-container, .page-content').forEach(el => {
                el.classList.remove('active');
            });
            
            // Show requested page
            if (page === 'main') {
                document.getElementById('main-hub').classList.add('active');
            } else if (page === 'worldbuilding') {
                document.getElementById('worldbuilding').classList.add('active');
            } else if (page === 'characters') {
                document.getElementById('characters').classList.add('active');
            }
            
            // Scroll to top
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function showCharacterProfile(characterId) {
            const character = characterData[characterId];
            if (!character) return;

            // --- ✨✨✨ 이 부분이 수정되었습니다 ✨✨✨ ---

            // Helper function to safely format text for innerHTML
            const formatHtml = (text) => {
                if (typeof text !== 'string') return '';
                // Replace newline characters with <br> tags
                return text.replace(/\n/g, '<br>');
            };

            // Update all character details
            document.getElementById('character-image').src = character.image;
            document.getElementById('character-detail-name').textContent = character.name;
            document.getElementById('character-detail-role').textContent = character.role;
            document.getElementById('character-quote').textContent = character.quote;
            
            // Basic Info (using textContent for single-line values)
            document.getElementById('character-age').textContent = character.age;
            document.getElementById('character-height').textContent = character.height;
            document.getElementById('character-born').textContent = character.born;
            document.getElementById('character-element').textContent = character.element;

            // Descriptions (using innerHTML for multi-line/HTML content)
            document.getElementById('character-appearance').innerHTML = formatHtml(character.appearance);
            document.getElementById('character-abilities').innerHTML = formatHtml(character.abilities);
            document.getElementById('character-tool').innerHTML = formatHtml(character.tool);
            document.getElementById('character-story').innerHTML = formatHtml(character.story);

            // Update personality traits
            const traitsContainer = document.getElementById('character-traits');
            traitsContainer.innerHTML = '';
            character.traits.forEach(trait => {
                const tag = document.createElement('span');
                tag.className = 'tag';
                tag.textContent = trait;
                traitsContainer.appendChild(tag);
            });

            // --- ✨✨✨ 여기까지 수정되었습니다 ✨✨✨ ---

            // Show character profile page
            document.querySelectorAll('.main-container, .page-content').forEach(el => {
                el.classList.remove('active');
            });
            document.getElementById('character-profile').classList.add('active');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>

</body>
</html>
