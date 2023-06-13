<script>
  import Trabajadores from "../../components/Trabajadores.svelte";
  import Horario from "./Horario.svelte";
  import Salud from "../../components/Salud.svelte";
  import Cookies from "js-cookie";

  let Menu = sessionStorage.getItem("Menu")

  console.log(Menu)
  function showMenu(menuId) {   
    sessionStorage.setItem("Menu", menuId);
    Menu = sessionStorage.getItem("Menu") 
  }

  function deleteCookies() {    
    Cookies.remove("token");
    sessionStorage.removeItem("Menu")
    location.href = location.href
  }
</script>

<div class="d-flex flex-column flex-sm-row">
  <div class="sidebar bg-light">       
    <ul class="nav nav-pills nav-flush flex-row flex-sm-column justify-content-between align-items-center px-2">
      <li class="nav-item">
        <button class="nav-link py-2 px-1 link-dark" on:click={() => showMenu("1")}>
          <i class="bi-bootstrap fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={() => showMenu("1")}>
          <i class="bi-house fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={() => showMenu("2")}>
          <i class="bi-truck fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={() => showMenu("3")}>             
          <i class="bi-calendar2-check fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={() => showMenu("4")}>
          <i class="bi-heart-pulse fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={() => showMenu("5")}>
          <i class="bi-people fs-1"/>
        </button>
      </li>
      <li class="nav-item">
        <button class="nav-link py-2 px-1" on:click={deleteCookies}>
          <i class="bi-box-arrow-left fs-1 text-danger"/>
        </button>
      </li>          
    </ul>
  </div>

  <div class="panel flex-grow-1">   
    {#if Menu === "1"}
      <p>Menu 1</p>
    {:else if Menu === "2"}
      <p>Menu 2</p>
    {:else if Menu === "3"}
      <Horario />
    {:else if Menu === "4"}
      <Salud />
    {:else if Menu === "5"}
      <Trabajadores />
    {/if}     
  </div>  
</div>
  
    

<style>
 
</style>