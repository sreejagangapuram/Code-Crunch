<style>
    #howto-popup{
        text-align: center;
        visibility: hidden;
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
</style>

<div class="play-container">
    <h2>Welcome To Our Site:</h2>
    <blockquote id = "how-to-text">Are you a first timer? Don't worry! Continue to read the instructions below to familiarize yourself with our site and learn to play Code Crunch!</blockquote>
    <br><button type="submit" class="howto-button">Play</button>
</div>

<div class="howto-container">
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
<script>
    var howtobutton = document.getElementById("howto-button");
    var closing = document.getElementById("closing-gamestart");
    howtobutton.onclick = function() {
        howtobutton.style.visibility = "hidden";
        document.getElementById("howto-popup").style.visibility = "visible";
        closing.style.visibility = "visible";
    }
    closing.onclick = function() {
        document.getElementById("howto-popup").style.visibility = "hidden";
        howtobutton.style.visibility = "visible";
        closing.style.visibility = "hidden";
    }
</script>
