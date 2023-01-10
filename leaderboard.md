<html>
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
          // Clear the current leaderboard
          $('#leaderboard tr').slice(1).remove();

          // Add the new scores to the leaderboard
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
