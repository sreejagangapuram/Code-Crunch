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
    

  </style>
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
