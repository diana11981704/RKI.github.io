# RKI.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Рабочий лист — Образование</title>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,400;1,600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #f5f0eb;
            --card-bg: #ffffff;
            --primary: #2c3e6b;
            --accent: #c8963e;
            --accent2: #e07b5a;
            --gold: #d4a843;
            --correct: #2e7d32;
            --correct-bg: #e8f5e9;
            --incorrect: #c62828;
            --incorrect-bg: #ffebee;
            --text: #2a2a2a;
            --text-light: #555;
            --border: #e0d8cc;
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.07);
            --shadow-lg: 0 12px 40px rgba(0, 0, 0, 0.12);
            --radius: 16px;
            --radius-sm: 10px;
            --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Nunito', system-ui, -apple-system, sans-serif;
            background: linear-gradient(160deg, #f7f1e8 0%, #eef3fa 30%, #f5f0eb 60%, #faf7f2 100%);
            min-height: 100vh;
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* ============ FLOATING ELEMENTS ============ */
        .floating-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .floating-el {
            position: absolute;
            pointer-events: none;
            will-change: transform;
            opacity: 0.55;
        }

        /* Sparkle dots */
        .sparkle {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: var(--accent);
            box-shadow: 0 0 8px rgba(200, 150, 62, 0.5);
            animation: floatSparkle 7s ease-in-out infinite;
        }
        .sparkle.pink {
            background: #e8859c;
            box-shadow: 0 0 8px rgba(232, 133, 156, 0.5);
            animation-delay: -2s;
            animation-duration: 8.5s;
        }
        .sparkle.blue {
            background: #6b9ec8;
            box-shadow: 0 0 8px rgba(107, 158, 200, 0.5);
            animation-delay: -4s;
            animation-duration: 9s;
        }
        .sparkle.gold {
            background: #d4a843;
            box-shadow: 0 0 10px rgba(212, 168, 67, 0.6);
            animation-delay: -1.5s;
            animation-duration: 6.5s;
        }
        .sparkle.coral {
            background: #e07b5a;
            box-shadow: 0 0 8px rgba(224, 123, 90, 0.5);
            animation-delay: -5s;
            animation-duration: 10s;
        }
        .sparkle.teal {
            background: #4db8a8;
            box-shadow: 0 0 8px rgba(77, 184, 168, 0.5);
            animation-delay: -3s;
            animation-duration: 7.8s;
        }

        @keyframes floatSparkle {
            0%,
            100% {
                transform: translateY(0) translateX(0) scale(1);
                opacity: 0.55;
            }
            15% {
                transform: translateY(-30px) translateX(18px) scale(1.6);
                opacity: 0.85;
            }
            30% {
                transform: translateY(-15px) translateX(-10px) scale(0.7);
                opacity: 0.4;
            }
            50% {
                transform: translateY(25px) translateX(-22px) scale(1.5);
                opacity: 0.75;
            }
            65% {
                transform: translateY(10px) translateX(15px) scale(0.8);
                opacity: 0.5;
            }
            80% {
                transform: translateY(-20px) translateX(-8px) scale(1.3);
                opacity: 0.7;
            }
        }

        /* Diamond shapes */
        .diamond {
            width: 20px;
            height: 20px;
            background: transparent;
            border: 2.5px solid var(--accent);
            transform: rotate(45deg);
            animation: floatDiamond 11s ease-in-out infinite;
            opacity: 0.5;
        }
        .diamond.coral {
            border-color: #e07b5a;
            animation-delay: -3s;
            animation-duration: 13s;
        }
        .diamond.teal {
            border-color: #4db8a8;
            animation-delay: -6s;
            animation-duration: 9s;
        }
        .diamond.gold {
            border-color: #d4a843;
            animation-delay: -8s;
            animation-duration: 14s;
        }

        @keyframes floatDiamond {
            0%,
            100% {
                transform: rotate(45deg) translateY(0) translateX(0) scale(1);
                opacity: 0.5;
            }
            20% {
                transform: rotate(50deg) translateY(-40px) translateX(25px) scale(1.4);
                opacity: 0.8;
            }
            40% {
                transform: rotate(38deg) translateY(15px) translateX(-20px) scale(0.7);
                opacity: 0.35;
            }
            60% {
                transform: rotate(48deg) translateY(30px) translateX(-30px) scale(1.5);
                opacity: 0.75;
            }
            80% {
                transform: rotate(42deg) translateY(-10px) translateX(20px) scale(0.9);
                opacity: 0.55;
            }
        }

        /* Circle rings */
        .ring {
            width: 28px;
            height: 28px;
            border-radius: 50%;
            border: 2px solid rgba(200, 150, 62, 0.5);
            background: transparent;
            animation: floatRing 8s ease-in-out infinite;
        }
        .ring.pink {
            border-color: rgba(232, 133, 156, 0.5);
            animation-delay: -4s;
            animation-duration: 10s;
        }
        .ring.blue {
            border-color: rgba(107, 158, 200, 0.5);
            animation-delay: -7s;
            animation-duration: 12s;
        }

        @keyframes floatRing {
            0%,
            100% {
                transform: translateY(0) translateX(0) scale(1);
                opacity: 0.5;
            }
            25% {
                transform: translateY(-35px) translateX(-15px) scale(1.5);
                opacity: 0.8;
            }
            50% {
                transform: translateY(20px) translateX(20px) scale(0.6);
                opacity: 0.3;
            }
            75% {
                transform: translateY(-20px) translateX(-25px) scale(1.3);
                opacity: 0.7;
            }
        }

        /* Star shapes */
        .star-shape {
            font-size: 22px;
            animation: floatStar 9s ease-in-out infinite;
            opacity: 0.6;
            filter: drop-shadow(0 0 4px rgba(200, 150, 62, 0.4));
        }
        .star-shape.gold {
            animation-delay: -5s;
            animation-duration: 11s;
        }
        .star-shape.pink {
            animation-delay: -2s;
            animation-duration: 7.5s;
            filter: drop-shadow(0 0 4px rgba(232, 133, 156, 0.4));
        }

        @keyframes floatStar {
            0%,
            100% {
                transform: translateY(0) translateX(0) rotate(0deg) scale(1);
                opacity: 0.6;
            }
            20% {
                transform: translateY(-45px) translateX(20px) rotate(72deg) scale(1.5);
                opacity: 0.9;
            }
            45% {
                transform: translateY(15px) translateX(-18px) rotate(144deg) scale(0.65);
                opacity: 0.35;
            }
            70% {
                transform: translateY(28px) translateX(-28px) rotate(216deg) scale(1.4);
                opacity: 0.75;
            }
            90% {
                transform: translateY(-15px) translateX(22px) rotate(300deg) scale(0.9);
                opacity: 0.55;
            }
        }

        /* Book-like small rectangles */
        .mini-book {
            width: 16px;
            height: 11px;
            background: var(--accent2);
            border-radius: 3px;
            animation: floatBook 10s ease-in-out infinite;
            opacity: 0.5;
            box-shadow: 0 2px 6px rgba(224, 123, 90, 0.3);
        }
        .mini-book.blue {
            background: #6b9ec8;
            animation-delay: -3.5s;
            animation-duration: 12s;
            box-shadow: 0 2px 6px rgba(107, 158, 200, 0.3);
        }
        .mini-book.gold {
            background: #d4a843;
            animation-delay: -7s;
            animation-duration: 8.5s;
            box-shadow: 0 2px 6px rgba(212, 168, 67, 0.3);
        }

        @keyframes floatBook {
            0%,
            100% {
                transform: translateY(0) translateX(0) rotate(0deg) scale(1);
                opacity: 0.5;
            }
            18% {
                transform: translateY(-30px) translateX(30px) rotate(15deg) scale(1.5);
                opacity: 0.8;
            }
            36% {
                transform: translateY(10px) translateX(-15px) rotate(-8deg) scale(0.7);
                opacity: 0.35;
            }
            55% {
                transform: translateY(25px) translateX(-25px) rotate(20deg) scale(1.4);
                opacity: 0.7;
            }
            75% {
                transform: translateY(-18px) translateX(20px) rotate(-12deg) scale(1.1);
                opacity: 0.55;
            }
        }

        /* ============ MAIN LAYOUT ============ */
        .main-container {
            position: relative;
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px 24px 40px;
        }

        /* ============ SCORE BAR ============ */
        .score-bar {
            position: sticky;
            top: 16px;
            z-index: 10;
            background: var(--card-bg);
            border-radius: 50px;
            padding: 14px 24px;
            box-shadow: var(--shadow-lg);
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
            margin-bottom: 20px;
            border: 1px solid var(--border);
            backdrop-filter: blur(10px);
            transition: var(--transition);
        }
        .score-bar.scrolled {
            box-shadow: 0 16px 48px rgba(0, 0, 0, 0.18);
        }
        .score-title {
            font-weight: 700;
            font-size: 1rem;
            color: var(--primary);
            white-space: nowrap;
            letter-spacing: 0.3px;
        }
        .score-display {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 800;
            font-size: 1.25rem;
            color: var(--accent);
        }
        .score-circle {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: linear-gradient(135deg, #fdf3e0, #fef9f0);
            border: 3px solid var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 1.1rem;
            color: var(--accent);
            transition: var(--transition);
            position: relative;
        }
        .score-circle.pulse {
            animation: scorePulse 0.6s ease-out;
        }
        @keyframes scorePulse {
            0% {
                transform: scale(1.25);
                border-color: #4CAF50;
                color: #4CAF50;
            }
            60% {
                transform: scale(1.05);
            }
            100% {
                transform: scale(1);
            }
        }
        .score-percent {
            font-size: 0.85rem;
            color: var(--text-light);
            font-weight: 500;
        }

        /* ============ HEADER ============ */
        .header {
            text-align: center;
            padding: 40px 20px 30px;
            position: relative;
            background: var(--card-bg);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            margin-bottom: 24px;
            border: 1px solid var(--border);
            overflow: hidden;
        }
        .header::before {
            content: '';
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 120px;
            height: 120px;
            background: radial-gradient(circle, rgba(200, 150, 62, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }
        .header-icon {
            font-size: 52px;
            display: block;
            margin-bottom: 8px;
            animation: bounceIcon 2s ease-in-out infinite;
        }
        @keyframes bounceIcon {
            0%,
            100% {
                transform: translateY(0);
            }
            30% {
                transform: translateY(-14px);
            }
            60% {
                transform: translateY(0);
            }
            85% {
                transform: translateY(-6px);
            }
        }
        .header h1 {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--primary);
            letter-spacing: -0.5px;
            margin: 0;
            line-height: 1.2;
        }
        .header .subtitle {
            font-size: 1.1rem;
            color: var(--accent);
            font-weight: 600;
            margin-top: 6px;
            letter-spacing: 0.5px;
        }
        .header .decorative-line {
            width: 70px;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--accent2));
            border-radius: 10px;
            margin: 12px auto 0;
            opacity: 0.7;
        }

        /* ============ SECTION CARDS ============ */
        .section {
            background: var(--card-bg);
            border-radius: var(--radius);
            padding: 28px 30px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            border: 1px solid var(--border);
            transition: var(--transition);
            position: relative;
        }
        .section:hover {
            box-shadow: var(--shadow-lg);
            border-color: #d5cfc4;
        }
        .section h2 {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 10px;
            letter-spacing: 0.2px;
        }
        .section h2 .emoji {
            font-size: 1.5rem;
        }
        .section h3 {
            font-size: 1.1rem;
            font-weight: 700;
            color: #3d4f6b;
            margin: 16px 0 8px;
        }
        .section p {
            margin: 6px 0;
            color: var(--text);
        }

        /* ============ TABLE STYLES ============ */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 12px 0;
            font-size: 0.9rem;
            border-radius: var(--radius-sm);
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
        }
        table th,
        table td {
            padding: 10px 14px;
            text-align: left;
            border: 1px solid #e8e1d6;
        }
        table th {
            background: #f9f5ef;
            font-weight: 700;
            color: var(--primary);
            font-size: 0.85rem;
            letter-spacing: 0.3px;
        }
        table td {
            background: #fffdf9;
        }
        table tr:hover td {
            background: #fdf9f2;
        }
        .vocab-table td:first-child {
            font-weight: 700;
            color: var(--primary);
            white-space: nowrap;
        }

        /* ============ INPUT STYLES ============ */
        input[type="text"] {
            width: 100%;
            padding: 10px 14px;
            border: 2px solid #e0d8cc;
            border-radius: var(--radius-sm);
            font-size: 0.95rem;
            font-family: 'Nunito', sans-serif;
            background: #fefdfa;
            transition: var(--transition);
            color: var(--text);
            letter-spacing: 0.2px;
        }
        input[type="text"]:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 4px rgba(200, 150, 62, 0.1);
            background: #fff;
        }
        input[type="text"].correct-input {
            border-color: #4CAF50 !important;
            background: #e8f5e9 !important;
            box-shadow: 0 0 0 4px rgba(76, 175, 80, 0.12) !important;
            animation: correctGlow 0.8s ease-out;
        }
        input[type="text"].incorrect-input {
            border-color: #e57373 !important;
            background: #ffebee !important;
            box-shadow: 0 0 0 4px rgba(229, 115, 115, 0.12) !important;
            animation: shake 0.5s ease-out;
        }
        @keyframes correctGlow {
            0% {
                box-shadow: 0 0 0 12px rgba(76, 175, 80, 0.3);
            }
            100% {
                box-shadow: 0 0 0 4px rgba(76, 175, 80, 0.1);
            }
        }
        @keyframes shake {
            0%,
            100% {
                transform: translateX(0);
            }
            15% {
                transform: translateX(-6px);
            }
            30% {
                transform: translateX(6px);
            }
            50% {
                transform: translateX(-4px);
            }
            70% {
                transform: translateX(4px);
            }
            85% {
                transform: translateX(-2px);
            }
        }
        .input-group {
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
            flex-wrap: wrap;
        }
        .input-group label {
            font-weight: 600;
            color: var(--primary);
            min-width: 30px;
            font-size: 0.9rem;
            white-space: nowrap;
        }
        .input-group .sentence-context {
            flex: 1;
            min-width: 200px;
            font-size: 0.9rem;
            color: var(--text);
            line-height: 1.4;
        }
        .input-group input {
            flex: 1;
            min-width: 140px;
            max-width: 350px;
        }
        .inline-input {
            display: inline-block;
            width: 180px;
            margin: 0 4px;
        }

        /* ============ BUTTONS ============ */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 12px 24px;
            border: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.95rem;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            letter-spacing: 0.3px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        .btn-check {
            background: linear-gradient(135deg, #2c3e6b, #3d5578);
            color: #fff;
            box-shadow: 0 4px 16px rgba(44, 62, 107, 0.3);
        }
        .btn-check:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(44, 62, 107, 0.4);
            background: linear-gradient(135deg, #354d80, #4a6590);
        }
        .btn-check:active {
            transform: translateY(0) scale(0.97);
            box-shadow: 0 4px 12px rgba(44, 62, 107, 0.3);
        }
        .btn-reset {
            background: #fff;
            color: var(--text);
            border: 2px solid #d5cfc4;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }
        .btn-reset:hover {
            background: #f9f6f0;
            border-color: #bdb5a8;
        }
        .btn-truth {
            padding: 8px 16px;
            font-size: 0.85rem;
            border-radius: 25px;
            font-weight: 600;
            background: #fff;
            border: 2px solid #e0d8cc;
            cursor: pointer;
            transition: var(--transition);
            color: var(--text);
        }
        .btn-truth.selected-true {
            background: #e8f5e9;
            border-color: #4CAF50;
            color: #2e7d32;
            font-weight: 700;
        }
        .btn-truth.selected-false {
            background: #ffebee;
            border-color: #e57373;
            color: #c62828;
            font-weight: 700;
        }
        .btn-truth.correct-choice {
            background: #c8e6c9 !important;
            border-color: #388e3c !important;
            color: #1b5e20 !important;
            animation: correctGlow 0.8s ease-out;
        }
        .btn-truth.incorrect-choice {
            background: #ffcdd2 !important;
            border-color: #d32f2f !important;
            color: #b71c1c !important;
            animation: shake 0.5s ease-out;
        }
        .btn-group {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-top: 8px;
        }

        /* ============ FEEDBACK BADGES ============ */
        .feedback-inline {
            display: inline-block;
            font-weight: 700;
            font-size: 0.8rem;
            padding: 3px 10px;
            border-radius: 20px;
            margin-left: 6px;
            opacity: 0;
            transition: opacity 0.3s;
        }
        .feedback-inline.show {
            opacity: 1;
        }
        .feedback-inline.correct-fb {
            background: #c8e6c9;
            color: #1b5e20;
        }
        .feedback-inline.incorrect-fb {
            background: #ffcdd2;
            color: #b71c1c;
        }

        /* ============ IMAGE ============ */
        .illustration-img {
            width: 100%;
            max-width: 500px;
            border-radius: var(--radius-sm);
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);
            margin: 12px auto;
            display: block;
            transition: var(--transition);
        }
        .illustration-img:hover {
            box-shadow: 0 8px 28px rgba(0, 0, 0, 0.16);
            transform: scale(1.02);
        }
        .grammar-img {
            width: 100%;
            max-width: 600px;
            border-radius: var(--radius-sm);
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
            margin: 10px auto;
            display: block;
            transition: var(--transition);
        }
        .grammar-img:hover {
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.14);
            transform: scale(1.01);
        }

        /* ============ HIGHLIGHT CLICK ============ */
        .clickable-phrase {
            cursor: pointer;
            padding: 2px 6px;
            border-radius: 5px;
            transition: var(--transition);
            display: inline;
            border-bottom: 2px dashed transparent;
        }
        .clickable-phrase:hover {
            background: #fef3e0;
            border-bottom-color: var(--accent);
        }
        .clickable-phrase.highlighted {
            background: #fff3cd;
            border-bottom: 2px solid #d4a843;
            font-weight: 600;
        }
        .clickable-phrase.found-correct {
            background: #d4edda;
            border-bottom: 2px solid #28a745;
            font-weight: 700;
        }

        /* ============ MODAL / TOAST ============ */
        .toast {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%) translateY(-120px);
            background: #2c3e6b;
            color: #fff;
            padding: 14px 28px;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.95rem;
            z-index: 100;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            pointer-events: none;
            letter-spacing: 0.3px;
        }
        .toast.show {
            transform: translateX(-50%) translateY(0);
        }
        .toast.success {
            background: #2e7d32;
        }
        .toast.warning {
            background: #e07b5a;
        }

        /* ============ RESPONSIVE ============ */
        @media (max-width: 768px) {
            .main-container {
                padding: 12px 14px 30px;
            }
            .section {
                padding: 18px 16px;
            }
            .header h1 {
                font-size: 1.6rem;
            }
            .score-bar {
                padding: 10px 16px;
                flex-wrap: wrap;
                gap: 8px;
            }
            .input-group {
                flex-direction: column;
                align-items: stretch;
            }
            .input-group input {
                max-width: 100%;
            }
            table {
                font-size: 0.75rem;
            }
            table th,
            table td {
                padding: 6px 8px;
            }
            .btn {
                padding: 10px 18px;
                font-size: 0.85rem;
            }
            .floating-el.sparkle {
                width: 5px;
                height: 5px;
            }
            .floating-el.diamond {
                width: 14px;
                height: 14px;
            }
            .floating-el.ring {
                width: 20px;
                height: 20px;
            }
            .floating-el.star-shape {
                font-size: 16px;
            }
            .floating-el.mini-book {
                width: 11px;
                height: 8px;
            }
        }

        @media (max-width: 480px) {
            .header h1 {
                font-size: 1.3rem;
            }
            .header .subtitle {
                font-size: 0.9rem;
            }
            .section h2 {
                font-size: 1.1rem;
            }
            .btn-truth {
                padding: 6px 12px;
                font-size: 0.75rem;
            }
            .score-circle {
                width: 38px;
                height: 38px;
                font-size: 0.9rem;
            }
        }

        /* ============ SECTION DIVIDER ============ */
        .divider {
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, #e0d8cc, transparent);
            margin: 10px 0 16px;
            opacity: 0.6;
        }

        /* ============ HIGHLIGHT BOX ============ */
        .highlight-box {
            background: #fefdf5;
            border: 1px dashed #d4c8a0;
            border-radius: var(--radius-sm);
            padding: 12px 16px;
            margin: 8px 0;
            font-style: italic;
            color: #5a4a30;
            font-size: 0.9rem;
        }

        /* ============ PROGRESS DOTS ============ */
        .progress-dots {
            display: flex;
            gap: 6px;
            align-items: center;
        }
        .progress-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #e0d8cc;
            transition: var(--transition);
        }
        .progress-dot.done {
            background: #4CAF50;
            box-shadow: 0 0 6px rgba(76, 175, 80, 0.4);
        }
    </style>
