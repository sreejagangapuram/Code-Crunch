## Sign Up
<html>   
<form method = "post" id = "SignUpForm">
    <label for="user_name_signup">Username</label>
    <input type="text" id="user_name_signup" name="user_name_signup" placeholder="JhonnoLovesCats_10" value=""><br>
    <label for="user_email_signup">Email</label>
    <input type="text" id="user_email_signup" name="user_email_signup" placeholder="CatsAreCool@email.com" value=""><br>
    <label for="user_password_signup">Password</label>
    <input type="password" id="user_password_signup" name="user_password_signup" placeholder="1L0v3Mr.T1bbl3$" value=""><br>
    <button type="button" id="signup_submit"><h3>Sign Up</h3></button>
  </form> 
  <br><div id = "RegistrationError">
    <h3><b>ERROR: Registration Failed. Try Again. </b></h3>
  </div>
  <div id = "RegistrationSuccess">
    <h3><b>Registration Successful. </b></h3>
  </div>
  <style>
    #SignUpForm{
      max-height: 400px;
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
  <script>
    $("#signup_submit").click(async function() {
   var text = "HELLOOOOO"
    console.log(text)
    let user = document.getElementById("user_name_signup").value;
    let user_email = document.getElementById("user_email_signup").value;
    let pass = document.getElementById("user_password_signup").value;
    let url = "https://dncodecrunch.duckdns.org/api/users/create";
  
    const headers = {
        'Content-Type': 'application/json',
    };
    const body = JSON.stringify({username: user, email: user_email,  password: pass});

  try {
    let response = await fetch(url, {
        mode: 'cors',
        method: 'POST',
        headers: headers,
        body: body
    });
    let result = await response.json();
    console.log('Success:', result);
  if (result.status == "success"){
    document.getElementById("RegistrationSuccess").style.display = "none";
    document.getElementById("RegistrationError").style.display = "none";
  } else {
    document.getElementById("RegistrationError").style.display = "none";
    document.getElementById("RegistrationSuccess").style.display = "none";
  }
  } catch (error) {
    console.error('Error:', error);
  }

});
  </script>