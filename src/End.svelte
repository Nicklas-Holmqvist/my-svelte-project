<script>
    import { fade } from 'svelte/transition';
    import HoverButton from './HoverButton.svelte'

    // different sizes of the h1
    let largeH1 = 3
    let smallH1 = 1.5
    export let name = ''

    /** function to reload the page */
    function restart() {
        location.reload()
    }

</script>

<!-- a if statement that checks if the windows innerwidth is larger than 680px
    The only way to control that this statement works is to reload the page -->
<div class="end" transition:fade>
    {#if window.innerWidth > 680}
    <h1 style="font-size: {largeH1}rem">Tack {name} för du var med och spela!</h1>

    {:else}
    <h1 style="font-size: {smallH1}rem">Tack {name} för du var med och spela!</h1>

    {/if}
    <HoverButton on:click={restart} btnText='Till början'/>
    
</div>

<style>
    	h1 {
		padding: .5rem 1rem;
        /* font-size: 5vw; */
        font-weight: 400;
	}

    .end {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

</style>