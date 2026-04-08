<script> //scrivo il javascript qui dentro
    import ClicksCounter from "../components/ClicksCounter.svelte"; //sono le due componenti che ho creato e le importo nella pagina principale, in questo modo posso usarle come se fossero dei tag html
    let count = $state(5)
    let doubled = count * 2;

</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<ClicksCounter bind:initialCount={count}/> 
<p>count from parent is {count}</p>
<ClicksCounter initialCount={3}/> 

<style>
    h1 {
        color: #B40123;
    }
</style>