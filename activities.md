<style>
  #howto-popup{
      text-align: center;
      display: none;
      margin: auto;
  }

  #how-to-text{
      text-align: left;
  }

  .play-container{
      text-align: center;
  }

  .howto-container{
      text-align: center;
  }

  #closing-gamestart{
      background-color: rgb(223, 109, 109);
      visibility: hidden;
  }

  #howto-button{
      background-color: #FCC05F;
      color: rgb(43, 41, 41);
      
  }

  #play-button{
      display: block;
      margin: auto;
  }
  
  #close-game{
      display: none;
      margin: auto;
      background-color: rgb(223, 109, 109);
  }

  #game-container{
      position: relative !important;
      background-color: #e5b76d;
      text-align: center;
      width: 480px;
      height: 555px;
      border-radius: 1em;
      margin: auto;
      display: none;
  }
#bar{
  margin-top: 40px;
  font-family: 'Fira Mono', monospace !important;
  border-collapse: collapse;
  width: 100%;
  border-radius: 0.75em;
  box-shadow: 0 0 0.5em #175178;
  padding: 10px 10px;
}
.bar-1 {
  margin-left: 90px;
  width: 100px;
}
.bar-2{
  margin-left: 10px;
  width: 100px;
}
.bar-3{
  margin-right: 50px;
  width: 100px;
}
#game {
  justify-self: center;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);
  width: 450px;
  height: 450px;  
}
.flip-card {
  background-color: transparent;
  width: 100px;
  height: 100px;
  perspective: 1000px;
  margin-top: 0px;
  position: relative;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}
.flip-card figure {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}
.flip-card .flip-card-front {
  width: 100px;
  height: 100px;
  background-color: #800000;
  border-radius: 6px;
}
.flip-card .flip-card-back {
  width: 100px;
  height: 100px;
  background-color: white;
  transform: rotateY(180deg);
  border-radius: 6px;
}
.flip-card.flipped {
  transform: rotateY(180deg);
}
#canvas{
  position: relative;
  display: block;
  padding-top: 22px;
  margin: 21px
}
img {
  border-radius: 20px;
}    
.frozen {
  pointer-events: none;
  opacity: 1;
}
.frozen-text {
  display: none;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 36px;
  font-weight: bold;
  font-family: "Lucida Console", "Monaco", monospace;
  color: #ff9304;
  text-align: center;
}
.frozen .frozen-text {
  display: block;
}
#popup-image {
  position: absolute;
  display: none;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 400px;
  height: 300px;
}
.progressbar {
  width: 80%;
  margin: 25px auto;
  border: solid 1px #000;
  border-radius: 6px;
}
.progressbar .inner {
  height: 15px;
  animation: progressbar-countdown;
  animation-duration: 40s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  animation-play-state: paused;
  animation-timing-function: linear;
  border-radius: 6px;
}
@keyframes progressbar-countdown {
  0% {
    width: 100%;
    background: #66D3FA;
  }
  100% {
    width: 0%;
    background: #F00;
  }
}
</style>

<div class="howto-container">
  <h2>Welcome To Our Site:</h2>
  <blockquote id = "how-to-text">Are you a first timer? Don't worry! Continue to read the instructions below to familiarize yourself with our site and learn to play Code Crunch!</blockquote>
  <button type="submit" id="howto-button">How to Play</button>
  <div class="howto-popup" id="howto-popup">
      <h2>Instructions for playing code crunch.</h2>
      <blockquote id = "how-to-text">
          - Navigate to the login page, then login with your email and make a password. 
          - Then, come back to this "Game" bar.
          - Click "start!" Now a thirty second clock will begin. 
          - Click on a card to turn it over.
          - Match the rest before the time runs out!
      </blockquote>
      <br><button type="button" id="closing-gamestart">Close</button>
  </div>
</div>

<div class="play-container">
  <button type="button" id="play-button">Play</button>
  <button type="button" id="close-game">Close</button>
  <div id = "timer">
    <table id="bar">
      <tr>
        <th><button type="button" class="bar-1">HS</button></th>
        <th><button type="button" class="bar-2">STAR</button></th>
        <th><button type="button" class="bar-3">TIMER</button></th>
      </tr>
    </table>
  </div>
  <br><div id="game-container">
      <!-- game goes here-->
      <section id="canvas" class="hidden">
      <div id='progressbar'></div>
      <div id="game">
        <div id="flip-card-1" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-2" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-3" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-4" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-5" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-6" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-7" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-8" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-9" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-10" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-11" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-12" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-13" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-14" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-15" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <div id="flip-card-16" class="flip-card">
          <figure class="flip-card-front"></figure>
          <figure class="flip-card-back"></figure>
        </div>
        <img id="popup-image" src="/images/m.png">
      </div>
    </section>
  </div><br>
