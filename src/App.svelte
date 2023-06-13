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