<script>
	import { fade } from 'svelte/transition';
	import HoverButton from './HoverButton.svelte'
	import Numbers from './Numbers.svelte'
	
	//username
	export let name = '';

	//an boolean to check if you have clicked the button to start the app
	let start = true;

	/**
	 * function to go to the next scene
	 */
	function begin() {
		start = false;
	}

</script>

<main>
	<div class="app-container" transition:fade>
		<!-- an if-statement that hides this html code inside if /if when the button is pushed -->
		{#if start == true}
			<h1>Hej!</h1>
			<h2>Vad heter du?</h2>
			<input type="text" bind:value={name} placeholder='Fyll i här'>

			<!-- button that shows when a user make an input, and dissapear when blank -->
			{#if !name== ''}
				<HoverButton on:click={begin} btnText='Fortsätt' />
			{/if}

		<!-- if button is pressed show this -->
		{:else}			
			<Numbers name={name}/>
		<!-- end of if-statement -->
		{/if}
	</div>
</main>

<style>
	* {
		padding: 0;
		margin: 0;
		box-sizing: border-box;
	}

	main {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;
		background-color: #F9F9F9;
	}

	h1 {
		padding: .5rem 0;
        font-size: 5rem;
        font-weight: 400;
	}

	h2 {
		padding: 1.5rem 0;
        font-size: 2.5rem;
        font-weight: 300;
	}

	.app-container {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		flex-direction: column;
		height: 25rem;
		margin: 0 auto;
	}

	input {
		border: none;
		border-bottom: 1px black solid;
		text-align: center;
		width: 15rem;
		height: 3rem;
		padding: 0.3rem;
		outline: none;
		font-size: 1.5rem;
		transition: all 0.2s ease-in-out;		
	}

	input:hover {
		background: hsla(0, 0%, 0%, 0.01);		
	}


</style>