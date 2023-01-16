<html>
  <h2>Login & Sign Up</h2>
  <blockquote>Login no Account no Problem Account Creation Below</blockquote>
  <br><br><h2>Login</h2>
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
            document.getElementById("lognav").style.visibility = "hidden";
            localStorage.setItem("userLoggedIn", "true");
            localStorage.setItem("userid", username);
            document.getElementById("SignInError").style.display = "none";
            window.location.href = "{{site.baseurl}}/game";
            
        } 
        else {
            console.log("Login Failed");
            localStorage.setItem("userLoggedIn", "false");
            localStorage.setItem("userid", "null");
            document.getElementById("SignInError").style.display = "block";
        }
    } catch(error) {
        console.log(error);
        document.getElementById("SignInError").style.display = "block";
    }
});
/*
$('#login_submittion').click(async function() {
  let username = $('#login_username').val();
  let email = $('#login_email').val();
  let password = $('#login_password').val();
  let url = './login.json'; 

  const headers = {
    method: 'POST',
    mode: 'cors',
    credentials: 'omit',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify({username, email, password})
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
      document.getElementById("lognav").style.visibility = "hidden";
      localStorage.setItem("userLoggedIn", "true");
      document.getElementById("SignInError").style.display = "none";
      window.location.href = "{{site.baseurl}}/game";
    } 
    else {
      console.log("Login Failed");
      document.getElementById("SignInError").style.display = "block";
    }
  } catch(error) {
    console.log(error);
    document.getElementById("SignInError").style.display = "block";
  }
});*/


  </script>  
</html>