</div>

<script>
  var howtobutton = document.getElementById("howto-button");
  var closing = document.getElementById("closing-gamestart");
  var playbutton = document.getElementById("play-button");
  var closegame = document.getElementById("close-game");
  howtobutton.onclick = function() {
      howtobutton.style.visibility = "hidden";
      document.getElementById("howto-popup").style.display = "block";
      closing.style.visibility = "visible";
  }
  closing.onclick = function() {
      document.getElementById("howto-popup").style.display = "none";
      howtobutton.style.visibility = "visible";
      closing.style.visibility = "hidden";
  }

  playbutton.onclick = function() {
      document.getElementById("game-container").style.display = "block";
      document.getElementById("play-button").style.display = "none";
      document.getElementById("close-game").style.display = "block";
  }

  closegame.onclick = function() {
      document.getElementById("game-container").style.display = "none";
      document.getElementById("play-button").style.display = "block";
      document.getElementById("close-game").style.display = "none";
  }

var possibleCardFaces = ["{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png", "{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png"];
var flippedCards = [];
var matchedCards = [];
var locked = false;
var flipTimeout = 700;
function getRandomIndex(length) {
return Math.floor(Math.random() * length);
}
function getRandomFace(randomIndex) {
var face;
randomIndex = getRandomIndex(possibleCardFaces.length);
face = possibleCardFaces[randomIndex];
possibleCardFaces.splice(randomIndex, 1);
return face;
}
function assignCardFaces($cardFaces) {
for (var i = 0; i < 16; i++) {
  $($cardFaces[i]).html('<img src="' + getRandomFace() + '">');
}
possibleCardFaces = ["{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png", "{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png"];
}
function isNotFlipped($card) {
return !$card.hasClass("flipped");
}
function areMatching(flippedCards) {
return (flippedCards[0].html() === flippedCards[1].html());
}
function hideCards(flippedCards) {
setTimeout(function() {
  $(flippedCards[0]).removeClass("flipped");
  $(flippedCards[1]).removeClass("flipped");
  locked = false;
}, flipTimeout);
}
function reset($cardFaces, $flipCardElements) {
assignCardFaces($cardFaces);
matchedCards = [];
$flipCardElements.removeClass("flipped");
}
$(document).ready(function(){
var $playButton = $("#play-button");
var $canvas = $("#canvas");
var $flipCardElements = $(".flip-card");
var $cardFaces = $(".flip-card .flip-card-back");
var $replay = $("#replay-button");
assignCardFaces($cardFaces);
$playButton.on("click", function() {
  $canvas.removeClass("hidden");
});
$canvas.on("click", ".flip-card-front, .flip-card-front h2", function(event) {
  if(event.target != this || locked){ return true; }
  var $card = $(event.target).closest(".flip-card");
  if (isNotFlipped($card)) {
    $card.addClass("flipped");
    flippedCards.push($card);
  }
  if (flippedCards.length === 2) {
    if (areMatching(flippedCards)) {
      matchedCards.push(flippedCards[0], flippedCards[1]);
    } else {
      locked = true;
      hideCards(flippedCards);
    }
    flippedCards = [];
  }
});
$replay.on("click", function() {
  reset($cardFaces, $flipCardElements);
});
})
function createProgressbar(id, duration, callback) {
  var progressbar = document.getElementById(id);
  progressbar.className = 'progressbar';
  var progressbarinner = document.createElement('div');
  progressbarinner.className = 'inner';
  progressbarinner.style.animationDuration = duration;
  if (typeof(callback) === 'function') {
    progressbarinner.addEventListener('animationend', callback);
  }
  progressbar.appendChild(progressbarinner);
  progressbarinner.style.animationPlayState = 'running';
}
addEventListener('load', function() {
  const container = document.getElementById("game-container");
  createProgressbar('progressbar', '3s', function() {
    // add jquery
    container.classList.add("frozen");
    document.getElementById("popup-image").style.display = "block";
    // or here
  });
});
</script>