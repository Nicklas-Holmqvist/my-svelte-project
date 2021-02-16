<script>
	
	import Name from './Name.svelte'
	import HoverButton from './HoverButton.svelte'
	import Numbers from './Numbers.svelte'
	
	//username
	let name = '';

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

	<!-- an if-statement that hides this html code inside if /if when the button is pushed -->
	{#if start == true}
		<h1>Hej!</h1>
		<h2>Vad heter du?</h2>
		<input type="text" bind:value={name} placeholder='Fyll i här'>

		<!-- button that shows when a user make an input, and dissapear when blank -->
		{#if !name== ''}
			<HoverButton on:click={begin} />
		{/if}

	<!-- if button is pressed show this -->
	{:else}
		<Name name={name} />
		<Numbers />

	<!-- end of if-statement -->
	{/if}

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
		flex-direction: column;
		width: 100%;
		height: 60rem;
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