<script>  

    let message = "";
    let username = "";
    let password = "";
    let inputUsername;
    let inputPassword;
    let showAlert = false;
    let data = {jean: {username: "jean", password: "1234"},
                    karina: {username: "karina", password: "12345"}};

    function login(e) {

        if (!username) {            
            inputUsername.focus();
            message = "REGISTER USERNAME !";
            showAlert = true;
        } else if (!password) {
            inputPassword.focus();
            message = "REGISTER PASSWORD !";
            showAlert = true;
        } else {

            if (username in data) {
                if (data[username].password === password) {
                    alert("ingresastes")
                } else {
                    inputPassword.focus();
                    message = "PASSWORD INVALID !";
                    showAlert = true;
                }
            } else {
                inputUsername.focus();
                message = "USERNAME INVALID !";
                showAlert = true;
            }
        }   

    }            
</script>

<main class="container d-flex justify-content-center align-items-center vh-100">  
        
    { #if showAlert }     
    <div class="alert alert-warning alert-dismissible fade show fixed-top" role="alert">
        <strong> { message } </strong>
        <button type="button" class="btn-close" on:click={ () => showAlert = false }></button>
    </div>   
    { /if }    

    <div class="login">        
        <h1 class="text-center mt-4">LOGIN</h1>

        <div class="form-floating mt-4">
            <input
                type="text"                
                class="form-control"
                id="floatingInput"
                placeholder="Username"
                maxlength="10"
                bind:value={ username }
                bind:this={ inputUsername }
                required/>
            <label for="floatingInput">Username</label>
        </div>

        <div class="form-floating mt-2">
            <input
                type="password"                   
                class="form-control"
                id="floatingPassword"
                placeholder="Password"
                maxlength="10"
                bind:value={ password }
                bind:this={ inputPassword }
                required/>
            <label for="floatingPassword">Password</label>
        </div>
        <div class="form-floating mt-4">
            <button class="w-100 btn btn-lg btn-primary" type="submit" on:click={ login }>SIGN IN </button>  
        </div>            
    </div>
  
</main>  
    

<style>
  .login {   
    width: 280px;   
    height: 330px;
    background-color: yellow;
    border-radius: 20px;
    background-color: rgba(255, 255, 255, 0.5);
  }  
  .form-floating {
    width: 80%;
    left: 10%;
  } 
</style>