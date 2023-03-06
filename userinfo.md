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

  <h2 id='User'> User Info </h2>
  <h3>Find your personal stats in our game here: </h3>
  <br>
  <br>
  <h4>User:  </h4>
  <h4 id='TopScore'>Top Score:  </h4>
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
// let userid = localStorage.getItem("userid");
let userid = 'ekam'
try {
  fetch('https://dncodecrunch.duckdns.org/api/lastscore/retrieve', {
  // fetch('http://127.0.0.1:8080/api/lastscore/retrieve', {  
    'method': 'POST' ,
    'headers' : {'Content-Type': 'application/json'},
    'Access-Control-Allow-Origin': 'https://dncodecrunch.duckdns.org'
  // 'mode': 'cors',
    'body': JSON.stringify({'username':userid}),
  })
   .then(response => response.json())
   .then(data => {
console.log(data);
$('#lastscore tr').slice(1).remove();
//adds score row
// Adds the new scores to the leaderboard from the json data
$('#lastscore').append('<tr style="text-align:center"><td>'
      + data.score1 + '</td><td>'
      + data.score2 + '</td><td>'
      + data.score3 + '</td><td>'
      + data.score4 + '</td><td>'
      + data.score5 + '</td><td>'
      + data.score6 + '</td><td>'
     );
$('#User').append(userid);
$('#TopScore').append(Object.values(data).reduce((max,score) => score > max? score : max));

   });

    } catch(e){
        console.log(error);
        debugger;
    }

</script>
</html>