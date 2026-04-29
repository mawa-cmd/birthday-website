<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Royal Birthday 🎉</title>

<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&display=swap" rel="stylesheet">

<style>
body {
    margin:0;
    font-family:'Cinzel', serif;
    background:black;
    color:gold;
    text-align:center;
    overflow:hidden;
}

/* Entry Screen */
#entry {
    position:absolute;
    top:40%;
    width:100%;
}

button {
    padding:15px 40px;
    font-size:18px;
    border:none;
    border-radius:40px;
    background:gold;
    color:black;
    cursor:pointer;
}

/* Main */
#main {
    display:none;
    padding-top:50px;
}

/* Image animation */
#hero {
    width:280px;
    border-radius:20px;
    opacity:0;
    transform:scale(0.7);
    transition:1.5s;
    box-shadow:0 0 40px gold;
}

/* Title */
h1 {
    font-size:40px;
    margin-top:20px;
    opacity:0;
    transition:2s;
}

/* Glow */
.glow {
    text-shadow:0 0 10px gold, 0 0 30px orange;
}
</style>
</head>

<body>

<div id="entry">
    <h2>👑 Enter the Royal Celebration 👑</h2>
    <button onclick="start()">Enter 🏰</button>
</div>

<div id="main">
    <img id="hero" src="https://i.ibb.co/mCwhD8XW/D23760-C8-5859-4003-9-DE5-062-BA235501-C.jpg">

    <h1 id="title" class="glow">🎂 Happy Birthday Mujeeb Gondal 🎂</h1>

    <br>

    <button onclick="openWhatsApp()">💬 Send Thanks</button>
</div>

<!-- 🎵 Royal Music -->
<audio id="music">
<source src="https://cdn.pixabay.com/audio/2022/03/15/audio_3b3b4b7d93.mp3">
</audio>

<script>
function start(){
    document.getElementById("entry").style.display="none";
    document.getElementById("main").style.display="block";

    let music=document.getElementById("music");
    music.volume=0.2;
    music.play();

    setTimeout(()=>{
        document.getElementById("hero").style.opacity=1;
        document.getElementById("hero").style.transform="scale(1)";
    },500);

    setTimeout(()=>{
        document.getElementById("title").style.opacity=1;
    },1500);
}

function openWhatsApp(){
    window.open("https://wa.me/923107244699?text=Royal thanks 👑🔥");
}
</script>

</body>
</html>
