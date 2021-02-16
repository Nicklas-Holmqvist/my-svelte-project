<script>
    import HoverButton from './HoverButton.svelte'
    import End from './End.svelte'

    let userInput = '';
    let end = false;

    function random() {
		return Math.ceil(Math.random()*20)
	}

    function theEnd(){
        end = true;
    }

	let a = random()
	let b = random()

	let total = a + b

</script>

<div class="math">
    {#if end == false}
    <p>Vad blir summan?</p>
    <span>{a} + {b}</span>
    <input type="number" bind:value={userInput} placeholder="Fyll i svar här">

    {#if userInput == total}
    <HoverButton on:click={theEnd}/>
    {/if}
    {/if}
    {#if !end == false}
    <End />
    {/if}
    
</div>

<style>
    
    * {
		padding: 0;
		margin: 0;
		box-sizing: border-box;
	}

    .math {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

    }

    p {
        font-size: 1.5rem;
        text-align: center;
    }

	span {
		text-align: center;
        font-size: 1.5rem;
        padding: 2rem
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