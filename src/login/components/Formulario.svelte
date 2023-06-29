<script>
  import { createEventDispatcher } from "svelte";
  import Cookies from "js-cookie";
  import Toastr from "toastr";
  import "toastr/build/toastr.css" 
 
  const dispatch = createEventDispatcher();

  let inputUsername;
  let inputPassword;

  async function validarUsuario() {
    let username = inputUsername.value;
    let password = inputPassword.value;

    if (!username) {
      inputUsername.focus();     
      Toastr.info("Registra tu usuario.");
    } else if (!password) {
      inputPassword.focus();
      Toastr.info("Registra tu contraseña.");
    } else {
      const data = { username, password };
      const url = "http://192.168.1.59:8000/login";
      const options = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(data),
      };

      try {
        const response = await fetch(url, options);

        if (response.ok) {
          const user = await response.json();

          if (user.valid) {
            Cookies.set("token", user.token);
            dispatch("cookieCreated");
          } else {
            Toastr.warning("Credenciales invalidas.");
          }
        } else {
          Toastr.error("Ocurrió un error.");
        }
      } catch (error) {
        Toastr.error("Servidor fuera de linea.");
      }
    }
  }
</script>


  <div class="login d-flex justify-content-center align-items-center flex-column">
    <h1 class="text-center mb-4"><strong>LOGIN</strong></h1>

    <div class="form-floating mb-1">
      <input
        type="text"
        class="form-control"
        placeholder="Usuario"
        maxlength="10"
        bind:this={inputUsername}
      />
      <label for="floatingInput">Usuario</label>
    </div>

    <div class="form-floating mb-3">
      <input
        type="password"
        class="form-control"
        placeholder="Contraseña"
        maxlength="10"
        bind:this={inputPassword}
      />
      <label for="floatingPassword">Contraseña</label>
    </div>

    <div class="form-floating">
      <button
        class="w-100 btn btn-primary btn-md"
        type="submit"
        on:click={validarUsuario}
      >
        <strong>INGRESAR</strong>
      </button>
    </div>
  </div>


<style>
 
  .login {
    width: 200px;
    height: 310px;
    border-radius: 16px;   
    box-shadow: 0px 0px 10px 4px rgba(24, 24, 24, 0.2);
    min-width: 200px;
    background-image: linear-gradient(to top, rgba(243, 238, 238, 0.6) 0%,rgba(240, 236, 236, 0.6) 100%);
  }

  .form-floating {
    width: 80%;
    margin: 0 auto;
  }  
  
  @media (min-width: 500px) {
  .login {
    width: 280px;
    height: 340px;
  }
}
</style>
