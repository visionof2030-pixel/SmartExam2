<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="theme-color" content="#020824">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="format-detection" content="telephone=no">
    <title>نُبـل - أداة التعلم الذكية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800;900&display=swap" rel="stylesheet">
    
    <style>
        /* CSS Reset أولاً */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }
        
        html, body {
            width: 100%;
            height: 100%;
            overflow-x: hidden;
            -webkit-text-size-adjust: 100%;
        }
        
        :root {
            --primary-dark: #0c2d41;
            --primary: #1a4865;
            --primary-light: #2a6a8f;
            --accent: #2a9d8f;
            --accent-light: #4ecdc4;
            --accent-dark: #21867a;
            --success: #27ae60;
            --success-light: #2ecc71;
            --error: #e74c3c;
            --warning: #f39c12;
            --info: #3498db;
            --light: #f8f9fa;
            --dark: #212529;
            --gray: #6c757d;
            --gray-light: #e9ecef;
            --shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
            --shadow-light: 0 4px 15px rgba(0, 0, 0, 0.08);
            --border-radius: 16px;
            --border-radius-sm: 10px;
            --transition: all 0.3s ease;
            --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-success: linear-gradient(135deg, #27ae60 0%, #2ecc71 100%);
            --gradient-accent: linear-gradient(135deg, #2a9d8f 0%, #4ecdc4 100%);
        }
        
        body {
    font-family: 'Tajawal', -apple-system, BlinkMacSystemFont, sans-serif;
    background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
    color: var(--light);
    min-height: 100vh;
    min-height: -webkit-fill-available;
    line-height: 1.5;
    margin: 0;
    
        
        /* تصحيح لـ iOS Safari */
        @supports (-webkit-touch-callout: none) {
            body {
                min-height: -webkit-fill-available;
            }
        }
        
        /* البار العلوي - محسن ليغطي الزوايا */
        ..top-bar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: calc(70px + env(safe-area-inset-top));
    padding-top: env(safe-area-inset-top);
    padding-left: 20px;
    padding-right: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, rgba(8, 32, 48, 0.98) 0%, rgba(12, 45, 65, 0.98) 100%);
    z-index: 10000;
    border-radius: 0;
}
        
        .top-bar i {
            margin-left: 8px;
            color: #4ecdc4;
        }
        
        /* الهيدر الرئيسي */
        .header {
    padding: calc(25px + 70px + env(safe-area-inset-top)) 16px 20px;
    text-align: center;
    background: linear-gradient(135deg, rgba(12, 45, 65, 0.9) 0%, rgba(26, 72, 101, 0.9) 100%);
    position: relative;
    overflow: hidden;
    width: 100%;
    margin-top: 0;
    border-top-left-radius: 22px;
    border-top-right-radius: 22px;
}
        
        .logo-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .logo-icon {
            width: 70px;
            height: 70px;
            background: var(--gradient-accent);
            border-radius: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.2rem;
            color: white;
            box-shadow: 0 8px 25px rgba(42, 157, 143, 0.5);
            transform: rotate(-5deg);
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(-5deg); }
            50% { transform: translateY(-10px) rotate(-5deg); }
        }
        
        .logo-text {
            font-size: 3rem;
            font-weight: 900;
            color: #4ecdc4;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            position: relative;
            margin-top: 5px;
        }
        
        .logo-text::after {
            content: "ُ";
            position: absolute;
            font-size: 2rem;
            color: var(--accent-light);
            right: -6px;
            top: -15px;
            text-shadow: 0 0 10px rgba(78, 205, 196, 0.7);
        }
        
        .header p {
            font-size: 1.2rem;
            color: var(--gray-light);
            max-width: 100%;
            margin: 10px auto 0;
            opacity: 0.95;
            font-weight: 300;
            line-height: 1.6;
            padding: 0 15px;
        }
        
        /* الحاوية الرئيسية */
        .container {
            width: 100%;
            max-width: 100%;
            padding: 20px 16px;
            margin: 0 auto;
            box-sizing: border-box;
        }
        
        /* بطاقة التحكم */
        .control-card {
            background: rgba(255, 255, 255, 0.07);
            border-radius: var(--border-radius);
            padding: 25px 20px;
            margin-bottom: 25px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: var(--shadow-light);
            position: relative;
            width: 100%;
            box-sizing: border-box;
            backdrop-filter: blur(10px);
        }
        
        .control-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-accent);
            border-radius: var(--border-radius) var(--border-radius) 0 0;
        }
        
        /* أزرار التبويب */
        .mode-tabs {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 25px;
            width: 100%;
        }
        
        .mode-tab {
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: var(--border-radius-sm);
            padding: 18px 15px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            width: 100%;
            min-height: 70px;
        }
        
        .mode-tab.active {
            background: rgba(42, 157, 143, 0.2);
            border-color: var(--accent);
            box-shadow: 0 5px 20px rgba(42, 157, 143, 0.25);
        }
        
        .mode-tab i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--accent-light);
        }
        
        .mode-tab span {
            font-weight: 800;
            font-size: 1.1rem;
            color: var(--light);
        }
        
        /* إعدادات التحكم */
        .control-group {
            margin-bottom: 25px;
            width: 100%;
        }
        
        .control-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 700;
            color: var(--accent-light);
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        select, textarea, input[type="file"] {
            width: 100%;
            padding: 16px 18px;
            background: rgba(255, 255, 255, 0.07);
            border: 2px solid rgba(255, 255, 255, 0.15);
            border-radius: var(--border-radius-sm);
            color: var(--light);
            font-family: 'Tajawal', sans-serif;
            font-size: 16px;
            transition: var(--transition);
            box-sizing: border-box;
            -webkit-appearance: none;
            appearance: none;
            backdrop-filter: blur(5px);
        }
        
        select:focus, textarea:focus, input[type="file"]:focus {
            border-color: var(--accent);
            box-shadow: 0 0 0 3px rgba(42, 157, 143, 0.2);
            outline: none;
        }
        
        textarea {
            min-height: 130px;
            resize: vertical;
            line-height: 1.6;
        }
        
        /* زر التنفيذ */
        .execute-btn {
            width: 100%;
            padding: 20px;
            background: var(--gradient-accent);
            color: white;
            border: none;
            border-radius: var(--border-radius-sm);
            font-family: 'Tajawal', sans-serif;
            font-size: 1.2rem;
            font-weight: 800;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            box-shadow: 0 8px 25px rgba(42, 157, 143, 0.35);
            position: relative;
            margin-top: 10px;
            min-height: 60px;
            letter-spacing: 0.5px;
        }
        
        .execute-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(42, 157, 143, 0.5);
        }
        
        .execute-btn:active {
            transform: translateY(-2px);
        }
        
        /* شاشة الانتظار - تصميم ليلي مع صقر */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #020824;
            display: none;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 9999;
            opacity: 0;
            transition: opacity 0.5s ease;
            overflow: hidden;
            font-family: 'Tajawal', sans-serif;
        }
        
        .loading-overlay.active {
            display: flex;
            opacity: 1;
            animation: fadeIn 0.5s ease;
        }
        
        #sky {
            position: absolute;
            inset: 0;
            background: radial-gradient(circle at bottom, #0b1d46, #020824 70%);
            z-index: 1;
        }
        
        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            animation: twinkle 3s infinite ease-in-out;
        }
        
        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }
        
        #moon {
            position: absolute;
            width: 140px;
            height: 140px;
            border-radius: 50%;
            top: 40px;
            right: 60px;
            background: radial-gradient(circle, #fff, #d9d9d9);
            box-shadow:
                0 0 40px rgba(255, 255, 255, 0.6),
                0 0 80px rgba(255, 255, 255, 0.3);
            z-index: 2;
        }
        
        #falcon {
            position: absolute;
            width: 180px;
            top: 60px;
            left: -220px;
            animation: fly 14s linear infinite;
            transform-origin: center;
            filter: drop-shadow(0 15px 20px rgba(0, 0, 0, 0.6));
            z-index: 3;
        }
        
        #falcon img {
            width: 100%;
            display: block;
            animation: flap 2s ease-in-out infinite;
            transform-origin: center;
        }
        
        @keyframes flap {
            0% { transform: scaleY(1); }
            25% { transform: scaleY(0.85); }
            50% { transform: scaleY(0.7); }
            75% { transform: scaleY(0.85); }
            100% { transform: scaleY(1); }
        }
        
        @keyframes fly {
            0% { transform: translateX(0); }
            100% { transform: translateX(160vw); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* محتوى شاشة الانتظار */
        .loading-content {
            position: relative;
            z-index: 4;
            text-align: center;
            max-width: 800px;
            padding: 0 20px;
            width: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }
        
        .loading-developer {
            font-size: 0.9rem;
            color: white;
            font-weight: 600;
            background: rgba(255, 255, 255, 0.1);
            padding: 10px 20px;
            border-radius: 25px;
            display: inline-block;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            margin-bottom: 40px;
            z-index: 5;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .loading-developer i {
            margin-left: 8px;
            color: #4ecdc4;
        }
        
        .loading-message {
            margin-bottom: 60px;
            z-index: 5;
            width: 100%;
        }
        
        .loading-title {
            font-size: 2.2rem;
            font-weight: 900;
            margin-bottom: 15px;
            color: white;
            line-height: 1.3;
            text-shadow: 0 0 20px rgba(78, 205, 196, 0.7);
            animation: titleGlow 4s ease-in-out infinite;
            position: relative;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 20px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            width: 80%;
            margin: 40px auto 20px;
            font-size: 80%;
        }
        
        @keyframes titleGlow {
            0%, 100% { text-shadow: 0 0 20px rgba(78, 205, 196, 0.7); }
            50% { text-shadow: 0 0 30px rgba(78, 205, 196, 1); }
        }
        
        .loading-subtitle {
            font-size: 1.5rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 400;
            margin-bottom: 30px;
            opacity: 0.9;
            line-height: 1.6;
            padding: 0 20px;
        }
        
        .loading-progress-container {
            width: 100%;
            max-width: 500px;
            margin: 0 auto 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            z-index: 5;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .loading-progress-text {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            color: white;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .loading-progress {
            width: 100%;
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }
        
        .loading-progress-bar {
            position: absolute;
            top: 0;
            right: 0;
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #2a9d8f, #4ecdc4);
            border-radius: 10px;
            transition: width 0.5s ease;
            box-shadow: 0 0 20px rgba(78, 205, 196, 0.6);
        }
        
        .loading-progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent 0%, 
                rgba(255, 255, 255, 0.4) 50%, 
                transparent 100%);
            animation: shine 2s infinite;
        }
        
        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .loading-stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 50px;
            flex-wrap: wrap;
            z-index: 5;
        }
        
        .stat-item {
            text-align: center;
            padding: 20px;
            min-width: 110px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }
        
        .stat-item:hover {
            transform: translateY(-5px);
        }
        
        .stat-number {
            font-size: 2.2rem;
            font-weight: 800;
            color: white;
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        
        .stat-label {
            font-size: 0.95rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 600;
        }
        
        .loading-footer {
            margin-top: 30px;
            z-index: 5;
        }
        
        .loading-footer-text {
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 400;
            line-height: 1.5;
            max-width: 500px;
            margin: 0 auto 20px;
        }
        
        .loading-timer {
            font-size: 1.1rem;
            color: #4ecdc4;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: rgba(78, 205, 196, 0.1);
            padding: 12px 25px;
            border-radius: 30px;
            border: 1px solid rgba(78, 205, 196, 0.3);
            backdrop-filter: blur(5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .loading-timer i {
            font-size: 1.3rem;
        }
        
        /* صفحة الأسئلة */
        .quiz-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
            z-index: 10000;
            overflow-y: auto;
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        
        .quiz-page.active {
            display: block;
            opacity: 1;
        }
        
        .quiz-header {
            background: rgba(12, 45, 65, 0.95);
            padding: 20px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.25);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 2px solid rgba(42, 157, 143, 0.3);
            backdrop-filter: blur(10px);
        }
        
        .quiz-title {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--accent-light);
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .back-btn {
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid var(--accent);
            border-radius: var(--border-radius-sm);
            color: var(--accent-light);
            padding: 14px 28px;
            font-family: 'Tajawal', sans-serif;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            backdrop-filter: blur(5px);
        }
        
        .back-btn:hover {
            background: rgba(42, 157, 143, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(42, 157, 143, 0.3);
        }
        
        .quiz-container {
            padding: 25px 16px;
            max-width: 1000px;
            margin: 0 auto;
        }
        
        /* صفحة الفلاش كاردز */
        .flashcards-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
            z-index: 10000;
            overflow-y: auto;
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        
        .flashcards-page.active {
            display: block;
            opacity: 1;
        }
        
        .flashcards-header {
            background: rgba(12, 45, 65, 0.95);
            padding: 20px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.25);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 2px solid rgba(42, 157, 143, 0.3);
            backdrop-filter: blur(10px);
        }
        
        .flashcards-title {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--accent-light);
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .flashcards-container {
            padding: 30px 16px;
            max-width: 800px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        /* صفحة التلخيص */
        .summary-page {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
            z-index: 10000;
            overflow-y: auto;
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        
        .summary-page.active {
            display: block;
            opacity: 1;
        }
        
        .summary-header {
            background: rgba(12, 45, 65, 0.95);
            padding: 20px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.25);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 2px solid rgba(42, 157, 143, 0.3);
            backdrop-filter: blur(10px);
        }
        
        .summary-title-header {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--accent-light);
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .summary-container {
            padding: 30px 16px;
            max-width: 900px;
            margin: 0 auto;
        }
        
        /* تصميم الأسئلة المحسن */
        .question {
            background: rgba(255, 255, 255, 0.07);
            border-radius: var(--border-radius);
            padding: 30px 25px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: var(--shadow-light);
            position: relative;
            width: 100%;
            box-sizing: border-box;
            animation: fadeIn 0.5s ease;
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }
        
        .question:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
        }
        
        .question-header {
            display: flex;
            flex-direction: column-reverse;
            gap: 20px;
            margin-bottom: 25px;
        }
        
        .question-text {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--light);
            line-height: 1.6;
            width: 100%;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }
        
        .question-number {
            background: var(--gradient-accent);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 1.4rem;
            box-shadow: 0 8px 20px rgba(42, 157, 143, 0.5);
            align-self: flex-start;
        }
        
        /* خيارات الأسئلة المحسنة */
        .options {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 25px;
            width: 100%;
        }
        
        .option {
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid rgba(255, 255, 255, 0.12);
            border-radius: var(--border-radius-sm);
            padding: 20px;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            align-items: center;
            gap: 15px;
            position: relative;
            width: 100%;
            min-height: 70px;
            user-select: none;
            overflow: hidden;
        }
        
        .option::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }
        
        .option:hover::before {
            transform: translateX(100%);
        }
        
        .option:hover:not(.disabled) {
            background: rgba(255, 255, 255, 0.09);
            transform: translateY(-5px) scale(1.02);
            border-color: rgba(255, 255, 255, 0.2);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }
        
        .option.selected {
            background: rgba(42, 157, 143, 0.2);
            border-color: var(--accent);
            animation: pulse 0.3s ease;
            box-shadow: 0 10px 20px rgba(42, 157, 143, 0.3);
        }
        
        .option.correct {
            background: rgba(39, 174, 96, 0.2);
            border-color: var(--success);
            box-shadow: 0 10px 20px rgba(39, 174, 96, 0.3);
        }
        
        .option.incorrect {
            background: rgba(231, 76, 60, 0.2);
            border-color: var(--error);
            box-shadow: 0 10px 20px rgba(231, 76, 60, 0.3);
        }
        
        .option.disabled {
            pointer-events: none;
            opacity: 0.7;
        }
        
        .option-letter {
            background: rgba(255, 255, 255, 0.1);
            color: var(--light);
            width: 45px;
            height: 45px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            flex-shrink: 0;
            font-size: 1.2rem;
            transition: var(--transition);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }
        
        .option.selected .option-letter,
        .option.correct .option-letter {
            background: var(--success);
            color: white;
            box-shadow: 0 6px 15px rgba(39, 174, 96, 0.4);
        }
        
        .option.incorrect .option-letter {
            background: var(--error);
            color: white;
            box-shadow: 0 6px 15px rgba(231, 76, 60, 0.4);
        }
        
        .option-text {
            font-size: 1.2rem;
            font-weight: 600;
            flex: 1;
            line-height: 1.5;
        }
        
        /* تصميم البطاقات التعليمية في صفحتها الخاصة */
        .flashcard-page {
            background: rgba(255, 255, 255, 0.07);
            border-radius: var(--border-radius);
            padding: 40px 30px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: var(--shadow-light);
            min-height: 350px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
            width: 100%;
            backdrop-filter: blur(10px);
            position: relative;
        }
        
        .flashcard-page:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.25);
        }
        
        .flashcard-front-page, .flashcard-back-page {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--light);
            line-height: 1.6;
            max-width: 100%;
            padding: 0 20px;
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .flashcard-back-page {
            color: var(--accent-light);
        }
        
        .flashcard-counter-page {
            margin-top: 25px;
            font-size: 1.1rem;
            color: var(--gray-light);
            font-weight: 600;
            background: rgba(255, 255, 255, 0.05);
            padding: 10px 25px;
            border-radius: 25px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .flashcard-nav-page {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
            width: 100%;
            flex-wrap: wrap;
        }
        
        .flashcard-btn-page {
            background: rgba(255, 255, 255, 0.07);
            border: 2px solid rgba(255, 255, 255, 0.12);
            border-radius: var(--border-radius-sm);
            color: var(--light);
            padding: 16px 25px;
            font-family: 'Tajawal', sans-serif;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            flex: 1;
            min-width: 130px;
            min-height: 55px;
            backdrop-filter: blur(5px);
        }
        
        .flashcard-btn-page:hover {
            background: rgba(42, 157, 143, 0.2);
            border-color: var(--accent);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(42, 157, 143, 0.3);
        }
        
        /* تصميم التلخيص في صفحته الخاصة */
        .summary-page-content {
            background: rgba(255, 255, 255, 0.07);
            border-radius: var(--border-radius);
            padding: 30px 25px;
            margin-bottom: 25px;
            border: 1px solid rgba(255, 255, 255, 0.12);
            box-shadow: var(--shadow-light);
            position: relative;
            width: 100%;
            backdrop-filter: blur(10px);
        }
        
        .summary-title-page {
            font-size: 2rem;
            font-weight: 900;
            margin-bottom: 30px;
            color: var(--accent-light);
            text-align: center;
            border-bottom: 2px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .summary-point-page {
            margin-bottom: 20px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.04);
            border-radius: var(--border-radius-sm);
            border-right: 4px solid var(--accent);
            transition: var(--transition);
            position: relative;
            width: 100%;
        }
        
        .summary-point-page:hover {
            background: rgba(255, 255, 255, 0.07);
            transform: translateX(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .summary-point-text-page {
            font-size: 1.2rem;
            line-height: 1.6;
            font-weight: 500;
        }
        
        /* تخصيص خيارات تحميل الملف */
        .file-upload-area {
            width: 100%;
            padding: 20px;
            background: rgba(255, 255, 255, 0.06);
            border: 2px solid rgba(255, 255, 255, 0.12);
            border-radius: var(--border-radius-sm);
            color: var(--light);
            transition: var(--transition);
            text-align: center;
            cursor: pointer;
            margin-bottom: 20px;
            box-sizing: border-box;
            backdrop-filter: blur(5px);
        }
        
        .file-upload-label {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            cursor: pointer;
        }
        
        .file-upload-label i {
            font-size: 3rem;
            color: var(--accent-light);
        }
        
        .upload-options {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-top: 15px;
            width: 100%;
        }
        
        .upload-option-btn {
            background: rgba(42, 157, 143, 0.2);
            border: 1px solid rgba(42, 157, 143, 0.4);
            border-radius: var(--border-radius-sm);
            padding: 16px;
            color: var(--accent-light);
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-weight: 600;
            width: 100%;
            min-height: 55px;
            backdrop-filter: blur(5px);
        }
        
        .upload-option-btn:hover {
            background: rgba(42, 157, 143, 0.3);
            transform: translateY(-3px);
        }
        
        .image-preview {
            margin-top: 20px;
            max-width: 100%;
            border-radius: var(--border-radius-sm);
            display: none;
        }
        
        .image-preview img {
            max-width: 100%;
            max-height: 250px;
            border-radius: var(--border-radius-sm);
            object-fit: contain;
        }
        
        .camera-container {
            width: 100%;
            height: 250px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: var(--border-radius-sm);
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            margin-top: 20px;
            display: none;
        }
        
        #camera-feed {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .camera-controls {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 20px;
            z-index: 10;
        }
        
        .camera-btn {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(231, 111, 81, 0.9);
            border: 3px solid white;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.4rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .camera-btn:hover {
            transform: scale(1.1);
        }
        
        /* الأصوات */
        .sound-controls {
            position: fixed;
            bottom: 25px;
            left: 25px;
            z-index: 100;
            display: flex;
            gap: 15px;
        }
        
        .sound-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(12, 45, 65, 0.9);
            border: 2px solid var(--accent);
            color: var(--accent-light);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.3rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
        }
        
        .sound-btn:hover {
            background: rgba(42, 157, 143, 0.9);
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(42, 157, 143, 0.4);
        }
        
        .sound-btn.muted {
            opacity: 0.5;
            border-color: var(--gray);
            color: var(--gray);
        }
        
        /* الرسائل */
        .message {
            padding: 20px;
            border-radius: var(--border-radius-sm);
            margin-bottom: 20px;
            text-align: center;
            font-weight: 700;
            font-size: 1.1rem;
            border-right: 4px solid;
            width: 100%;
            box-sizing: border-box;
            animation: fadeIn 0.5s ease;
            backdrop-filter: blur(5px);
        }
        
        .message.success {
            background: rgba(42, 157, 143, 0.15);
            color: var(--accent-light);
            border-right-color: var(--success);
        }
        
        .message.error {
            background: rgba(231, 111, 81, 0.15);
            color: #f4a261;
            border-right-color: var(--error);
        }
        
        .message.info {
            background: rgba(78, 205, 196, 0.15);
            color: var(--accent-light);
            border-right-color: var(--info);
        }
        
        /* استعلامات الوسائط للشاشات المتوسطة والكبيرة */
        @media (min-width: 768px) {
            .container {
                max-width: 90%;
                padding: 35px 25px;
            }
            
            .mode-tabs {
                flex-direction: row;
                flex-wrap: wrap;
            }
            
            .mode-tab {
                flex: 1;
                min-width: 160px;
            }
            
            .question-header {
                flex-direction: row;
                justify-content: space-between;
                align-items: flex-start;
            }
            
            .options {
                display: grid;
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
            
            .upload-options {
                flex-direction: row;
                flex-wrap: wrap;
            }
            
            .upload-option-btn {
                flex: 1;
                min-width: 150px;
            }
            
            .flashcard-nav-page {
                flex-wrap: nowrap;
            }
            
            .loading-title {
                font-size: 2.5rem;
            }
            
            .loading-subtitle {
                font-size: 1.7rem;
            }
            
            .quiz-container {
                padding: 35px 25px;
            }
            
            .flashcards-container, .summary-container {
                padding: 40px 25px;
            }
            
            #falcon {
                width: 220px;
            }
        }
        
        @media (min-width: 1024px) {
            .container {
                max-width: 1000px;
                padding: 50px 30px;
            }
            
            .options {
                grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            }
            
            .flashcard-page {
                min-height: 400px;
                padding: 60px 50px;
            }
            
            .flashcard-front-page, .flashcard-back-page {
                font-size: 2.2rem;
            }
            
            .loading-title {
                font-size: 3rem;
            }
            
            .quiz-container {
                padding: 50px;
            }
            
            .flashcards-container, .summary-container {
                padding: 50px;
            }
            
            #falcon {
                width: 250px;
            }
        }
        
        /* تصحيحات خاصة لأجهزة iOS */
        @supports (-webkit-touch-callout: none) {
            select, textarea, input[type="file"], button, .execute-btn {
                font-size: 16px !important;
            }
            
            body {
                -webkit-user-select: none;
                user-select: none;
            }
        }
        
        /* إخفاء العناصر */
        .hidden {
            display: none !important;
        }
        
        .quiz-hidden {
            display: none;
        }
    </style>
</head>

<body>
    <!-- شاشة الانتظار -->
    <div class="loading-overlay" id="loadingOverlay">
        <div id="sky">
            <div id="moon"></div>
        </div>
        
        <div id="falcon">
            <img src="https://i.ibb.co/yFgvtvrw/IMG-2428.png">
        </div>
        
        <div class="loading-content">
            <div class="loading-developer">
                <i class="fas fa-code"></i> تنفيذ وتطوير معلم اللغة الإنجليزية: فهد الخالدي
            </div>
            
            <div class="loading-message">
                <h1 class="loading-title">العلم نُبل والجهل سقوط</h1>
                <p class="loading-subtitle">على مهلٍ، يشق نور العلم ظلام الجهل كحلمٍ جميل</p>
            </div>
            
            <div class="loading-progress-container">
                <div class="loading-progress-text">
                    <span id="progressStatus">يجمع المعلومات...</span>
                    <span id="progressPercent">0%</span>
                </div>
                <div class="loading-progress">
                    <div class="loading-progress-bar" id="progressBar"></div>
                </div>
            </div>
            
            <div class="loading-stats">
                <div class="stat-item">
                    <div class="stat-number" id="statQuestions">0</div>
                    <div class="stat-label">أسئلة</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="statSeconds">0</div>
                    <div class="stat-label">ثانية</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="statProgress">0%</div>
                    <div class="stat-label">اكتمال</div>
                </div>
            </div>
            
            <div class="loading-footer">
                <p class="loading-footer-text">يتم حالياً تحليل المحتوى وإنشاء الأسئلة التعليمية الذكية تحت ضوء القمر</p>
                <div class="loading-timer">
                    <i class="fas fa-clock"></i>
                    <span id="loadingTimer">جارٍ المعالجة...</span>
                </div>
            </div>
        </div>
    </div>
    
    <!-- صفحة الأسئلة -->
    <div class="quiz-page" id="quizPage">
        <div class="quiz-header">
            <div class="quiz-title">
                <i class="fas fa-brain"></i>
                <span>اختبار المعرفة</span>
            </div>
            <button class="back-btn" onclick="backToMain()">
                <i class="fas fa-arrow-right"></i>
                العودة للرئيسية
            </button>
        </div>
        
        <div class="quiz-container" id="quizContainer"></div>
    </div>
    
    <!-- صفحة الفلاش كاردز -->
    <div class="flashcards-page" id="flashcardsPage">
        <div class="flashcards-header">
            <div class="flashcards-title">
                <i class="fas fa-layer-group"></i>
                <span>البطاقات التعليمية</span>
            </div>
            <button class="back-btn" onclick="backToMainFromFlashcards()">
                <i class="fas fa-arrow-right"></i>
                العودة للرئيسية
            </button>
        </div>
        
        <div class="flashcards-container" id="flashcardsContainer"></div>
    </div>
    
    <!-- صفحة التلخيص -->
    <div class="summary-page" id="summaryPage">
        <div class="summary-header">
            <div class="summary-title-header">
                <i class="fas fa-scroll"></i>
                <span>التلخيص</span>
            </div>
            <button class="back-btn" onclick="backToMainFromSummary()">
                <i class="fas fa-arrow-right"></i>
                العودة للرئيسية
            </button>
        </div>
        
        <div class="summary-container" id="summaryContainer"></div>
    </div>
    
    <!-- الصفحة الرئيسية -->
    <div id="mainPage">
        <!-- البار العلوي المحسن -->
        <div class="top-bar">
            <i class="fas fa-code"></i> تطوير: فهد الخالدي | نُبـل - أداة التعلم الذكية
        </div>
        
        <!-- الهيدر -->
        <div class="header">
            <div class="logo-container">
                <div class="logo-icon">
                    <i class="fas fa-book-open"></i>
                </div>
                <h1 class="logo-text">نُبـل</h1>
            </div>
            <p>تعلمٌ أذكى… تحصيلٌ أرقى</p>
        </div>
        
        <!-- الحاوية الرئيسية -->
        <div class="container">
            <!-- بطاقة التحكم -->
            <div class="control-card">
                <!-- أزرار التبويب -->
                <div class="mode-tabs">
                    <div class="mode-tab active" data-mode="manual">
                        <i class="fas fa-edit"></i>
                        <span>اختبار يدوي</span>
                    </div>
                    <div class="mode-tab" data-mode="file">
                        <i class="fas fa-file-alt"></i>
                        <span>اختبار من ملف</span>
                    </div>
                    <div class="mode-tab" data-mode="flashcards">
                        <i class="fas fa-layer-group"></i>
                        <span>فلاش كاردز</span>
                    </div>
                    <div class="mode-tab" data-mode="summary">
                        <i class="fas fa-scroll"></i>
                        <span>تلخيص</span>
                    </div>
                </div>
                
                <!-- إعدادات التحكم -->
                <div class="control-group">
                    <label for="language"><i class="fas fa-language"></i> لغة المحتوى</label>
                    <select id="language">
                        <option value="ar">عربي</option>
                        <option value="en">English</option>
                    </select>
                </div>
                
                <div class="control-group">
                    <label for="num"><i class="fas fa-list-ol"></i> عدد الأسئلة/البطاقات</label>
                    <select id="num">
                        <option value="5">5</option>
                        <option value="10" selected>10</option>
                        <option value="20">20</option>
                        <option value="30">30</option>
                        <option value="40">40</option>
                        <option value="50">50</option>
                        <option value="60">60</option>
                    </select>
                </div>
                
                <!-- منطقة الإدخال اليدوي -->
                <div class="control-group" id="topic-group">
                    <label for="topic"><i class="fas fa-book-open"></i> اكتب الموضوع هنا</label>
                    <textarea id="topic" rows="4" placeholder="اكتب الموضوع أو النص الذي تريد إنشاء أسئلة أو تلخيص منه..."></textarea>
                </div>
                
                <!-- منطقة تحميل الملف -->
                <div class="control-group hidden" id="file-group">
                    <label for="file"><i class="fas fa-upload"></i> اختر مصدر المحتوى</label>
                    
                    <!-- خيارات تحميل الملف -->
                    <div class="file-upload-area">
                        <label class="file-upload-label">
                            <i class="fas fa-cloud-upload-alt"></i>
                            <span id="upload-instruction">انقر لاختيار ملف أو استخدم الخيارات أدناه</span>
                            
                            <div class="upload-options">
                                <div class="upload-option-btn active" data-upload-type="file">
                                    <i class="fas fa-file"></i> ملف نصي
                                </div>
                                <div class="upload-option-btn" data-upload-type="image">
                                    <i class="fas fa-image"></i> صورة
                                </div>
                                <div class="upload-option-btn" data-upload-type="camera">
                                    <i class="fas fa-camera"></i> الكاميرا
                                </div>
                            </div>
                            
                            <!-- حقل اختيار الملف المخفي -->
                            <input type="file" id="file-input" accept=".txt,.pdf,.doc,.docx,.jpg,.jpeg,.png,.gif">
                            
                            <!-- حقل اختيار الصورة -->
                            <input type="file" id="image-input" accept="image/*" class="hidden">
                            
                            <!-- معاينة الصورة -->
                            <div class="image-preview" id="image-preview">
                                <img id="preview-image" src="" alt="معاينة الصورة">
                            </div>
                            
                            <!-- حاوية الكاميرا -->
                            <div class="camera-container" id="camera-container">
                                <video id="camera-feed" autoplay playsinline></video>
                                <div class="camera-controls">
                                    <div class="camera-btn capture" id="capture-btn">
                                        <i class="fas fa-camera"></i>
                                    </div>
                                    <div class="camera-btn" id="cancel-camera-btn">
                                        <i class="fas fa-times"></i>
                                    </div>
                                </div>
                            </div>
                        </label>
                    </div>
                    
                    <div class="message" id="file-message" style="display: none;">
                        <i class="fas fa-file"></i> يمكنك رفع ملفات نصية أو PDF أو Word أو صور
                    </div>
                </div>
                
                <!-- زر التنفيذ -->
                <button class="execute-btn" onclick="start()">
                    <i class="fas fa-play-circle"></i> بدء التنفيذ
                </button>
            </div>
            
            <!-- منطقة الإخراج للنتائج الأخرى (غير الاختبار) -->
            <div id="out"></div>
        </div>
    </div>
    
    <!-- عناصر التحكم في الصوت -->
    <div class="sound-controls">
        <div class="sound-btn" id="soundToggle">
            <i class="fas fa-volume-up"></i>
        </div>
        <div class="sound-btn" id="musicToggle">
            <i class="fas fa-music"></i>
        </div>
    </div>
    
    <!-- الأصوات -->
    <audio id="correct-sound" preload="auto">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-correct-answer-tone-2870.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="wrong-sound" preload="auto">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-wrong-answer-fail-notification-946.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="click-sound" preload="auto">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-select-click-1109.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="success-sound" preload="auto">
        <source src="https://assets.mixkit.co/sfx/preview/mixkit-achievement-bell-600.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="background-music" preload="auto" loop>
        <source src="https://assets.mixkit.co/music/preview/mixkit-driving-ambition-32.mp3" type="audio/mpeg">
    </audio>
    
    <audio id="loading-music" preload="auto" loop>
        <source src="https://assets.mixkit.co/music/preview/mixkit-tech-house-vibes-130.mp3" type="audio/mpeg">
    </audio>

    <script>
        // كشف نوع الجهاز
        const isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
        const isIOS = /iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream;
        
        const API = "https://smarttest-0ycc.onrender.com";
        
        // العناصر الأساسية
        const modeTabs = document.querySelectorAll('.mode-tab');
        const topicGroup = document.getElementById('topic-group');
        const fileGroup = document.getElementById('file-group');
        const topic = document.getElementById('topic');
        const out = document.getElementById('out');
        const language = document.getElementById('language');
        const num = document.getElementById('num');
        const loadingOverlay = document.getElementById('loadingOverlay');
        const quizPage = document.getElementById('quizPage');
        const flashcardsPage = document.getElementById('flashcardsPage');
        const summaryPage = document.getElementById('summaryPage');
        const mainPage = document.getElementById('mainPage');
        const quizContainer = document.getElementById('quizContainer');
        const flashcardsContainer = document.getElementById('flashcardsContainer');
        const summaryContainer = document.getElementById('summaryContainer');
        
        // عناصر شاشة الانتظار
        const loadingTitle = document.querySelector('.loading-title');
        const loadingSubtitle = document.querySelector('.loading-subtitle');
        const progressStatus = document.getElementById('progressStatus');
        const progressPercent = document.getElementById('progressPercent');
        const progressBar = document.getElementById('progressBar');
        const statQuestions = document.getElementById('statQuestions');
        const statSeconds = document.getElementById('statSeconds');
        const statProgress = document.getElementById('statProgress');
        const loadingTimer = document.getElementById('loadingTimer');
        const sky = document.getElementById('sky');
        
        // عناصر تحميل الملفات الجديدة
        const fileInput = document.getElementById('file-input');
        const imageInput = document.getElementById('image-input');
        const uploadOptions = document.querySelectorAll('.upload-option-btn');
        const uploadInstruction = document.getElementById('upload-instruction');
        const imagePreview = document.getElementById('image-preview');
        const previewImage = document.getElementById('preview-image');
        const cameraContainer = document.getElementById('camera-container');
        const cameraFeed = document.getElementById('camera-feed');
        const captureBtn = document.getElementById('capture-btn');
        const cancelCameraBtn = document.getElementById('cancel-camera-btn');
        
        // عناصر الصوت
        const soundToggle = document.getElementById('soundToggle');
        const musicToggle = document.getElementById('musicToggle');
        const correctSound = document.getElementById('correct-sound');
        const wrongSound = document.getElementById('wrong-sound');
        const clickSound = document.getElementById('click-sound');
        const successSound = document.getElementById('success-sound');
        const backgroundMusic = document.getElementById('background-music');
        const loadingMusic = document.getElementById('loading-music');
        
        // متغيرات التحكم
        let currentUploadType = 'file';
        let currentFile = null;
        let stream = null;
        let loadingInterval = null;
        let timerSeconds = 0;
        let totalQuestions = 0;
        let currentQuizData = null;
        let currentMode = 'manual';
        let flashcardsData = null;
        let summaryData = null;
        
        // إعدادات الصوت
        let soundEnabled = true;
        let musicEnabled = false;
        backgroundMusic.volume = 0.3;
        loadingMusic.volume = 0.2;
        
        // إنشاء النجوم
        function createStars() {
            for(let i = 0; i < 160; i++) {
                let star = document.createElement("div");
                star.className = "star";
                star.style.top = Math.random() * window.innerHeight + "px";
                star.style.left = Math.random() * window.innerWidth + "px";
                star.style.animationDelay = (Math.random() * 3) + "s";
                loadingOverlay.appendChild(star);
            }
        }
        
        // تهيئة وضع التبويب
        modeTabs.forEach(tab => {
            tab.addEventListener('click', () => {
                playSound('click');
                // إزالة النشط من جميع الألسنة
                modeTabs.forEach(t => t.classList.remove('active'));
                // إضافة النشط للسان المحدد
                tab.classList.add('active');
                
                // تحديث الواجهة بناءً على الوضع المحدد
                currentMode = tab.dataset.mode;
                
                if (currentMode === 'manual') {
                    topicGroup.classList.remove('hidden');
                    fileGroup.classList.add('hidden');
                } else {
                    topicGroup.classList.add('hidden');
                    fileGroup.classList.remove('hidden');
                    
                    // عرض رسالة إرشادية للملف
                    const fileMessage = document.getElementById('file-message');
                    if (fileMessage) {
                        fileMessage.style.display = 'block';
                        fileMessage.classList.remove('success', 'error');
                        fileMessage.classList.add('success');
                        fileMessage.innerHTML = '<i class="fas fa-file"></i> يمكنك رفع ملفات نصية أو PDF أو Word أو صور';
                    }
                }
            });
        });
        
        // التحكم في الصوت
        soundToggle.addEventListener('click', function() {
            soundEnabled = !soundEnabled;
            this.classList.toggle('muted', !soundEnabled);
            this.innerHTML = soundEnabled ? '<i class="fas fa-volume-up"></i>' : '<i class="fas fa-volume-mute"></i>';
            playSound('click');
        });
        
        musicToggle.addEventListener('click', function() {
            musicEnabled = !musicEnabled;
            this.classList.toggle('muted', !musicEnabled);
            this.innerHTML = musicEnabled ? '<i class="fas fa-music"></i>' : '<i class="fas fa-music-slash"></i>';
            
            if (musicEnabled) {
                backgroundMusic.play().catch(e => console.log('Music play error:', e));
            } else {
                backgroundMusic.pause();
                loadingMusic.pause();
            }
            playSound('click');
        });
        
        // دالة تشغيل الصوت
        function playSound(type) {
            if (!soundEnabled) return;
            
            try {
                const sounds = {
                    'click': clickSound,
                    'correct': correctSound,
                    'wrong': wrongSound,
                    'success': successSound
                };
                
                if (sounds[type]) {
                    sounds[type].currentTime = 0;
                    sounds[type].play().catch(e => console.log('Sound play error:', e));
                }
            } catch (e) {
                console.log('Sound error:', e);
            }
        }
        
        // تغيير لغة المحتوى
        language.addEventListener('change', function() {
            playSound('click');
            const isEnglish = this.value === 'en';
            document.body.classList.toggle('english-mode', isEnglish);
            
            // تحديث النصوص حسب اللغة
            updateLanguage(isEnglish);
        });
        
        function updateLanguage(isEnglish) {
            if (isEnglish) {
                document.querySelector('.top-bar').innerHTML = '<i class="fas fa-code"></i> Development: Fahad Al-Khalidi | Nubl - Smart Learning Tool';
                document.querySelector('.header p').textContent = 'Smarter Learning... Better Achievement';
                document.querySelector('.execute-btn').innerHTML = '<i class="fas fa-play-circle"></i> Start Processing';
                document.querySelectorAll('.mode-tab span')[0].textContent = 'Manual Test';
                document.querySelectorAll('.mode-tab span')[1].textContent = 'Test from File';
                document.querySelectorAll('.mode-tab span')[2].textContent = 'Flash Cards';
                document.querySelectorAll('.mode-tab span')[3].textContent = 'Summary';
                document.querySelector('label[for="language"]').innerHTML = '<i class="fas fa-language"></i> Content Language';
                document.querySelector('label[for="num"]').innerHTML = '<i class="fas fa-list-ol"></i> Number of Questions/Cards';
                document.querySelector('label[for="topic"]').innerHTML = '<i class="fas fa-book-open"></i> Write the topic here';
                document.querySelector('#topic').placeholder = 'Write the topic or text you want to create questions or summarize from...';
                document.querySelector('label[for="file"]').innerHTML = '<i class="fas fa-upload"></i> Choose content source';
                uploadInstruction.textContent = 'Click to choose a file or use the options below';
                document.querySelectorAll('.upload-option-btn')[0].innerHTML = '<i class="fas fa-file"></i> Text File';
                document.querySelectorAll('.upload-option-btn')[1].innerHTML = '<i class="fas fa-image"></i> Image';
                document.querySelectorAll('.upload-option-btn')[2].innerHTML = '<i class="fas fa-camera"></i> Camera';
                
                // تحديث رسالة الملف
                const fileMessage = document.getElementById('file-message');
                if (fileMessage) {
                    fileMessage.innerHTML = '<i class="fas fa-file"></i> You can upload text files, PDF, Word, or images';
                }
                
                // تحديث شاشة الانتظار
                loadingTitle.textContent = 'Knowledge is nobility and ignorance is downfall';
                loadingSubtitle.textContent = 'Slowly, the light of knowledge pierces the darkness of ignorance like a beautiful dream';
                progressStatus.textContent = 'Gathering information...';
                
                // تحديث شعار المطور
                document.querySelector('.loading-developer').innerHTML = '<i class="fas fa-code"></i> Implementation & Development: English Teacher Fahad Al-Khalidi';
                document.querySelector('.loading-footer-text').textContent = 'Analyzing content and creating intelligent educational questions under moonlight';
            } else {
                document.querySelector('.top-bar').innerHTML = '<i class="fas fa-code"></i> تطوير: فهد الخالدي | نُبـل - أداة التعلم الذكية';
                document.querySelector('.header p').textContent = 'تعلمٌ أذكى… تحصيلٌ أرقى';
                document.querySelector('.execute-btn').innerHTML = '<i class="fas fa-play-circle"></i> بدء التنفيذ';
                document.querySelectorAll('.mode-tab span')[0].textContent = 'اختبار يدوي';
                document.querySelectorAll('.mode-tab span')[1].textContent = 'اختبار من ملف';
                document.querySelectorAll('.mode-tab span')[2].textContent = 'فلاش كاردز';
                document.querySelectorAll('.mode-tab span')[3].textContent = 'تلخيص';
                document.querySelector('label[for="language"]').innerHTML = '<i class="fas fa-language"></i> لغة المحتوى';
                document.querySelector('label[for="num"]').innerHTML = '<i class="fas fa-list-ol"></i> عدد الأسئلة/البطاقات';
                document.querySelector('label[for="topic"]').innerHTML = '<i class="fas fa-book-open"></i> اكتب الموضوع هنا';
                document.querySelector('#topic').placeholder = 'اكتب الموضوع أو النص الذي تريد إنشاء أسئلة أو تلخيص منه...';
                document.querySelector('label[for="file"]').innerHTML = '<i class="fas fa-upload"></i> اختر مصدر المحتوى';
                uploadInstruction.textContent = 'انقر لاختيار ملف أو استخدم الخيارات أدناه';
                document.querySelectorAll('.upload-option-btn')[0].innerHTML = '<i class="fas fa-file"></i> ملف نصي';
                document.querySelectorAll('.upload-option-btn')[1].innerHTML = '<i class="fas fa-image"></i> صورة';
                document.querySelectorAll('.upload-option-btn')[2].innerHTML = '<i class="fas fa-camera"></i> الكاميرا';
                
                // تحديث رسالة الملف
                const fileMessage = document.getElementById('file-message');
                if (fileMessage) {
                    fileMessage.innerHTML = '<i class="fas fa-file"></i> يمكنك رفع ملفات نصية أو PDF أو Word أو صور';
                }
                
                // تحديث شاشة الانتظار
                loadingTitle.textContent = 'العلم نُبل والجهل سقوط';
                loadingSubtitle.textContent = 'على مهلٍ، يشق نور العلم ظلام الجهل كحلمٍ جميل';
                progressStatus.textContent = 'يجمع المعلومات...';
                
                // تحديث شعار المطور
                document.querySelector('.loading-developer').innerHTML = '<i class="fas fa-code"></i> تنفيذ وتطوير معلم اللغة الإنجليزية: فهد الخالدي';
                document.querySelector('.loading-footer-text').textContent = 'يتم حالياً تحليل المحتوى وإنشاء الأسئلة التعليمية الذكية تحت ضوء القمر';
            }
        }
        
        // إدارة خيارات التحميل
        uploadOptions.forEach(option => {
            option.addEventListener('click', function() {
                playSound('click');
                // إزالة النشط من جميع الخيارات
                uploadOptions.forEach(opt => opt.classList.remove('active'));
                // إضافة النشط للخيار المحدد
                this.classList.add('active');
                
                // تحديث نوع التحميل الحالي
                currentUploadType = this.dataset.uploadType;
                
                // تحديث التعليمات
                const isEnglish = language.value === 'en';
                
                if (currentUploadType === 'file') {
                    uploadInstruction.textContent = isEnglish ? 
                        'Click to choose a text file (TXT, PDF, DOC, DOCX)' : 
                        'انقر لاختيار ملف نصي (TXT, PDF, DOC, DOCX)';
                    imagePreview.style.display = 'none';
                    stopCamera();
                } else if (currentUploadType === 'image') {
                    uploadInstruction.textContent = isEnglish ? 
                        'Click to choose an image (JPG, PNG, GIF)' : 
                        'انقر لاختيار صورة (JPG, PNG, GIF)';
                    imagePreview.style.display = 'none';
                    stopCamera();
                } else if (currentUploadType === 'camera') {
                    uploadInstruction.textContent = isEnglish ? 
                        'Click to start the camera' : 
                        'انقر لبدء الكاميرا';
                    imagePreview.style.display = 'none';
                    startCamera();
                }
                
                // إعادة تعيين الملف الحالي
                currentFile = null;
            });
        });
        
        // إدارة اختيار الملف
        fileInput.addEventListener('change', function() {
            if (this.files && this.files[0]) {
                handleFileSelect(this.files[0]);
            }
        });
        
        // إدارة اختيار الصورة
        imageInput.addEventListener('change', function() {
            if (this.files && this.files[0]) {
                handleFileSelect(this.files[0], true);
            }
        });
        
        // دالة معالجة اختيار الملف
        function handleFileSelect(file, isImage = false) {
            currentFile = file;
            playSound('click');
            
            const isEnglish = language.value === 'en';
            const fileMessage = document.getElementById('file-message');
            
            if (isImage) {
                // عرض معاينة الصورة
                const reader = new FileReader();
                reader.onload = function(e) {
                    previewImage.src = e.target.result;
                    imagePreview.style.display = 'block';
                    
                    if (fileMessage) {
                        fileMessage.innerHTML = isEnglish ? 
                            `<i class="fas fa-image"></i> Selected image: ${file.name}` : 
                            `<i class="fas fa-image"></i> الصورة المحددة: ${file.name}`;
                        fileMessage.classList.remove('success', 'error');
                        fileMessage.classList.add('success');
                        fileMessage.style.display = 'block';
                    }
                };
                reader.readAsDataURL(file);
            } else {
                // ملف نصي
                if (fileMessage) {
                    fileMessage.innerHTML = isEnglish ? 
                        `<i class="fas fa-file"></i> Selected file: ${file.name}` : 
                        `<i class="fas fa-file"></i> الملف المحدد: ${file.name}`;
                    fileMessage.classList.remove('success', 'error');
                    fileMessage.classList.add('success');
                    fileMessage.style.display = 'block';
                }
            }
        }
        
        // بدء تشغيل الكاميرا
        function startCamera() {
            cameraContainer.style.display = 'flex';
            
            // إعدادات الكاميرا المبسطة للجوال
            const constraints = {
                video: {
                    facingMode: 'environment',
                    width: { ideal: 1280 },
                    height: { ideal: 720 }
                },
                audio: false
            };
            
            navigator.mediaDevices.getUserMedia(constraints)
            .then(function(mediaStream) {
                stream = mediaStream;
                cameraFeed.srcObject = stream;
                
                // تفعيل زر التقاط الصورة
                captureBtn.disabled = false;
            })
            .catch(function(err) {
                console.error("Error accessing camera: ", err);
                const isEnglish = language.value === 'en';
                showMessage(isEnglish ? 
                    "Unable to access camera. Please check permissions." : 
                    "تعذر الوصول إلى الكاميرا. الرجاء التحقق من الأذونات.", 
                'error');
                captureBtn.disabled = true;
                
                // العودة إلى خيار الصورة
                uploadOptions.forEach(opt => {
                    if (opt.dataset.uploadType === 'image') {
                        opt.click();
                    }
                });
            });
        }
        
        // إيقاف تشغيل الكاميرا
        function stopCamera() {
            cameraContainer.style.display = 'none';
            
            if (stream) {
                stream.getTracks().forEach(track => {
                    track.stop();
                });
                stream = null;
            }
        }
        
        // التقاط صورة من الكاميرا
        captureBtn.addEventListener('click', function() {
            if (!stream || this.disabled) return;
            
            playSound('click');
            const canvas = document.createElement('canvas');
            const video = cameraFeed;
            
            // تحديد أبعاد القماش بناءً على أبعاد الفيديو
            canvas.width = video.videoWidth;
            canvas.height = video.videoHeight;
            
            const context = canvas.getContext('2d');
            
            // عكس الصورة للكاميرا الأمامية
            if (stream.getVideoTracks()[0].getSettings().facingMode === 'user') {
                context.translate(canvas.width, 0);
                context.scale(-1, 1);
            }
            
            context.drawImage(video, 0, 0, canvas.width, canvas.height);
            
            canvas.toBlob(function(blob) {
                const file = new File([blob], 'camera-capture.jpg', { type: 'image/jpeg' });
                handleFileSelect(file, true);
                stopCamera();
                
                // العودة إلى خيار الصورة
                uploadOptions.forEach(opt => {
                    if (opt.dataset.uploadType === 'image') {
                        opt.click();
                    }
                });
            }, 'image/jpeg', 0.95);
        });
        
        // إلغاء الكاميرا
        cancelCameraBtn.addEventListener('click', function() {
            playSound('click');
            stopCamera();
            
            // العودة إلى خيار الملف
            uploadOptions.forEach(opt => {
                if (opt.dataset.uploadType === 'file') {
                    opt.click();
                }
            });
        });
        
        // دالة عرض شاشة الانتظار
        function showLoadingScreen(numQuestions) {
            totalQuestions = numQuestions;
            timerSeconds = 0;
            
            // إنشاء النجوم
            createStars();
            
            // إظهار شاشة الانتظار
            loadingOverlay.style.display = 'flex';
            setTimeout(() => loadingOverlay.classList.add('active'), 10);
            document.body.style.overflow = 'hidden';
            
            // تشغيل موسيقى الانتظار
            if (musicEnabled) {
                loadingMusic.currentTime = 0;
                loadingMusic.play().catch(e => console.log('Loading music error:', e));
            }
            
            // إعادة تعيين الإحصائيات
            statQuestions.textContent = totalQuestions;
            statSeconds.textContent = '0';
            statProgress.textContent = '0%';
            progressPercent.textContent = '0%';
            progressBar.style.width = '0%';
            
            // تحديث رسالة المؤقت
            const isEnglish = language.value === 'en';
            const statusMessages = isEnglish ? [
                "Gathering information...",
                "Analyzing content...",
                "Creating questions...",
                "Optimizing difficulty...",
                "Adding explanations...",
                "Finalizing content...",
                "Knowledge is ready!"
            ] : [
                "يجمع المعلومات...",
                "يحلل المحتوى...",
                "ينشئ الأسئلة...",
                "يُحسن مستوى الصعوبة...",
                "يضيف الشرح...",
                "يُعد المحتوى النهائي...",
                "المعرفة جاهزة!"
            ];
            
            let messageIndex = 0;
            
            loadingInterval = setInterval(() => {
                timerSeconds++;
                
                // تحديث المؤقت
                const minutes = Math.floor(timerSeconds / 60);
                const seconds = timerSeconds % 60;
                loadingTimer.textContent = isEnglish 
                    ? `Processing... ${minutes}:${seconds.toString().padStart(2, '0')}`
                    : `جارٍ المعالجة... ${minutes}:${seconds.toString().padStart(2, '0')}`;
                
                // تحديث الإحصائيات
                statSeconds.textContent = timerSeconds;
                
                // حساب التقدم
                const progress = Math.min(Math.floor((timerSeconds / 60) * 100), 95);
                statProgress.textContent = `${progress}%`;
                progressBar.style.width = `${progress}%`;
                progressPercent.textContent = `${progress}%`;
                
                // تغيير الرسالة كل 8 ثواني
                if (timerSeconds % 8 === 0) {
                    messageIndex = (messageIndex + 1) % statusMessages.length;
                    progressStatus.textContent = statusMessages[messageIndex];
                }
                
                // إذا تجاوز 90 ثانية، إظهار رسالة تشجيعية
                if (timerSeconds === 90) {
                    const encouragement = isEnglish 
                        ? "Almost there! Preparing excellent content..."
                        : "تقريباً انتهينا! نُعد محتوى ممتازاً...";
                    progressStatus.textContent = encouragement;
                }
                
            }, 1000);
        }
        
        // دالة إخفاء شاشة الانتظار
        function hideLoadingScreen() {
            if (loadingInterval) {
                clearInterval(loadingInterval);
                loadingInterval = null;
            }
            
            // إيقاف موسيقى الانتظار
            loadingMusic.pause();
            
            // إكمال شريط التقدم
            progressBar.style.width = '100%';
            progressPercent.textContent = '100%';
            statProgress.textContent = '100%';
            
            // رسالة النجاح
            const isEnglish = language.value === 'en';
            progressStatus.textContent = isEnglish ? "Complete! Loading results..." : "اكتمل! جارٍ تحميل النتائج...";
            
            // إزالة النجوم
            const stars = document.querySelectorAll('.star');
            stars.forEach(star => star.remove());
            
            setTimeout(() => {
                loadingOverlay.classList.remove('active');
                setTimeout(() => {
                    loadingOverlay.style.display = 'none';
                    document.body.style.overflow = '';
                    playSound('success');
                }, 500);
            }, 1000);
        }
        
        // دالة العودة للصفحة الرئيسية من صفحة الأسئلة
        function backToMain() {
            playSound('click');
            quizPage.classList.remove('active');
            mainPage.style.display = 'block';
            document.body.style.overflow = '';
        }
        
        // دالة العودة للصفحة الرئيسية من صفحة الفلاش كاردز
        function backToMainFromFlashcards() {
            playSound('click');
            flashcardsPage.classList.remove('active');
            mainPage.style.display = 'block';
            document.body.style.overflow = '';
        }
        
        // دالة العودة للصفحة الرئيسية من صفحة التلخيص
        function backToMainFromSummary() {
            playSound('click');
            summaryPage.classList.remove('active');
            mainPage.style.display = 'block';
            document.body.style.overflow = '';
        }
        
        // دالة الانتقال لصفحة الأسئلة
        function goToQuizPage() {
            mainPage.style.display = 'none';
            quizPage.classList.add('active');
            document.body.style.overflow = 'auto';
            // التمرير للأعلى
            window.scrollTo(0, 0);
        }
        
        // دالة الانتقال لصفحة الفلاش كاردز
        function goToFlashcardsPage() {
            mainPage.style.display = 'none';
            flashcardsPage.classList.add('active');
            document.body.style.overflow = 'auto';
            // التمرير للأعلى
            window.scrollTo(0, 0);
        }
        
        // دالة الانتقال لصفحة التلخيص
        function goToSummaryPage() {
            mainPage.style.display = 'none';
            summaryPage.classList.add('active');
            document.body.style.overflow = 'auto';
            // التمرير للأعلى
            window.scrollTo(0, 0);
        }
        
        // دالة البدء
        async function start() {
            playSound('click');
            const activeTab = document.querySelector('.mode-tab.active');
            const mode = activeTab.dataset.mode;
            
            // التحقق من صحة الإدخال
            if (mode === 'manual' && !topic.value.trim()) {
                const isEnglish = language.value === 'en';
                showMessage(isEnglish ? 
                    "Please enter a topic to create questions" : 
                    "الرجاء إدخال موضوع لإنشاء الأسئلة", 
                'error');
                return;
            }
            
            if (mode !== 'manual') {
                if (!currentFile && currentUploadType !== 'camera') {
                    const isEnglish = language.value === 'en';
                    showMessage(isEnglish ? 
                        "Please choose a file or take a picture" : 
                        "الرجاء اختيار ملف أو التقاط صورة", 
                    'error');
                    return;
                }
                
                if (currentUploadType === 'camera' && !previewImage.src) {
                    const isEnglish = language.value === 'en';
                    showMessage(isEnglish ? 
                        "Please take a picture first" : 
                        "الرجاء التقاط صورة أولاً", 
                    'error');
                    return;
                }
            }
            
            // عرض شاشة الانتظار
            const numQuestions = parseInt(num.value);
            showLoadingScreen(numQuestions);
            
            try {
                if (mode === 'manual') {
                    await runManual();
                } else {
                    await runFile(mode);
                }
            } catch (error) {
                console.error('Error:', error);
                const isEnglish = language.value === 'en';
                showMessage(isEnglish ? 
                    "An error occurred during processing. Please try again." : 
                    "حدث خطأ أثناء المعالجة. الرجاء المحاولة مرة أخرى.", 
                'error');
                hideLoadingScreen();
            }
        }
        
        // دالة الاختبار اليدوي
        async function runManual() {
            const response = await fetch(API + "/ask", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({
                    prompt: topic.value,
                    language: language.value,
                    total_questions: +num.value
                })
            });
            
            const data = await response.json();
            hideLoadingScreen();
            
            if (currentMode === 'manual' || currentMode === 'file') {
                renderQuiz(JSON.parse(extractJSON(data.result)));
                goToQuizPage();
            } else if (currentMode === 'flashcards') {
                flashcardsData = JSON.parse(extractJSON(data.result));
                renderFlashcardsPage(flashcardsData);
                goToFlashcardsPage();
            } else if (currentMode === 'summary') {
                summaryData = data.result;
                renderSummaryPage(summaryData);
                goToSummaryPage();
            }
        }
        
        // دالة معالجة الملف
        async function runFile(mode) {
            const formData = new FormData();
            
            // إضافة الملف المناسب
            if (currentUploadType === 'image' && currentFile) {
                formData.append("file", currentFile, "image.jpg");
            } else if (currentFile) {
                formData.append("file", currentFile);
            } else if (previewImage.src) {
                // تحويل base64 إلى blob
                const base64Response = await fetch(previewImage.src);
                const blob = await base64Response.blob();
                formData.append("file", blob, "image.jpg");
            }
            
            formData.append("language", language.value);
            formData.append("num_questions", num.value);
            formData.append("mode", mode === 'file' ? "questions" : mode);
            
            const response = await fetch(API + "/ask-file", {
                method: "POST",
                body: formData
            });
            
            if (!response.ok) {
                throw new Error(`HTTP error! status: ${response.status}`);
            }
            
            const data = await response.json();
            hideLoadingScreen();
            
            if (mode === 'summary') {
                summaryData = data.result;
                renderSummaryPage(summaryData);
                goToSummaryPage();
            } else if (mode === 'flashcards') {
                flashcardsData = JSON.parse(extractJSON(data.result));
                renderFlashcardsPage(flashcardsData);
                goToFlashcardsPage();
            } else {
                renderQuiz(JSON.parse(extractJSON(data.result)));
                goToQuizPage();
            }
        }
        
        // دالة عرض الأسئلة مع التغذية الراجعة المحسنة
        function renderQuiz(data) {
            if (!data || !data.questions || !Array.isArray(data.questions)) {
                const isEnglish = language.value === 'en';
                showMessage(isEnglish ? 
                    "No questions found in received data" : 
                    "لم يتم العثور على أسئلة في البيانات المستلمة", 
                'error');
                return;
            }
            
            // حفظ بيانات الاختبار
            currentQuizData = data;
            
            const isEnglish = language.value === 'en';
            const letters = isEnglish ? ['A', 'B', 'C', 'D', 'E', 'F'] : ['أ', 'ب', 'ج', 'د', 'هـ', 'و'];
            
            const questionsHTML = data.questions.map((q, qi) => {
                return `
                    <div class="question" data-q="${qi}" data-answered="false">
                        <div class="question-header">
                            <div class="question-number">${qi + 1}</div>
                            <div class="question-text">${q.q}</div>
                        </div>
                        
                        <div class="options">
                            ${q.options.map((o, oi) => `
                                <div class="option" data-o="${oi}" data-q="${qi}">
                                    <div class="option-letter">${letters[oi]}</div>
                                    <div class="option-text">${o}</div>
                                </div>
                            `).join('')}
                        </div>
                        
                        <!-- زر تفسير الخيارات الخاطئة (سيظهر بعد الإجابة) -->
                        <button class="wrong-explanation-btn hidden" id="wrong-btn-${qi}" onclick="showWrongExplanations(${qi})">
                            <i class="fas fa-lightbulb"></i>
                            ${isEnglish ? 'Explain Wrong Options' : 'تفسير الخيارات الخاطئة'}
                        </button>
                        
                        <!-- التغذية الراجعة للإجابة الصحيحة فقط -->
                        <div class="feedback hidden" id="feedback-${qi}"></div>
                    </div>
                `;
            }).join('');
            
            quizContainer.innerHTML = questionsHTML;
            bindQuizEvents(data, letters);
        }
        
        // دالة ربط أحداث الأسئلة
        function bindQuizEvents(data, letters) {
            document.querySelectorAll('.option').forEach(option => {
                option.addEventListener('click', function() {
                    if (this.classList.contains('disabled')) return;
                    
                    playSound('click');
                    const questionIndex = parseInt(this.dataset.q);
                    const optionIndex = parseInt(this.dataset.o);
                    const question = data.questions[questionIndex];
                    const correctAnswer = question.answer;
                    const feedback = document.getElementById(`feedback-${questionIndex}`);
                    const wrongBtn = document.getElementById(`wrong-btn-${questionIndex}`);
                    const questionElement = document.querySelector(`.question[data-q="${questionIndex}"]`);
                    const isEnglish = language.value === 'en';
                    
                    // التحقق إذا تمت الإجابة على هذا السؤال مسبقاً
                    if (questionElement.dataset.answered === "true") return;
                    
                    // تعطيل جميع خيارات هذا السؤال
                    const allOptions = this.parentElement.querySelectorAll('.option');
                    allOptions.forEach(opt => {
                        opt.classList.add('disabled');
                    });
                    
                    // إزالة التحديد من جميع الخيارات
                    allOptions.forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    
                    // تحديد الخيار المختار
                    this.classList.add('selected');
                    
                    // التحقق من الإجابة وتحديث الخيارات
                    let feedbackHTML = '';
                    
                    if (optionIndex === correctAnswer) {
                        this.classList.add('correct');
                        playSound('correct');
                        
                        feedbackHTML = `
                            <div class="feedback-header">
                                <i class="fas fa-check-circle"></i>
                                <h3 class="feedback-title">${isEnglish ? 'Correct! Excellent!' : 'إجابة صحيحة! ممتاز!'}</h3>
                            </div>
                            <div class="feedback-content">
                                ${isEnglish ? 
                                    `Perfect! You've chosen the correct answer <strong>${letters[correctAnswer]}</strong>.` : 
                                    `ممتاز! لقد اخترت الإجابة الصحيحة <strong>${letters[correctAnswer]}</strong>.`
                                }
                                ${question.explanations && question.explanations[correctAnswer] ? 
                                    `<div class="feedback-details">
                                        <h4><i class="fas fa-info-circle"></i> ${isEnglish ? 'Detailed Explanation:' : 'الشرح التفصيلي:'}</h4>
                                        <p>${question.explanations[correctAnswer]}</p>
                                    </div>` : ''
                                }
                            </div>
                        `;
                    } else {
                        this.classList.add('incorrect');
                        playSound('wrong');
                        
                        // إظهار الإجابة الصحيحة
                        const correctOption = allOptions[correctAnswer];
                        if (correctOption) {
                            correctOption.classList.add('correct');
                        }
                        
                        feedbackHTML = `
                            <div class="feedback-header">
                                <i class="fas fa-times-circle"></i>
                                <h3 class="feedback-title">${isEnglish ? 'Incorrect' : 'إجابة خاطئة'}</h3>
                            </div>
                            <div class="feedback-content">
                                ${isEnglish ? 
                                    `The correct answer is <strong>${letters[correctAnswer]}</strong>.` : 
                                    `الإجابة الصحيحة هي <strong>${letters[correctAnswer]}</strong>.`
                                }
                                ${question.explanations && question.explanations[correctAnswer] ? 
                                    `<div class="feedback-details">
                                        <h4><i class="fas fa-info-circle"></i> ${isEnglish ? 'Why this is correct:' : 'لماذا هذه الإجابة صحيحة:'}</h4>
                                        <p>${question.explanations[correctAnswer]}</p>
                                    </div>` : ''
                                }
                            </div>
                        `;
                    }
                    
                    feedback.className = 'feedback';
                    feedback.innerHTML = feedbackHTML;
                    feedback.classList.remove('hidden');
                    
                    // إظهار زر تفسير الخيارات الخاطئة
                    if (wrongBtn) {
                        wrongBtn.classList.remove('hidden');
                    }
                    
                    // تحديث حالة السؤال للإجابة عليه
                    questionElement.dataset.answered = "true";
                    
                    // التمرير إلى التغذية الراجعة
                    feedback.scrollIntoView({ behavior: 'smooth', block: 'center' });
                });
            });
        }
        
        // دالة لعرض شرح الخيارات الخاطئة
        function showWrongExplanations(questionIndex) {
            playSound('click');
            const feedback = document.getElementById(`feedback-${questionIndex}`);
            const wrongBtn = document.getElementById(`wrong-btn-${questionIndex}`);
            const question = currentQuizData.questions[questionIndex];
            const isEnglish = language.value === 'en';
            const letters = isEnglish ? ['A', 'B', 'C', 'D', 'E', 'F'] : ['أ', 'ب', 'ج', 'د', 'هـ', 'و'];
            
            // إنشاء قسم شرح الخيارات الخاطئة
            let wrongExplanationsHTML = `
                <div class="wrong-explanations-section">
                    <h4 style="color: var(--warning); margin-bottom: 20px;">
                        <i class="fas fa-lightbulb"></i>
                        ${isEnglish ? 'Explanation of Wrong Options:' : 'شرح الخيارات الخاطئة:'}
                    </h4>
            `;
            
            // إضافة شرح لكل خيار خاطئ
            question.options.forEach((option, idx) => {
                if (idx === question.answer) return; // تخطي الإجابة الصحيحة
                
                const explanation = question.explanations && question.explanations[idx] 
                    ? question.explanations[idx] 
                    : (isEnglish ? `Option ${letters[idx]} is incorrect because it doesn't match the correct answer.` 
                               : `الخيار ${letters[idx]} خاطئ لأنه لا يتطابق مع الإجابة الصحيحة.`);
                
                wrongExplanationsHTML += `
                    <div class="wrong-explanation">
                        <h4><i class="fas fa-times"></i> ${letters[idx]}: ${option}</h4>
                        <div class="wrong-explanation-content">
                            ${explanation}
                        </div>
                    </div>
                `;
            });
            
            wrongExplanationsHTML += '</div>';
            
            // إضافة قسم الخيارات الخاطئة إلى التغذية الراجعة
            feedback.insertAdjacentHTML('beforeend', wrongExplanationsHTML);
            
            // إخفاء زر الشرح
            if (wrongBtn) {
                wrongBtn.classList.add('hidden');
            }
            
            // التمرير إلى قسم الخيارات الخاطئة
            const wrongSection = feedback.querySelector('.wrong-explanations-section');
            if (wrongSection) {
                wrongSection.scrollIntoView({ behavior: 'smooth', block: 'center' });
            }
        }
        
        // دالة عرض البطاقات التعليمية في صفحتها الخاصة
        function renderFlashcardsPage(data) {
            if (!data || !data.cards || !Array.isArray(data.cards)) {
                const isEnglish = language.value === 'en';
                showMessage(isEnglish ? 
                    "No cards found in received data" : 
                    "لم يتم العثور على بطاقات في البيانات المستلمة", 
                'error');
                return;
            }
            
            const isEnglish = language.value === 'en';
            
            window.cards = data.cards;
            window.cardIndex = 0;
            
            flashcardsContainer.innerHTML = `
                <div class="flashcard-page" onclick="flipCardPage()">
                    <div class="flashcard-front-page">${data.cards[0].front}</div>
                    <div class="flashcard-back-page hidden">${data.cards[0].back}</div>
                    <div class="flashcard-counter-page">${cardIndex + 1} / ${data.cards.length}</div>
                </div>
                
                <div class="flashcard-nav-page">
                    <button class="flashcard-btn-page" onclick="prevCardPage()">
                        <i class="fas fa-arrow-right"></i> ${isEnglish ? 'Previous' : 'السابق'}
                    </button>
                    <button class="flashcard-btn-page" onclick="flipCardPage()">
                        <i class="fas fa-sync-alt"></i> ${isEnglish ? 'Flip Card' : 'قلب البطاقة'}
                    </button>
                    <button class="flashcard-btn-page" onclick="nextCardPage()">
                        <i class="fas fa-arrow-left"></i> ${isEnglish ? 'Next' : 'التالي'}
                    </button>
                </div>
            `;
        }
        
        // دالة قلب البطاقة في صفحتها الخاصة
        function flipCardPage() {
            playSound('click');
            const card = document.querySelector('.flashcard-page');
            const front = card.querySelector('.flashcard-front-page');
            const back = card.querySelector('.flashcard-back-page');
            
            // تأثير قلب البطاقة
            card.style.transform = 'rotateY(90deg)';
            setTimeout(() => {
                front.classList.toggle('hidden');
                back.classList.toggle('hidden');
                card.style.transform = 'rotateY(0deg)';
            }, 150);
        }
        
        // دالة البطاقة التالية في صفحتها الخاصة
        function nextCardPage() {
            playSound('click');
            cardIndex = (cardIndex + 1) % cards.length;
            updateCardPage();
        }
        
        // دالة البطاقة السابقة في صفحتها الخاصة
        function prevCardPage() {
            playSound('click');
            cardIndex = (cardIndex - 1 + cards.length) % cards.length;
            updateCardPage();
        }
        
        // دالة تحديث البطاقة في صفحتها الخاصة
        function updateCardPage() {
            const card = document.querySelector('.flashcard-page');
            const front = card.querySelector('.flashcard-front-page');
            const back = card.querySelector('.flashcard-back-page');
            const counter = card.querySelector('.flashcard-counter-page');
            
            front.textContent = cards[cardIndex].front;
            back.textContent = cards[cardIndex].back;
            counter.textContent = `${cardIndex + 1} / ${cards.length}`;
            
            // التأكد من إظهار الوجه الأمامي
            back.classList.add('hidden');
            front.classList.remove('hidden');
            
            // إضافة تأثير التحريك
            card.style.transform = 'scale(0.95)';
            setTimeout(() => {
                card.style.transform = 'scale(1)';
            }, 150);
        }
        
        // دالة عرض التلخيص في صفحته الخاصة
        function renderSummaryPage(text) {
            // تحويل النص إلى نقاط منسقة
            const paragraphs = text.split('\n').filter(p => p.trim().length > 0);
            let summaryHTML = '<div class="summary-page-content">';
            
            const isEnglish = language.value === 'en';
            summaryHTML += `<div class="summary-title-page"><i class="fas fa-scroll"></i> ${isEnglish ? 'Summary' : 'التلخيص'}</div>`;
            
            paragraphs.forEach((paragraph, idx) => {
                summaryHTML += `
                    <div class="summary-point-page">
                        <i class="fas fa-lightbulb"></i>
                        <div class="summary-point-text-page">${paragraph}</div>
                    </div>
                `;
            });
            
            summaryHTML += '</div>';
            summaryContainer.innerHTML = summaryHTML;
        }
        
        // دالة عرض الرسائل
        function showMessage(text, type = 'info') {
            out.innerHTML = `
                <div class="message ${type}">
                    <i class="fas fa-${type === 'error' ? 'exclamation-triangle' : 'info-circle'}"></i>
                    ${text}
                </div>
            `;
        }
        
        // دالة لاستخراج JSON من النص
        function extractJSON(text) {
            try {
                // محاولة تحليل النص مباشرة كـ JSON
                const parsed = JSON.parse(text);
                return JSON.stringify(parsed);
            } catch (e) {
                // البحث عن JSON في النص
                const match = text.match(/\{[\s\S]*\}/);
                if (match) {
                    try {
                        return match[0];
                    } catch (e2) {
                        return '{"questions":[]}';
                    }
                }
                return '{"questions":[]}';
            }
        }
        
        // تهيئة أولية
        document.addEventListener('DOMContentLoaded', function() {
            // تحسينات خاصة للجوال
            if (isMobile) {
                // إضافة حدث للنقر على منطقة التحميل
                document.querySelector('.file-upload-area').addEventListener('click', function(e) {
                    if (e.target.closest('.upload-option-btn')) {
                        return;
                    }
                    
                    if (currentUploadType === 'image') {
                        imageInput.click();
                    } else {
                        fileInput.click();
                    }
                });
                
                // تحسينات للشاشات الصغيرة
                if (window.innerWidth < 768) {
                    // ضبط حجم الخط للحقول على iOS
                    if (isIOS) {
                        document.querySelectorAll('input, textarea, select').forEach(el => {
                            el.style.fontSize = '16px';
                        });
                    }
                }
            }
            
            // تحديث التعليمات الافتراضية
            const fileMessage = document.getElementById('file-message');
            if (fileMessage) {
                fileMessage.innerHTML = '<i class="fas fa-file"></i> يمكنك رفع ملفات نصية أو PDF أو Word أو صور';
                fileMessage.classList.add('success');
                fileMessage.style.display = 'block';
            }
            
            // إصلاح مشكلة الـ 100vh على iOS
            function setVh() {
                let vh = window.innerHeight * 0.01;
                document.documentElement.style.setProperty('--vh', `${vh}px`);
            }
            
            setVh();
            window.addEventListener('resize', setVh);
            window.addEventListener('orientationchange', setVh);
            
            // توقف عن تشغيل الكاميرا عند إغلاق الصفحة
            window.addEventListener('beforeunload', function() {
                if (stream) {
                    stream.getTracks().forEach(track => {
                        track.stop();
                    });
                }
                if (loadingInterval) {
                    clearInterval(loadingInterval);
                }
                backgroundMusic.pause();
                loadingMusic.pause();
            });
            
            // بدء تشغيل الموسيقى الخلفية
            if (musicEnabled) {
                backgroundMusic.play().catch(e => console.log('Background music error:', e));
            }
        });
    </script>
</body>
</html>