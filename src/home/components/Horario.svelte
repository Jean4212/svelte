<script> 
    const colores = ["#DDEAFA", "#DDFAE9", "#FAF0DD", "#FADDDD", "#FAF1E9"];
    const dataBase = [ {unidad: "sur 1", 
                        trabajadores: [ "Mayorga Alejos Livio Alberto", 
                                        "Ramos De la Cruz Luis Alberto", 
                                        "Guerrero Serveleon Marcos Clodoaldo"],
                        turnos: {   dia: [0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0]}},
                       {unidad: "sur 2", 
                        trabajadores: [ "Calixto rivera vides", 
                                        "Malpartida Condor Jonathan Fernando", 
                                        "Osorio Yupanqui Victor Lee",
                                        "Oropeza Inca Jeancarlos Alberto"],
                        turnos: {   dia: [0, 0, 0, 99, 1, 1, 1, 2, 2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 1, 1, 1],
                                  noche: [2, 2, 2, 0, 0, 0, 0, 1, 1, 1, 1, 2, 2, 2, 2, 0, 3, 99, 3, 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3]},
                    }];

</script>

<div class="container">
    <h2 class="title">Horario</h2>

    {#each dataBase as unidad}      
    
    <p class="zona">{unidad.unidad.toUpperCase()}</p> 
    <div class="names">     
        {#each unidad.trabajadores as trabajador, index}
            <p style="background-color: {colores[index]};">{trabajador}</p>
        {/each}              
    </div>    

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
                        <td style="background-color: transparent;">.</td>
                    {:else}
                        <td style="background-color: {colores[dia]};">.</td>
                    {/if}
                    
                {/each} 
            </tr>  
            <tr>                            
                {#each unidad.turnos.noche as dia}
                    {#if dia === 99}
                        <td style="background-color: transparent;">.</td>
                    {:else}
                        <td style="background-color: {colores[dia]};">.</td>
                    {/if}
                {/each} 
            </tr>          
        </tbody>
    </table>

    {/each}

</div>  

<style>   
    .container {
        width: 100%;
        display: flex;
        flex-direction: column;              
    }

    .zona {
        font-weight: bold;
    }

    .names {
        display: flex;
        flex-wrap: wrap;
        justify-content: start;
        margin-left: 2px;
        gap: 0 2.5rem;
    }
    
    table {
        margin-bottom: 1.2rem;           
    }
    
    thead th {      
        background-color: #ebf0f0;       
    }

    tbody td {
        text-align: center;
        color: transparent;
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

        table {
            font-size: 0.4rem;
        }

        .names {
            display: block;           
        }
    }
  
    @media screen and (max-width: 900px) {        
        .container {
            font-size: 0.8rem;  
        }

        thead th {
            font-size: 0.7rem;
        }

        tbody td {
            font-size: 0.5rem;
        }
    }
</style>


