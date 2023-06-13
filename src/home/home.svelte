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
        <button class="item logo" on:click={() => showMenu("1")}>
            <i class="bi-bootstrap fs-1"/>
        </button>
        <button class="item" on:click={() => showMenu("1")}>
            <i class="bi-house fs-1"/>
        </button>
        <button class="item" on:click={() => showMenu("2")}>
            <i class="bi-truck fs-1"/>
        </button>
        <button class="item" on:click={() => showMenu("3")}>             
            <i class="bi-calendar2-check fs-1"/>
        </button>
        <button class="item" on:click={() => showMenu("4")}>
            <i class="bi-heart-pulse fs-1"/>
        </button>
        <button class="item" on:click={() => showMenu("5")}>
            <i class="bi-people fs-1"/>
        </button>
        <button class="item close" on:click={deleteCookies}>
            <i class="bi-box-arrow-left fs-1 text-danger"/>
        </button>        
    </div>

    <div class="panel">   
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
    .container {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        max-width: 1400px; 
        margin: 0 auto;
    }

    .sidebar {        
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        background-color: #f1fcf5;
    }
        
    .item {
        background-color: transparent;
        color: #434344;
        border: none;
        font-size: 1.9rem;        
        cursor: pointer;
        outline: none;
        transition: transform 0.3s ease-in-out;
    }

    .close {
        color: #d12727;
    }

    @media screen and (min-width: 460px){
        .container {
            grid-template-columns: 80px 1fr;       
        }

        .sidebar {
            flex-direction: column;  
            justify-content: start;            
        }     
        
        .item {
            font-size: 3rem;
            margin-bottom: 1rem;              
        }

        .close {
            margin-bottom: 0;
        }

        .item:hover {         
            color: #0f0f0f;
            transform: scale(1.1);
        }

        .close:hover {
            color: #c00707; 
        }       
    }
</style>