# Baby
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Eli 💜</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  overflow: hidden;
  background: linear-gradient(135deg, lavender, #ffd6e8);
  font-family: 'Georgia', serif;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #7a003c;
}

.container {
  text-align: center;
  z-index: 3;
  padding: 20px;
}

/* Typewriter text */
.typewriter {
  font-size: 26px;
  min-height: 70px;
}

/* Heart animation */
.heart {
  margin: 25px auto;
  font-size: 55px;
  animation: beat 1.4s infinite;
}

@keyframes beat {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.25); }
}

/* Envelope */
.envelope {
  margin: 30px auto;
  width: 180px;
  height: 120px;
  background: #fff;
  position: relative;
  border-radius: 8px;
  cursor: pointer;
  box-shadow: 0 8px 18px rgba(0,0,0,0.3);
  overflow: hidden;
}

.flap {
  position: absolute;
  width: 100%;
  height: 60%;
  background: #ff5c8a;
  clip-path: polygon(0 0, 100% 0, 50% 100%);
  transform-origin: top;
  transition: transform 1s ease;
}

.paper {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  color: #ff5c8a;
}

.envelope.open .flap {
  transform: rotateX(180deg);
}

/* Final message */
.final {
  display: none;
  font-size: 28px;
  margin-top: 25px;
  animation: fadeIn 2s ease forwards;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(15px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Floating items */
.floating {
  position: absolute;
  animation: float linear infinite;
  opacity: 0.9;
  pointer-events: none;
}

@keyframes float {
  from { transform: translateY(110vh); }
  to { transform: translateY(-10vh); }
}
</style>
</head>

<body>

<div class="container">
  <div class="typewriter" id="text"></div>

  <div class="heart">❤️</div>

  <div class="envelope" onclick="openLetter(this)">
    <div class="flap"></div>
    <div class="paper">💌 Click me</div>
  </div>

  <div class="final" id="final">
    You will always be my princess 👑🌻<br>
    <small>— Dada 💜</small>
  </div>
</div>

<script>
/* Typewriter effect */
const message = "Happy Rose Day, baby Eli 🌹\nDada loves you more than words can say.";
let i = 0;
const speed = 50;
const textDiv = document.getElementById("text");

function type() {
  if (i < message.length) {
    textDiv.innerHTML += message.charAt(i) === "\n" ? "<br>" : message.charAt(i);
    i++;
    setTimeout(type, speed);
  }
}
type();

/* Envelope open */
function openLetter(el) {
  el.classList.add("open");
  document.getElementById("final").style.display = "block";
}

/* Floating roses & hearts */
const symbols = ["🌹","❤️","🤍","✨"];
for (let j = 0; j < 90; j++) {
  const item = document.createElement("div");
  item.classList.add("floating");
  item.innerHTML = symbols[Math.floor(Math.random() * symbols.length)];
  item.style.left = Math.random() * 100 + "vw";
  item.style.fontSize = (14 + Math.random() * 26) + "px";
  item.style.animationDuration = (7 + Math.random() * 8) + "s";
  document.body.appendChild(item);
}
</script>

</body>
</html>
