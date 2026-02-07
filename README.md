<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💖</title>

<style>
body {
  margin: 0;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: radial-gradient(circle, #ffb6c1, #ff4d6d);
  font-family: 'Comic Sans MS', cursive;
  overflow: hidden;
}

.container {
  text-align: center;
  background: white;
  padding: 45px;
  border-radius: 30px;
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
}

h1 {
  font-size: 2.6rem;
  color: #e60073;
  margin-bottom: 30px;
}

button {
  font-size: 1.3rem;
  padding: 16px 35px;
  border-radius: 50px;
  border: none;
  cursor: pointer;
  transition: all 0.25s ease;
}

#yesBtn {
  background: #ff2e63;
  color: white;
}

#noBtn {
  background: #444;
  color: white;
  position: relative;
}

.firework {
  position: absolute;
  font-size: 2.2rem;
  animation: pop 1.3s ease-out forwards;
}

@keyframes pop {
  0% { transform: scale(0); opacity: 1; }
  100% { transform: scale(3); opacity: 0; }
}
</style>
</head>

<body>

<div class="container">
  <h1>💖 Will you be my Valentine? 💖</h1>
  <button id="yesBtn">Yes 💕</button>
  <button id="noBtn">No</button>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");

let noCount = 0;

noBtn.addEventListener("mouseover", () => {
  if (noCount === 0) return;
  noBtn.style.position = "absolute";
  noBtn.style.left = Math.random() * (window.innerWidth - 150) + "px";
  noBtn.style.top = Math.random() * (window.innerHeight - 80) + "px";
});

noBtn.addEventListener("click", () => {
  noCount++;
  noBtn.style.fontSize = (1.3 + noCount * 0.5) + "rem";
  noBtn.style.padding = (16 + noCount * 12) + "px";

  if (noCount === 1) noBtn.innerText = "there is no 'no' 😏";
  else if (noCount === 2) noBtn.innerText = "PRESS YES 😡";
  else if (noCount === 3) noBtn.innerText = "HANEENN !!! 😤";
  else noBtn.innerText = "press yes khls 😭";
});

yesBtn.addEventListener("click", () => {
  document.querySelector(".container").innerHTML =
    "<h1>🎉 YAYYYY!!! 😍💖🥰</h1><p>I knew you’d say yes 😉</p>";

  for (let i = 0; i < 30; i++) {
    const f = document.createElement("div");
    f.className = "firework";
    f.innerText = ["🎆","🎇","💖","💘","😍","🥰"][Math.floor(Math.random()*6)];
    f.style.left = Math.random() * 100 + "vw";
    f.style.top = Math.random() * 100 + "vh";
    document.body.appendChild(f);
    setTimeout(() => f.remove(), 1300);
  }
});
</script>

</body>
</html>
