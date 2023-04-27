<script>
    let message = "";
    let username = "";
    let password = "";
    let inputUsername;
    let inputPassword;
    
    function mostrarMensaje(e) {
        let data = {jean: {username: "jean", password: "1234"},
                    karina: {username: "karina", password: "12345"}};
        
        if (!username) {
            message = "Register username"
            inputUsername.focus()
            return
        }

        if (!password) {
            message = "Register password"
            inputPassword.focus()
            return
        }

        if (username in data){
            if (data[username].password === password) {
                alert("ingresastes")
            } else {
                message = "Password invalid"
                inputPassword.focus()

            }
        } else {
            message = "Username invalid"
            inputUsername.focus()
        }
    }            
</script>

<main class="container d-flex justify-content-center align-items-center vh-100">  
        
    {#if message}     
    <div class="alert alert-warning alert-dismissible fade show fixed-top" role="alert">
        <strong> {message}.</strong>
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>   
    {/if}    

    <div class="login">        
        <h1 class="text-center">LOGIN</h1>

        <div class="form-floating mt-3">
            <input
                type="text"                
                class="form-control"
                id="floatingInput"
                placeholder="Username"
                maxlength="10"
                bind:value={username}
                bind:this={inputUsername}
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
                bind:value={password}
                bind:this={inputPassword}
                required/>
            <label for="floatingPassword">Password</label>
        </div>

        <button class="w-100 btn btn-lg btn-primary mt-4" type="submit" on:click={mostrarMensaje}>SIGN IN </button>      
    </div>
  
</main>  
    

<style>
  
</style>