# Valentine<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Vanshu 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
*{box-sizing:border-box;font-family:'Poppins',sans-serif}
body{
  margin:0;height:100vh;overflow:hidden;
  background: linear-gradient(135deg,#ff758c,#ff7eb3);
  display:flex;align-items:center;justify-content:center;
}
.card{
  background: rgba(255,255,255,.25);
  backdrop-filter: blur(14px);
  border-radius:28px;
  padding:26px;
  width:92%;max-width:380px;
  text-align:center;color:#fff;
  box-shadow:0 25px 50px rgba(0,0,0,.35);
  animation:pop .8s ease;
}
@keyframes pop{from{transform:scale(.9);opacity:0}to{transform:scale(1);opacity:1}}

.photo{
  width:150px;height:150px;border-radius:50%;
  object-fit:cover;border:4px solid #fff;margin:10px auto 14px;
}
h1{font-size:30px;margin:6px 0}
p{font-size:15px;line-height:1.6}

.btns{margin-top:18px}
button{
  border:none;border-radius:30px;padding:12px 26px;
  font-size:16px;margin:8px;cursor:pointer
}
.yes{background:#ff4d6d;color:#fff}
.no{background:#444;color:#fff;position:absolute}

.emoji{
  position:fixed;bottom:-30px;font-size:26px;
  animation:float 6s linear forwards;
}
@keyframes float{
  to{transform:translateY(-110vh);opacity:0}
}

/* tap-to-play overlay */
.overlay{
  position:fixed;inset:0;background:rgba(0,0,0,.6);
  display:flex;align-items:center;justify-content:center;
  color:#fff;z-index:9
}
.overlay div{
  background:rgba(255,255,255,.2);
  backdrop-filter:blur(10px);
  padding:18px 22px;border-radius:18px;text-align:center
}
</style>
</head>

<body>

<!-- 🎵 Music -->
<audio id="bgm" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3" type="audio/mpeg">
</audio>

<!-- Tap to play -->
<div class="overlay" id="overlay" onclick="playMusic()">
  <div>
    <h3>Tap to feel the vibe 🎧💖</h3>
    <p>(Music + magic starts)</p>
  </div>
</div>

<div class="card" id="card">
  <!-- 🖼️ VANSU KI PHOTO -->
  <img class="photo" src="https://i.imgur.com/8Km9tLL.jpg" alt="Vanshu">

  <h1>Hey Vanshu 💕</h1>
  <p>
    Tumhari ek smile bhi<br>
    mere din ko special bana deti hai 🥹<br><br>
    Shayad words perfect na ho,<br>
    par feelings bilkul real hain ❤️
  </p>
  <p><b>— Vipul</b></p>

  <h2>Will you be my Valentine? 🌹</h2>

  <div class="btns">
    <button class="yes" onclick="yes()">YES 💖</button>
    <button class="no" onmouseover="moveNo()">NO 🙈</button>
  </div>
</div>

<script>
const emojis=["💖","💕","✨","🌸","😍","💫","💝"];

function rain(){
  const e=document.createElement("div");
  e.className="emoji";
  e.innerHTML=emojis[Math.floor(Math.random()*emojis.length)];
  e.style.left=Math.random()*100+"vw";
  document.body.appendChild(e);
  setTimeout(()=>e.remove(),6000);
}
setInterval(rain,280);

function moveNo(){
  const n=document.querySelector(".no");
  n.style.left=Math.random()*(innerWidth-120)+"px";
  n.style.top=Math.random()*(innerHeight-60)+"px";
}

function playMusic(){
  document.getElementById("bgm").play();
  document.getElementById("overlay").style.display="none";
}

function yes(){
  document.getElementById("card").innerHTML=`
    <h1>Yaaaay 💖✨</h1>
    <p>
      Tumne is Valentine ko<br>
      hamesha ke liye yaadgaar bana diya 🥹❤️
    </p>
    <img class="photo" src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif">
    <h2>— Vipul 🌸</h2>
  `;
}
</script>

</body>
</html>
