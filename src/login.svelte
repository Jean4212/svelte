<script>    
    import iziToast from "izitoast";
    import "izitoast/dist/css/iziToast.min.css";
    import "izitoast/dist/js/iziToast.min.js";
    import { createEventDispatcher } from 'svelte';
  
    const dispatch = createEventDispatcher();
       
    let inputUsername;
    let inputPassword;   

    const mostrarMensaje = (mensaje) => {
        iziToast.warning({
            title: "Caution",
            timeout: 1500,   
            position: "topLeft",
            message: mensaje  
        });
    }

    async function validarUsuario() {
        let username = inputUsername.value
        let password = inputPassword.value

        if (!username) {            
            inputUsername.focus();
            mostrarMensaje("Register username!");
        } else if (!password) {
            inputPassword.focus();
            mostrarMensaje("Register password!");
        } else {

            const url = "http://localhost:8000/login";
            const datos = {username, password};
            const options = {
                method: "POST",
                headers: {"Content-Type": "application/json"},
                body: JSON.stringify(datos)
            };

            const response = await fetch(url, options);          
            if (response.ok) {
                const responseJson = await response.json();
                
                if (!responseJson.username) {
                    inputUsername.focus();   
                    mostrarMensaje("Invalid username!");                 
                } else if (!responseJson.password) {
                    inputPassword.focus();
                    mostrarMensaje("Invalid password!");
                } else {
                    iziToast.success({
                        title: "Success",
                        timeout: 1500,   
                        position: "topLeft",
                        message: "Username and Password Valid !"  
                    });                   
                    dispatch("pulso");
                }
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
                bind:this={ inputPassword }
                required/>
            <label for="floatingPassword">Password</label>
        </div>

        <div class="form-floating mt-4">
            <button class="w-100 btn btn-lg btn-primary" type="submit" on:click={ validarUsuario }>SIGN IN</button>  
        </div>            
    </div>
  
</main>  

<style>
  .login {   
    width: 280px;   
    height: 330px;  
    border-radius: 20px;
    background-color: rgba(255, 255, 255, 0.5);
  }

  .form-floating {
    width: 80%;
    left: 10%;
  } 
</style>