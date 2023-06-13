<script>
    import { onMount } from 'svelte';

    let lista = [];

    for (let num = 1; num <= 90; num++) {
        if (num === 90) {
            lista.push({dni: "48555618", paterno: "Oropeza", materno: "Inca", nombre: "Jeancarlos Marcelo", ingreso: "01/01/2020", cargo: "Operador de grua liviana"});
        } else {
            lista.push({dni: "48555618", paterno: "Oropeza", materno: "Inca", nombre: "Jeancarlos Alberto", ingreso: "01/01/2020", cargo: "Operador de grua liviana"});
        };
    }
    
    let currentPage = 0;
    let itemsPerPage = 15;
    let showPage = lista.slice(0, itemsPerPage);

    function getCurrentPageItems() {
        const startIndex = currentPage * itemsPerPage;
        const endIndex = startIndex + itemsPerPage;
        showPage = lista.slice(startIndex, endIndex);        
    }

    function setCurrentPage(page) {
        currentPage = page;
    }

    function getTotalPages() {
        return Math.ceil(lista.length / itemsPerPage);
    }

    function loadPages(page) {
        setCurrentPage(page);
        getCurrentPageItems();
    }

    let totalPages;

    onMount(() => {
        totalPages = getTotalPages();       
    });   
</script>

<div class="container">
    <h2 class="title">Trabajadores</h2>   
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
                    <td>
                        <button class="options">
                            <i class="bi bi-file-earmark-text"></i>
                        </button>
                        <button class="delete">
                            <i class="bi bi-trash"></i>
                        </button>
                    </td>
                </tr>
            {/each}
        </tbody>
    </table>
       
    <nav class="pagination">       
        {#each Array.from({ length: totalPages }) as _, i}               
            <button class="page" id="btn{i}" on:click={() => loadPages(i)}>{i + 1}</button>               
        {/each}       
    </nav>
</div>


<style>
    .container {
        width: 100%;
        display: flex;
        flex-direction: column;              
    }

    table td:nth-child(3),
    table th:nth-child(3),
    table td:nth-child(4),
    table th:nth-child(4) {        
        text-align: center;
    }

    table td:nth-child(6),
    table th:nth-child(6)  {        
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .options {
        margin-right: 2px;        
        border: none;        
        padding: 0.1rem;        
        border-radius: 5px;
        background-color: transparent;
        color: black;
        font-size: 1rem;
    }

    .options:hover {
        background-color: #0b329e;
        color: #e0e4e6;
    }

    .delete {
        border: none;
        padding: 0.1rem;
        border-radius: 5px;  
        background-color: transparent;
        color: black;  
        font-size: 1rem;      
    }
    
    .delete:hover {
        background-color: #c50f0f;
        color: #e0e4e6;
    }

    .pagination {   
        margin: 0.8rem 0;   
        display: flex;
        flex-direction: row;
        justify-content: center;             
    }
   
    .page {
        width: 1.5rem;
        cursor: pointer;
        margin: 0 1px;
    }

    tbody button {
        cursor: pointer;
    }

    thead th {
        background-color: #f1fcf5;
    }

    tbody tr:hover {
        background-color: #f5f5f5;
    }    

    .page:active {
        transform: scale(1.1);
        font-weight: bold;
    }

    @media screen and (min-width: 460px) {
        .container {
            padding: 1rem;           
        }

        .title {
            margin-bottom: 0.5rem;
        }
    }

    @media screen and (max-width: 460px) {  
        .title {
            margin: 0.5rem 0;
        }
    }

    @media screen and (max-width: 370px) {
        table td:nth-child(3),
        table th:nth-child(3) {
            display: none;
        }
    }

    @media screen and (max-width: 440px) {
        table td:nth-child(4),
        table th:nth-child(4) {
            display: none;            
        }
    }
    
    @media screen and (max-width: 700px) {
        table td:nth-child(5),
        table th:nth-child(5) {
            display: none;
        }        
    }

    @media screen and (max-width: 900px) {        
        .container {
            font-size: 0.8rem;  
        }
    }

</style>