<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tes Matematika</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@500;700&display=swap" rel="stylesheet">
    <style>
        .math-body {
            font-family: 'Nunito', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
            color: #000 !important;
        }
        .math-container-quiz {
            max-width: 100%;
            margin: 0 auto;
            padding: 0px;
            background-color: white;
            position: relative;
            font-family: 'Nunito', sans-serif;
        }
        .math-h2, .math-h3, .math-p, .math-div, .math-span, .math-button {
            color: #000 !important;
            font-family: 'Nunito', sans-serif;
        }
        .math-h2 {
            margin: 5px 0;
            font-size: 18px;
            font-family: 'Nunito', sans-serif;
            margin-bottom: 15px;
        }
        .math-h3 {
            margin: 10px 0;
            font-size: 16px;
            font-family: 'Nunito', sans-serif;
        }
        .math-progress {
            margin: 10px 0;
            font-size: 14px;
            font-family: 'Nunito', sans-serif;
            color: #000;
        }

        /* Dropdown Menu Styles */
        .math-dropdown-menu {
            position: relative;
            margin: auto;
            width: 100%;
            font-family: 'Nunito', sans-serif;
          	color: #000;
        }
        .math-dropdown-toggle {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px 13px;
            border-radius: 5px;
            background-color: white;
            border: 2px solid #1976D2;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            font-weight: 500;
            font-size: 14px;
            width: 100%;
            box-sizing: border-box;
            text-align: left;
        }
        .math-dropdown-toggle i.fa-chevron-down {
            margin-left: 10px;
            transition: transform 0.3s;
        }
        .math-dropdown-toggle.active i.fa-chevron-down {
            transform: rotate(180deg);
        }
        .math-dropdown-toggle::after {
            display: none;
        }
        .math-dropdown-content {
            display: none;
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background-color: white;
            border: 1px solid #ddd;
            border-top: none;
            border-radius: 0 0 5px 5px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            z-index: 10;
            font-family: 'Nunito', sans-serif;
        }
        .math-dropdown-content.show {
            display: block;
        }
        .math-dropdown-item {
            padding: 10px 13px;
            cursor: pointer;
            transition: background-color 0.3s;
            border-bottom: 1px solid #eee;
            font-family: 'Nunito', sans-serif;
        }
        .math-dropdown-item:last-child {
            border-bottom: none;
        }
        .math-dropdown-item:hover {
            background-color: #f5f5f5;
        }
        .math-dropdown-item.active {
            background-color: #E3F2FD;
            font-weight: 500;
        }

        /* Question Navigation Toggle */
        .math-question-nav-toggle {
            position: relative;
            margin-bottom: 15px;
            width: 100%;
            font-family: 'Nunito', sans-serif;
        }
        .math-question-nav-btn {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px 13px;
            border-radius: 8px;
            background: linear-gradient(135deg, #1976D2 0%, #2196F3 50%, #42A5F5 100%);
            border: none;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            font-weight: 500;
            font-size: 14px;
            width: 100%;
            box-sizing: border-box;
            text-align: left;
            color: white !important;
        }
        .math-question-nav-btn i.fa-chevron-down {
            margin-left: 10px;
            transition: transform 0.3s;
        }
        .math-question-nav-btn.active i.fa-chevron-down {
            transform: rotate(180deg);
        }
        .math-question-nav-container {
            display: none;
            margin-top: 10px;
            transition: all 0.3s ease;
        }
        .math-question-nav-container.show {
            display: block;
        }

        /* Start Screen Styles */
        .math-start-screen {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            text-align: center;
            font-family: 'Nunito', sans-serif;
            color: #000;
        }
        .math-start-screen h1 {
            color: #1976D2 !important;
            margin-bottom: 20px;
            font-size: 24px;
            font-family: 'Nunito', sans-serif;
        }
        .math-instructions {
            text-align: justify;
            margin-bottom: 30px;
            font-family: 'Nunito', sans-serif;
        }
        .math-instructions ol {
            padding-left: 20px;
            font-family: 'Nunito', sans-serif;
        }
        .math-instructions li {
            margin-bottom: 10px;
            font-family: 'Nunito', sans-serif;
        }
        .math-bullet-points {
            list-style-type: none;
            padding-left: 0;
            font-family: 'Nunito', sans-serif;
        }
        .math-bullet-points li {
            margin-bottom: auto;
            font-family: 'Nunito', sans-serif;
        }
        .math-bullet-points span {
            margin-right: 4px;
            font-size: 18px;
        }
        .math-btn-start {
            background-color: #1976D2;
            color: white !important;
            padding: 12px 30px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            font-weight: 500;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: all 0.3s;
        }
        .math-btn-start:hover {
            background-color: #1565C0;
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.2);
        }

        /* Quiz Elements (initially hidden) */
        .math-quiz-elements {
            display: none;
            font-family: 'Nunito', sans-serif;
        }

        /* Question Navigation */
        .math-question-nav {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            margin: 0 0 20px 0;
            font-family: 'Nunito', sans-serif;
            animation: fadeInDown 0.5s ease-out;
        }

        /* Keyframe untuk animasi fade in down - muncul dari atas */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px); /* Negatif untuk mulai dari atas */
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .math-question-nav button {
            width: 40px;
            height: 40px;
            border: 2px solid #ddd;
            background-color: white;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
            font-family: 'Nunito', sans-serif;
            font-weight: 500;
            position: relative;
            color: #000 !important;
        }
        .math-question-nav button.active {
            border: 2px solid #1976D2;
            box-shadow: 0 0 0 2px rgba(25, 118, 210, 0.3);
        }
        .math-question-nav button.answered {
            background-color: #2196F3;
            color: white !important;
            border-color: #00838F;
        }
        .math-question-nav button.marked {
            background-color: #FFC107;
            color: #000 !important;
            border-color: #FFA000;
        }
        .math-question-nav button.correct {
            background-color: #4CAF50;
            color: white !important;
            border-color: #2E7D32;
        }
        .math-question-nav button.wrong {
            background-color: #f44336;
            color: white !important;
            border-color: #d32f2f;
        }

        /* Question Container */
        .math-question-container {
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-bottom: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            background-color: white;
            position: relative;
            text-align: justify;
            font-family: 'Nunito', sans-serif;
            overflow: hidden; /* Untuk memastikan border-radius pada header */
        }
        
        /* Header dengan background gradasi biru */
        .math-question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background: linear-gradient(135deg, #1976D2 0%, #2196F3 50%, #42A5F5 100%);
            margin: 0; /* Hilangkan margin */
            position: relative;
        }
        
        /* Nomor soal dengan teks putih */
        .math-question-number {
            font-weight: bold;
            font-size: 16px;
            color: white !important; /* Teks putih */
            font-family: 'Nunito', sans-serif;
            margin: 0;
            padding: 0;
        }
        
        /* Hapus pseudo-element ::after */
        .math-question-number::after {
            display: none;
        }
        
        /* Tombol ragu dengan teks putih */
        .math-btn-mark {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 5px;
            color: white !important; /* Teks putih */
            padding: 8px 12px;
            border-radius: 4px;
            font-family: 'Nunito', sans-serif;
            transition: all 0.3s;
        }
        
        /* Hapus pseudo-element ::after untuk tombol mark */
        .math-btn-mark::after {
            display: none;
        }
        
        .math-btn-mark:hover {
            background: rgba(255, 255, 255, 0.3);
            border-color: rgba(255, 255, 255, 0.5);
        }
        
        .math-btn-mark.marked {
            background: rgba(255, 193, 7, 0.9);
            color: #000 !important; /* Teks hitam saat marked */
            border-color: #FFA000;
            font-weight: 500;
        }
        
        .math-btn-mark i {
            font-size: 15px;
        }
        
        /* Konten soal dengan padding */
        .math-question-text {
            margin: 0;
            padding: 20px 15px 15px 15px; /* Top padding lebih besar */
            line-height: 1.5;
            font-family: 'Nunito', sans-serif;
          	color: #000;
        }

        /* Options */
        .math-options {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin: 0;
            padding: 0 15px 15px 15px; /* Padding samping dan bawah */
            font-family: 'Nunito', sans-serif;
        }
        .math-option {
            display: flex;
            align-items: center;
            padding: 12px;
            border-radius: 8px;
            cursor: pointer;
            border: 1px solid #ddd;
            transition: all 0.3s;
            background-color: white;
            position: relative;
            color: #000 !important;
            font-family: 'Nunito', sans-serif;
        }
        .math-option-letter {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 24px;
            height: 24px;
            border-radius: 4px;
            background-color: #f0f0f0;
            margin-right: 12px;
            font-weight: 500;
            flex-shrink: 0;
            color: #000 !important;
            font-family: 'Nunito', sans-serif;
        }
        .math-option-text {
            flex-grow: 1;
            font-family: 'Nunito', sans-serif;
        }
        .math-option:hover {
            background-color: #f5f5f5;
        }
        .math-option:hover .math-option-letter {
            background-color: #e0e0e0;
        }
        .math-option.selected {
            background-color: #e3f2fd;
            border-left: 3px solid #2196F3;
        }
        .math-option.selected .math-option-letter {
            background-color: #2196F3;
            color: white !important;
        }
        .math-option.correct {
            background-color: #E8F5E9;
            border-left: 3px solid #4CAF50;
        }
        .math-option.correct .math-option-letter {
            background-color: #4CAF50;
            color: white !important;
        }
        .math-option.wrong {
            background-color: #FFEBEE;
            border-left: 3px solid #f44336;
        }
        .math-option.wrong .math-option-letter {
            background-color: #f44336;
            color: white !important;
        }
        .math-option.partially-correct {
            background-color: #FFF8E1;
            border-left: 3px solid #FFC107;
        }
        .math-option.partially-correct .math-option-letter {
            background-color: #FFC107;
            color: white !important;
        }

        /* Short Answer Input - PERBAIKAN UTAMA */
        .math-short-answer-input {
            width: calc(100% - 30px); /* Kurangi lebar dengan total padding kiri-kanan */
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-family: 'Nunito', sans-serif;
            margin: 10px 15px 15px 15px; /* Margin tetap sama */
            box-sizing: border-box;
        }
        .math-short-answer-input:focus {
            outline: none;
            border-color: #00ACC1;
            box-shadow: 0 0 0 2px rgba(0, 172, 193, 0.2);
        }

        /* Matching Question Styles */
        .math-matching-container {
            display: flex;
            flex-direction: column;
            gap: 1px; /* awalnya 10px */
            margin: 15px;
            font-family: 'Nunito', sans-serif;
            color: black;
        }
        .math-matching-row {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .math-matching-left {
            flex: 1;
            padding: 8px;
            font-weight: 500;
        }
        .math-matching-select {
            flex: 1;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            background-color: white;
            font-family: 'Nunito', sans-serif;
        }
        .math-matching-select:disabled {
            background-color: #f5f5f5;
        }
        .math-matching-select.correct {
            background-color: #E8F5E9;
            border-color: #4CAF50;
        }
        .math-matching-select.wrong {
            background-color: #FFEBEE;
            border-color: #f44336;
        }

        /* Navigation */
        .math-navigation {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 20px;
            font-family: 'Nunito', sans-serif;
        }
        .math-nav-buttons {
            display: flex;
            gap: 10px;
            width: 100%;
        }
        .math-nav-buttons button {
            flex: 1;
            min-width: 150px;
            white-space: nowrap;
            padding: 12px 5px;
            text-align: center;
            font-family: 'Nunito', sans-serif;
        }
        .math-submit-container {
            width: 100%;
        }
        .math-navigation button {
            padding: 12px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            font-weight: 500;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .math-btn-prev, .math-btn-next {
            background-color: #e0e0e0;
            transition: all 0.3s;
            color: #000 !important;
            font-family: 'Nunito', sans-serif;
        }
        .math-btn-prev:hover, .math-btn-next:hover {
            background-color: #d0d0d0;
            box-shadow: 0 2px 6px rgba(0,0,0,0.15);
        }
        .math-btn-submit {
            background-color: #f44336;
            color: white !important;
            padding: 12px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            box-shadow: 0 2px 4px rgba(0,0,0,0.2);
            width: 100%;
            font-family: 'Nunito', sans-serif;
        }

        /* Timer */
        .math-timer-box {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: white;
            color: black !important;
            box-shadow: 0 8px 16px rgba(0,0,0,0.1);
            padding: 10px 15px;
            border-radius: 5px;
            border: none;
            font-weight: bold;
            z-index: 100;
            display: flex;
            align-items: center;
            gap: 8px;
            font-family: 'Nunito', sans-serif;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        .math-timer-emoji {
            font-size: 18px;
          	color: #1976D2 !important;
        }
        .math-time-up {
            color: #f44336 !important;
            font-weight: bold;
        }

        /* Submit Confirmation */
        .math-submit-confirm {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            justify-content: center;
            align-items: center;
            z-index: 1000;
            font-family: 'Nunito', sans-serif;
        }
        .math-submit-dialog {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            max-width: 400px;
            text-align: center;
            font-family: 'Nunito', sans-serif;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }
        .math-dialog-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 20px;
        }
        .math-dialog-buttons button {
            padding: 8px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-family: 'Nunito', sans-serif;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .math-btn-cancel {
            background-color: #f1f1f1;
            color: #000 !important;
        }
        .math-btn-confirm {
            background-color: #f44336;
            color: white !important;
        }

        /* Score Display */
        .math-score-display {
            display: none;
            padding: 15px;
            border-radius: 5px;
            text-align: center;
            margin-top: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
            font-family: 'Nunito', sans-serif;
            width: 100%;
            max-width: 100%;
            box-sizing: border-box;
        }
        .math-score-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
            color: #000 !important;
        }
        .math-score-percentage {
            font-size: 36px;
            font-weight: bold;
            margin: 10px 0;
            color: #000 !important;
        }
        .math-score-detail {
            font-size: 16px;
            margin: 5px 0;
            color: #000 !important;
        }
        .math-score-message {
            font-size: 16px;
            margin-top: 10px;
            font-style: italic;
            color: #000 !important;
        }
        .math-score-excellent {
            background-color: #E8F5E9;
            border: 2px solid #4CAF50;
        }
        .math-score-good {
            background-color: #E0F2F1;
            border: 2px solid #00ACC1;
        }
        .math-score-fair {
            background-color: #FFF8E1;
            border: 2px solid #FFC107;
        }
        .math-score-poor {
            background-color: #FFEBEE;
            border: 2px solid #f44336;
        }
      
        /* Data Table */
        .math-data-table {
            width: 100%;
            border-collapse: collapse;
            margin: 15px 0;
            font-size: 14px;
            font-family: 'Nunito', sans-serif;
        }
        .math-data-table th, 
        .math-data-table td {
            padding: 10px;
            border: 1px solid #ddd;
            text-align: center;
            font-family: 'Nunito', sans-serif;
        }
        .math-data-table th {
            background-color: #f5f5f5;
            font-weight: 500;
        }

        /* Explanation Box */
        .math-explanation-box {
            margin: 15px;
            padding: 15px;
            background-color: #f8f9fa;
            border-left: 4px solid #2196F3;
            border-radius: 4px;
            font-size: 14px;
            color: #333;
            font-family: 'Nunito', sans-serif;
        }
        .math-explanation-box strong {
            color: #2196F3;
        }

        /* Question Type Indicator */
        .math-question-type {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: 500;
            margin-left: 10px;
            background-color: rgba(255, 255, 255, 0.2);
            color: white !important; /* Teks putih */
            font-family: 'Nunito', sans-serif;
        }
        .math-type-single {
            background-color: rgba(255, 255, 255, 0.2);
            color: white !important;
        }
        .math-type-multiple {
            background-color: rgba(255, 255, 255, 0.2);
            color: white !important;
        }
        .math-type-short {
            background-color: rgba(255, 255, 255, 0.2);
            color: white !important;
        }
        .math-type-matching {
            background-color: rgba(255, 255, 255, 0.2);
            color: white !important;
        }
      
      /* Style untuk Tombol Reset */
        .math-btn-reset {
            background-color: #f39c12;
            color: white !important;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
            display: inline-block;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
      
      .math-btn-reset:hover {
            background-color: #e67e22;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.3);
        }
        
        .math-btn-reset i {
            margin-right: 8px;
        }
        
      /* Style untuk Status Tes */
        .math-test-status {
            padding: 15px;
            margin: 20px 0;
            border-radius: 8px;
            background-color: #e8f4f8;
            border-left: 5px solid #3498db;
            font-weight: 500;
            display: flex;
            align-items: center;
            justify-content: space-between;
            color: #000;
        }
        
        .math-test-status.completed {
            background-color: #e8f5e9;
            border-left-color: #2ecc71;
        }
      
        /* Answer triangle - only shown for user's selected answers after submission */
        .math-option.selected::after {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 0;
            height: 0;
            border-style: solid;
            border-width: 0 15px 15px 0;
            border-color: transparent #0088ff transparent transparent;
            border-radius: 0 8px 0 0;
        }

        /* Responsive Styles */
        @media (max-width: 600px) {
            .math-data-table {
                font-size: 12px;
            }
            .math-data-table th, 
            .math-data-table td {
                padding: 6px;
            }
            .math-question-nav button {
              width: 36px;
              height: 36px;
              font-size: 12px;
            }
            .math-start-screen h1 {
                font-size: 20px;
            }
            .math-instructions {
                font-size: 14px;
            }
            .math-btn-start {
                padding: 10px 25px;
                font-size: 14px;
            }
            .math-explanation-box {
                padding: 10px;
                font-size: 13px;
                margin: 10px;
            }
          
            .math-timer-box { 
               	padding: 7px 12px;
               	font-size: 14px;
            }
            .math-timer-emoji {
                font-size: 14px;
            }
            
            /* Responsive untuk question header */
            .math-question-header {
                padding: 12px;
            }
            .math-question-number {
                font-size: 14px;
            }
            .math-btn-mark {
                padding: 6px 10px;
                font-size: 14px;
            }
            
            /* Responsive untuk matching questions */
            /* Perbaikan khusus untuk soal menjodohkan di mobile */
            .math-matching-row {
                flex-direction: row !important;  /* Pastikan tetap horizontal */
                align-items: center;
                gap: 8px;
            }

            .math-matching-left {
                flex: 1;
                min-width: 120px;  /* Beri lebar minimum */
                font-size: 14px;
                padding: 6px;
                word-break: break-word;  /* Untuk teks panjang */
            }

            .math-matching-select {
                flex: 1;
                min-width: 100px;
                font-size: 13px;
                padding: 6px;
            }
        }
        
        
        @media (min-width: 768px) {
            .math-navigation {
                flex-direction: row;
                justify-content: space-between;
                align-items: flex-start;
                gap: 20px;
            }
            
            .math-nav-buttons {
                width: auto;
                flex: 0 0 auto;
                min-width: 250px;
            }
            
            .math-submit-container {
                width: auto;
                text-align: right;
                min-width: 350px;
            }
            
            .math-score-display {
                width: 100%;
                max-width: 400px;
                margin-left: auto;
                padding: 20px;
            }
            
            .math-btn-submit {
                width: auto;
                min-width: 150px;
            }
            
            .math-btn-prev, .math-btn-next {
                min-width: 120px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body class="math-body">
    <div class="math-timer-box" id="mathTimerBox">
        <i class="fas fa-clock math-timer-emoji"></i>
        <span id="mathTimerText">30:00</span>
    </div>

    <div class="math-container-quiz">
       <div class="math-test-status" id="mathTestStatus">
            <span>Status Tes: <span id="mathStatusText">Belum Dimulai</span></span>
            <span id="mathCompletedTime"></span>
        </div>
        <header>
            <h2 class="math-h2">Tes Matematika - Bilangan dan Operasi Dasar</h2>
            
            <!-- Dropdown Menu -->
            <div class="math-dropdown-menu">
                <button class="math-dropdown-toggle" id="mathDropdownToggle">
                    Level Mudah <i class="fas fa-chevron-down"></i>
                </button>
                <div class="math-dropdown-content" id="mathDropdownContent">
                    <div class="math-dropdown-item active" onclick="location.href='bilangan-easy.html'">Level Mudah</div>
                    <div class="math-dropdown-item" onclick="location.href='bilangan-medium.html'">Level Menengah</div>
                    <div class="math-dropdown-item" onclick="location.href='bilangan-hard.html'">Level Sulit</div>
                </div>
            </div>
            
            <!-- Start Screen -->
            <div class="math-start-screen" id="mathStartScreen">
                <h1 class="math-h1">Petunjuk Pengerjaan</h1>
                <div class="math-instructions">
                    <ol>
                        <li>Tes ini terdiri dari 30 soal dengan waktu pengerjaan 30 menit.</li>
                        <li>Terdapat 4 jenis soal:
                            <ul class="math-bullet-points">
                                <li><span style="color: #0D47A1;">🔹</span> Pilihan Ganda (1 jawaban benar)</li>
                                <li><span style="color: #1B5E20;">🔹</span> Pilihan Ganda Multi Jawaban</li>
                                <li><span style="color: #FF6F00;">🔹</span> Uraian Singkat</li>
                                <li><span style="color: #6A1B9A;">🔹</span> Menjodohkan</li>
                            </ul>
                        </li>
                        <li>Anda dapat menandai soal yang ingin dikerjakan nanti dengan tombol "Ragu-ragu".</li>
                        <li>Gunakan tombol navigasi di bawah soal untuk berpindah antar soal.</li>
                        <li>Tombol angka di bagian atas menunjukkan status soal:
                            <ul class="math-bullet-points">
                                <li><span style="color: #2196F3;">🟦</span> Biru: Sudah dijawab</li>
                                <li><span style="color: #FFC107;">🟨</span> Kuning: Ditandai ragu-ragu</li>
                                <li><span style="color: #4CAF50;">🟩</span> Hijau: Jawaban benar</li>
                                <li><span style="color: #f44336;">🟥</span> Merah: Jawaban salah</li>
                            </ul>
                        </li>
                        <li>Waktu akan terus berjalan selama tes berlangsung.</li>
                        <li>Setelah submit, Anda tidak dapat mengubah jawaban.</li>
                        <li>Pembahasan akan muncul setelah Anda menyelesaikan tes.</li>
                    </ol>
                    <p>Selamat mengerjakan!</p>
                </div>
                <button class="math-btn-start" id="mathBtnStart">Mulai Tes</button>
            </div>
        </header>

        <!-- Quiz Elements (initially hidden) -->
        <div class="math-quiz-elements" id="mathQuizElements">
            <div class="math-progress" id="mathProgressText">0 dari <span id="mathTotalQuestions">0</span> Soal dikerjakan</div>

            <!-- Question Navigation Toggle -->
            <div class="math-question-nav-toggle">
                <button class="math-question-nav-btn" id="mathQuestionNavBtn">
                    <span><i class="fas fa-list"></i> Navigasi Soal</span>
                    <i class="fas fa-chevron-down"></i>
                </button>
                <div class="math-question-nav-container" id="mathQuestionNavContainer">
                    <div class="math-question-nav" id="mathQuestionNav">
                        <!-- Questions will be generated by JavaScript -->
                    </div>
                </div>
            </div>

            <div class="math-question-container">
                <div class="math-question-header">
                    <div class="math-question-number" id="mathQuestionNumber">No. 1 <span class="math-question-type" id="mathQuestionType"></span></div>
                    <button class="math-btn-mark" id="mathBtnMark"><i class="fas fa-flag"></i> Ragu-ragu</button>
                </div>
                <div class="math-question-text" id="mathQuestionText">
                    <!-- Question text will be loaded by JavaScript -->
                </div>
                <div class="math-options" id="mathOptions">
                    <!-- Options will be loaded by JavaScript -->
                </div>
                <div class="math-short-answer-container" id="mathShortAnswerContainer" style="display: none;">
                    <input type="text" class="math-short-answer-input" id="mathShortAnswerInput" placeholder="Tulis jawaban singkat Anda di sini...">
                </div>
                <!-- Matching container will be added dynamically -->
            </div>

            <div class="math-navigation">
                <div class="math-nav-buttons">
                    <button class="math-btn-prev" id="mathBtnPrev">Sebelumnya</button>
                    <button class="math-btn-next" id="mathBtnNext">Selanjutnya</button>
                </div>
                <div class="math-submit-container">
                    <button class="math-btn-submit" id="mathBtnSubmit">Submit Jawaban</button>
                    <div class="math-score-display" id="mathScoreDisplay">
                        <div class="math-score-title">Hasil Tes Anda:</div>
                        <div class="math-score-percentage" id="mathScorePercentage">0%</div>
                        <div class="math-score-detail" id="mathScoreDetail">0 benar dari 0 soal</div>
                        <div class="math-score-message" id="mathScoreMessage"></div>
                      	<button class="math-btn-reset" id="mathBtnReset">
                            <i class="fas fa-redo"></i> Kerjakan Ulang
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="math-submit-confirm" id="mathSubmitConfirm">
        <div class="math-submit-dialog">
            <h3 class="math-h3">Konfirmasi Submit Jawaban</h3>
            <p>Apakah Anda yakin ingin mengirim jawaban? Anda tidak dapat mengubah jawaban setelah submit.</p>
            <div class="math-dialog-buttons">
                <button class="math-btn-cancel" id="mathBtnCancel">Batal</button>
                <button class="math-btn-confirm" id="mathBtnConfirm">Ya, Submit</button>
            </div>
        </div>
    </div>

    <script>
        // Sample math questions data with explanations
        const mathQuestions = [
            // Soal Pilihan Ganda Tunggal
            {
                number: 1,
                type: "single",
                text: "Hasil dari 245 + 367 adalah...",
                options: [
                    "A. 512",
                    "B. 602",
                    "C. 612",
                    "D. 622",
                    "E. 712"
                ],
                correctAnswer: [2], // C
                explanation: "245 + 367 = (200+300) + (40+60) + (5+7) = 500 + 100 + 12 = <strong>612</strong>."
            },
            {
                number: 2,
                type: "single",
                text: "Hasil dari 48 ÷ 6 × 2 = ...",
                options: [
                    "A. 4",
                    "B. 8",
                    "C. 12",
                    "D. 16",
                    "E. 24"
                ],
                correctAnswer: [3], // D
                explanation: "48 ÷ 6 = 8, lalu 8 × 2 = <strong>16</strong>."
            },
            {
                number: 3,
                type: "single",
                text: "Bentuk desimal dari 3/4 adalah...",
                options: [
                    "A. 0.25",
                    "B. 0.34",
                    "C. 0.5",
                    "D. 0.75",
                    "E. 0.8"
                ],
                correctAnswer: [3], // D
                explanation: "3 ÷ 4 = <strong>0.75</strong>."
            },
            {
                number: 4,
                type: "single",
                text: "25% dari 120 adalah...",
                options: [
                    "A. 25",
                    "B. 30",
                    "C. 40",
                    "D. 48",
                    "E. 60"
                ],
                correctAnswer: [1], // B
                explanation: "25% = 1/4, jadi 120 × 1/4 = <strong>30</strong>."
            },
            {
                number: 5,
                type: "single",
                text: "Hasil dari 7 × (8 - 3) adalah...",
                options: [
                    "A. 35",
                    "B. 42",
                    "C. 45",
                    "D. 56",
                    "E. 77"
                ],
                correctAnswer: [0], // A
                explanation: "8 - 3 = 5, lalu 7 × 5 = <strong>35</strong>."
            },
            {
                number: 6,
                type: "single",
                text: "Bilangan bulat yang terletak antara -3 dan 2 adalah...",
                options: [
                    "A. -4, -5",
                    "B. -2, -1, 0, 1",
                    "C. 3, 4",
                    "D. 0, 1, 2, 3",
                    "E. -3, -2, -1, 0, 1, 2"
                ],
                correctAnswer: [1], // B
                explanation: "Bilangan bulat antara -3 dan 2 adalah <strong>-2, -1, 0, 1</strong>."
            },
            {
                number: 7,
                type: "single",
                text: "Hasil dari 2³ + 3² adalah...",
                options: [
                    "A. 5",
                    "B. 13",
                    "C. 17",
                    "D. 25",
                    "E. 35"
                ],
                correctAnswer: [2], // C
                explanation: "2³ = 8 dan 3² = 9, jadi 8 + 9 = <strong>17</strong>."
            },
            {
                number: 8,
                type: "single",
                text: "Jika a = 5 dan b = 3, maka nilai dari 2a - b adalah...",
                options: [
                    "A. 4",
                    "B. 7",
                    "C. 8",
                    "D. 10",
                    "E. 13"
                ],
                correctAnswer: [1], // B
                explanation: "2a - b = (2×5) - 3 = 10 - 3 = <strong>7</strong>."
            },
            {
                number: 9,
                type: "single",
                text: "Hasil dari 0.6 + 0.25 adalah...",
                options: [
                    "A. 0.31",
                    "B. 0.75",
                    "C. 0.81",
                    "D. 0.85",
                    "E. 1.0"
                ],
                correctAnswer: [3], // D
                explanation: "0.6 + 0.25 = <strong>0.85</strong>."
            },
            {
                number: 10,
                type: "single",
                text: "Bentuk pecahan paling sederhana dari 0.125 adalah...",
                options: [
                    "A. 1/8",
                    "B. 1/4",
                    "C. 1/3",
                    "D. 1/2",
                    "E. 2/5"
                ],
                correctAnswer: [0], // A
                explanation: "0.125 = <strong>1/8</strong>."
            },
            {
                number: 11,
                type: "single",
                text: "Hasil dari 15 - (-7) adalah...",
                options: [
                    "A. 8",
                    "B. 18",
                    "C. 22",
                    "D. -8",
                    "E. -22"
                ],
                correctAnswer: [2], // C
                explanation: "15 - (-7) = 15 + 7 = <strong>22</strong>."
            },
            {
                number: 12,
                type: "single",
                text: "FPB dari 24 dan 36 adalah...",
                options: [
                    "A. 6",
                    "B. 8",
                    "C. 12",
                    "D. 18",
                    "E. 24"
                ],
                correctAnswer: [2], // C
                explanation: "Faktor 24: 1,2,3,4,6,8,12,24; Faktor 36: 1,2,3,4,6,9,12,18,36. FPB adalah <strong>12</strong>."
            },
            {
                number: 13,
                type: "single",
                text: "KPK dari 5 dan 6 adalah...",
                options: [
                    "A. 15",
                    "B. 20",
                    "C. 25",
                    "D. 30",
                    "E. 60"
                ],
                correctAnswer: [3], // D
                explanation: "Kelipatan 5: 5,10,15,20,25,30,...; Kelipatan 6: 6,12,18,24,30,... KPK adalah <strong>30</strong>."
            },
            {
                number: 14,
                type: "single",
                text: "Hasil dari 3/5 + 1/2 adalah...",
                options: [
                    "A. 4/7",
                    "B. 4/10",
                    "C. 8/10",
                    "D. 9/10",
                    "E. 11/10"
                ],
                correctAnswer: [4], // E
                explanation: "3/5 + 1/2 = 6/10 + 5/10 = <strong>11/10</strong>."
            },
            {
                number: 15,
                type: "single",
                text: "Jika 5x + 3 = 23, maka nilai x adalah...",
                options: [
                    "A. 2",
                    "B. 4",
                    "C. 5",
                    "D. 6",
                    "E. 7"
                ],
                correctAnswer: [1], // B
                explanation: "5x + 3 = 23 → 5x = 20 → x = <strong>4</strong>."
            },

            // Soal Pilihan Ganda Multi Jawaban (5 soal)
            {
                number: 16,
                type: "multiple",
                text: "Manakah yang termasuk bilangan cacah? <strong>(Pilih lebih dari satu jawaban)</strong>",
                options: [
                    "A. 0",
                    "B. 1",
                    "C. -1",
                    "D. 0.5",
                    "E. 100"
                ],
                correctAnswer: [0, 1, 4],
                explanation: "Bilangan cacah adalah 0,1,2,3,... Jadi <strong>0, 1, dan 100</strong> adalah bilangan cacah."
            },
            {
                number: 17,
                type: "multiple",
                text: "Operasi hitung yang hasilnya 24 adalah... <strong>(Pilih lebih dari satu jawaban)</strong>",
                options: [
                    "A. 6 × 4",
                    "B. 30 - 4",
                    "C. 8 × 3",
                    "D. 48 ÷ 2",
                    "E. 5 × 5"
                ],
                correctAnswer: [0, 2, 3],
                explanation: "A: 6×4=24; B: 30-4=26; C: 8×3=24; D: 48÷2=24; E: 5×5=25. Jadi <strong>A, C, D</strong> benar."
            },
            {
                number: 18,
                type: "multiple",
                text: "Pernyataan yang benar tentang sifat operasi hitung adalah... <strong>(Pilih lebih dari satu jawaban)</strong>",
                options: [
                    "A. a + b = b + a (komutatif penjumlahan)",
                    "B. a × (b + c) = (a × b) + c (distributif salah)",
                    "C. (a × b) × c = a × (b × c) (asosiatif perkalian)",
                    "D. a - b = b - a (komutatif pengurangan)",
                    "E. a ÷ b = b ÷ a (komutatif pembagian)"
                ],
                correctAnswer: [0, 2],
                explanation: "<strong>A dan C</strong> benar. B salah (harusnya a×(b+c)=a×b+a×c). D dan E salah karena pengurangan dan pembagian tidak komutatif."
            },
            {
                number: 19,
                type: "multiple",
                text: "Bilangan yang habis dibagi 3 adalah... <strong>(Pilih lebih dari satu jawaban)</strong>",
                options: [
                    "A. 123",
                    "B. 235",
                    "C. 333",
                    "D. 448",
                    "E. 501"
                ],
                correctAnswer: [0, 2, 4],
                explanation: "Ciri bilangan habis dibagi 3: jumlah digitnya habis dibagi 3. A:1+2+3=6; C:3+3+3=9; E:5+0+1=6. Jadi <strong>A, C, E</strong> benar."
            },
            {
                number: 20,
                type: "multiple",
                text: "Pecahan yang senilai dengan 2/3 adalah... <strong>(Pilih lebih dari satu jawaban)</strong>",
                options: [
                    "A. 4/6",
                    "B. 6/9",
                    "C. 8/12",
                    "D. 10/15",
                    "E. 9/12"
                ],
                correctAnswer: [0, 1, 2, 3],
                explanation: "2/3 = 4/6 = 6/9 = 8/12 = 10/15. <strong>A, B, C, D</strong> benar. E salah (9/12=3/4)."
            },
          
            // Soal Menjodohkan (5 soal)
            {
                number: 21,
                type: "matching",
                text: "Pasangkan operasi hitung dengan hasil yang benar:",
                leftItems: [
                    "12 × 5",
                    "100 ÷ 4",
                    "7 + 8 × 2",
                    "3² + 4²",
                    "0.4 × 5"
                ],
                rightItems: [
                    "A. 25",
                    "B. 2",
                    "C. 60",
                    "D. 23",
                    "E. 25"
                ],
                correctPairs: {
                    0: 2,  // 12×5=60 (C)
                    1: 0,  // 100÷4=25 (A)
                    2: 3,  // 7+(8×2)=23 (D)
                    3: 4,  // 9+16=25 (E)
                    4: 1   // 0.4×5=2 (B)
                },
                explanation: "<br>1. 12 × 5 = 60 (C)<br>2. 100 ÷ 4 = 25 (A)<br>3. 7 + (8 × 2) = 23 (D)<br>4. 3² + 4² = 9 + 16 = 25 (E)<br>5. 0.4 × 5 = 2 (B)"
            },
            {
                number: 22,
                type: "matching",
                text: "Pasangkan bilangan dengan jenisnya yang tepat:",
                leftItems: [
                    "0",
                    "-5",
                    "2.5",
                    "3/4",
                    "100%"
                ],
                rightItems: [
                    "A. Bilangan bulat negatif",
                    "B. Bilangan cacah",
                    "C. Bilangan pecahan",
                    "D. Bilangan desimal",
                    "E. Persen"
                ],
                correctPairs: {
                    0: 1,  // 0 adalah bilangan cacah (B)
                    1: 0,  // -5 adalah bilangan bulat negatif (A)
                    2: 3,  // 2.5 adalah bilangan desimal (D)
                    3: 2,  // 3/4 adalah bilangan pecahan (C)
                    4: 4   // 100% adalah persen (E)
                },
                explanation: "<br>1. 0 adalah bilangan cacah (B)<br>2. -5 adalah bilangan bulat negatif (A)<br>3. 2.5 adalah bilangan desimal (D)<br>4. 3/4 adalah bilangan pecahan (C)<br>5. 100% adalah persen (E)"
            },
            {
                number: 23,
                type: "matching",
                text: "Pasangkan soal cerita dengan operasi hitung yang tepat:",
                leftItems: [
                    "Andi memiliki 12 permen dan membagikan kepada 3 temannya sama rata",
                    "Harga 1 buku Rp5.000. Rina membeli 7 buku",
                    "Pak Joko mempunyai 50 kg beras, dijual 15 kg",
                    "Sebuah bus berangkat dengan 20 penumpang, di halte pertama turun 5 dan naik 8",
                    "Luas persegi panjang dengan panjang 8 cm dan lebar 5 cm"
                ],
                rightItems: [
                    "A. 50 - 15 = 35 kg",
                    "B. 12 ÷ 3 = 4 permen",
                    "C. 8 × 5 = 40 cm²",
                    "D. 20 - 5 + 8 = 23 penumpang",
                    "E. 5.000 × 7 = Rp35.000"
                ],
                correctPairs: {
                    0: 1,  // 12 ÷ 3 = 4 (B)
                    1: 4,  // 5.000 × 7 = 35.000 (E)
                    2: 0,  // 50 - 15 = 35 (A)
                    3: 3,  // 20 - 5 + 8 = 23 (D)
                    4: 2   // 8 × 5 = 40 (C)
                },
                explanation: "<br>1. 12 ÷ 3 = 4 permen (B)<br>2. 5.000 × 7 = Rp35.000 (E)<br>3. 50 - 15 = 35 kg (A)<br>4. 20 - 5 + 8 = 23 penumpang (D)<br>5. 8 × 5 = 40 cm² (C)"
            },
            {
                number: 24,
                type: "matching",
                text: "Pasangkan sifat operasi hitung dengan contoh yang benar:",
                leftItems: [
                    "Komutatif penjumlahan",
                    "Asosiatif perkalian",
                    "Distributif perkalian terhadap penjumlahan",
                    "Identitas penjumlahan",
                    "Identitas perkalian"
                ],
                rightItems: [
                    "A. 2 × (3 + 4) = (2 × 3) + (2 × 4)",
                    "B. 5 + 0 = 5",
                    "C. 3 + 4 = 4 + 3",
                    "D. 7 × 1 = 7",
                    "E. (2 × 3) × 4 = 2 × (3 × 4)"
                ],
                correctPairs: {
                    0: 2,  // 3+4=4+3 (C)
                    1: 4,  // (2×3)×4=2×(3×4) (E)
                    2: 0,  // 2×(3+4)=(2×3)+(2×4) (A)
                    3: 1,  // 5+0=5 (B)
                    4: 3   // 7×1=7 (D)
                },
                explanation: "<br>1. Komutatif penjumlahan: 3+4=4+3 (C)<br>2. Asosiatif perkalian: (2×3)×4=2×(3×4) (E)<br>3. Distributif: 2×(3+4)=(2×3)+(2×4) (A)<br>4. Identitas penjumlahan: 5+0=5 (B)<br>5. Identitas perkalian: 7×1=7 (D)"
            },
            {
                number: 25,
                type: "matching",
                text: "Pasangkan jenis bilangan dengan contoh yang sesuai:",
                leftItems: [
                    "Bilangan asli",
                    "Bilangan cacah",
                    "Bilangan bulat negatif",
                    "Bilangan pecahan sederhana",
                    "Bilangan desimal berulang"
                ],
                rightItems: [
                    "A. 0, 1, 2, 3, ...",
                    "B. 1, 2, 3, 4, ...",
                    "C. -1, -2, -3, ...",
                    "D. 0.333...",
                    "E. 1/2, 3/4, 2/5"
                ],
                correctPairs: {
                    0: 1,  // Bilangan asli: 1,2,3,... (B)
                    1: 0,  // Bilangan cacah: 0,1,2,... (A)
                    2: 2,  // Bilangan bulat negatif: -1,-2,... (C)
                    3: 4,  // Pecahan sederhana: 1/2, 3/4,... (E)
                    4: 3   // Desimal berulang: 0.333... (D)
                },
                explanation: "<br>1. Bilangan asli dimulai dari 1 (B)<br>2. Bilangan cacah termasuk 0 (A)<br>3. Bilangan bulat negatif (C)<br>4. Pecahan sederhana (E)<br>5. Desimal berulang seperti 0.333... (D)"
            },

            // Soal Isian Singkat (5 soal)
            {
                number: 26,
                type: "short",
                text: "Hasil dari 128 ÷ (4 + 4) adalah... <strong>(Jawab dalam angka)</strong>",
                correctAnswer: ["16"],
                explanation: "Kerjakan dalam kurung dulu: 4 + 4 = 8, lalu 128 ÷ 8 = <strong>16</strong>."
            },
            {
                number: 27,
                type: "short",
                text: "Jika 3/8 = x/24, maka nilai x adalah... <strong>(Jawab dalam angka)</strong>",
                correctAnswer: ["9"],
                explanation: "3/8 = x/24 → x = (3×24)/8 = 72/8 = <strong>9</strong>."
            },
            {
                number: 28,
                type: "short",
                text: "Bentuk desimal dari 5% adalah... <strong>(Jawab dalam bentuk desimal)</strong>",
                correctAnswer: ["0.05"],
                explanation: "5% = 5/100 = <strong>0.05</strong>."
            },
            {
                number: 29,
                type: "short",
                text: "Hasil dari (-15) + 20 - (-5) adalah... <strong>(Jawab dalam angka)</strong>",
                correctAnswer: ["10"],
                explanation: "(-15) + 20 = 5, lalu 5 - (-5) = 5 + 5 = <strong>10</strong>."
            },
            {
                number: 30,
                type: "short",
                text: "Jumlah semua bilangan asli antara 10 dan 15 adalah... <strong>(Jawab dalam angka)</strong>",
                correctAnswer: ["50"],
                explanation: "Bilangan asli antara 10 dan 15: 11,12,13,14. Jumlahnya: 11+12+13+14 = <strong>50</strong>."
            }
        ];

        // Initialize variables
        let mathCurrentQuestion = 0;
        let mathAnswers = Array(mathQuestions.length).fill(null);
        let mathMarkedQuestions = Array(mathQuestions.length).fill(false);
        let mathAnsweredCount = 0;
        let mathTimerInterval;
        let mathIsSubmitted = false;
        let mathTestCompleted = false;
        let mathCompletionTime = null;

        // DOM elements
        const mathStartScreen = document.getElementById('mathStartScreen');
        const mathQuizElements = document.getElementById('mathQuizElements');
        const mathBtnStart = document.getElementById('mathBtnStart');
        const mathQuestionNav = document.getElementById('mathQuestionNav');
        const mathQuestionNavBtn = document.getElementById('mathQuestionNavBtn');
        const mathQuestionNavContainer = document.getElementById('mathQuestionNavContainer');
        const mathProgressText = document.getElementById('mathProgressText');
        const mathTotalQuestionsSpan = document.getElementById('mathTotalQuestions');
        const mathQuestionNumber = document.getElementById('mathQuestionNumber');
        const mathQuestionType = document.getElementById('mathQuestionType');
        const mathQuestionText = document.getElementById('mathQuestionText');
        const mathOptionsContainer = document.getElementById('mathOptions');
        const mathShortAnswerContainer = document.getElementById('mathShortAnswerContainer');
        const mathShortAnswerInput = document.getElementById('mathShortAnswerInput');
        const mathBtnMark = document.getElementById('mathBtnMark');
        const mathBtnPrev = document.getElementById('mathBtnPrev');
        const mathBtnNext = document.getElementById('mathBtnNext');
        const mathBtnSubmit = document.getElementById('mathBtnSubmit');
        const mathTimerText = document.getElementById('mathTimerText');
        const mathScoreDisplay = document.getElementById('mathScoreDisplay');
        const mathScorePercentage = document.getElementById('mathScorePercentage');
        const mathScoreDetail = document.getElementById('mathScoreDetail');
        const mathScoreMessage = document.getElementById('mathScoreMessage');
        const mathDropdownToggle = document.getElementById('mathDropdownToggle');
        const mathDropdownContent = document.getElementById('mathDropdownContent');
        const mathSubmitConfirm = document.getElementById('mathSubmitConfirm');
        const mathBtnCancel = document.getElementById('mathBtnCancel');
        const mathBtnConfirm = document.getElementById('mathBtnConfirm');
        const mathTestStatus = document.getElementById('mathTestStatus');
        const mathStatusText = document.getElementById('mathStatusText');
        const mathCompletedTime = document.getElementById('mathCompletedTime');
        const mathBtnReset = document.getElementById('mathBtnReset');

        // Helper function to check if an answer is actually filled
        function isAnswerFilled(answer, questionType) {
            if (!answer || answer.length === 0) return false;

            if (questionType === "short") {
                // For short answers, check if the text is not empty after trimming
                return answer[0] && answer[0].toString().trim() !== "";
            } else if (questionType === "matching") {
                // For matching questions, check if all pairs are selected
                return answer.length > 0 && answer.every(item => item !== undefined && item !== "");
            } else {
                // For multiple choice, just check if there are selections
                return answer.length > 0;
            }
        }

        // Check test status from localStorage
        function checkTestStatus() {
            const savedData = localStorage.getItem('bilangan-easy-data');
            if (savedData) {
                const testData = JSON.parse(savedData);

                if (testData.isSubmitted) {
                    // Restore all test data
                    mathAnswers = testData.answers || Array(mathQuestions.length).fill(null);
                    mathMarkedQuestions = testData.markedQuestions || Array(mathQuestions.length).fill(false);
                    mathIsSubmitted = true;
                    mathTestCompleted = true;
                    mathCompletionTime = testData.completionTime;
                    mathCurrentQuestion = testData.currentQuestion || 0;

                    // Update UI for submitted state - HIDE START SCREEN AND SHOW QUIZ
                    mathStartScreen.style.display = 'none';
                    mathQuizElements.style.display = 'block';

                    // IMPORTANT: Generate navigation BEFORE loading question
                    mathGenerateQuestionNav();

                    // Show score display
                    mathScoreDisplay.style.display = 'block';
                    mathScorePercentage.textContent = testData.score;
                    mathScoreDetail.textContent = `${testData.correctAnswers} benar dari ${mathQuestions.length} soal`;

                    // Apply score styling and message
                    let colorClass, message;
                    const percentage = parseInt(testData.score);
                    if (percentage >= 80) {
                        colorClass = 'math-score-excellent';
                        message = "Luar biasa! Hasil yang sangat baik!";
                    } else if (percentage >= 60) {
                        colorClass = 'math-score-good';
                        message = "Bagus! Tetap semangat belajar!";
                    } else if (percentage >= 40) {
                        colorClass = 'math-score-fair';
                        message = "Cukup baik. Tingkatkan lagi!";
                    } else {
                        colorClass = 'math-score-poor';
                        message = "Perlu belajar lebih giat lagi!";
                    }
                    mathScoreDisplay.className = 'math-score-display ' + colorClass;
                    mathScoreMessage.textContent = message;

                    // Hide elements that shouldn't be visible after submission
                    mathBtnSubmit.style.display = 'none';
                    mathBtnStart.style.display = 'none';
                    mathBtnMark.style.display = 'none';

                    // Show status as completed
                    mathStatusText.textContent = 'Selesai';
                    mathTestStatus.classList.add('completed');
                    if (mathCompletionTime) {
                        mathCompletedTime.textContent = 'Selesai pada: ' + new Date(mathCompletionTime).toLocaleString();
                    }

                    // Set timer to show 00:00
                    mathTimerText.textContent = "00:00";
                    mathTimerText.classList.add('math-time-up');

                    // Update answered count
                    mathUpdateAnsweredCount();

                    // Load the current question
                    mathLoadQuestion();

                    return true;
                }
            }
            return false;
        }

        // Timer functionality (countdown from 30 minutes)
        function mathStartTimer() {
            let mathTimeLeft = 30 * 60; // 30 minutes in seconds

            function mathUpdateTimerDisplay() {
                const minutes = Math.floor(mathTimeLeft / 60);
                const seconds = mathTimeLeft % 60;
                mathTimerText.textContent = `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;

                if (mathTimeLeft <= 0) {
                    clearInterval(mathTimerInterval);
                    mathTimerText.textContent = "00:00";
                    mathTimerText.classList.add('math-time-up');
                    alert("Waktu telah habis! Jawaban akan disubmit secara otomatis.");
                    mathSubmitAnswers();
                }
            }

            mathUpdateTimerDisplay();

            mathTimerInterval = setInterval(() => {
                mathTimeLeft--;
                mathUpdateTimerDisplay();

                if (mathTimeLeft <= 0) {
                    clearInterval(mathTimerInterval);
                }
            }, 1000);
        }

        // Generate question navigation buttons
        function mathGenerateQuestionNav() {
            mathQuestionNav.innerHTML = '';
            mathTotalQuestionsSpan.textContent = mathQuestions.length;

            mathQuestions.forEach((_, index) => {
                const button = document.createElement('button');
                button.textContent = index + 1;
                button.addEventListener('click', () => {
                    mathCurrentQuestion = index;
                    mathLoadQuestion();
                });
                mathQuestionNav.appendChild(button);
            });
        }

        // Show explanation for the current question
        function mathShowExplanation(explanation) {
            const oldExplanation = document.querySelector('.math-explanation-box');
            if (oldExplanation) {
                oldExplanation.remove();
            }

            const explanationElement = document.createElement('div');
            explanationElement.className = 'math-explanation-box';
            explanationElement.innerHTML = `<strong>Pembahasan:</strong> ${explanation}`;

            const questionContainer = document.querySelector('.math-question-container');
            questionContainer.appendChild(explanationElement);
        }

        // Save current answer for short answer questions
        function saveCurrentShortAnswer() {
            if (mathQuestions[mathCurrentQuestion].type === "short") {
                const trimmedValue = mathShortAnswerInput.value.trim();
                if (trimmedValue !== "") {
                    mathAnswers[mathCurrentQuestion] = [trimmedValue];
                } else {
                    mathAnswers[mathCurrentQuestion] = null;
                }
                mathUpdateAnsweredCount();
                mathUpdateQuestionNav();
            }
        }

        // Load question
        function mathLoadQuestion() {
            const question = mathQuestions[mathCurrentQuestion];
            mathQuestionNumber.textContent = `No. ${question.number}`;

            // Set question type indicator
            mathQuestionType.textContent = question.type === "single" ? "Pilihan Ganda" : 
                                      question.type === "multiple" ? "Multi Jawaban" : 
                                      question.type === "matching" ? "Menjodohkan" : "Uraian Singkat";
            mathQuestionType.className = "math-question-type " + 
                                   (question.type === "single" ? "math-type-single" : 
                                    question.type === "multiple" ? "math-type-multiple" : 
                                    question.type === "matching" ? "math-type-matching" : "math-type-short");

            mathQuestionText.innerHTML = question.text;

            // Remove previous explanation if exists
            const oldExplanation = document.querySelector('.math-explanation-box');
            if (oldExplanation) {
                oldExplanation.remove();
            }

            // Remove previous matching container if exists
            const oldMatchingContainer = document.querySelector('.math-matching-container');
            if (oldMatchingContainer) {
                oldMatchingContainer.remove();
            }

            // Show appropriate input based on question type
            if (question.type === "short") {
                mathOptionsContainer.style.display = "none";
                mathShortAnswerContainer.style.display = "block";

                // Load saved answer, but handle null/undefined properly
                const savedAnswer = mathAnswers[mathCurrentQuestion];
                mathShortAnswerInput.value = (savedAnswer && savedAnswer[0]) ? savedAnswer[0] : "";

                // Disable input if submitted
                mathShortAnswerInput.disabled = mathIsSubmitted;
            } 
            else if (question.type === "matching") {
                mathOptionsContainer.style.display = "none";
                mathShortAnswerContainer.style.display = "none";
                
                // Create matching container
                const matchingContainer = document.createElement('div');
                matchingContainer.className = 'math-matching-container';
                mathQuestionText.parentNode.insertBefore(matchingContainer, mathOptionsContainer);
                
                // Create matching rows
                question.leftItems.forEach((leftItem, index) => {
                    const row = document.createElement('div');
                    row.className = 'math-matching-row';
                    
                    const left = document.createElement('div');
                    left.className = 'math-matching-left';
                    left.textContent = leftItem;
                    row.appendChild(left);
                    
                    const select = document.createElement('select');
                    select.className = 'math-matching-select';
                    select.disabled = mathIsSubmitted;
                    
                    // Add default option
                    const defaultOption = document.createElement('option');
                    defaultOption.value = '';
                    defaultOption.textContent = '-- Pilih Jawaban --';
                    select.appendChild(defaultOption);
                    
                    // Add answer options
                    question.rightItems.forEach((rightItem, rightIndex) => {
                        const option = document.createElement('option');
                        option.value = rightIndex;
                        option.textContent = rightItem;
                        select.appendChild(option);
                    });
                    
                    // Set selected value if answered
                    if (mathAnswers[mathCurrentQuestion] && mathAnswers[mathCurrentQuestion][index] !== undefined) {
                        select.value = mathAnswers[mathCurrentQuestion][index];
                        
                        // After submission, show correct/wrong
                        if (mathIsSubmitted) {
                            if (question.correctPairs[index] === parseInt(mathAnswers[mathCurrentQuestion][index])) {
                                select.classList.add('correct');
                            } else {
                                select.classList.add('wrong');
                            }
                        }
                    }
                    
                    select.addEventListener('change', () => {
                        if (!mathAnswers[mathCurrentQuestion]) {
                            mathAnswers[mathCurrentQuestion] = [];
                        }
                        mathAnswers[mathCurrentQuestion][index] = select.value;
                        mathUpdateAnsweredCount();
                        mathUpdateQuestionNav();
                    });
                    
                    row.appendChild(select);
                    matchingContainer.appendChild(row);
                });
            }
            else {
                mathOptionsContainer.style.display = "flex";
                mathShortAnswerContainer.style.display = "none";

                // Update options
                mathOptionsContainer.innerHTML = '';
                question.options.forEach((option, index) => {
                    const optionElement = document.createElement('div');
                    optionElement.className = 'math-option';

                    const letterBox = document.createElement('div');
                    letterBox.className = 'math-option-letter';
                    letterBox.textContent = option.substring(0, 1);

                    const optionText = document.createElement('div');
                    optionText.className = 'math-option-text';
                    optionText.innerHTML = option.substring(3);

                    optionElement.appendChild(letterBox);
                    optionElement.appendChild(optionText);

                    // Check if this option was selected by user
                    const isSelected = mathAnswers[mathCurrentQuestion] && mathAnswers[mathCurrentQuestion].includes(index);
                    if (isSelected) {
                        optionElement.classList.add('selected');
                    }

                    // After submission, show correct/wrong answers
                    if (mathIsSubmitted) {
                        const isCorrectOption = question.correctAnswer.includes(index);

                        if (isSelected) {
                            if (isCorrectOption) {
                                optionElement.classList.add('correct');
                            } else {
                                optionElement.classList.add('wrong');
                            }
                        } else if (isCorrectOption) {
                            optionElement.classList.add('correct');
                        }
                    }

                    optionElement.addEventListener('click', () => {
                        if (!mathIsSubmitted) {
                            if (question.type === "single") {
                                // For single answer questions
                                document.querySelectorAll('.math-option').forEach(opt => {
                                    opt.classList.remove('selected');
                                });
                                optionElement.classList.add('selected');
                                mathAnswers[mathCurrentQuestion] = [index];
                            } else {
                                // For multiple answer questions
                                if (!mathAnswers[mathCurrentQuestion]) {
                                    mathAnswers[mathCurrentQuestion] = [];
                                }

                                const selectedIndex = mathAnswers[mathCurrentQuestion].indexOf(index);
                                if (selectedIndex === -1) {
                                    mathAnswers[mathCurrentQuestion].push(index);
                                    optionElement.classList.add('selected');
                                } else {
                                    mathAnswers[mathCurrentQuestion].splice(selectedIndex, 1);
                                    optionElement.classList.remove('selected');

                                    // If no options are selected, set to null
                                    if (mathAnswers[mathCurrentQuestion].length === 0) {
                                        mathAnswers[mathCurrentQuestion] = null;
                                    }
                                }
                            }

                            mathUpdateAnsweredCount();
                            mathUpdateQuestionNav();
                        }
                    });
                    mathOptionsContainer.appendChild(optionElement);
                });
            }

            // Show explanation after submit
            if (mathIsSubmitted) {
                mathShowExplanation(question.explanation);
            }

            mathBtnMark.classList.toggle('marked', mathMarkedQuestions[mathCurrentQuestion]);
            mathUpdateQuestionNav();
            mathBtnPrev.disabled = mathCurrentQuestion === 0;
            mathBtnNext.disabled = mathCurrentQuestion === mathQuestions.length - 1;

            // Hide mark button after submission
            mathBtnMark.style.display = mathIsSubmitted ? 'none' : 'block';
        }

        // Update question navigation buttons
        function mathUpdateQuestionNav() {
            const buttons = mathQuestionNav.querySelectorAll('button');
            buttons.forEach((button, index) => {
                button.className = '';
                button.style.border = '2px solid #ddd';
                button.style.boxShadow = 'none';

                if (index === mathCurrentQuestion) {
                    button.style.border = '2px solid #1976D2';
                    button.style.boxShadow = '0 0 0 2px rgba(25, 118, 210, 0.3)';
                }

                if (mathIsSubmitted) {
                    if (mathAnswers[index] !== null) {
                        const question = mathQuestions[index];
                        let isCorrect = false;

                        if (question.type === "short") {
                            // For short answer questions
                            const userAnswer = mathAnswers[index] ? mathAnswers[index][0].toLowerCase().trim() : "";
                            isCorrect = question.correctAnswer.some(correct => 
                                correct.toLowerCase().trim() === userAnswer
                            );
                        } 
                        else if (question.type === "matching") {
                            // For matching questions
                            isCorrect = true;
                            for (let i = 0; i < question.leftItems.length; i++) {
                                if (!mathAnswers[index] || 
                                    mathAnswers[index][i] === undefined || 
                                    parseInt(mathAnswers[index][i]) !== question.correctPairs[i]) {
                                    isCorrect = false;
                                    break;
                                }
                            }
                        }
                        else {
                            // For multiple choice questions
                            const userAnswers = mathAnswers[index] || [];
                            const correctAnswers = question.correctAnswer;

                            if (question.type === "single") {
                                isCorrect = userAnswers.length === 1 && 
                                            correctAnswers.length === 1 && 
                                            userAnswers[0] === correctAnswers[0];
                            } else {
                                // For multiple-answer questions
                                const allCorrectSelected = correctAnswers.every(ca => 
                                    userAnswers.includes(ca)
                                );
                                const noIncorrectSelected = userAnswers.every(ua => 
                                    correctAnswers.includes(ua)
                                );
                                isCorrect = allCorrectSelected && noIncorrectSelected;
                            }
                        }

                        button.classList.add(isCorrect ? 'correct' : 'wrong');
                    }
                } else {
                    if (mathMarkedQuestions[index]) {
                        button.classList.add('marked');
                    } else if (isAnswerFilled(mathAnswers[index], mathQuestions[index].type)) {
                        button.classList.add('answered');
                    }
                }
            });
        }

        // Update answered count
        function mathUpdateAnsweredCount() {
            mathAnsweredCount = 0;
            mathAnswers.forEach((answer, index) => {
                if (isAnswerFilled(answer, mathQuestions[index].type)) {
                    mathAnsweredCount++;
                }
            });
            mathProgressText.textContent = `${mathAnsweredCount} dari ${mathQuestions.length} Soal dikerjakan`;
        }

        // Calculate score
        function mathCalculateScore() {
            let score = 0;
            mathQuestions.forEach((question, index) => {
                if (isAnswerFilled(mathAnswers[index], question.type)) {
                    if (question.type === "short") {
                        // For short answer questions
                        const userAnswer = mathAnswers[index][0].toLowerCase().trim();
                        if (question.correctAnswer.some(correct => 
                            correct.toLowerCase().trim() === userAnswer
                        )) {
                            score++;
                        }
                    } 
                    else if (question.type === "matching") {
                        // For matching questions
                        let allCorrect = true;
                        for (let i = 0; i < question.leftItems.length; i++) {
                            if (!mathAnswers[index] || 
                                mathAnswers[index][i] === undefined || 
                                parseInt(mathAnswers[index][i]) !== question.correctPairs[i]) {
                                allCorrect = false;
                                break;
                            }
                        }
                        if (allCorrect) score++;
                    }
                    else {
                        // For multiple choice questions
                        const userAnswers = mathAnswers[index] || [];
                        const correctAnswers = question.correctAnswer;

                        if (question.type === "single") {
                            if (userAnswers.length === 1 && 
                                correctAnswers.length === 1 && 
                                userAnswers[0] === correctAnswers[0]) {
                                score++;
                            }
                        } else {
                            // For multiple-answer questions
                            const allCorrectSelected = correctAnswers.every(ca => 
                                userAnswers.includes(ca)
                            );
                            const noIncorrectSelected = userAnswers.every(ua => 
                                correctAnswers.includes(ua)
                            );
                            if (allCorrectSelected && noIncorrectSelected) {
                                score++;
                            }
                        }
                    }
                }
            });
            return score;
        }

        // Save score for main dashboard
        function saveScoreForDashboard(percentage, correctAnswers) {
            localStorage.setItem('bilangan-easy-score', percentage + '%');
            localStorage.setItem('bilangan-easy-status', 'completed');
            localStorage.setItem('bilangan-easy-correct-answers', correctAnswers);
        }

        // Submit answers
        function mathSubmitAnswers() {
            mathIsSubmitted = true;
            clearInterval(mathTimerInterval);

            // Save current short answer if on a short answer question
            saveCurrentShortAnswer();

            const correctAnswers = mathCalculateScore();
            const percentage = Math.round((correctAnswers / mathQuestions.length) * 100);

            // Save COMPLETE test data
            saveScoreForDashboard(percentage, correctAnswers);
            localStorage.setItem('bilangan-easy-data', JSON.stringify({
                answers: mathAnswers,
                markedQuestions: mathMarkedQuestions,
                isSubmitted: true,
                score: percentage + '%',
                correctAnswers: correctAnswers,
                completionTime: new Date().toISOString(),
                currentQuestion: mathCurrentQuestion
            }));

            // Update UI
            mathBtnSubmit.style.display = 'none';
            mathBtnMark.style.display = 'none';
            mathScoreDisplay.style.display = 'block';
            mathScorePercentage.textContent = percentage + '%';
            mathScoreDetail.textContent = `${correctAnswers} benar dari ${mathQuestions.length} soal`;

            // Determine color class and message based on percentage
            let colorClass, message;
            if (percentage >= 80) {
                colorClass = 'math-score-excellent';
                message = "Luar biasa! Hasil yang sangat baik!";
            } else if (percentage >= 60) {
                colorClass = 'math-score-good';
                message = "Bagus! Tetap semangat belajar!";
            } else if (percentage >= 40) {
                colorClass = 'math-score-fair';
                message = "Cukup baik. Tingkatkan lagi!";
            } else {
                colorClass = 'math-score-poor';
                message = "Perlu belajar lebih giat lagi!";
            }

            mathScoreDisplay.className = 'math-score-display ' + colorClass;
            mathScoreMessage.textContent = message;

            // Update status display
            mathStatusText.textContent = 'Selesai';
            mathTestStatus.classList.add('completed');
            mathCompletionTime = new Date();
            mathCompletedTime.textContent = 'Selesai pada: ' + mathCompletionTime.toLocaleString();

            // Set timer to show 00:00
            mathTimerText.textContent = "00:00";
            mathTimerText.classList.add('math-time-up');

            // Reload current question to show explanations
            mathLoadQuestion();
            mathUpdateQuestionNav();
        }

        // Reset test
        function resetTest() {
            if (confirm('Apakah Anda yakin ingin mengulang tes ini? Semua jawaban dan skor sebelumnya akan dihapus.')) {
                // Clear all test data
                localStorage.removeItem('bilangan-easy-data');
                localStorage.removeItem('bilangan-easy-score');
                localStorage.removeItem('bilangan-easy-status');
                localStorage.removeItem('bilangan-easy-correct-answers');

                // Reset all variables
                mathCurrentQuestion = 0;
                mathAnswers = Array(mathQuestions.length).fill(null);
                mathMarkedQuestions = Array(mathQuestions.length).fill(false);
                mathAnsweredCount = 0;
                mathIsSubmitted = false;
                mathTestCompleted = false;
                mathCompletionTime = null;

                // Reset UI
                mathStartScreen.style.display = 'block';
                mathQuizElements.style.display = 'none';
                mathScoreDisplay.style.display = 'none';
                mathBtnStart.style.display = 'block';
                mathBtnSubmit.style.display = 'block';
                mathBtnMark.style.display = 'block';
                mathStatusText.textContent = 'Belum Dimulai';
                mathTestStatus.classList.remove('completed');
                mathCompletedTime.textContent = '';

                // Reset timer
                clearInterval(mathTimerInterval);
                mathTimerText.textContent = "15:00";
                mathTimerText.classList.remove('math-time-up');

                // Reload page
                location.reload();
            }
        }

        // Initialize with proper state checking
        document.addEventListener('DOMContentLoaded', () => {
            // First check if test was completed
            const testWasCompleted = checkTestStatus();

            if (!testWasCompleted) {
                // Only show start screen if test wasn't completed
                mathQuizElements.style.display = 'none';
                mathStartScreen.style.display = 'block';
                mathScoreDisplay.style.display = 'none';
                mathStatusText.textContent = 'Belum Dimulai';
            }

            // Event listeners
            mathBtnStart.addEventListener('click', () => {
                mathStartScreen.style.display = 'none';
                mathQuizElements.style.display = 'block';
                mathStartTimer();
                mathGenerateQuestionNav();
                mathLoadQuestion();
                mathScoreDisplay.style.display = 'none';
                mathStatusText.textContent = 'Sedang Berlangsung';
            });

            mathQuestionNavBtn.addEventListener('click', () => {
                mathQuestionNavBtn.classList.toggle('active');
                mathQuestionNavContainer.classList.toggle('show');
            });

            mathBtnMark.addEventListener('click', () => {
                if (!mathIsSubmitted) {
                    mathMarkedQuestions[mathCurrentQuestion] = !mathMarkedQuestions[mathCurrentQuestion];
                    mathBtnMark.classList.toggle('marked', mathMarkedQuestions[mathCurrentQuestion]);
                    mathUpdateQuestionNav();
                }
            });

            mathBtnPrev.addEventListener('click', () => {
                if (mathCurrentQuestion > 0) {
                    // Save current answer before moving
                    saveCurrentShortAnswer();
                    mathCurrentQuestion--;
                    mathLoadQuestion();
                }
            });

            mathBtnNext.addEventListener('click', () => {
                if (mathCurrentQuestion < mathQuestions.length - 1) {
                    // Save current answer before moving
                    saveCurrentShortAnswer();
                    mathCurrentQuestion++;
                    mathLoadQuestion();
                }
            });

            mathBtnSubmit.addEventListener('click', () => {
                mathSubmitConfirm.style.display = 'flex';
            });

            mathBtnCancel.addEventListener('click', () => {
                mathSubmitConfirm.style.display = 'none';
            });

            mathBtnConfirm.addEventListener('click', () => {
                mathSubmitConfirm.style.display = 'none';
                mathSubmitAnswers();
            });

            mathBtnReset.addEventListener('click', resetTest);

            mathDropdownToggle.addEventListener('click', () => {
                mathDropdownToggle.classList.toggle('active');
                mathDropdownContent.classList.toggle('show');
            });

            document.addEventListener('click', (e) => {
                if (!mathDropdownToggle.contains(e.target) && !mathDropdownContent.contains(e.target)) {
                    mathDropdownToggle.classList.remove('active');
                    mathDropdownContent.classList.remove('show');
                }
            });

            mathShortAnswerInput.addEventListener('input', () => {
                if (!mathIsSubmitted) {
                    // Real-time update as user types
                    saveCurrentShortAnswer();
                }
            });
        });
    </script>
</body>
</html>
