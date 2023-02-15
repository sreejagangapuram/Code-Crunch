<html>
  <style>
    #leaderboard{
      font-family: 'Fira Mono', monospace !important;
      border-collapse: collapse;
      width: 100%;
      border-radius: 0.75em;
      box-shadow: 0 0 0.5em #175178;
      padding: 10px 10px;
    }
    
    #finder{
      position: absolute;
      top: 235px;
      left: 58%;
      justify-content: right;
      width: fit-content;
      height: fit-content;
      display: inline-block;
      padding: 10px;
    }

    #search{
      width: 200px;
      border-radius: 13px;
      text-align: center;
      height: fit-content;
      background-color: transparent !important;
      border: none;
      color: white;
      box-shadow: 0 0 1em #175178;
    }

    ::placeholder{
      color: white; 
    }
    #search-button{
      height: 40px;
      width: 40px;
      background-color: #e5b76d;
      border-radius: 50%;
      display: inline-block;
      justify-content: center;
      padding: 0px;
      margin: 10px;
      font-size: 10pt;
      color: #20323f;
      border-width: 2px;
      box-shadow: 0 0 1em #175178;
    }
    #RegistrationError{
      text-align: center;
      align-self: center;
      background-color: rgb(223, 109, 109, 0.60);
      border-radius: 0.5em;
      min-height: 25px;
      width: 100%;
      line-height: 25px;
      display: none;
    }
    #RegistrationSuccess{
      text-align: center;
      align-self: center;
      background-color: rgb(109, 223, 109, 0.60);
      border-radius: 0.5em;
      min-height: 25px;
      width: 100%;
      line-height: 25px;
      display: none;
    }
  </style>
  <form id = "finder">
    <input type="text" id="search" name="searchbar" placeholder="Search">
    <button type="button" id = "search-button"><i class="fa-solid fa-magnifying-glass"></i></button>
  </form>
  <h2>Leaderboard</h2>
  <table id="leaderboard">
    <tr>
      <th>Username</th>
      <th>Score</th>
    </tr>
  </table>  
  <form id = "test">
    <input type="text" id="usernametesting" name="username bar" placeholder="add username">
    <input type="text" id="testing" name="testingbar" placeholder="add score">
    <button type="button" id = "enterbutton">Enter</button>
  </form>
  <br><div id = "RegistrationError">
    <h3><b>ERROR: Registration Failed. Try Again. </b></h3>
  </div>
  <div id = "RegistrationSuccess">
    <h3><b>Registration Successful. </b></h3>
  </div>
  <script>
  
  $("#enterbutton").click(async function() {
  let form = document.getElementById("test");
  let formData = new FormData(form);
  let username = formData.get("username bar");
  let score = formData.get("testingbar");

  let url = "http://localhost:8086/api/leadersfiltered/score";

  const headers = {
    'Content-Type': 'application/json',
  };
  const body = JSON.stringify({username: username, score: score});

  try {
    let response = await fetch(url, {
      mode: 'cors',
      method: 'POST',
      headers: headers,
      body: body
    });
    let result = await response.json();
    console.log('Success:', result);
    if (result.status == "success") {
      document.getElementById("RegistrationSuccess").style.display = "block";
      document.getElementById("RegistrationError").style.display = "none";
    } else {
      document.getElementById("RegistrationError").style.display = "block";
      document.getElementById("RegistrationSuccess").style.display = "none";
    }
  } catch (error) {
    console.error('Error:', error);
  }
});

    // Update the leaderboard every 5 seconds
    setInterval(updateLeaderboard, 5000);

    // Retrieve the leaderboard data and create the table when the page is loaded
    updateLeaderboard();

    function updateLeaderboard() {
      $.ajax({
        url: './leaderboard.json',
        type: 'GET',
        dataType: 'json',
        success: function(data) {
          // Clear the current leaderboard on update
          $('#leaderboard tr').slice(1).remove();

          // Adds the new scores to the leaderboard from the json data
          data.forEach(function(score) {
            $('#leaderboard').append('<tr><td>' + score.username + '</td><td>' + score.score + '</td></tr>');
          });
        },
        error: function(error) {
          console.log(error);
        }
      });
    }
  </script>
</html>
