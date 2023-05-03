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