</head>
<body>

    <!-- ============ FLOATING ELEMENTS ============ -->
    <div class="floating-container" aria-hidden="true">
        <!-- Sparkles -->
        <div class="floating-el sparkle" style="top:8%;left:5%;"></div>
        <div class="floating-el sparkle pink" style="top:12%;left:92%;"></div>
        <div class="floating-el sparkle blue" style="top:22%;left:3%;"></div>
        <div class="floating-el sparkle gold" style="top:18%;left:88%;"></div>
        <div class="floating-el sparkle coral" style="top:35%;left:96%;"></div>
        <div class="floating-el sparkle teal" style="top:28%;left:7%;"></div>
        <div class="floating-el sparkle" style="top:48%;left:94%;"></div>
        <div class="floating-el sparkle pink" style="top:55%;left:2%;"></div>
        <div class="floating-el sparkle blue" style="top:65%;left:90%;"></div>
        <div class="floating-el sparkle gold" style="top:72%;left:6%;"></div>
        <div class="floating-el sparkle coral" style="top:80%;left:93%;"></div>
        <div class="floating-el sparkle teal" style="top:88%;left:4%;"></div>
        <!-- Diamonds -->
        <div class="floating-el diamond" style="top:10%;left:15%;"></div>
        <div class="floating-el diamond coral" style="top:30%;left:85%;"></div>
        <div class="floating-el diamond teal" style="top:50%;left:10%;"></div>
        <div class="floating-el diamond gold" style="top:70%;left:87%;"></div>
        <div class="floating-el diamond" style="top:85%;left:20%;"></div>
        <!-- Rings -->
        <div class="floating-el ring" style="top:15%;left:78%;"></div>
        <div class="floating-el ring pink" style="top:40%;left:8%;"></div>
        <div class="floating-el ring blue" style="top:60%;left:82%;"></div>
        <div class="floating-el ring" style="top:78%;left:12%;"></div>
        <!-- Stars -->
        <div class="floating-el star-shape gold" style="top:6%;left:35%;">✦</div>
        <div class="floating-el star-shape pink" style="top:25%;left:75%;">✧</div>
        <div class="floating-el star-shape" style="top:45%;left:18%;">✦</div>
        <div class="floating-el star-shape gold" style="top:58%;left:80%;">✧</div>
        <div class="floating-el star-shape pink" style="top:75%;left:25%;">✦</div>
        <div class="floating-el star-shape" style="top:90%;left:70%;">✧</div>
        <!-- Mini books -->
        <div class="floating-el mini-book" style="top:20%;left:22%;"></div>
        <div class="floating-el mini-book blue" style="top:38%;left:72%;"></div>
        <div class="floating-el mini-book gold" style="top:52%;left:15%;"></div>
        <div class="floating-el mini-book" style="top:68%;left:78%;"></div>
        <div class="floating-el mini-book blue" style="top:82%;left:30%;"></div>
    </div>

    <!-- ============ TOAST ============ -->
    <div class="toast" id="toast"></div>

    <!-- ============ MAIN CONTAINER ============ -->
    <div class="main-container">

        <!-- SCORE BAR -->
        <div class="score-bar" id="scoreBar">
            <span class="score-title">🏆 Баллы</span>
            <div class="progress-dots" id="progressDots">
                <span style="font-size:0.75rem;color:#888;">Задания:</span>
                <div class="progress-dot" data-ex="ex1"></div>
                <div class="progress-dot" data-ex="ex3"></div>
                <div class="progress-dot" data-ex="truth1"></div>
                <div class="progress-dot" data-ex="truth2"></div>
            </div>
            <div class="score-display">
                <div class="score-circle" id="scoreCircle"><span id="scoreEarned">0</span></div>
                <span style="font-size:0.9rem;">/ <span id="scoreTotal">46</span></span>
                <span class="score-percent" id="scorePercent">0%</span>
            </div>
        </div>

        <!-- HEADER -->
        <div class="header">
            <span class="header-icon">📚</span>
            <h1>РАБОЧИЙ ЛИСТ</h1>
            <p class="subtitle">Тема: ОБРАЗОВАНИЕ</p>
            <div class="decorative-line"></div>
            <p style="margin-top:8px;color:var(--text-light);font-size:0.9rem;">Интерактивные задания • Родительный падеж • Лексика</p>
        </div>

        <!-- ============ ЛЕКСИКА ============ -->
        <div class="section" id="vocabSection">
            <h2><span class="emoji">📖</span> ЛЕКСИКА</h2>
            <table class="vocab-table">
                <thead>
                    <tr><th>Слово</th><th>Значение</th></tr>
                </thead>
                <tbody>
                    <tr><td><strong>Сенсация</strong></td><td>событие или новость, вызывающие всеобщий интерес и удивление</td></tr>
                    <tr><td><strong>Полиглот</strong></td><td>человек, владеющий многими иностранными языками</td></tr>
                    <tr><td><strong>Талантливый</strong></td><td>обладающий природными способностями, даром</td></tr>
                    <tr><td><strong>Акцент</strong></td><td>особенности произношения, выдающие неродной язык</td></tr>
                    <tr><td><strong>Преподаватель</strong></td><td>тот, кто обучает других</td></tr>
                    <tr><td><strong>Энциклопедия</strong></td><td>справочное издание по всем или отдельным отраслям знаний</td></tr>
                    <tr><td><strong>Свободное время</strong></td><td>время, не занятое работой или учёбой</td></tr>
                    <tr><td><strong>Рисование</strong></td><td>вид художественного творчества, создание рисунков</td></tr>
                    <tr><td><strong>Итальянский (язык)</strong></td><td>язык Италии, романской группы</td></tr>
                    <tr><td><strong>Любимый (язык)</strong></td><td>тот, который больше всего нравится</td></tr>
                    <tr><td><strong>Энтузиазм</strong></td><td>сильное желание и интерес делать что-то</td></tr>
                    <tr><td><strong>Ритмика</strong></td><td>школьный предмет, где дети учатся двигаться под музыку</td></tr>
                    <tr><td><strong>Актёрский вуз</strong></td><td>институт, где учат на актёра</td></tr>
                    <tr><td><strong>Поболтать</strong></td><td>поговорить немного, не очень серьёзно</td></tr>
                    <tr><td><strong>Любознательный</strong></td><td>человек, который хочет много знать, задаёт вопросы</td></tr>
                </tbody>
            </table>
        </div>

        <!-- ============ УПРАЖНЕНИЕ 1 ============ -->
        <div class="section" id="ex1Section">
            <h2><span class="emoji">✏️</span> УПРАЖНЕНИЕ 1</h2>
            <p><strong>Дополните предложения. Используйте винительный падеж.</strong></p>
            <p style="color:var(--text-light);font-size:0.85rem;"><em>Модель:</em> Она вышла замуж за <u>итальянского футболиста</u> (итальянский футболист).</p>
            <div class="divider"></div>
            <div id="ex1Inputs">
                <div class="input-group"><label>1.</label><span class="sentence-context">Каждый год он покупает</span><input type="text" data-answer="новую машину" placeholder="новая машина" data-id="1"></div>
                <div class="input-group"><label>2.</label><span class="sentence-context">Я удивился, когда услышал</span><input type="text" data-answer="её игру" placeholder="её игра" data-id="2"></div>
                <div class="input-group"><label>3.</label><span class="sentence-context">В каком году ты окончил</span><input type="text" data-answer="университет" placeholder="университет" data-id="3"></div>
                <div class="input-group"><label>4.</label><span class="sentence-context">Вчера мы видели</span><input type="text" data-answer="нашего преподавателя" placeholder="наш преподаватель" data-id="4"></div>
                <div class="input-group"><label>5.</label><span class="sentence-context">Вы знаете</span><input type="text" data-answer="эту американскую писательницу" placeholder="эта американская писательница" data-id="5"></div>
                <div class="input-group"><label>6.</label><span class="sentence-context">Открой, пожалуйста,</span><input type="text" data-answer="дверь" placeholder="дверь" data-id="6"></div>
                <div class="input-group"><label>7.</label><span class="sentence-context">Когда я училась в школе, мы носили</span><input type="text" data-answer="школьную форму" placeholder="школьная форма" data-id="7"></div>
                <div class="input-group"><label>8.</label><span class="sentence-context">Она пригласила</span><input type="text" data-answer="её нового друга" placeholder="её новый друг" data-id="8"></div>
                <div class="input-group"><label>9.</label><span class="sentence-context">Я мечтаю поехать в</span><input type="text" data-answer="Латинскую Америку" placeholder="Латинская Америка" data-id="9"></div>
                <div class="input-group"><label>10.</label><span class="sentence-context">Моя сестра влюбилась в</span><input type="text" data-answer="известного писателя" placeholder="известный писатель" data-id="10"></div>
            </div>
            <div class="btn-group" style="margin-top:14px;">
                <button class="btn btn-check" onclick="checkExercise1()">✅ Проверить упражнение 1</button>
                <button class="btn btn-reset" onclick="resetExercise1()">🔄 Сбросить</button>
            </div>
            <div id="ex1Feedback" style="margin-top:8px;font-weight:600;"></div>
        </div>

        <!-- ============ РАБОТА С ИЛЛЮСТРАЦИЕЙ ============ -->
        <div class="section" id="illustrationSection">
            <h2><span class="emoji">🖼️</span> РАБОТА С ИЛЛЮСТРАЦИЕЙ</h2>
            <p><strong>Рассмотрите картинку. Что вы на ней видите?</strong></p>
            <p style="color:var(--text-light);"><em>Модель:</em> На картинке есть …</p>
            <img class="illustration-img" src="https://i.pinimg.com/736x/6b/e2/a3/6be2a3edde61d6f6e307f604e732b4e5.jpg" alt="Иллюстрация для обсуждения" loading="lazy">
            <p><strong>Ответьте на вопросы:</strong></p>
            <ul style="list-style:'🎵 ';padding-left:20px;color:var(--text);">
                <li>Есть ли на картинке большая гитара?</li>
                <li>Есть ли на картинке белая птица?</li>
                <li>Есть ли на картинке маленький мальчик?</li>
            </ul>
        </div>

        <!-- ============ ТЕКСТ ============ -->
        <div class="section" id="textSection">
            <h2><span class="emoji">📖</span> ТЕКСТ</h2>
            <p><strong>Прочитайте текст и выделите примеры родительного падежа.</strong></p>
            <p style="color:var(--text-light);">(Текст представлен ниже в разделе «Аудирование / Чтение» — ищите формы родительного падежа в ответах Елены, Натальи и Александра.)</p>
        </div>

        <!-- ============ ГРАММАТИКА ============ -->
        <div class="section" id="grammarSection">
            <h2><span class="emoji">📐</span> ГРАММАТИКА</h2>
            <h3>Родительный падеж (Gen/2) singular nouns and adjectives</h3>
            <p><strong>Родительный падеж = кого? чего?</strong></p>
            <img class="grammar-img" src="https://i.pinimg.com/736x/48/63/aa/4863aaa192b9058239f69be5648cd1e7.jpg" alt="The genitive case of singular nouns and adjectives" loading="lazy">
            <h3 style="margin-top:16px;">Слова-сигналы родительного падежа:</h3>
            <p><strong>нет</strong> + Gen/2 (нет времени) • <strong>без</strong> + Gen/2 (без учительницы) • <strong>у</strong> + Gen/2 (у подруги) • <strong>из</strong> + Gen/2 (из школы) • <strong>для</strong> + Gen/2 (для студента) • <strong>после</strong> + Gen/2 (после урока) • <strong>до</strong> + Gen/2 (до вечера) • <strong>во время</strong> + Gen/2 (во время перерыва)</p>
            <h3>Родительный падеж личных местоимений:</h3>
            <img class="grammar-img" src="https://i.pinimg.com/736x/7c/23/e3/7c23e329f93d07d517793ddbbcce78bc.jpg" alt="The genitive case of personal pronouns" loading="lazy">
            <p style="margin-top:8px;"><strong>Правило буквы «н» (после предлогов):</strong> у + он → у него • без + она → без неё • для + они → для них</p>
        </div>

        <!-- ============ УПРАЖНЕНИЕ 2 ============ -->
        <div class="section" id="ex2Section">
            <h2><span class="emoji">✏️</span> УПРАЖНЕНИЕ 2</h2>
            <p><strong>Прочитайте предложения 1-10. Нажмите на словосочетания в родительном падеже, чтобы выделить их.</strong></p>
            <p style="color:var(--text-light);font-size:0.85rem;">Кликните по выделенным фразам — они подсветятся. Правильные фразы отмечены зелёным.</p>
            <div class="divider"></div>
            <div id="ex2Sentences">
                <p><strong>1)</strong> Мой преподаватель <span class="clickable-phrase" data-phrase="из Нижнего Новгорода" data-correct="true">из Нижнего Новгорода</span>.</p>
                <p><strong>2)</strong> Я купил этот учебник <span class="clickable-phrase" data-phrase="для моего нового студента" data-correct="true">для моего нового студента</span>.</p>
                <p><strong>3)</strong> Это школа <span class="clickable-phrase" data-phrase="русского языка" data-correct="true">русского языка</span>. Мой преподаватель – <span class="clickable-phrase" data-phrase="носитель языка" data-correct="false">носитель языка</span>.</p>
                <p><strong>4)</strong> <span class="clickable-phrase" data-phrase="Во время обеденного перерыва" data-correct="true">Во время обеденного перерыва</span> он читает новости.</p>
                <p><strong>5)</strong> <span class="clickable-phrase" data-phrase="После рабочего дня" data-correct="true">После рабочего дня</span> они любят гулять в парке.</p>
                <p><strong>6)</strong> Мой дедушка работал <span class="clickable-phrase" data-phrase="до последнего дня своей жизни" data-correct="true">до последнего дня своей жизни</span>.</p>
                <p><strong>7)</strong> <span class="clickable-phrase" data-phrase="У меня" data-correct="true">У меня</span> <span class="clickable-phrase" data-phrase="нет свободного времени" data-correct="true">нет свободного времени</span>.</p>
                <p><strong>8)</strong> Мне не нравятся уроки <span class="clickable-phrase" data-phrase="без домашнего задания" data-correct="true">без домашнего задания</span>.</p>
                <p><strong>9)</strong> <span class="clickable-phrase" data-phrase="У моей хорошей подруги" data-correct="true">У моей хорошей подруги</span> есть свой книжный магазин.</p>
                <p><strong>10)</strong> Недалеко <span class="clickable-phrase" data-phrase="от нашего офиса" data-correct="true">от нашего офиса</span> находится прекрасный парк.</p>
            </div>
            <p style="margin-top:8px;font-size:0.8rem;color:var(--text-light);">🟡 Жёлтая подсветка = вы кликнули • 🟢 Зелёная = правильное словосочетание в род. падеже • ⚪ Без подсветки = не род. падеж (кликните чтобы проверить)</p>
            <button class="btn btn-reset" style="margin-top:8px;" onclick="resetExercise2()">🔄 Сбросить выделение</button>
        </div>

        <!-- ============ УПРАЖНЕНИЕ 3 ============ -->
        <div class="section" id="ex3Section">
            <h2><span class="emoji">✏️</span> УПРАЖНЕНИЕ 3</h2>
            <p><strong>Вставьте пропущенные слова в правильной форме.</strong></p>
            <p style="color:var(--text-light);font-size:0.85rem;"><em>Слова для справки:</em> литература, аттестат, тихий час, иностранный язык, информатика, предмет, воспитательница, отличница, частная школа, голос, золотая медаль, пение</p>
            <div class="divider"></div>
            <div id="ex3Inputs">
                <div class="input-group"><label>1.</label><span class="sentence-context">В японском детском саду нет</span><input type="text" data-answer="тихий час" placeholder="тихий час" data-id="1">, дети днём не спят.</div>
                <div class="input-group"><label>2.</label><span class="sentence-context">Я иногда встречаю свою</span><input type="text" data-answer="воспитательницу" placeholder="воспитательница" data-id="2"> из детского сада.</div>
                <div class="input-group"><label>3.</label><span class="sentence-context">Я ходил в государственную школу, а мой друг – в</span><input type="text" data-answer="частную школу" placeholder="частная школа" data-id="3">.</div>
                <div class="input-group"><label>4.</label><span class="sentence-context">Чтобы получить</span><input type="text" data-answer="золотую медаль" placeholder="золотая медаль" data-id="4">, необходимо знать все предметы на «отлично».</div>
                <div class="input-group"><label>5.</label><span class="sentence-context">Мой любимый предмет –</span><input type="text" data-answer="литература" placeholder="литература" data-id="5">, поэтому я расскажу о русских писателях.</div>
                <div class="input-group"><label>6.</label><span class="sentence-context">Какой</span><input type="text" data-answer="предмет" placeholder="предмет" data-id="6"> вы преподаёте? – Математику.</div>
                <div class="input-group"><label>7.</label><span class="sentence-context">Мой брат так любил</span><input type="text" data-answer="информатику" placeholder="информатика" data-id="7">, что стал программистом.</div>
                <div class="input-group"><label>8.</label><span class="sentence-context">Я умею красиво петь, поэтому</span><input type="text" data-answer="пение" placeholder="пение" data-id="8"> было любимым предметом.</div>
                <div class="input-group"><label>9.</label><span class="sentence-context">В каком классе начинают изучать второй</span><input type="text" data-answer="иностранный язык" placeholder="иностранный язык" data-id="9">?</div>
                <div class="input-group"><label>10.</label><span class="sentence-context">Школьники сдают экзамены в июне и получают</span><input type="text" data-answer="аттестат" placeholder="аттестат" data-id="10">.</div>
                <div class="input-group"><label>11.</label><span class="sentence-context">С твоим прекрасным</span><input type="text" data-answer="голосом" placeholder="голос" data-id="11"> ты можешь сделать карьеру певицы.</div>
                <div class="input-group"><label>12.</label><span class="sentence-context">В нашем классе была только одна</span><input type="text" data-answer="отличница" placeholder="отличница" data-id="12">, она знала все предметы.</div>
            </div>
            <div class="btn-group" style="margin-top:14px;">
                <button class="btn btn-check" onclick="checkExercise3()">✅ Проверить упражнение 3</button>
                <button class="btn btn-reset" onclick="resetExercise3()">🔄 Сбросить</button>
            </div>
            <div id="ex3Feedback" style="margin-top:8px;font-weight:600;"></div>
        </div>

        <!-- ============ АУДИРОВАНИЕ / ЧТЕНИЕ + КАРТОЧКА ============ -->
        <div class="section" id="readingSection">
            <h2><span class="emoji">👂📖</span> АУДИРОВАНИЕ / ЧТЕНИЕ</h2>
            <p><strong>Прослушайте интервью и запишите ответы в таблицу.</strong></p>

            <h3>Текст для чтения:</h3>
            <div style="background:#fdfaf5;border-radius:var(--radius-sm);padding:16px;margin:8px 0;font-size:0.9rem;line-height:1.5;">
                <p><strong>Елена</strong></p>
                <p>1. <em>Вам нравилось ходить в школу?</em> Да, у меня ни разу не было большого желания пропускать школу. Я была отличницей, и у меня не было даже малейших проблем с домашними заданиями.</p>
                <p>2. <em>Без какого предмета вы не представляли школу?</em> Я не представляла школу без уроков литературы. А ещё я не могла обойтись без английского языка.</p>
                <p>3. <em>Вы помните свою первую учительницу?</em> Да, без неё мои школьные годы были бы другими. У неё не было строгости, но было много терпения.</p>
                <p>4. <em>Чего вам не хватало в школе?</em> Мне не хватало дополнительных занятий по английскому языку.</p>
                <p style="margin-top:8px;"><strong>Наталья</strong></p>
                <p>1. <em>У вас было чувство страха перед школой?</em> Нет, у меня не было никакого страха. Наоборот, я ждала каждого урока с нетерпением.</p>
                <p>2. <em>Каких предметов у вас не было?</em> У нас не было ритмики и театрального искусства. Но после школы я пошла в актёрский ВУЗ.</p>
                <p>3. <em>Без кого вы не представляете школьные годы?</em> Без нашей учительницы истории. У неё не было семьи, но было много учеников.</p>
                <p>4. <em>Чего не хватало для счастья?</em> Мне не хватало интересных уроков физики.</p>
                <p style="margin-top:8px;"><strong>Александр</strong></p>
                <p>1. <em>У вас был энтузиазм ходить в школу?</em> В первом классе – да. А с пятого класса у меня не было никаких сил рано вставать.</p>
                <p>2. <em>Каких предметов не хватало?</em> Мне не хватало рисования и физкультуры. Потом появилась любовь к химии, физике и математике.</p>
                <p>3. <em>Вы помните первую учительницу?</em> Я помню её улыбку. У неё не было плохого настроения.</p>
                <p>4. <em>Без чего не можете представить школу?</em> Без больших перемен и друзей.</p>
            </div>

            <h3>📋 КАРТОЧКА К ТЕКСТУ</h3>
            <table id="cardTable">
                <thead>
                    <tr><th>Имя</th><th>Нравилась ли школа?</th><th>Без кого/чего не представлял(а)?</th><th>Чего не хватало?</th></tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Елена</strong></td>
                        <td><input type="text" data-answer="Да, нравилось" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="уроков литературы и английского" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="дополнительных занятий по английскому" placeholder="Ответ..."></td>
                    </tr>
                    <tr>
                        <td><strong>Наталья</strong></td>
                        <td><input type="text" data-answer="Да, ждала уроки" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="учительницы истории" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="интересных уроков физики" placeholder="Ответ..."></td>
                    </tr>
                    <tr>
                        <td><strong>Александр</strong></td>
                        <td><input type="text" data-answer="В 1 классе да, с 5 нет" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="больших перемен и друзей" placeholder="Ответ..."></td>
                        <td><input type="text" data-answer="рисования и физкультуры" placeholder="Ответ..."></td>
                    </tr>
                </tbody>
            </table>
            <div class="btn-group" style="margin-top:10px;">
                <button class="btn btn-check" onclick="checkCardTable()">✅ Проверить карточку</button>
                <button class="btn btn-reset" onclick="resetCardTable()">🔄 Сбросить</button>
            </div>
            <div id="cardFeedback" style="margin-top:8px;font-weight:600;"></div>
        </div>

        <!-- ============ ПРОВЕРКА "ПРАВДА ИЛИ ЛОЖЬ" ============ -->
        <div class="section" id="truthSection">
            <h2><span class="emoji">✅</span> ПРОВЕРКА «ПРАВДА ИЛИ ЛОЖЬ»</h2>
            <p><strong>Прочитайте утверждения. Выберите «Правда» или «Ложь» для каждого.</strong></p>

            <h3>Вариант 1</h3>
            <div id="truthVariant1">
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>1.</strong> У Елены было большое желание пропускать школу.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',0)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',0)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>2.</strong> Елена была отличницей, и у неё не было проблем с домашними заданиями.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',1)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',1)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>3.</strong> Елена не представляла школу без уроков литературы.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',2)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',2)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>4.</strong> У первой учительницы Елены была строгость.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',3)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',3)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>5.</strong> У Натальи был страх перед школой.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',4)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',4)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>6.</strong> У Натальи в расписании были ритмика и театральное искусство.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',5)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',5)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>7.</strong> Наталья пошла учиться в актёрский ВУЗ после школы.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',6)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',6)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>8.</strong> Александр всегда любил рано вставать в школу.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant1',7)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant1',7)">Ложь</button>
                </div>
            </div>
            <button class="btn btn-check" style="margin-top:8px;" onclick="checkTruth('truthVariant1', 8)">✅ Проверить Вариант 1</button>

            <h3 style="margin-top:20px;">Вариант 2</h3>
            <div id="truthVariant2">
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>1.</strong> Елена ни разу не хотела пропускать школу.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',0)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',0)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>2.</strong> Елена могла обойтись без английского языка.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',1)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',1)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>3.</strong> У первой учительницы Елены было много терпения.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',2)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',2)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>4.</strong> Наталья ждала каждый урок со страхом.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',3)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',3)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>5.</strong> Учитель истории Натальи не имела семьи, но её любили ученики.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',4)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',4)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>6.</strong> Александру не хватало рисования и физкультуры.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',5)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',5)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="true" style="margin-bottom:10px;">
                    <p><strong>7.</strong> Александр помнит улыбку своей первой учительницы.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',6)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',6)">Ложь</button>
                </div>
                <div class="truth-item" data-correct="false" style="margin-bottom:10px;">
                    <p><strong>8.</strong> У первой учительницы Александра было плохое настроение.</p>
                    <button class="btn-truth" data-choice="true" onclick="selectTruth(this,'truthVariant2',7)">Правда</button>
                    <button class="btn-truth" data-choice="false" onclick="selectTruth(this,'truthVariant2',7)">Ложь</button>
                </div>
            </div>
            <button class="btn btn-check" style="margin-top:8px;" onclick="checkTruth('truthVariant2', 8)">✅ Проверить Вариант 2</button>
            <div id="truthFeedback" style="margin-top:10px;font-weight:600;"></div>
        </div>

        <!-- ============ РАЗДАТОЧНЫЙ МАТЕРИАЛ ============ -->
        <div class="section" id="handoutSection">
            <h2><span class="emoji">📄</span> РАЗДАТОЧНЫЙ МАТЕРИАЛ</h2>
            <p><strong>Родительный падеж — дополните окончания:</strong></p>
            <h3>Вариант 1</h3>
            <p>1) Это тропические фрукты из Южн<strong>ой</strong> Америк<strong>и</strong>.</p>
            <p>2) У мо<strong>ей</strong> хорош<strong>ей</strong> подруг<strong>и</strong> скоро свадьба.</p>
            <p>3) В нашем городе нет част<strong>ных</strong> школ<strong>ы</strong>.</p>
            <h3>Вариант 2</h3>
            <p>1) Как ты отдыхаешь после рабоч<strong>ей</strong> недел<strong>и</strong>?</p>
            <p>2) У вас нет русск<strong>ого</strong> словар<strong>я</strong>?</p>
            <p>3) Желаю всем спокойн<strong>ой</strong> ноч<strong>и</strong>!</p>
        </div>

    </div><!-- end main-container -->

    <script>
        // ============ GLOBAL STATE ============
        const TOTAL_POSSIBLE = 46; // Ex1:10 + Ex3:12 + Card:9 + Truth1:8 + Truth2:8 - card is bonus, let's count: 10+12+8+8=38 + card 9 = 47. Let me set 46.
        // Actually: Ex1=10, Ex3=12, Truth1=8, Truth2=8, Card=9 → total 47. I'll use 47.
        const TOTAL_POSSIBLE_FINAL = 47;
        document.getElementById('scoreTotal').textContent = TOTAL_POSSIBLE_FINAL;

        let scores = {
            ex1: 0,
            ex3: 0,
            card: 0,
            truth1: 0,
            truth2: 0,
        };
        let maxScores = {
            ex1: 10,
            ex3: 12,
            card: 9,
            truth1: 8,
            truth2: 8,
        };
        let checkedSections = {
            ex1: false,
            ex3: false,
            card: false,
            truth1: false,
            truth2: false,
        };
        let truthSelections = {
            truthVariant1: [null, null, null, null, null, null, null, null],
            truthVariant2: [null, null, null, null, null, null, null, null],
        };

        function getTotalEarned() {
            return scores.ex1 + scores.ex3 + scores.card + scores.truth1 + scores.truth2;
        }

        function updateScoreDisplay(animate = false) {
            const total = getTotalEarned();
            document.getElementById('scoreEarned').textContent = total;
            const percent = Math.round((total / TOTAL_POSSIBLE_FINAL) * 100);
            document.getElementById('scorePercent').textContent = percent + '%';
            const circle = document.getElementById('scoreCircle');
            if (animate && total > 0) {
                circle.classList.add('pulse');
                setTimeout(() => circle.classList.remove('pulse'), 700);
            }
            // Update progress dots
            const dots = document.querySelectorAll('.progress-dot');
            dots.forEach(dot => {
                const ex = dot.getAttribute('data-ex');
                if (ex === 'ex1' && checkedSections.ex1) dot.classList.add('done');
                if (ex === 'ex3' && checkedSections.ex3) dot.classList.add('done');
                if (ex === 'truth1' && checkedSections.truth1) dot.classList.add('done');
                if (ex === 'truth2' && checkedSections.truth2) dot.classList.add('done');
            });
        }

        function showToast(message, type = '') {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.className = 'toast ' + type + ' show';
            setTimeout(() => {
                toast.className = 'toast';
            }, 2200);
        }

        function normalizeAnswer(str) {
            return str.trim().replace(/\s+/g, ' ').toLowerCase();
        }

        // ============ EXERCISE 1 ============
        function checkExercise1() {
            const inputs = document.querySelectorAll('#ex1Inputs input[type="text"]');
            let correctCount = 0;
            inputs.forEach(input => {
                const userAnswer = normalizeAnswer(input.value);
                const correctAnswer = normalizeAnswer(input.getAttribute('data-answer'));
                input.classList.remove('correct-input', 'incorrect-input');
                if (userAnswer === correctAnswer && userAnswer !== '') {
                    input.classList.add('correct-input');
                    correctCount++;
                } else {
                    input.classList.add('incorrect-input');
                }
            });
            scores.ex1 = correctCount;
            checkedSections.ex1 = true;
            updateScoreDisplay(true);
            const fb = document.getElementById('ex1Feedback');
            fb.textContent = `Результат: ${correctCount} / ${maxScores.ex1} правильно.`;
            fb.style.color = correctCount === maxScores.ex1 ? '#2e7d32' : '#c62828';
            if (correctCount === maxScores.ex1) {
                showToast('🎉 Упражнение 1 — всё верно!', 'success');
            } else {
                showToast(`📝 Упражнение 1: ${correctCount}/${maxScores.ex1}`, 'warning');
            }
        }

        function resetExercise1() {
            const inputs = document.querySelectorAll('#ex1Inputs input[type="text"]');
            inputs.forEach(input => {
                input.value = '';
                input.classList.remove('correct-input', 'incorrect-input');
            });
            scores.ex1 = 0;
            checkedSections.ex1 = false;
            document.getElementById('ex1Feedback').textContent = '';
            updateScoreDisplay();
            document.querySelector('.progress-dot[data-ex="ex1"]').classList.remove('done');
        }

        // ============ EXERCISE 2 (clickable phrases) ============
        document.querySelectorAll('#ex2Sentences .clickable-phrase').forEach(phrase => {
            phrase.addEventListener('click', function() {
                if (this.classList.contains('found-correct')) {
                    this.classList.remove('found-correct');
                    this.classList.add('highlighted');
                } else if (this.classList.contains('highlighted')) {
                    this.classList.remove('highlighted');
                } else {
                    const isCorrect = this.getAttribute('data-correct') === 'true';
                    if (isCorrect) {
                        this.classList.add('found-correct');
                        this.classList.remove('highlighted');
                    } else {
                        this.classList.add('highlighted');
                    }
                }
            });
        });

        function resetExercise2() {
            document.querySelectorAll('#ex2Sentences .clickable-phrase').forEach(phrase => {
                phrase.classList.remove('highlighted', 'found-correct');
            });
        }

        // ============ EXERCISE 3 ============
        function checkExercise3() {
            const inputs = document.querySelectorAll('#ex3Inputs input[type="text"]');
            let correctCount = 0;
            inputs.forEach(input => {
                const userAnswer = normalizeAnswer(input.value);
                const correctAnswer = normalizeAnswer(input.getAttribute('data-answer'));
                input.classList.remove('correct-input', 'incorrect-input');
                if (userAnswer === correctAnswer && userAnswer !== '') {
                    input.classList.add('correct-input');
                    correctCount++;
                } else {
                    input.classList.add('incorrect-input');
                }
            });
            scores.ex3 = correctCount;
            checkedSections.ex3 = true;
            updateScoreDisplay(true);
            const fb = document.getElementById('ex3Feedback');
            fb.textContent = `Результат: ${correctCount} / ${maxScores.ex3} правильно.`;
            fb.style.color = correctCount === maxScores.ex3 ? '#2e7d32' : '#c62828';
            if (correctCount === maxScores.ex3) {
                showToast('🎉 Упражнение 3 — всё верно!', 'success');
            } else {
                showToast(`📝 Упражнение 3: ${correctCount}/${maxScores.ex3}`, 'warning');
            }
        }

        function resetExercise3() {
            const inputs = document.querySelectorAll('#ex3Inputs input[type="text"]');
            inputs.forEach(input => {
                input.value = '';
                input.classList.remove('correct-input', 'incorrect-input');
            });
            scores.ex3 = 0;
            checkedSections.ex3 = false;
            document.getElementById('ex3Feedback').textContent = '';
            updateScoreDisplay();
            document.querySelector('.progress-dot[data-ex="ex3"]').classList.remove('done');
        }

        // ============ CARD TABLE ============
        function checkCardTable() {
            const inputs = document.querySelectorAll('#cardTable input[type="text"]');
            let correctCount = 0;
            inputs.forEach(input => {
                const userAnswer = normalizeAnswer(input.value);
                const correctAnswer = normalizeAnswer(input.getAttribute('data-answer'));
                input.classList.remove('correct-input', 'incorrect-input');
                // For card, be a bit more flexible - check if user answer contains key parts
                const correctWords = correctAnswer.split(' ');
                const userWords = userAnswer.split(' ');
                let matchCount = 0;
                correctWords.forEach(cw => {
                    if (userWords.some(uw => uw.includes(cw) || cw.includes(uw))) matchCount++;
                });
                const isClose = matchCount >= Math.max(1, Math.floor(correctWords.length * 0.5));
                if (isClose && userAnswer.length > 2) {
                    input.classList.add('correct-input');
                    correctCount++;
                } else if (userAnswer === correctAnswer) {
                    input.classList.add('correct-input');
                    correctCount++;
                } else {
                    input.classList.add('incorrect-input');
                }
            });
            // Re-evaluate with exact match for cleaner scoring
            correctCount = 0;
            inputs.forEach(input => {
                const userAnswer = normalizeAnswer(input.value);
                const correctAnswer = normalizeAnswer(input.getAttribute('data-answer'));
                input.classList.remove('correct-input', 'incorrect-input');
                if (userAnswer === correctAnswer && userAnswer !== '') {
                    input.classList.add('correct-input');
                    correctCount++;
                } else if (userAnswer.length > 2 && correctAnswer.includes(userAnswer)) {
                    input.classList.add('correct-input');
                    correctCount++;
                } else if (userAnswer.length > 3 && userAnswer.includes(correctAnswer.substring(0, Math.floor(
                        correctAnswer.length * 0.6)))) {
                    input.classList.add('correct-input');
                    correctCount++;
                } else {
                    input.classList.add('incorrect-input');
                }
            });
            scores.card = Math.min(correctCount, maxScores.card);
            checkedSections.card = true;
            updateScoreDisplay(true);
            const fb = document.getElementById('cardFeedback');
            fb.textContent = `Результат: ${scores.card} / ${maxScores.card} примерно правильно.`;
            fb.style.color = scores.card >= 7 ? '#2e7d32' : '#c62828';
            if (scores.card >= 8) {
                showToast('🎉 Карточка заполнена отлично!', 'success');
            }
        }

        function resetCardTable() {
            const inputs = document.querySelectorAll('#cardTable input[type="text"]');
            inputs.forEach(input => {
                input.value = '';
                input.classList.remove('correct-input', 'incorrect-input');
            });
            scores.card = 0;
            checkedSections.card = false;
            document.getElementById('cardFeedback').textContent = '';
            updateScoreDisplay();
        }

        // ============ TRUTH / LIE ============
        function selectTruth(button, variantId, index) {
            const parent = button.parentElement;
            const allBtns = parent.querySelectorAll('.btn-truth');
            allBtns.forEach(b => {
                b.classList.remove('selected-true', 'selected-false', 'correct-choice',
                'incorrect-choice');
            });
            const choice = button.getAttribute('data-choice') === 'true';
            if (choice) {
                button.classList.add('selected-true');
            } else {
                button.classList.add('selected-false');
            }
            truthSelections[variantId][index] = choice;
        }

        function checkTruth(variantId, totalItems) {
            const container = document.getElementById(variantId);
            const items = container.querySelectorAll('.truth-item');
            let correctCount = 0;
            items.forEach((item, index) => {
                const correctAnswer = item.getAttribute('data-correct') === 'true';
                const userChoice = truthSelections[variantId][index];
                const allBtns = item.querySelectorAll('.btn-truth');
                allBtns.forEach(b => {
                    b.classList.remove('correct-choice', 'incorrect-choice',
                        'selected-true', 'selected-false');
                });
                if (userChoice === null) {
                    // No selection made
                    return;
                }
                if (userChoice === correctAnswer) {
                    correctCount++;
                    // Highlight the correct button
                    item.querySelectorAll('.btn-truth').forEach(b => {
                        if ((b.getAttribute('data-choice') === 'true') === correctAnswer) {
                            b.classList.add('correct-choice');
                        }
                    });
                } else {
                    // Highlight both: the wrong choice and the correct one
                    item.querySelectorAll('.btn-truth').forEach(b => {
                        const bChoice = b.getAttribute('data-choice') === 'true';
                        if (bChoice === userChoice) {
                            b.classList.add('incorrect-choice');
                        }
                        if (bChoice === correctAnswer) {
                            b.classList.add('correct-choice');
                        }
                    });
                }
            });
            if (variantId === 'truthVariant1') {
                scores.truth1 = correctCount;
                checkedSections.truth1 = true;
            } else {
                scores.truth2 = correctCount;
                checkedSections.truth2 = true;
            }
            updateScoreDisplay(true);
            const fb = document.getElementById('truthFeedback');
            const totalTruth = scores.truth1 + scores.truth2;
            const maxTruth = maxScores.truth1 + maxScores.truth2;
            fb.textContent =
                `Результат: ${variantId === 'truthVariant1' ? 'Вариант 1' : 'Вариант 2'}: ${correctCount}/${totalItems}. Всего по правда/ложь: ${totalTruth}/${maxTruth}.`;
            fb.style.color = correctCount === totalItems ? '#2e7d32' : '#c62828';
            if (correctCount === totalItems) {
                showToast('🎉 Все утверждения верны!', 'success');
            }
        }

        // ============ INITIAL SETUP ============
        updateScoreDisplay();

        // Add scroll effect to score bar
        window.addEventListener('scroll', () => {
            const bar = document.getElementById('scoreBar');
            if (window.scrollY > 30) {
                bar.classList.add('scrolled');
            } else {
                bar.classList.remove('scrolled');
            }
        });

        // ============ KEYBOARD SUPPORT ============
        document.addEventListener('keydown', function(e) {
            if (e.ctrlKey && e.key === 'Enter') {
                // Check all visible exercises
                checkExercise1();
                checkExercise3();
                checkCardTable();
                checkTruth('truthVariant1', 8);
                checkTruth('truthVariant2', 8);
                showToast('🚀 Все задания проверены!', 'success');
            }
        });

        console.log('📚 Рабочий лист "Образование" готов!');
        console.log('💡 Подсказка: нажмите Ctrl+Enter чтобы проверить все задания сразу.');
        console.log('🎯 Всего баллов можно набрать: ' + TOTAL_POSSIBLE_FINAL);
        console.log('✏️ Упражнение 1: 10 баллов | Упражнение 3: 12 баллов | Карточка: 9 баллов | Правда/Ложь: 16 баллов');
    </script>
</body>
</html>
