<script>
	import Navbar from './navBar.svelte'
	let name="Gaurang Bhatt";
	let points=100;
	const addPoints= ()=>{
		points=points+1;
	}
	const decreasePoints=()=>{
		points=points-1;
	}
	let showControls=false;
	const toggleControls= ()=>{
		showControls=!showControls;
	}
</script>
<style>
	h1 {
		color: #ff3e00;
	}
	button.btn-dark {
    color: black;
	}
</style>
<Navbar />
<div class="container">
	<div class="card">
		<h1>{name} <button class="btn" on:click="{toggleControls}">
		{#if showControls}-{:else}+{/if}</button></h1>
		<h3>Points: {points}</h3>
		{#if showControls}
			<button class="btn" on:click="{addPoints}">+1</button>
	    	<button class="btn btn-dark" on:click="{decreasePoints}">-1</button>
	    	<input type="number" bind:value="{points}" />
	    {/if}
		</div> 
</div>