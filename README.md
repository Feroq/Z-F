# Z-F
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sonsuza Dek Z🤍F</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial;}
body{
background:linear-gradient(135deg,#050505,#111);
color:white;
text-align:center;
overflow:hidden;
}

canvas{
position:fixed;
inset:0;
z-index:-1;
}

/* LOGIN */
#login{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
}

.box{
background:rgba(255,255,255,.08);
backdrop-filter:blur(18px);
padding:30px;
border-radius:25px;
width:300px;
}

input{
width:100%;
padding:12px;
border:none;
border-radius:20px;
margin-top:15px;
text-align:center;
}

button{
padding:12px 25px;
border:none;
border-radius:25px;
margin-top:15px;
cursor:pointer;
transition:.3s;
}

button:hover{transform:scale(1.05);}

.shake{animation:shake .4s;}

@keyframes shake{
0%{transform:translateX(0);}
25%{transform:translateX(-10px);}
50%{transform:translateX(10px);}
75%{transform:translateX(-10px);}
100%{transform:translateX(0);}
}

/* SITE */
#site{
display:none;
padding:25px;
height:100vh;
overflow-y:auto;
}

.heart{
font-size:60px;
animation:pulse 1.5s infinite;
}

@keyframes pulse{
50%{transform:scale(1.2);}
}

/* GALERI */
.slider{
display:flex;
gap:20px;
overflow-x:auto;
padding:20px;
scroll-snap-type:x mandatory;
}

.slider::-webkit-scrollbar{display:none;}

.card{
min-width:250px;
scroll-snap-align:center;
}

.card img{
width:250px;
height:330px;
object-fit:cover;
border-radius:20px;
cursor:pointer;
transition:.3s;
}

.card img:hover{transform:scale(1.05);}

.card p{
margin-top:10px;
color:#ddd;
}

/* POPUP */
#popup{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,.9);
justify-content:center;
align-items:center;
z-index:999;
}

#popup img{
max-width:90%;
max-height:90%;
border-radius:20px;
}

/* FLASH */
.flash{
position:fixed;
inset:0;
background:white;
animation:flash .5s;
z-index:9999;
}

@keyframes flash{
0%{opacity:0;}
30%{opacity:1;}
100%{opacity:0;}
}

/* HEART BURST */
.burst{
position:fixed;
animation:up 1s linear forwards;
font-size:20px;
z-index:9999;
}

@keyframes up{
to{transform:translateY(-200px);opacity:0;}
}
</style>
</head
