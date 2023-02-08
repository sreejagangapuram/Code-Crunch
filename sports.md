<style>
  .play-container{
      text-align: center;
  }

  #closing-gamestart{
      background-color: rgb(223, 109, 109);
      visibility: hidden;
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
</style>
<span id="match-count"></span>
<div class="play-container">
  <button type="button" id="play-button">Play</button>
  <button type="button" id="close-game">Close</button>
  <br><div id="game-container">
      <section id="canvas" class="hidden">
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
      </div>
    </section>
  </div><br>
</div>

<script>
var playbutton = document.getElementById("play-button");
var closegame = document.getElementById("close-game");
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

var possibleCardSides = ["/images/aw.png", "/images/dc.png", "/images/fp.png", "/images/gh.png", "/images/html.png", "/images/p.png", "/images/so.png", "/images/vs.png", "/images/aw.png", "/images/dc.png", "/images/fp.png", "/images/gh.png", "/images/html.png", "/images/p.png", "/images/so.png", "/images/vs.png"];
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
possibleCardSides = ["/images/aw.png", "/images/dc.png", "/images/fp.png", "/images/gh.png", "/images/html.png", "/images/p.png", "/images/so.png", "/images/vs.png", "/images/aw.png", "/images/dc.png", "/images/fp.png", "/images/gh.png", "/images/html.png", "/images/p.png", "/images/so.png", "/images/vs.png"];
}
function notFlipped($card) {
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
var $replay = $("#replay-button");
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
  if (notFlipped($card)) {
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
$replay.on("click", function() {
  reset($cardSides, $flipCardElements);
  matchCounter = 0; // reset the counter
  $matchCountDisplay.text(matchCounter); // reset the match count display
});
})
</script>