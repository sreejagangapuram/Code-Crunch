##  Login & Sign Up
> Login no Account no Problem Account Creation Below

## <br>Login
<html>
  <div>
    <br><form id = "LoginForm">
      <label for="user_id">Username</label>
      <input type="text" id="login_username" name="user_id" placeholder="JeraldLovesBlueberries" value=""><br>
      <label for="user_email">Email</label>
      <input type="text" id="login_email" name="user_email" placeholder="100%legit@emailAddress.pizza" value=""><br>
      <label for="user_password">Password</label>
      <input type="password" id="login_password" name="user_password" placeholder="P@$$w0rd" value=""><br>
      <button type="button" id="login_submittion"><h3>Login</h3></button>
    </form>
    <br><div id = "SignInError">
      <h3><b>ERROR: No Account Found With Matching Credentials.</b>
        <br><b>Don't have an account?</b> <a href="{{site.baseurl}}/SignIn"><b>Sign Up</b></a>
      </h3>
    </div>
  </div>
  
  <style>
    #SignInError{
      text-align: center;
      align-self: center;
      background-color: rgb(223, 109, 109, 0.60);
      border-radius: 0.5em;
      min-height: 50px;
      width: 100%;
      line-height: 50px;
      display: none;
    }
    
    #LoginForm{
      max-height: 400px;
    }  
  </style>
  
  <script>
    window.onload = function() {
        let userLoggedIn = sessionStorage.getItem("userLoggedIn");
        if (userLoggedIn === "true") {
            document.getElementById("navigation").style.visibility = "visible";
        } else {
            document.getElementById("navigation").style.visibility = "hidden";
        }
    }
    
    $('#login_submittion').click(async function() {
    let username = $('#login_username').val();
    let email = $('#login_email').val();
    let password = $('#login_password').val();
    let url = './login.json'; 

    const headers = {
        method: 'GET',
        mode: 'cors',
        credentials: 'omit',
        headers: {'Content-Type': 'application/json'},
    };
    try {
        const response = await fetch(url, headers);
        if (!response.ok) {
            throw new Error("Login Failed");
        }
        const data = await response.json();
        const user = data.users.find(user => user.username === username && user.password === password && user.email === email);
        if (user) {
            console.log("Login Successful");
            document.getElementById("navigation").style.visibility = "visible";
            localStorage.setItem("userLoggedIn", "true");
            document.getElementById("SignInError").style.display = "none";
        } 
        else {
            console.log("Login Failed");
            document.getElementById("SignInError").style.display = "block";
        }
    } catch(error) {
        console.log(error);
        document.getElementById("SignInError").style.display = "block";
    }

    
    /*function logout() {
    localStorage.setItem("userLoggedIn", "false");
    document.getElementById("navigation").style.visibility = "hidden";
}*/
});

  </script>  
</html>


