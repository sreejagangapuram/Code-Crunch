## Sign In
> <h3>Tempory Non Functional Form By: Tirth</h3>

<html>
  <style>
    form {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: left !important;
        justify-content: left !important;
    }
    label {
        font-family: 'Fira Mono', monospace;
        font-size:1em;
    }
    input[type=text], input[type=password] {
        font-family: 'Fira Mono', monospace;
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        box-sizing: border-box;
        box-shadow: 0 0 0.5em #000;
        border-radius: 0.5em;
    }
    #login_submittion {
        align-self: center;
        font-family: 'Fira Mono', monospace;
        width: 100%;
        background-color: #6F8E67;
        color: white;
        padding: 10px 10px;
        max-width: 50%;
        max-height: 50px !important;
        margin: 8px 0;SS
        cursor: pointer;
        border-radius: 0.75em;
        box-shadow: 0 0 1em #175178;
    }
  </style>
  
  <br><form>
    <label for="user_id">Username</label>
    <input type="text" id="login_username" name="user_id" placeholder="JeraldLovesBlueberries" value=""><br>
    <label for="user_email">Email</label>
    <input type="text" id="login_email" name="user_email" placeholder="100%legit@emailAddress.pizza" value=""><br>
    <label for="user_password">Password</label>
    <input type="password" id="login_password" name="user_password" placeholder="P@$$w0rd" value=""><br>
    <button type="button" id="login_submittion"><h3>Login</h3></button>
  </form> 
  <script>
    document.getElementById("login_submittion").addEventListener("click", function(){
  // Get the entered username and password
  var username = document.getElementById("login_username").value;
  var password = document.getElementById("login_password").value;
  // Validate the username and password (e.g. check if they match a list of valid usernames and passwords)
  if (username == "test" && password == "test") {
    // If the username and password are valid, show the navbar and redirect the user to the main page
    showNavbar();
    window.location.href = "outline.html";
  } else {
    // If the username and password are invalid, display an error message
    alert("Invalid username or password");
  }
});
</script>