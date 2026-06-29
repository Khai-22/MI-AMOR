<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Happy Anniversary - Mi Amor Chel</title>

<style>

*{

    margin:0;

    padding:0;

    box-sizing:border-box;

    font-family:'Georgia', serif;

}

body{

    min-height:100vh;

    display:flex;

    justify-content:center;

    align-items:center;

    overflow:hidden;

    /* Put your photo in the same folder and name it couple.jpg */

    background:

        linear-gradient(rgba(0,0,0,.45), rgba(0,0,0,.45)),

        url('couple.jpg');

    background-size:cover;

    background-position:center;

    background-repeat:no-repeat;

}

/* Floating hearts */

.heart{

    position:absolute;

    color:#FFD700;

    pointer-events:none;

    animation:float 8s linear infinite;

    opacity:.8;

    z-index:1;

}

@keyframes float{

    0%{

        transform:translateY(100vh) scale(0);

    }

    100%{

        transform:translateY(-120vh) scale(1.5);

    }

}

/* Envelope */

.envelope-wrapper{

    position:relative;

    width:340px;

    height:230px;

    cursor:pointer;

    z-index:10;

}

.envelope{

    position:relative;

    width:100%;

    height:100%;

    background:#FFE082;

    border-radius:0 0 15px 15px;

    box-shadow:0 15px 35px rgba(0,0,0,.35);

}

/* Front of envelope */

.envelope::before{

    content:"";

    position:absolute;

    bottom:0;

    width:0;

    height:0;

    border-left:170px solid transparent;

    border-right:170px solid transparent;

    border-bottom:120px solid #FFD54F;

    z-index:4;

}

/* Flap */

.flap{

    position:absolute;

    top:0;

    width:0;

    height:0;

    border-left:170px solid transparent;

    border-right:170px solid transparent;

    border-top:120px solid #FBC02D;

    transform-origin:top;

    transition:1.4s ease;

    z-index:5;

}

/* Letter */

.letter{

    position:absolute;

    left:20px;

    top:15px;

    width:300px;

    min-height:390px;

    background:rgba(255,255,255,.96);

    border-radius:20px;

    padding:30px;

    text-align:center;

    box-shadow:0 15px 30px rgba(0,0,0,.25);

    transform:translateY(90px);

    opacity:0;

    transition:all 2s ease;

    z-index:2;

}

.open .flap{

    transform:rotateX(180deg);

    z-index:0; /* moves behind */

}

.open .letter{

    transform:translateY(-210px);

    opacity:1;

    z-index:10;

}

.click{

    position:absolute;

    bottom:-55px;

    width:100%;

    text-align:center;

    color:white;

    font-size:20px;

    text-shadow:0 0 10px black;

    animation:pulse 1.5s infinite;

}

@keyframes pulse{

    50%{

        transform:scale(1.08);

    }

}

/* Message animation */

.message{

    opacity:0;

    transform:translateY(20px);

}

.show .message{

    animation:showText 1.5s forwards;

}

.show .message:nth-child(2){animation-delay:.8s;}

.show .message:nth-child(3){animation-delay:1.6s;}

.show .message:nth-child(4){animation-delay:2.4s;}

.show .message:nth-child(5){animation-delay:3.2s;}

@keyframes showText{

    to{

        opacity:1;

        transform:translateY(0);

    }

}

h1{

    color:#C49000;

    margin-bottom:15px;

}

.special{

    font-size:55px;

    color:#E6A700;

    margin:15px 0;

    font-weight:bold;

}

p{

    color:#555;

    font-size:20px;

    margin:15px 0;

    line-height:1.5;

}

.roses{

    font-size:45px;

    margin-top:20px;

}

</style>

</head>

<body>

<div class="envelope-wrapper" id="envelope">

    <div class="envelope">

        <div class="flap"></div>

        <div class="letter" id="letter">

            <h1 class="message">💛 Happy Anniversary 💛</h1>

            <div class="message special">

                5 + 6 ✨

            </div>

            <p class="message">

                Mi Amor Chel ❤️

            </p>

            <p class="message">

                Every moment with you is my favorite memory,

                and every day with you is a beautiful blessing.

            </p>

            <div class="message roses">

                🌹 &nbsp; 🌹

            </div>

        </div>

    </div>

    <div class="click">

        💌 Click the envelope to open 💌

    </div>

</div>

<script>

const envelope = document.getElementById("envelope");

const letter = document.getElementById("letter");

envelope.addEventListener("click", () => {

    envelope.classList.add("open");

    setTimeout(() => {

        letter.classList.add("show");

    }, 1500);

}, {once:true});

function createHeart(){

    const heart = document.createElement("div");

    heart.className = "heart";

    heart.innerHTML = "💛";

    heart.style.left = Math.random() * 100 + "vw";

    heart.style.fontSize = (15 + Math.random()*25) + "px";

    heart.style.animationDuration = (5 + Math.random()*5) + "s";

    document.body.appendChild(heart);

    setTimeout(() => {

        heart.remove();

    }, 8000);

}

setInterval(createHeart, 300);

</script>

</body>

</html>
