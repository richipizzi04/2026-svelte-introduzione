<script> //scrivo il javascript qui dentro
    console.log("Hello world");
    let count = $state(0); //è lo stato del comonente, se cambia in qualche modo, il componente si aggiorna
    let doubled = $derived(count * 2); 
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<button onclick={() => count++}>
    clicks: {count} <!--stampo il valore di count, ogni volta che clicco sul bottone, count aumenta di 1 e quindi il componente si aggiorna e mostra il nuovo valore di count-->
</button>

<span>doubled is {doubled}</span>

<style>
    h1 {
        color: #B40123;
    }
    
</style>