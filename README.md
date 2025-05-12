# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

ANSWER 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Animated Page</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      background-color: white;
      transition: background-color 0.5s ease;
    }

    body.dark {
      background-color: #222;
      color: white;
    }

    .animated-button {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      border: none;
      background-color: #3498db;
      color: white;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.3s ease;
      margin-right: 10px;
    }

    .animated-button:hover {
      transform: scale(1.1);
    }

    .shake {
      animation: shake 0.5s;
    }

    @keyframes shake {
      0% { transform: translateX(0); }
      25% { transform: translateX(-5px); }
      50% { transform: translateX(5px); }
      75% { transform: translateX(-5px); }
      100% { transform: translateX(0); }
    }
  </style>
</head>
<body>

  <h1>Welcome to My Animated Page</h1>

  <button class="animated-button" id="animateBtn">Click Me!</button>
  <button class="animated-button" id="themeBtn">Toggle Theme</button>

  <script>
    const animateBtn = document.getElementById('animateBtn');
    const themeBtn = document.getElementById('themeBtn');
    const body = document.body;

    animateBtn.addEventListener('click', () => {
      animateBtn.classList.add('shake');
      setTimeout(() => {
        animateBtn.classList.remove('shake');
      }, 500);
    });

    themeBtn.addEventListener('click', () => {
      body.classList.toggle('dark');
      localStorage.setItem('theme', body.classList.contains('dark') ? 'dark' : 'light');
    });

    window.addEventListener('DOMContentLoaded', () => {
      const savedTheme = localStorage.getItem('theme');
      if (savedTheme === 'dark') {
        body.classList.add('dark');
      }
    });
  </script>
</body>
</html>

