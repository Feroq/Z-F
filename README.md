<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sonsuza Dek Z🤍F</title>

<style>
body{
margin:0;
font-family:Arial;
background:linear-gradient(135deg,#050505,#111);
color:white;
text-align:center;
overflow:hidden;
}

/* LOGIN */
#login{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
}

.box{
background:rgba(255,255,255,0.08);
padding:30px;
border-radius:20px;
width:280px;
backdrop-filter:blur(10px);
}

input{
width:100%;
padding:12px;
border:none;
border-radius:15px;
margin-top:10px;
text-align:center;
}

button{
padding:10px 20px;
border:none;
border-radius:20px;
margin-top:10px;
cursor:pointer;
}

.shake{
animation:shake .4s;
}

@keyframes shake{
0%{transform:translateX(0);}
25%{transform:translateX(-8px);}
50%{transform:translateX(8px);}
75%{transform:translateX(-8px);}
100%{transform:translateX(0);}
}

/* SITE */
#site{
display:none;
padding:20px;
height:100vh;
overflow-y:auto;
}

.heart{
font-size:50px;
animation:pulse 1.5s infinite;
}

@keyframes pulse{
50%{transform:scale(1.2);}
}

/* GALERİ */
.gallery{
display:flex;
gap:15px;
overflow-x:auto;
padding:20px;
}

.gallery img{
width:220px;
height:300px;
object-fit:cover;
border-radius:15px;
cursor:pointer;
}

/* POPUP */
#popup{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,0.9);
justify-content:center;
align-items:center;
}

#popup img{
max-width:90%;
max-height:90%;
border-radius:10px;
}

/* STAR */
.star{
position:fixed;
width:3px;
height:3px;
background:white;
border-radius:50%;
animation:fall 4s linear infinite;
}

@keyframes fall{
from{transform:translateY(-10vh);opacity:1;}
to{transform:translateY(110vh);opacity:0;}
}
</style>
</head>

<body>

<!-- LOGIN -->
<div id="login">
<div class="box" id="box">
<h2>🤍 Gizli Sayfa</h2>
<input type="password" id="pass" placeholder="Şifre">
<button onclick="login()">Giriş Yap</button>
<p id="err"></p>
</div>
</div>

<!-- SITE -->
<div id="site">

<div class="heart">🤍</div>
<h1>Sonsuza Dek Z🤍F</h1>

<p id="days"></p>

<button onclick="toggleMusic()">🎵 Müziği Aç/Kapat</button>

<!-- MUSIC -->
<audio id="music" loop>
<source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<div class="gallery">

<img src="https://picsum.photos/id/1011/500/700" onclick="openImg(this.src)">
<img src="https://picsum.photos/id/1025/500/700" onclick="openImg(this.src)">
<img src="https://picsum.photos/id/1035/500/700" onclick="openImg(this.src)">
<img src="https://picsum.photos/id/1043/500/700" onclick="openImg(this.src)">

</div>

</div>

<!-- POPUP -->
<div id="popup" onclick="closeImg()">
<img id="big">
</div>

<script>

const password="ZeynepFeridun";

/* LOGIN */
function login(){
const p=document.getElementById("pass").value;
const box=document.getElementById("box");

if(p===password){
document.getElementById("login").style.display="none";
document.getElementById("site").style.display="block";
}else{
box.classList.add("shake");
setTimeout(()=>box.classList.remove("shake"),400);
document.getElementById("err").innerText="Yanlış şifre 🤍";
}
}

/* IMAGE */
function openImg(src){
document.getElementById("popup").style.display="flex";
document.getElementById("big").src=src;
}
function closeImg(){
document.getElementById("popup").style.display="none";
}

/* MUSIC */
function toggleMusic(){
const m=document.getElementById("music");
if(m.paused){
m.play();
}else{
m.pause();
}
}

/* DAYS */
const start=new Date("2024-01-01");
const now=new Date();
const diff=Math.floor((now-start)/86400000);
document.getElementById("days").innerText=diff+" gündür birlikte 🤍";

/* STARS */
setInterval(()=>{
const s=document.createElement("div");
s.className="star";
s.style.left=Math.random()*100+"vw";
document.body.appendChild(s);
setTimeout(()=>s.remove(),4000);
},200);

</script>

</body>
</html>
