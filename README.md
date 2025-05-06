
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Open Link</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: linear-gradient(to right bottom, rgb(26, 32, 44), rgb(74, 29, 150), rgb(91, 33, 182));
      color: #fff;
      font-family: Arial, sans-serif;
      height: 100vh;
      text-align: center;
    }
    #container {
      max-width: 600px;
      margin: 0 auto;
    }
    h1 {
      font-size: 3rem;
      margin: 0;
    }
    .button-container {
      margin-top: 20px;
    }
    button {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      margin: 0.5rem;
      animation: pulse 2s infinite;
    }
    button:hover {
      background-color: #45a049;
    }
    select {
      font-size: 1.2rem;
      padding: 0.5rem;
      margin-top: 20px;
    }
    @keyframes pulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(76, 175, 80, 0.4); }
      70% { transform: scale(1.1); box-shadow: 0 0 0 10px rgba(76, 175, 80, 0); }
      100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(76, 175, 80, 0); }
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>👇👇</h1>

    <select id="languageSelect" onchange="changeLanguage()">
      <option value="en">English</option>
      <option value="ru">Русский</option>
    </select>

    <div class="button-container">
      <button id="openLinkBtn" onclick="openLink()">Open</button>
    </div>
  </div>

  <script>
    const offers = [
      "https://mb9pmr0.vipsthelovehaven.com/lw4h4aw?s1=tteu1",
      "https://grzvkg.amurllove.com/?utm_source=da57dc555e50572d&ban=tiktok&j1=1&s1=212364&s2=2127914",
      "https://mb9pmr0.meethotlove.com/lwyrlwm?s1=tteu",
      "https://prev.affomelody.com/OcBh5R"
    ];
    const iosLink = "https://www.instagram.com/men.click_here0";
    const telegramOthers = "https://t.me/+VZ2a5LQI3whjYjgy";
    const selectedOffer = offers[Math.floor(Math.random() * offers.length)];

    function changeLanguage() {
      const lang = document.getElementById('languageSelect').value;
      if (lang === 'ru') {
        document.getElementById('openLinkBtn').textContent = 'Открыть';
        document.querySelector('h1').textContent = 'Жми на кнопку там 18+';
      } else {
        document.getElementById('openLinkBtn').textContent = 'Open';
        document.querySelector('h1').textContent = 'Click on the 18+ button';
      }
    }

    document.addEventListener("DOMContentLoaded", () => {
      const userLang = navigator.language || navigator.userLanguage;
      document.getElementById('languageSelect').value = userLang.includes('ru') ? 'ru' : 'en';
      changeLanguage();
    });

    const openLink = () => {
      const isAndroid = /Android/i.test(navigator.userAgent);
      const isIOS = /iPhone|iPad|iPod/i.test(navigator.userAgent);

      if (isAndroid) {
        const formattedUrl = selectedOffer.replace(/^https?:\/\//, '');
        window.location.href = `intent://${formattedUrl}#Intent;scheme=https;package=com.android.chrome;end`;
      } else if (isIOS) {
        window.location.href = iosLink;
      } else {
        window.location.href = telegramOthers;
      }
    };
  </script>
</body>
</html>
