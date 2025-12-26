<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Vetrex Scripts</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      background: black;
      overflow: hidden;
      min-height: 100vh;
      color: white;
    }

    canvas {
      position: fixed;
      inset: 0;
      z-index: 0;
    }

    .container {
      position: relative;
      z-index: 1;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 20px;
      opacity: 0;
      animation: fadeIn 2s ease forwards;
    }

    @keyframes fadeIn {
      to { opacity: 1; }
    }

    .title {
      font-size: clamp(28px, 7vw, 42px);
      margin-bottom: 35px;
      color: white;
      text-shadow:
        0 0 6px #00ccff,
        0 0 18px #00ccff,
        0 0 30px #00ccff;
    }

    .btn {
      padding: 14px 50px;
      font-size: 18px;
      border-radius: 30px;
      background: transparent;
      color: white;
      cursor: pointer;
      border: 2px solid transparent;
      background-image:
        linear-gradient(black, black),
        linear-gradient(90deg, #00ccff, #8a2be2, #00ccff);
      background-origin: border-box;
      background-clip: padding-box, border-box;
      animation: borderGlow 4s linear infinite;
      transition: transform 0.3s ease;
      margin-bottom: 18px;
      width: 100%;
      max-width: 280px;
    }

    .btn:hover { transform: scale(1.06); }

    @keyframes borderGlow {
      from { filter: hue-rotate(0deg); }
      to { filter: hue-rotate(360deg); }
    }

    .link-box {
      display: none;
      margin-bottom: 20px;
      animation: fadeIn 0.8s forwards;
    }

    .link {
      margin-bottom: 10px;
      font-size: 15px;
      user-select: all;
      word-break: break-all;
    }

    .copy-btn {
      padding: 9px 26px;
      border-radius: 22px;
      background: #0a0a0a;
      color: white;
      border: 1px solid #00ccff;
      cursor: pointer;
    }

    .status {
      font-size: 13px;
      margin-top: 6px;
      color: #00ccff;
    }
  </style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="container">
  <div class="title">vetrex scripts</div>

  <!-- Discord -->
  <button class="btn" onclick="toggleLink('discordBox')">Discord</button>
  <div class="link-box" id="discordBox">
    <div class="link" id="discordLink">https://discord.gg/Gx5F6pZCw5</div>
    <button class="copy-btn" onclick="copyText('discordLink', 'discordStatus')">Копировать</button>
    <div class="status" id="discordStatus"></div>
  </div>

  <!-- TikTok -->
  <button class="btn" onclick="toggleLink('tiktokBox')">Tik Tok</button>
  <div class="link-box" id="tiktokBox">
    <div class="link" id="tiktokLink">https://www.tiktok.com/@vetrex1337.dev?_r=1&_t=ZS-92Wa8W9wwYZ</div>
    <button class="copy-btn" onclick="copyText('tiktokLink', 'tiktokStatus')">Копировать</button>
    <div class="status" id="tiktokStatus"></div>
  </div>
</div>

<script>
  /* Matrix background */
  const canvas = document.getElementById('matrix');
  const ctx = canvas.getContext('2d');

  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }

  resize();
  window.addEventListener('resize', resize);

  const symbols = ['0', '1'];
  const colors = ['#ffffff', '#00ccff', '#8a2be2'];
  const fontSize = 14;
  let columns = Math.floor(canvas.width / fontSize);
  let drops = Array.from({ length: columns }).fill(1);

  function draw() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.1)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.font = fontSize + 'px monospace';

    for (let i = 0; i < drops.length; i++) {
      const text = symbols[Math.floor(Math.random() * symbols.length)];
      ctx.fillStyle = colors[Math.floor(Math.random() * colors.length)];
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);

      if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }

  setInterval(draw, 33);

  function toggleLink(id) {
    const el = document.getElementById(id);
    el.style.display = el.style.display === 'block' ? 'none' : 'block';
  }

  // Clipboard-safe copy (fallback for restricted environments)
  function copyText(linkId, statusId) {
    const text = document.getElementById(linkId).innerText;
    const status = document.getElementById(statusId);

    try {
      const textarea = document.createElement('textarea');
      textarea.value = text;
      textarea.style.position = 'fixed';
      textarea.style.opacity = '0';
      document.body.appendChild(textarea);
      textarea.focus();
      textarea.select();

      const successful = document.execCommand('copy');
      document.body.removeChild(textarea);

      status.textContent = successful ? 'Ссылка скопирована' : 'Не удалось скопировать';
    } catch (err) {
      status.textContent = 'Копирование недоступно';
    }

    setTimeout(() => status.textContent = '', 2000);
  }
</script>

</body>
</html>
