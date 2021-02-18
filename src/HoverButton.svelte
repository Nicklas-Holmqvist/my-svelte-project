<script>
    export let btnText;
</script>

<!-- This is the main button type that can be re-used -->
<style>
    button {
        margin-top: 1.5rem;
        background-color: white;
        color: black;
        padding: 1rem 2rem;
        border: 0.5px lightgrey solid;
        transition: background-color, color 0.3s ease-in-out;
        font-size: 1.2rem;
        font-weight: 500;
        width: 10rem;
    }

    button:hover {
        background-color: black;
        color: white;
    }

</style>

<!-- The basic button that is clickable with function callback at the page it is on -->
<button on:click>{btnText}</button>