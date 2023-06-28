<script>    
    let lista = [];
   
    for (let num = 1; num <= 90; num++) {
        if (num === 90) {
            lista.push({dni: "48555618", paterno: "Oropeza", materno: "Inca", nombre: "Jeancarlos Marcelo", ingreso: "01/01/2020", cargo: "Operador de grua liviana"});
        } else {
            lista.push({dni: "48555618", paterno: "Oropeza", materno: "Collahuacho", nombre: "Jeancarlos Alberto Miguel", ingreso: "01/01/2020", cargo: "Operador de Grua Semi Pesada"});
        };
    };
         
    let currentPage = 0;
    let itemsPerPage = 20;

    let totalPages = Math.ceil(lista.length / itemsPerPage);

    let showPage = lista.slice(currentPage, itemsPerPage);

    function getCurrentPageItems(page) {
        currentPage = page;
        const startIndex = currentPage * itemsPerPage;
        const endIndex = startIndex + itemsPerPage;
        showPage = lista.slice(startIndex, endIndex);  
        
        for (let i = 1; i <= totalPages; i++) {
            let name = "btn" + (i - 1);
            const elemento = document.getElementById(name);
            elemento.classList.remove("active");
            console.log(i-1);
        };

        let btn_activo = "btn" + page;
        const activo = document.getElementById(btn_activo);
        activo.classList.add("active");  
    };
</script>

<div class="container">
    <h2>Personal</h2>   
    <table>
        <thead>
            <tr>
                <th>#</th>                
                <th>Nombre</th>
                <th>Dni</th>                
                <th>Ingreso</th>
                <th>Cargo</th>
                <th>Gestion</th>               
            </tr>
        </thead>
        <tbody>
            {#each showPage as person, index}
                <tr>
                    <th>{currentPage * itemsPerPage + index + 1}</th>                    
                    <td>{person.paterno} {person.materno} {person.nombre}</td>
                    <td>{person.dni}</td>                    
                    <td>{person.ingreso}</td>
                    <td>{person.cargo}</td>
                    <td class="menu">
                        <button class="options">
                            <img src="Mas.svg"  height="21" alt="mas">  
                        </button>
                        <button class="delete">
                            <img src="Del.svg"  height="21" alt="del">    
                        </button>
                    </td>
                </tr>
            {/each}
        </tbody>
    </table>
       
    <nav class="pagination">       
        {#each Array.from({ length: totalPages }) as _, i}               
            <button class:active={i === 0} class="page" id="btn{i}" on:click={() => getCurrentPageItems(i)}>{i + 1}</button>               
        {/each}       
    </nav>
</div>

<style>
    .container {
        width: 100%;
        padding: 5px;
        display: flex;
        flex-direction: column;    
        font-size: 0.9rem;          
    }

    table thead {
        background-color: #bcdff3;        
    }

    table tbody {
        background-color: #f7f9fa;       
    }

    tbody tr:hover {
        background-color: #d0dff0;
    }    
     
    table td:nth-child(3),
    table th:nth-child(3),
    table td:nth-child(4),
    table th:nth-child(4) {        
        text-align: center;
    }

    .menu  {        
        display: flex;
        flex-direction: row;
        justify-content: center;       
        gap: 4px     
    }

    .options, .delete {  
        width: 21px;
        height: 21px;             
        cursor: pointer;
        border: none;
        background-color: transparent;    
        transition: transform 0.3s ease-in-out;
    }

    .pagination {   
        margin-top: 15px;     
        display: flex;
        flex-direction: row;        
        justify-content: center;   
        gap: 2px;          
    }
   
    .page {
        width: 20px;
        cursor: pointer;        
    }
   
    .active {       
        font-weight: bold;
        transform: scale(1.1);  
    }

    @media screen and (min-width: 460px) {
        .options:hover, .delete:hover {    
            transform: scale(1.1);
        }
    }
      
    @media screen and (max-width: 600px) {
        table td:nth-child(3),
        table th:nth-child(3) {
            display: none;
        }
    }  

    @media screen and (max-width: 700px) {
        table td:nth-child(4),
        table th:nth-child(4) {
            display: none;
        }
    }   
    
    @media screen and (max-width: 1000px) {
        table td:nth-child(5),
        table th:nth-child(5) {
            display: none;
        }        
    }  
</style>