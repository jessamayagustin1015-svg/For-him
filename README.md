<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Happy Valentine’s Day ❤️</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Poppins&display=swap');

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  color: #fff;
  text-align: center;
  overflow-x: hidden;
}

.container {
  padding: 40px 16px;
  max-width: 420px;
  margin: auto;
}

h1 {
  font-family: 'Playfair Display', serif;
  font-size: 2.4rem;
}

.card {
  background: rgba(255,255,255,0.18);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 22px;
  margin: 18px 0;
}

.heart {
  position: fixed;
  font-size: 1.5rem;
  animation: floatUp 2s ease-out forwards;
  pointer-events: none;
}

@keyframes floatUp {
  0% { opacity: 1; transform: translateY(0) scale(1); }
  100% { opacity: 0; transform: translateY(-120px) scale(1.8); }
}

iframe {
  border-radius: 12px;
}

#countdown {
  font-size: 1.2rem;
  margin-top: 10px;
}

.hidden {
  display: none;
}

footer {
  margin-top: 30px;
  font-size: 0.85rem;
  opacity: 0.85;
}
</style>
</head>

<body>

<div class="container">
  <h1>Happy Valentine’s Day ❤️</h1>
  <p>Tap anywhere for love ✨</p>

  <div class="card">
    <p>
      Loving you is my favorite thing.
      Every moment with you feels like home.
    </p>
  </div>

  <div class="card">
    <h3>Our Song 🎶</h3>
    <iframe 
      src="https://open.spotify.com/track/5xCsdnbeg7yhVX2qlRaDUw?si=UdWENVU_RBSZJhhlQdK0LA"
      width="100%" 
      height="152" 
      frameborder="0" 
      allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
    </iframe>
  </div>

  <div class="card">
    <h3>Something special unlocks in… ⏳</h3>
    <div id="countdown"></div>
  </div>

  <div id="loveLetter" class="card hidden">
    <h3>My Love Letter to You 💌</h3>
    <p>
      From the moment you walked into my life,
      everything felt warmer and brighter.
      I love the way you laugh, the way you care,
      and the way you make me feel so deeply loved.
      <br/><br/>
      I choose you. Today. Tomorrow. Always.
    </p>
  </div>

  <footer>
    Made with love, just for you ❤️
  </footer>
</div>

<script>
// 💖 Floating hearts on tap
document.addEventListener("click", function(e) {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerText = "❤️";
  heart.style.left = e.clientX + "px";
  heart.style.top = e.clientY + "px";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 2000);
});

// ⏳ COUNTDOWN TIMER
// 👉 CHANGE THIS DATE (YYYY-MM-DDT00:00:00)
const targetDate = new Date("2026-02-07T00:00:00").getTime();
const countdownEl = document.getElementById("countdown");
const letter = document.getElementById("loveLetter");

setInterval(() => {
  const now = new Date().getTime();
  const distance = targetDate - now;

  if (distance <= 0) {
    countdownEl.innerHTML = "It’s time ❤️";
    letter.classList.remove("hidden");
    return;
  }

  const days = Math.floor(distance / (1000 * 60 * 60 * 24));
  const hours = Math.floor((distance / (1000 * 60 * 60)) % 24);
  const minutes = Math.floor((distance / (1000 * 60)) % 60);
  const seconds = Math.floor((distance / 1000) % 60);

  countdownEl.innerHTML =
    `${days}d ${hours}h ${minutes}m ${seconds}s`;
}, 1000);
</script>

</body>
</html>
