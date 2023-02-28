<html>
  <style>
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
  <table id="highscores">
    <tr>
      <th>Username</th>
      <th>High Score</th>
    </tr>
  </table>  
  <script>
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
</html>
