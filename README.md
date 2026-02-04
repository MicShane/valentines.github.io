<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine</title>

<style>
@font-face {
  font-family: 'CreameCake';
  src: url('CreameCake.ttf');
}

body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ffd1e6, #ffe6f2);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'CreameCake', cursive;
  overflow: hidden;
}

/* Floating hearts */
.heart {
  position: absolute;
  font-size: 18px;
  opacity: 0.35;
  animation: float 7s linear infinite;
}

@keyframes float {
  0% {
    transform: translateY(100vh) scale(0.8);
    opacity: 0;
  }
  30% { opacity: 0.4; }
  100% {
    transform: translateY(-10vh) scale(1.2);
    opacity: 0;
  }
}

/* Main content */
#content {
  text-align: center;
  z-index: 2;
}

h1 {
  color: #b86b8a;
  font-size: 3.2rem;
  margin-bottom: 20px;
}

.card {
  background: rgba(255,255,255,0.92);
  padding: 36px 46px;
  border-radius: 26px;
  box-shadow: 0 18px 40px rgba(0,0,0,0.15);
}

.card p {
  font-size: 1.5rem;
  color: #a84f72;
  margin-bottom: 28px;
}

.buttons {
  position: relative;
  height: 70px;
}

button {
  border: none;
  border-radius: 28px;
  cursor: pointer;
  position: absolute;
  font-family: 'CreameCake', cursive;
}

#yesBtn {
  background: #d86a9a;
  color: white;
  font-size: 1.2rem;
  padding: 12px 28px;
  left: 50%;
  transform: translateX(-70%);
}

#noBtn {
  background: #e6d0d9;
  color: #555;
  font-size: 0.9rem;
  padding: 8px 20px;
  left: 50%;
  transform: translateX(45%);
}

/* Love message */
#love {
  display: none;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(0.8);
  font-size: 4.5rem;
  color: #b45b7a;
  letter-spacing: 3px;
  animation: pop 1.4s ease forwards;
  z-index: 3;
}


@keyframes pop {
  from {
    opacity: 0;
    transform: translate(-50%, -50%) scale(0.8);
  }
  to {
    opacity: 1;
    transform: translate(-50%, -50%) scale(1);
  }
}

</style>
</head>

<body>

<script>
for (let i = 0; i < 25; i++) {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "❤";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = 14 + Math.random() * 20 + "px";
  heart.style.animationDuration = 5 + Math.random() * 5 + "s";
  heart.style.color = "#f2a1c2";
  document.body.appendChild(heart);
}
</script>

<div id="content">
  <h1>Welcome Mwoluuu</h1>

  <div class="card">
    <p>Will you be my Valentine</p>
    <div class="buttons">
      <button id="yesBtn">Yes</button>
      <button id="noBtn">No</button>
    </div>
  </div>
</div>

<div id="love">I Love You Chellom</div>

<script>
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const content = document.getElementById("content");
const love = document.getElementById("love");

noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * 160 - 80;
  const y = Math.random() * 40 - 10;
  noBtn.style.transform = `translate(${x}px, ${y}px)`;
});

yesBtn.addEventListener("click", () => {
  content.style.display = "none";
  love.style.display = "block";
});
</script>

</body>
</html>
