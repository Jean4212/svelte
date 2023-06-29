<<<<<<< HEAD
<script>	
	import Login from "./login.svelte";	
	
	let login = false;

	function manejarEventoPersonalizado() {
    	console.log("fdsfsdfsad");
		if (login) {
			login = false;
		} else {
			login = true;
		}
  	}
</script>

{#if !login}
<Login on:pulso={ manejarEventoPersonalizado }/>
{:else}
<p>hola</p>
{/if}


<style>
</style>
=======
<script>
	import Login from "./login/login.svelte";
	import Home from "./home/home.svelte";	
	import Cookies from "js-cookie";
  
	let Token = Cookies.get("token");
  
	function loadCookies() {
	  Token = Cookies.get("token");
	}
</script>
  

{#if Token}
	<Home />
{:else}
	<Login on:myEvent={loadCookies}/>	  
{/if}
>>>>>>> c7c92cbebbbb416c5a1d3476484a80b5eead0f97
