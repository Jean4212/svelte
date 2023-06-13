<script>
    import { onMount } from 'svelte';
  
    let calendar = []

    
    function ajustarElementosResponsivos() {
        calendar = []
        let anchoVentana = document.documentElement.clientWidth;
        

        if (anchoVentana < 400) {               
            for (let num = 1; num <= 12; num++) {
                calendar.push(num)
            }
            console.log("menor a 400")

        } else if (anchoVentana < 900) {           
            for (let num = 1; num <= 16; num++) {
                calendar.push(num)
            }
            console.log("menor a 600")

        } else {           
            for (let num = 1; num <= 31; num++) {                
                calendar.push(num)
            }
            console.log("mayor a 600")
        }

        console.log(anchoVentana)
    }

    window.addEventListener('DOMContentLoaded', ajustarElementosResponsivos);
    window.addEventListener('resize', ajustarElementosResponsivos);
      
    let dbData = [{nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto 1"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto 2"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto 3"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto 4"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto 5"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "claret magna"},
        {nacimiento: "01-01-2020", ingreso: "01-01-1950", dni: "48555618", paterno: "oropeza", materno: "inca", nombre: "jeancarlos alberto"},
        {nacimiento: "01-01-1979", ingreso: "01-01-2021", dni: "40137921", paterno: "garcia", materno: "guivin", nombre: "maria elena"},];
    
    let currentPage = 0;
    let itemsPerPage = 10;

    let showData = dbData.slice(0, itemsPerPage);

    function getCurrentPageItems() {
        const startIndex = currentPage * itemsPerPage;
        const endIndex = startIndex + itemsPerPage;    
        showData = dbData.slice(startIndex, endIndex);
    }

    function setCurrentPage(page) {
        currentPage = page;
    }

    function getTotalPages() {
        return Math.ceil(dbData.length / itemsPerPage);
    }

    let totalPages;

    function loadData(num) {
        setCurrentPage(num);
        getCurrentPageItems();
    }

    onMount(() => {
        totalPages = getTotalPages();
    });
</script>

<div class="container">
    <h2 class="title">Horario</h2>

    <p>Sur 01</p>
    <p>Ramos De la cruz Luis Alberto</p>
    <p>Osorio Yupanqui Victor Lee</p>
    <p>Mayorga Alejos Livio Alberto</p>
    
    <div class="row d-flex justify-content-start">
        <div class="col">1

        </div>
        <div class="col">2
            
        </div>
        <div class="col">3
            
        </div>
        <div class="col">4
            
        </div>
        <div class="col">5
            
        </div>
        <div class="col">6
            
        </div>
        <div class="col">7
            
        </div>
        <div class="col">8
            
        </div>
        <div class="col">9
            
        </div>
        <div class="col">10
            
        </div>
        <div class="col">11
            
        </div>
        <div class="col">12
            
        </div>
        <div class="col">13
            
        </div>
        <div class="col">14
            
        </div>
        <div class="col">15
            
        </div>
        <div class="col">16
            
        </div>
        <div class="col">17
            
        </div>
        <div class="col">18
            
        </div>
        <div class="col">19
            
        </div>
        <div class="col">20
            
        </div>
        <div class="col">21
            
        </div>
        <div class="col">22
            
        </div>
        <div class="col">23
            
        </div>
        <div class="col">24
            
        </div>
        <div class="col">25
            
        </div>
        <div class="col">26
            
        </div>
        <div class="col">27
            
        </div>
        <div class="col">28
            
        </div>
        <div class="col">29
            
        </div>
        <div class="col">30
            
        </div>
        <div class="col">31
            
        </div>        
    </div>
   
   

</div>  

<style>   
    .container {
        width: 100%;
        display: flex;
        flex-direction: column;              
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

    @media screen and (max-width: 900px) {        
        .container {
            font-size: 0.8rem;  
        }
    }
</style>


