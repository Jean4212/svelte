<script>  
    import iziToast from "izitoast";
    import 'izitoast/dist/css/iziToast.min.css';
    import 'izitoast/dist/js/iziToast.min.js';

    let username = "";
    let password = "";
    let inputUsername;
    let inputPassword;   
    let data = {jean: {username: "jean", password: "1234"},
                    karina: {username: "karina", password: "12345"}};

    const mensajeWarning = (mensaje) => {
        iziToast.warning({
            title: 'Caution',           
            message: mensaje,
            timeout: 1500,     
            position: 'topLeft'      
        });
    }

    function login(e) {        

        if (!username) {            
            inputUsername.focus();
            mensajeWarning("Register username!");
        } else if (!password) {
            inputPassword.focus();
            mensajeWarning("Register password!");
        } else {

            if (username in data) {
                if (data[username].password === password) {
                    alert("ingresastes")
                } else {
                    inputPassword.focus();
                    mensajeWarning("Invalid password!");
                }
            } else {
                inputUsername.focus();   
                mensajeWarning("Invalid username!");            
            }
        }   

    }            
</script>

<main class="container d-flex justify-content-center align-items-center vh-100">  

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