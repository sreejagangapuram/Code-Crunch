<html>
  <style>
    #lastscore{
      font-family: 'Fira Mono', monospace !important;
      border-collapse: collapse;
      width: 100%;
      border-radius: 0.75em;
      box-shadow: 0 0 0.5em #175178;
      padding: 10px 10px;
      display: table;
    }
    
    #finder{
      position: absolute;
      top: 235px;
      left: 49%;
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
    .navigation-button{
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

    #return-button{
      background-color: #368ac2;
      color: white;
      border-color: white;
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

  <h2>User Info </h2>
  <h3>Find your personal stats in our game here: </h3>
  <br>
  <br>
  <h4>User:  </h4>
  <h4>Top Score:  </h4>
  <h4>Starred Games:  </h4>
  <h2>Last 6 Scores</h2>
  <table id="lastscore">
    <tr>
      <th>Score 1</th>
      <th>Score 2</th>
      <th>Score 3</th>
      <th>Score 4</th>
      <th>Score 5</th>
      <th>Score 6</th>
    </tr>
  </table>  
  <script>
//localStorage.getItem("lowScore")
  let userid = localStorage.getItem("userid");

//updates every 20 seconds
    // setInterval(retrieveScore, 5000);
//retrieve data/create table
    // await retrieveScore();
     (async function retrieveScore() {

    //     const headers = {
    //       method: 'GET',
    //       mode: 'cors',
    //       credentials: 'omit',
    //       headers: { 'Content-Type': 'application/json' },
    //     };
    //   debugger;

       try {
        const user_url = {{ url_for("https://dncodecrunch.duckdns.org/api/lastscore/retrieve", _username="ekam")|tojson }}
        fetch(user_url)
          .then(response => response.json())
          .then(scores => {
             $('#lastscore').append('<tr><td>' + score._score1 + '</td><td>' + score._score2 + '</td><td>' + score._score3 + '</td><td>' + score._score4 + '</td><td>' + score._score5 + '</td><td>' + score._score6 + '</td></tr>');
           });
        } catch(e){
         console.log(e);
        }

        // let result = await fetch('https://dncodecrunch.duckdns.org/api/lastscore/retrieve', data={"_username":"ekam"});
         let data = await result.json();
           console.log(data);
           $('#lastscore tr').slice(1).remove();
           //adds score row
           // Adds the new scores to the leaderboard from the json data
           // data.forEach(function(score) {
          // console.log(score);
            // $('#lastscore').append('<tr><td>' + score._score1 + '</td><td>' + score._score2 + '</td><td>' + score._score3 + '</td><td>' + score._score4 + '</td><td>' + score._score5 + '</td><td>' + score._score6 + '</td></tr>');
          // });

      // } catch(e){
        // console.log(error);
        // debugger;
      // }

      <!-- /* $.ajax({
        url: 'https://dncodecrunch.duckdns.org/api/lastscore/retrieve',
        type: 'GET',
        crossDomain: true,
        data: {username: userid},
        dataType: 'json',
        success: function(data) {
          debugger;
          // clears user table before update
          $('#lastscore tr').slice(1).remove();
//adds score row
 // Adds the new scores to the leaderboard from the json data
          data.forEach(function(score) {
            $('#lastscore').append('<tr><td>' + score._score1 + '</td><td>' + score._score2 + '</td><td>' + score._score3 + '</td><td>' + score._score4 + '</td><td>' + score._score5 + '</td><td>' + score._score6 + '</td></tr>');
          });
        },
        error: function(error) {
          console.log(error);
        }
      }); */ -->
    })()
  </script>
</html>