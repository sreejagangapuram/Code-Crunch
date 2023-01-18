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
        background-color: #e5b76d;
        text-align: center;
        width: 500px;
        height: 500px;
        border-radius: 2em;
        margin: auto;
        display: none;
    }


    
</style>


<!-- timer: this is just a draft; this will be moved to inside the game later in development (E) --> 


<!--- end (E) --->


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
    <br><div id="game-container">
        <!-- game goes here-->
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
</script>

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
}
 
.flip-card {
  background-color: transparent;
  width: 100px;
  height: 100px;
  perspective: 1000px;
}
 
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
}
.flip-card-inner.flip {
  transform: rotateY(180deg);
}
 
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
 
.flip-card-front {
  background-color: #800000;
  border-radius: 6px;
  border-color: #FFFFFF
  color: black;
}
 
.flip-card-back {
  background-color: #ffffff;
  border-radius: 6px;
  transform: rotateY(180deg);
}
 
img {
  border-radius: 6px;
}
 
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 60px;
}
 
</style>
</head>
<body>
  <div class="grid-container">
    <div class="flip-card" id="card1">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card2">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card3">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card4">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card5">
    <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card6">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card7">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card8">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card9">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card10">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card11">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card12">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card13">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card14">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card15">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
    <div class="flip-card" id="card16">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img src="{{site.baseurl}}/images/b.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
        <div class="flip-card-back">
          <img src="{{site.baseurl}}/images/image2.jpg" alt="Avatar" style="width:100px;height:100px;">
        </div>
      </div>
    </div>
<script>
  const flipCard1 = document.getElementById("card1");
  const flipCard2 = document.getElementById("card2");
  const flipCard3 = document.getElementById("card3");
  const flipCard4 = document.getElementById("card4");
  const flipCard5 = document.getElementById("card5");
  const flipCard6 = document.getElementById("card6");
  const flipCard7 = document.getElementById("card7");
  const flipCard8 = document.getElementById("card8");
  const flipCard9 = document.getElementById("card9");
  const flipCard10 = document.getElementById("card10");
  const flipCard11 = document.getElementById("card11");
  const flipCard12 = document.getElementById("card12");
  const flipCard13 = document.getElementById("card13");
  const flipCard14 = document.getElementById("card14");
  const flipCard15 = document.getElementById("card15");
  const flipCard16 = document.getElementById("card16");
  flipCard1.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard2.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard3.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard4.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard5.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard6.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard7.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard8.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard9.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard10.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard11.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard12.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard13.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard14.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard15.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
  flipCard16.addEventListener("click", function() {
    this.querySelector('.flip-card-inner').classList.toggle('flip');
  });
</script>
