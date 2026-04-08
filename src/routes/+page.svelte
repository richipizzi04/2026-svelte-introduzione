<script> //scrivo il javascript qui dentro
    import ClicksCounter from "../components/ClicksCounter.svelte"; //sono le due componenti che ho creato e le importo nella pagina principale, in questo modo posso usarle come se fossero dei tag html
    import CanvasSquare from "../components/CanvasSquare.svelte"; //per fare comparire la linea sella size e il colore

    let count = $state(5)
    let doubled = count * 2;

</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<ClicksCounter bind:initialCount={count}/> 
{#if count > 10 && count < 20}
    <p>count from parent is {count}</p>
{:else if count > 30}
    <p>that's a lot of clicks!</p>
{:else}
    <p>count is not in range</p>
{/if}


<CanvasSquare/>

<style>
    h1 {
        color: #B40123;
    }
</style>