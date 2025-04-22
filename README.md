<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do List Premium | Somalie</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --somali-blue: #4189DD;
      --somali-blue-dark: #2A5A9A;
      --white: #FFFFFF;
      --light-gray: #F5F7FA;
      --dark-gray: #2C3E50;
      --black: #1A1A1A;
      --red: #E74C3C;
      --orange: #F39C12;
      --green: #2ECC71;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: var(--light-gray);
      color: var(--black);
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
    }

    .somali-flag-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: var(--somali-blue);
      z-index: -1;
    }

    .app-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 30px;
      background-color: rgba(255, 255, 255, 0.95);
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(5px);
      margin-top: 30px;
      margin-bottom: 30px;
    }

    /* Add all other CSS styles from the original here */
    /* ... */

    /* Corrected floating icon style */
    .floating-icon {
      position: fixed;
      width: 60px;
      opacity: 0.1;
      animation: float 8s ease-in-out infinite;
      z-index: -1;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-30px) rotate(5deg); }
    }
  </style>
</head>
<body>
  <div class="somali-flag-bg">
    <!-- Corrected SVG icons -->
    <svg class="floating-icon" style="top:15%; left:5%" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
      <path d="M50,10 L70,30 L70,60 L60,60 L60,90 L40,90 L40,60 L30,60 L30,30 Z" fill="white"/>
      <path d="M50,5 L55,10 L45,10 Z" fill="white"/>
    </svg>
    
    <svg class="floating-icon" style="top:75%; left:85%" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
      <circle cx="50" cy="50" r="40" fill="none" stroke="white" stroke-width="2"/>
      <path d="M50,10 A40,40 0 0,1 50,90" fill="none" stroke="white" stroke-width="2"/>
    </svg>
  </div>

  <button id="dark-mode-toggle">
    <i class="fas fa-moon"></i>
  </button>

  <div class="app-container">
    <header>
      <h1><i class="fas fa-tasks"></i> To-Do List Premium</h1>
      <p>Organisez votre journée avec style 🇸🇴</p>
    </header>

    <!-- Rest of your HTML content -->
    <!-- ... -->

  </div>

  <script>
    // Your JavaScript code here
    document.addEventListener('DOMContentLoaded', function() {
      // All your existing JavaScript
      // ...
    });
  </script>
</body>
</html>
