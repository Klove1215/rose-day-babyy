# rose-day-babyy
Rose Day Surprise for You
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Rose Day Babyyy 🌹</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{box-sizing:border-box}
body{
margin:0;
height:100vh;
font-family:'Poppins',sans-serif;
background:linear-gradient(135deg,#ff758f,#ffb3c6);
display:flex;
align-items:center;
justify-content:center;
overflow:hidden;
color:#6a040f;
}
.card{
width:90%;
max-width:420px;
background:rgba(255,255,255,.25);
backdrop-filter:blur(14px);
border-radius:25px;
padding:30px;
text-align:center;
box-shadow:0 25px 50px rgba(0,0,0,.25);
animation:fade 1s ease;
}
.hidden{display:none}
h1{margin:10px 0;color:#9d0208}
p{font-size:17px;line-height:1.6}
button{
margin:10px;
padding:14px 26px;
border:none;
border-radius:30px;
background:#ff4d6d;
color:#fff;
font-size:16px;
cursor:pointer;
transition:.3s;
}
button:hover{transform:scale(1.08)}
.no{
background:#adb5bd;
color:#333;
position:relative;
}
.rose{font-size:70px;animation:float 2.5s infinite}
@keyframes float{
0%{transform:translateY(0)}
50%{transform:translateY(-15px)}
100%{transform:translateY(0)}
}
@keyframes fade{
from{opacity:0;transform:scale(.9)}
to{opacity:1;transform:scale(1)}
}
.heart,.kiss{
position:absolute;
font-size:20px;
animation:fall 6s linear infinite;
opacity:.8;
}
.kiss{
font-size:26px;
animation:kissPop 2.5s ease forwards;
}
@keyframes fall{
to{transform:translateY(110vh)}
}
@keyframes kissPop{
0%{transform:scale(0) translateY(0);opacity:0}
50%{transform:scale(1.5);opacity:1}
100%{transform:scale(1) translateY(-120px);opacity:0}
}
.final{
font-size:19px;
color:#800f2f;
}
</style>
</head>

<body>

<audio id="music" loop>
<source src="https://cdn.pixabay.com/audio/2022/03/15/audio_9c07d64b9b.mp3">
</audio>

<div class="card" id="s1">
<div class="rose">🌹</div>
<h1>Happy Rose Day</h1>
<p>For the most beautiful rose in my life 💖</p>
<button onclick="go2()">Tap for Magic ✨</button>
</div>

<div class="card hidden" id="s2">
<h1>Hey Babyyy 🥰</h1>
<p>
Every rose reminds me of you 💕<br>
Soft, beautiful & perfect
</p>
<button onclick="go3()">Something Special 💝</button>
</div>

<div class="card hidden" id="s3">
<h1>One Honest Question 😳</h1>
<p class="final">
Not just for Rose Day…<br>
But for every day 🌹<br><br>
<b>Will you be mine, babyyy? 💍❤️</b>
</p>

<button onclick="yesClicked()">YES 💖</button>
<button class="no" id="noBtn" onmouseover="moveNo()">NO 🙈</button>
</div>

<div class="card hidden" id="s4">
<h1>💖 SHE SAID YES 💖</h1>
<p class="final">
Yayyy!!! 🥹❤️<br><br>
Come here… 💋💋💋<br>
I promise to choose you every single day 💞<br><br>
<b>Happy Rose Day, my babyyy 🌹</b>
</p>
</div>

<script>
const music=document.getElementById("music");

function go2(){
music.play();
s1.classList.add("hidden");
s2.classList.remove("hidden");
}
function go3(){
s2.classList.add("hidden");
s3.classList.remove("hidden");
}

function yesClicked(){
s3.classList.add("hidden");
s4.classList.remove("hidden");
startKissAnimation();
}

function moveNo(){
const btn=document.getElementById("noBtn");
const x=Math.random()*200-100;
const y=Math.random()*200-100;
btn.style.transform=`translate(${x}px,${y}px)`;
}

// Falling hearts (always)
setInterval(()=>{
const h=document.createElement("div");
h.className="heart";
h.innerHTML="❤️";
h.style.left=Math.random()*100+"vw";
h.style.animationDuration=(Math.random()*3+4)+"s";
document.body.appendChild(h);
setTimeout(()=>h.remove(),7000);
},350);

// Kiss animation on YES 💋
function startKissAnimation(){
for(let i=0;i<25;i++){
setTimeout(()=>{
const k=document.createElement("div");
k.className="kiss";
k.innerHTML="💋";
k.style.left=Math.random()*100+"vw";
k.style.top=Math.random()*60+"vh";
document.body.appendChild(k);
setTimeout(()=>k.remove(),2500);
},i*120);
}
}
</script>

</body>
</html>
