<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>vetrex scripts</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Arial', sans-serif;
}

body {
    background: black;
    overflow: hidden;
    height: 100vh;
    color: white;
}

/* Canvas фон */
canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 0;
}

/* Контент */
.container {
    position: relative;
    z-index: 2;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 20px;
    animation: fadeIn 2s ease;
}

/* Заголовок */
.title {
    font-size: 36px;
    color: white;
    text-shadow:
        0 0 10px #00ccff,
        0 0 20px #00ccff,
        0 0 40px #00ccff;
    margin-bottom: 40px;
}

/* Кнопки */
.button {
    width: 85%;
    max-width: 320px;
    padding: 15px;
    margin: 12px 0;
    font-size: 18px;
    color: white;
    background: rgba(0,0,0,0.6);
    border-radius: 15px;
    border: 2px solid;
    cursor: pointer;
    animation: glow 3s infinite linear;
    transition: transform 0.3s;
}

.button:active {
    transform: scale(0.95);
}

/* Перелив обводки */
@keyframes glow {
    0% { border-color: #00ccff; box-shadow: 0 0 10px #00ccff; }
    50% { border-color: #a855f7; box-shadow: 0 0 15px #a855f7; }
    100% { border-color: #00ccff; box-shadow: 0 0 10px #00ccff; }
}

/* Блок ссылки */
.link-box {
    margin-top: 10px;
    display: none;
    flex-direction: column;
    align-items: center;
    animation: fadeIn 0.6s ease;
}

.link {
    font-size: 14px;
    color: #00ccff;
    word-break: break-all;
    margin-bottom: 8px;
}

.copy {
    padding: 8px 16px;
    border-radius: 10px;
    border: 1px solid #00ccff;
    background: transparent;
    color: white;
    cursor: pointer;
}

/* Анимация появления */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="container">
    <div class="title">vetrex scripts</div>

    <button class="button" onclick="toggleLink('discord')">Discord</button>
    <div class="link-box" id="discord">
        <div class="link">https://discord.gg/Gx5F6pZCw5</div>
        <button class="copy" onclick="copyText('https://discord.gg/Gx5F6pZCw5')">Копировать</button>
    </div>

    <button class="button" onclick="toggleLink('tiktok')">Tik Tok</button>
    <div class="link-box" id="tiktok">
        <div class="link">https://www.tiktok.com/@vetrex1337.dev?_r=1&_t=ZS-92Wa8W9wwYZ</div>
        <button class="copy" onclick="copyText('https://www.tiktok.com/@vetrex1337.dev?_r=1&_t=ZS-92Wa8W9wwYZ')">Копировать</button>
    </div>
</div>

<script>
/* Matrix фон */
const canvas = document.getElementById('matrix');
const ctx = canvas.getContext('2d');

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

const symbols = ['0','1'];
const fontSize = 14;
const columns = canvas.width / fontSize;
const drops = Array(Math.floor(columns)).fill(0);

function draw() {
    ctx.fillStyle = 'rgba(0,0,0,0.1)';
    ctx.fillRect(0,0,canvas.width,canvas.height);

    ctx.font = fontSize + 'px monospace';

    for(let i=0;i<drops.length;i++){
        const text = symbols[Math.floor(Math.random()*symbols.length)];
        const colors = ['#ffffff','#00ccff','#a855f7'];
        ctx.fillStyle = colors[Math.floor(Math.random()*colors.length)];
        ctx.fillText(text, i*fontSize, drops[i]*fontSize);

        if(drops[i]*fontSize > canvas.height && Math.random() > 0.95){
            drops[i] = 0;
        }
        drops[i]++;
    }
}

setInterval(draw, 50);

/* Логика кнопок */
function toggleLink(id){
    const el = document.getElementById(id);
    el.style.display = el.style.display === 'flex' ? 'none' : 'flex';
}

function copyText(text){
    navigator.clipboard.writeText(text);
    alert('Ссылка скопирована');
}
</script>

</body>
</html>
