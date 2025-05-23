<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>PUBG STYLISH NAMES</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron&display=swap');

    body {
      margin: 0;
      padding: 0;
      font-family: 'Orbitron', sans-serif;
      color: #00fff7;
      background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
      overflow-x: hidden;
      text-align: center;
    }

    #bgVideo {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      z-index: -1;
      filter: brightness(0.3) blur(2px);
    }

    h1 {
      margin-top: 40px;
      font-size: 3em;
      text-shadow: 0 0 15px #00fff7, 0 0 25px #00fff7;
    }

    #inputText {
      margin-top: 20px;
      padding: 10px;
      width: 80%;
      max-width: 400px;
      font-size: 1.2em;
      border-radius: 10px;
      border: none;
      outline: none;
      animation: neonGlow 2s infinite alternate;
    }

    @keyframes neonGlow {
      0% { box-shadow: 0 0 10px red, 0 0 20px red, 0 0 30px red; }
      50% { box-shadow: 0 0 10px lime, 0 0 20px lime, 0 0 30px lime; }
      100% { box-shadow: 0 0 10px blue, 0 0 20px blue, 0 0 30px blue; }
    }

    .tabs {
      margin-top: 20px;
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .tab {
      padding: 10px 20px;
      background: #00fff7;
      color: black;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
      font-weight: bold;
    }

    .tab:hover {
      background: #00c9a7;
    }

    #styledNames {
      margin-top: 20px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 15px;
      padding: 20px;
    }

    .styledName {
      padding: 10px;
      border-radius: 10px;
      background: rgba(0, 255, 247, 0.1);
      box-shadow: 0 0 15px #00fff7;
      font-size: 1.1em;
      transition: 0.3s;
      position: relative;
    }

    .styledName:hover {
      transform: scale(1.05);
      background: rgba(0, 255, 247, 0.3);
    }

    .copyButton {
      position: absolute;
      top: 5px;
      right: 5px;
      background: #00fff7;
      color: black;
      border: none;
      border-radius: 5px;
      padding: 2px 5px;
      cursor: pointer;
      font-size: 0.8em;
    }

    #moreButton {
      margin: 20px;
      padding: 10px 20px;
      background: #00fff7;
      color: black;
      border: none;
      border-radius: 10px;
      font-size: 1.2em;
      cursor: pointer;
      transition: 0.3s;
    }

    #moreButton:hover {
      background: #00c9a7;
    }

    #developer {
      position: fixed;
      right: 20px;
      bottom: 20px;
      font-size: 1em;
      color: #ffffff;
      text-shadow: 0 0 5px #fff, 0 0 10px #0ff, 0 0 15px #0ff;
      animation: rgb-glow 3s infinite alternate;
    }

    @keyframes rgb-glow {
      0% { text-shadow: 0 0 5px red, 0 0 10px red, 0 0 20px red; }
      50% { text-shadow: 0 0 5px lime, 0 0 10px lime, 0 0 20px lime; }
      100% { text-shadow: 0 0 5px blue, 0 0 10px blue, 0 0 20px blue; }
    }
  </style>
</head>
<body>

  <video autoplay muted loop id="bgVideo">
    <source src="https://assets.mixkit.co/videos/preview/mixkit-gun-firing-in-the-dark-23359-large.mp4" type="video/mp4">
  </video>

  <h1>PUBG STYLISH NAMES</h1>

  <input type="text" id="inputText" placeholder="Type your PUBG name here..." oninput="generateStyles()">

  <div class="tabs">
    <button class="tab" onclick="setLanguage('english')">English 🇬🇧</button>
    <button class="tab" onclick="setLanguage('urdu')">Urdu 🇵🇰</button>
    <button class="tab" onclick="setCategory('funny')">Funny 😂</button>
    <button class="tab" onclick="setCategory('dangerous')">Dangerous ☠️</button>
    <button class="tab" onclick="setCategory('clan')">Clan 🏹</button>
  </div>

  <div id="styledNames"></div>

  <button id="moreButton" onclick="generateStyles()">More 🔥</button>

  <div id="developer">DEVELOPER: ALYAN SAFDAR</div>

<script>
let language = 'english';
let category = 'funny';

const englishNames = {
  funny: ["CrazyShooter", "NoScopeKing", "PandaKiller", "MadDog🐶", "BoomHead🧨"],
  dangerous: ["DeathBringer", "SilentKiller", "DarkKnight", "BloodHunter", "Nightmare☠️"],
  clan: ["AlphaClan", "WolfPack", "ShadowSquad", "EliteForce", "DeadlyAssassins"]
};

const urduNames = {
  funny: ["پاگل شوٹر", "دیوانہ گنر", "ہنستا قاتل", "چلو مارو", "بندوق باز"],
  dangerous: ["موت کا قاصد", "خاموش قاتل", "رات کا شہزادہ", "خونخوار شکاری", "خوفناک سایہ"],
  clan: ["شاہین گروپ", "دھماکہ ٹیم", "بادل اسکواڈ", "طاقتور لشکر", "خطرناک مجاہدین"]
};

const fancyStyles = [
  (t) => `꧁${t}꧂`,
  (t) => `『${t}』`,
  (t) => `★彡${t}彡★`,
  (t) => `𓆩${t}𓆪`,
  (t) => `${t}ツ`,
  (t) => `♡${t}♡`,
  (t) => `☬${t}☬`,
  (t) => `♛${t}♛`,
  (t) => `乂${t}乂`,
  (t) => `⎊${t}⎊`,
  (t) => `⚡${t}⚡`,
  (t) => `♞${t}♞`,
  (t) => `🄷🄳 ${t} 🄷🄳`,
  (t) => `✘${t}✘`,
  (t) => `★${t}★`,
  (t) => `✪${t}✪`,
  (t) => `☠${t}☠`,
  (t) => `༒${t}༒`,
  (t) => `➳${t}➳`,
  (t) => `℣${t}℣`
];

function setLanguage(lang) {
  language = lang;
  generateStyles();
}

function setCategory(cat) {
  category = cat;
  generateStyles();
}

function generateStyles() {
  const input = document.getElementById('inputText').value || 'YourName';
  const styledNamesDiv = document.getElementById('styledNames');
  styledNamesDiv.innerHTML = '';

  if (input.trim() !== '' && input !== 'YourName') {
    fancyStyles.forEach(style => {
      const div = document.createElement('div');
      div.className = 'styledName';
      div.innerHTML = `${style(input)} <button class="copyButton" onclick="copyText(this)">Copy</button>`;
      styledNamesDiv.appendChild(div);
    });
  } else {
    let namesArray = (language === 'english') ? englishNames[category] : urduNames[category];

    for (let i = 0; i < 10; i++) {
      const div = document.createElement('div');
      div.className = 'styledName';
      let name = namesArray[Math.floor(Math.random() * namesArray.length)];
      div.innerHTML = `${name} <button class="copyButton" onclick="copyText(this)">Copy</button>`;
      styledNamesDiv.appendChild(div);
    }
  }
}

function copyText(btn) {
  const text = btn.parentElement.innerText.replace("Copy", "").trim();
  navigator.clipboard.writeText(text);
  btn.innerText = "🎉 Copied!";
  setTimeout(() => btn.innerText = "Copy", 1500);
}

window.onload = generateStyles;
</script>

</body>
</html>
