<html>
  <style>
    #userinfo{
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
  <h4>Find your personal stats in our game here: </h4>
  <br>
  <h2>Username:  </h2>