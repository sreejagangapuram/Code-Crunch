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
