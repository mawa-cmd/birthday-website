<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Mujeeb 🎉</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;700&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: radial-gradient(circle, #1a2a6c, #b21f1f, #fdbb2d);
    overflow: hidden;
    color: white;
    text-align: center;
}

/* Start Screen */
#start {
    position: absolute;
    top: 40%;
    width: 100%;
}

button {
    padding: 15px 40px;
    font-size: 18px;
    border-radius: 50px;
    border: none;
    cursor: pointer;
    background: white;
    color: #b21f1f;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
    background: #ff4e50;
    color: white;
}

/* Main */
#main {
    display: none;
    padding-top: 60px;
}

h1 {
    font-size: 55px;
    animation: glow 2s infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px #fff; }
    to { text-shadow: 0 0 30px #ff00ff; }
}

/* Slideshow */
.slider {
    width: 300px;
    height: 200px;
    margin: 20px auto;
    border-radius: 20px;
    overflow: hidden;
}

.slider img {
    width: 100%;
    height: 100%;
    display: none;
}

.slider img.active {
    display: block;
}

/* Balloons */
.balloon {
    position: absolute;
    bottom: -100px;
    width: 40px;
    height: 60px;
    border-radius: 50%;
    animation: float 6s infinite;
}

@keyframes float {
    to { transform: translateY(-120vh); }
}

/* Confetti */
.confetti {
    position: fixed;
    width: 8px;
    height: 8px;
    top: -10px;
    animation: fall 3s linear infinite;
}

@keyframes fall {
    to { transform: translateY(100vh); }
}

/* Footer */
.footer {
    position: absolute;
    bottom: 10px;
    width: 100%;
}
</style>
</head>

<body>

<div id="start">
    <h2>🎁 Special Surprise 🎁</h2>
    <button onclick="start()">Start 🎉</button>
</div>

<div id="main">
    <h1>🎂 Happy Birthday<br>Mujeeb Gondal 🎂</h1>
    <p>May your life be full of happiness, success & love 💖</p>

    <!-- Slideshow -->
    <div class="slider">
        <img src="https://picsum.photos/300/200?1" class="active">
        <img src="https://picsum.photos/300/200?2">
        <img src="https://picsum.photos/300/200?3">
    </div>

    <br>

    <button onclick="openWhatsApp()">💬 Say Thanks</button>
    <button onclick="sendEmail()">📧 Email</button>
</div>

<audio id="music" loop>
<source src="https://www.bensound.com/bensound-music/bensound-happyrock.mp3">
</audio>

<script>
function start(){
    document.getElementById("start").style.display="none";
    document.getElementById("main").style.display="block";
    document.getElementById("music").play();
    balloons();
    confetti();
    slideshow();
}

// WhatsApp
function openWhatsApp(){
    let number="923107244699";
    let msg="Thank you for the amazing birthday surprise 🎉";
    window.open("https://wa.me/"+number+"?text="+encodeURIComponent(msg));
}

// Email
function sendEmail(){
    window.location.href="mailto:mawa.hub.official@gmail.com?subject=Thanks&body=Thank you for the birthday wish!";
}

// Balloons
function balloons(){
    for(let i=0;i<20;i++){
        let b=document.createElement("div");
        b.className="balloon";
        b.style.left=Math.random()*100+"vw";
        b.style.background=randomColor();
        b.style.animationDuration=(4+Math.random()*3)+"s";
        document.body.appendChild(b);
    }
}

// Confetti
function confetti(){
    setInterval(()=>{
        let c=document.createElement("div");
        c.className="confetti";
        c.style.left=Math.random()*100+"vw";
        c.style.background=randomColor();
        document.body.appendChild(c);
        setTimeout(()=>c.remove(),3000);
    },150);
}

// Slideshow
function slideshow(){
    let slides=document.querySelectorAll(".slider img");
    let i=0;
    setInterval(()=>{
        slides[i].classList.remove("active");
        i=(i+1)%slides.length;
        slides[i].classList.add("active");
    },2000);
}

function randomColor(){
    const colors=["#ff4e50","#f9d423","#00c9ff","#92fe9d","#ff00ff"];
    return colors[Math.floor(Math.random()*colors.length)];
}
</script>

<div class="footer">
    <p>Made with ❤️ by Mawa Hub</p>
</div>

</body>
</html>
