## Sign Up
<html>   
<form method = "post" id = "SignUpForm">
    <label for="user_id_signup">Username</label>
    <input type="text" id="user_id_signup" name="user_id_signup" placeholder="JhonnoLovesCats" value=""><br>
    <label for="user_email_signup">Email</label>
    <input type="text" id="user_email_signup" name="user_email_signup" placeholder="CatsAreCool@email.com" value=""><br>
    <label for="user_password_signup">Password</label>
    <input type="password" id="user_password_signup" name="user_password" placeholder="1L0v3Mr.T1bbl3$" value=""><br>
    <button type="button" id="signup_submittion"><h3>Sign Up</h3></button>
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
    /*$("#registration_submit").click(async function() {
        let user = document.getElementById("user_id_signup").value;
        let user_email = document.getElementById("user_email_signup").value;
        let pass = document.getElementById("user_password_signup").value;
        let url = "";
        const headers = {
            method: 'POST',
            mode: 'cors',
            cache: 'default',
            credentials: 'include',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify({username: user, email: user_email,  password: pass}),
        };
        try {
            let response = await fetch(url, headers);
            let result = await response.json();
            console.log('Success:', result);
            if (result.status == "success"){
                document.getElementById("RegistrationSuccess").style.display = "block";
                document.getElementById("RegistrationError").style.display = "none";
            } else {
                document.getElementById("RegistrationError").style.display = "block";
                document.getElementById("RegistrationSuccess").style.display = "none";
            }
        } catch (error) {
            console.error('Error:', error);
        }
    });*/
  </script>
</html>