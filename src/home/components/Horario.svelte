<script>     
    const dataBase = [ {unidad: "sur 1", 
                        trabajadores: [ "Mayorga Alejos Livio Alberto", 
                                        "Ramos De la Cruz Luis Alberto", 
                                        "Guerrero Serveleon Marcos Clodoaldo"],
                        turnos: {   dia: [0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 99, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 1]}},
                        {unidad: "sur 2", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                        {unidad: "sur 3", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                        {unidad: "sur 4", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                        {unidad: "sur 5", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "sur 6", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "norte 1", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "norte 2", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "liviana 10", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "liviana 20", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "liviana 30", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}},
                    {unidad: "liviana 40", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 1]}}];
</script>

<div class="container">
    <h2>Horario</h2>

    {#each dataBase as unidad}      
    
    <p>{unidad.unidad.toUpperCase()}</p> 
    <div>        
        {#each unidad.trabajadores as trabajador}
            <p>
                <img src="check1.svg" height="20" alt="">
                {trabajador}
            </p>
        {/each}              
    </div>    
      
    <div class="table">
    <table>
        <thead>
            <tr>      
                {#each unidad.turnos.dia as _, index}
                    <th>{index + 1}</th>
                {/each} 
            </tr>
        </thead>
        <tbody>                     
            <tr>                            
                {#each unidad.turnos.dia as dia}

                {#if dia === 99}
                    <td>
                        <img src="check6.svg" height="20" alt="">
                    </td>
                {:else if dia === 0}
                    <td>
                        <img src="check1.svg" height="20" alt="">
                    </td>
                {:else if dia === 1}
                    <td>
                        <img src="check2.svg" height="20" alt="">
                    </td>
                {:else if dia === 2}   
                    <td>
                        <img src="check3.svg" height="20" alt="">
                    </td>  
                {:else if dia === 3}   
                    <td>
                        <img src="check4.svg" height="20" alt="">
                    </td>
                {:else}
                    <td>
                        <img src="check5.svg" height="20" alt="">
                    </td>
                {/if}
                    
                {/each} 
            </tr>  
            <tr>                            
                {#each unidad.turnos.noche as dia}
                    {#if dia === 99}
                        <td>
                            <img src="check6.svg" height="20" alt="">
                        </td>
                    {:else if dia === 0}
                        <td>
                            <img src="check1.svg" height="20" alt="">
                        </td>
                    {:else if dia === 1}
                        <td>
                            <img src="check2.svg" height="20" alt="">
                        </td>
                    {:else if dia === 2}   
                        <td>
                            <img src="check3.svg" height="20" alt="">
                        </td>  
                    {:else if dia === 3}   
                        <td>
                            <img src="check4.svg" height="20" alt="">
                        </td>
                    {:else}
                        <td>
                            <img src="check5.svg" height="20" alt="">
                        </td>
                    {/if}
                {/each} 
            </tr>          
        </tbody>
    </table>
    </div>

    {/each}

</div>  

<style>   
    .container {
        width: 100%;
        padding: 5px;
        display: flex;
        flex-direction: column;    
        font-size: 0.9rem;          
    }
    
    .table {       
        overflow: visible;         
    }

    table {   
        min-width: 600px;
        text-align: center;
        width: 100%;
    }

    table thead {
        background-color: #bcdff3;
    }

    table tbody {
        background-color: #f7f9fa;       
    }

    table img {
        margin-top: 4px;
    }
   
    div p {
        display: flex;
        align-items: center;
        justify-content: start;
        gap: 2px;
    }
</style>


