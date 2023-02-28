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
      height: 480px;
      border-radius: 1em;
      margin: auto;
      display: none;
  }
#tcontainer{
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
  margin-left: 10px;
  width: 150px;
  height: 40px;
  border-radius: 40px;
  background-color: #90fff0;
  color: #000000;
  box-shadow: 0 0 0em;
}
.bar-2{
  width: 150px;
  height: 40px;
  border-radius: 40px;
  background-color: #ffe100;
  color: #000000;
  box-shadow: 0 0 0em;
}
.bar-3{
  width: 150px;
  height: 40px;
  border-radius: 40px;
  background-color: #ff00c8;
  color: #000000;
  box-shadow: 0 0 0em;
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
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 400px;
  height: 300px;
}
.progressbar {
  width: 200px;
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
#highscores{
  font-family: 'Fira Mono', monospace !important;
  border-collapse: collapse;
  width: 100%;
  border-radius: 0.75em;
  box-shadow: 0 0 0.5em #175178;
  padding: 10px 10px;
  display: table;
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
          - Close the game and click play to replay!
      </blockquote>
      <br><button type="button" id="closing-gamestart">Close</button>
  </div>
</div>

<div class="play-container">
  <button type="button" id="play-button">Play</button>
  <button type="button" id="close-game">Close</button>
  <div id="tcontainer">
    <div id = "timer">
      <table id="bar">
        <tr>
          <th><button type="button" class="bar-1"><span id="match-count">Score</span></button></th>
          <th><button type="button" class="bar-2">STAR</button></th>
          <th><button type="button" class="bar-3">HS</button></th>
          <th><div id='progressbar'></div></th>
        </tr>
      </table>
    </div>
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
        <img id="popup-image" src="{{site.baseurl}}/images/m.png">
      </div>
    </section>
  </div><br>
</div>
<table id="highscores">
  <tr>
    <th>Username</th>
    <th>Score</th>
  </tr>
</table>  
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
      document.getElementById("tcontainer").style.display = "block";
      document.getElementById("play-button").style.display = "none";
      document.getElementById("close-game").style.display = "block";
  }

  closegame.onclick = function() {
      document.getElementById("game-container").style.display = "none";
      document.getElementById("tcontainer").style.display = "none";
      document.getElementById("play-button").style.display = "block";
      document.getElementById("close-game").style.display = "none";
  }

var possibleCardSides = ["{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png", "{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png"];
var flippedCards = [];
var matchedCards = [];
var locked = false;
var flipTimeout = 700;
function getRandomIndex(length) {
return Math.floor(Math.random() * length);
}
function getRandomSide(randomIndex) {
var side;
randomIndex = getRandomIndex(possibleCardSides.length);
side = possibleCardSides[randomIndex];
possibleCardSides.splice(randomIndex, 1);
return side;
}
function assignCardSides($cardSides) {
for (var i = 0; i < 16; i++) {
  $($cardSides[i]).html('<img src="' + getRandomSide() + '">');
}
possibleCardSides = ["{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png", "{{site.baseurl}}/images/aw.png", "{{site.baseurl}}/images/dc.png", "{{site.baseurl}}/images/fp.png", "{{site.baseurl}}/images/gh.png", "{{site.baseurl}}/images/html.png", "{{site.baseurl}}/images/p.png", "{{site.baseurl}}/images/so.png", "{{site.baseurl}}/images/vs.png"];
}
function unFlipped($card) {
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
function reset($cardSides, $flipCardElements) {
assignCardSides($cardSides);
matchedCards = [];
$flipCardElements.removeClass("flipped");
}
$(document).ready(function(){
var $playButton = $("#play-button");
var $canvas = $("#canvas");
var $flipCardElements = $(".flip-card");
var $cardSides = $(".flip-card .flip-card-back");
var $replay = $("#close-game");
var $matchCountDisplay = $("#match-count"); // added a display element to show the match count
var matchCounter = 0; // added a counter for matched cards
var totalCards = $flipCardElements.length; // added a variable to store the total number of cards
assignCardSides($cardSides);
$playButton.on("click", function() {
  $canvas.removeClass("hidden");
});
$canvas.on("click", ".flip-card-front, .flip-card-front h2", function(event) {
  if(event.target != this || locked){ return true; }
  var $card = $(event.target).closest(".flip-card");
  if (unFlipped($card)) {
    $card.addClass("flipped");
    flippedCards.push($card);
  }
  if (flippedCards.length === 2) {
    if (areMatching(flippedCards)) {
      matchCounter++; // increment the counter for each matching pair
      matchedCards.push(flippedCards[0], flippedCards[1]);
      $matchCountDisplay.text(matchCounter); // update the match count display
      if (matchCounter == (totalCards / 2)) { // check if all cards are matched
        alert("All cards matched!"); // display the alert
      }        
    } else {
      locked = true;
      hideCards(flippedCards);
    }
    flippedCards = [];
  }
});
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
  createProgressbar('progressbar', '30s', function() {
    container.classList.add("frozen");
    document.getElementById("popup-image").style.display = "block";
    console.log(matchCounter);
    // Get user ID from local storage
    const userId = localStorage.getItem("userid");

    // Define the endpoint URL
    const url = "https://dncodecrunch.duckdns.org/api/leadersfiltered/score";
    const url1 = "https://dncodecrunch.duckdns.org/api/highscores/hscore";
    const url2 = "https://dncodecrunch.duckdns.org/api/lastscore/score";

    // Define the request parameters as an object
    const data = {
      username: userId,
      score: matchCounter
    };
    
//    const data1 = {
//      username: userid,
//      score: matchCounter
//    }
    // Define the request options
    const options = {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify(data)
    };
//    const options1 = {
//      method: "POST",
//      headers: {
//        "Content-Type": "application/json"
//      },
//      body: JSON.stringify(data1)
//    };

    // Send the request with fetch()
    fetch(url, options)
      .then(response => {
        if (!response.ok) {
          throw new Error("Network response was not ok");
        }
        return response.json();
      })
      .then(data => {
        console.log(data);
      })
      .catch(error => {
        console.error("There was a problem with the fetch operation:", error);
      });

        
    });
});
$replay.on("click", function() {
  const container = document.getElementById("game-container");
  reset($cardSides, $flipCardElements);
  matchCounter = 0;
  $matchCountDisplay.text(matchCounter);
  container.classList.remove("frozen");
  document.getElementById("popup-image").style.display = "none";
});

})
setInterval(updateHighscores, 5000);

updateHighscores();

function updateHighscores() {
  $.ajax({
    url1: "https://dncodecrunch.duckdns.org/api/highscores/retrieve",
    type: 'GET',
    dataType: 'json',
    success: function(data1) {
      $('#highscores tr').slice(1).remove();

      data1.forEach(function(hscore) {
        $('#highscores').append('<tr><td>' + hscore.username + '</td><td>' + hscore.hscore + '</td></tr>');
      });
    },
    error: function(error) {
      console.log(error);
    }
  });
}
</script>