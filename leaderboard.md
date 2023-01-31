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
      left: 60%;
      justify-content: right;
      width: fit-content;
      height: fit-content;
      display: inline-block;
      padding: 10px;
    }

    #search{
      width: 200px;
      border-radius: 20px;
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
      margin: 5px;
      font-size: 10pt;
      color: #20323f;
      border-width: 2px;
      box-shadow: 0 0 1em #175178;
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

  <script>
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
