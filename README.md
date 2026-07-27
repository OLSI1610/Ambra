# Ambra
<!DOCTYPE html>
<html lang="sq">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>❤️ Për Ambra ❤️</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:
    radial-gradient(circle at top,#ff9ecb,#4b003b,#120022);
    color:white;
    font-family:'Arial',sans-serif;
}

.container{
    text-align:center;
    padding:25px;
    z-index:5;
}

h1{
    font-size:35px;
    text-shadow:0 0 15px pink;
}

p{
    font-size:20px;
}

input{
    padding:15px;
    border-radius:30px;
    border:none;
    text-align:center;
    font-size:20px;
    width:200px;
}

button{
    margin-top:15px;
    padding:14px 30px;
    border:none;
    border-radius:30px;
    background:#ff4f9a;
    color:white;
    font-size:18px;
    cursor:pointer;
}

button:hover{
    transform:scale(1.05);
}

.hidden{
    display:none;
}

#message{
    max-width:700px;
    margin:auto;
    line-height:1.7;
    font-size:21px;
    text-shadow:0 0 10px white;
}

.bears{
    font-size:70px;
    margin:20px;
    animation:hug 2s infinite;
}

@keyframes hug{
    50%{
        transform:scale(1.15);
    }
}

.fall{
    position:absolute;
    top:-50px;
    animation:fall linear infinite;
    z-index:1;
}

@keyframes fall{
    to{
        transform:translateY(110vh) rotate(360deg);
    }
}

.glow{
    animation:glow 2s infinite alternate;
}

@keyframes glow{
    from{
        text-shadow:0 0 5px white;
    }
    to{
        text-shadow:0 0 25px pink;
    }
}

</style>
</head>

<body>


<div class="container" id="lock">

<h1 class="glow">
Një surprizë vetëm për ty ❤️
</h1>

<p>
Shkruaj kodin sekret
</p>

<input 
id="password"
type="password"
placeholder="1610">

<br>

<button onclick="unlock()">
Hape ❤️
</button>

<p id="error"></p>

</div>



<div class="container hidden" id="love">

<h1 class="glow">
Për Ambra ❤️
</h1>

<div class="bears">
🐻 Olsi ❤️ Ambra 🐻
</div>

<div id="message"></div>

<h2>
Forever & Always ♾️❤️
</h2>

</div>
<script>

const letter = 
"Ambra jeme vogël, gjithçkaja që i jep kuptim jetës time, nuk e di nëse do ta kuptosh ndonjëherë sa shumë të dua, jo se nuk e kupton ti por se çdo fjalë duket e vogël për atë që ndiej për ty. Ti je arsyeja pse buzëqesh pa e kuptuar, qetësia ime kur gjithçka tjetër duket e vështirë dhe personi me të cilin dua të ndaj çdo moment të jetës sime. Faleminderit që je me mua, që më do, më kupton dhe më bën të ndihem djali më i lumtur në gjithë botën. Sado të mërzis ti e di që qëllimi im nuk është ai. Të dua me gjithë shpirt o jet dhe më fal ❤️";


function unlock(){

let code = document.getElementById("password").value;

if(code === "1610"){

document.getElementById("lock").classList.add("hidden");

document.getElementById("love").classList.remove("hidden");


createLove();


typeWriter();


}

else{

document.getElementById("error").innerHTML =
"Provo përsëri zemra ime ❤️";

}

}



function createLove(){

let items=[
"❤️",
"🌹",
"🌸",
"✨",
"💗"
];


for(let i=0;i<120;i++){

let element=document.createElement("div");

element.className="fall";

element.innerHTML =
items[Math.floor(Math.random()*items.length)];


element.style.left =
Math.random()*100+"%";


element.style.fontSize =
(15+Math.random()*35)+"px";


element.style.animationDuration =
(3+Math.random()*6)+"s";


element.style.animationDelay =
Math.random()*5+"s";


document.body.appendChild(element);

}

}



function typeWriter(){

let i=0;

let box=document.getElementById("message");


let speed=35;


function write(){

if(i < letter.length){

box.innerHTML += letter.charAt(i);

i++;

setTimeout(write,speed);

}

}


write();

}


</script>

</body>
</html>