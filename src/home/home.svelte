<script>
    import Trabajadores from "./components/Trabajadores.svelte";
    import Horario from "./components/Horario.svelte";
    import Salud from "./components/Salud.svelte";
    import Cookies from "js-cookie";
  
    let Menu = sessionStorage.getItem("Menu");  
    console.log(Menu);

    function showMenu(menuId) {   
        sessionStorage.setItem("Menu", menuId);
        Menu = sessionStorage.getItem("Menu"); 
    };
  
    function deleteCookies() {    
        Cookies.remove("token");
        sessionStorage.removeItem("Menu");
        location.href = location.href;
    };
</script>
    
<div class="container">    
    <div class="sidebar">       
        <button class="item item1" on:click={() => showMenu("1")}>  
            <img src="Reporte.svg" height="50" alt="reporte">     
        </button>
        <button class="item" on:click={() => showMenu("2")}>
            <img src="Servicio.svg" height="50" alt="servicio">           
        </button>
        <button class="item" on:click={() => showMenu("3")}>             
            <img src="Horario.svg" height="50" alt="horario">      
        </button>
        <button class="item" on:click={() => showMenu("4")}>
            <img src="Salud.svg" height="50" alt="salud">            
        </button>
        <button class="item" on:click={() => showMenu("5")}>
            <img src="Personal.svg"  height="50" alt="personal">               
        </button>
        <button class="item close" on:click={deleteCookies}>
            <img src="Salir.svg" height="50" alt="salir">                
        </button>        
    </div>

    <div class="panel">
        {#if Menu === "0"}
            <p>Home</p>    

        {:else if Menu === "1"}
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
    .container {
        width: 100%;
        max-width: 1400px; 
        display: grid;
        grid-template-columns: 1fr;        
        margin: 0 auto;      
    }

    .sidebar {        
        display: flex;
        flex-direction: row;
        justify-content: space-around;       
    }
        
    .item {
        background-color: rgb(230, 230, 238);
        border: none;        
        cursor: pointer;
        outline: none;
        transition: transform 0.3s ease-in-out; 
        border-radius: 10px;
    }    

    .item1 {
        margin-top: 6px;
    }

    .panel {
        background-color: aquamarine;
    }
   
    @media screen and (min-width: 460px){
        .container {
            grid-template-columns: 80px 1fr;       
        }

        .sidebar {
            flex-direction: column;   
            justify-content: start; 
            gap: 25px;                    
        }     
        
        .item {
            padding-top: 7px;
            padding-bottom: 2px;
            margin-left: 6px;
            margin-right: 6px;
        }
       
        .item:hover {         
            transform: scale(1.1);              
        }         
    }    
</style>