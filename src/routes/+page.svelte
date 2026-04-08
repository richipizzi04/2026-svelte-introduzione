<script> //scrivo il javascript qui dentro
    import {website} from "../components/state.svelte.js"; //importo lo stato globale del sito, in questo modo posso usarlo in tutti i componenti che lo importano, se cambio il titolo in uno dei componenti, cambia anche negli altri componenti che lo usano
    import ClicksCounter from "../components/ClicksCounter.svelte"; //sono le due componenti che ho creato e le importo nella pagina principale, in questo modo posso usarle come se fossero dei tag html
    import CanvasSquare from "../components/CanvasSquare.svelte"; //per fare comparire la linea sella size e il colore
    import ToDoList from "../components/ToDoList.svelte";
    import TitleEditor from "../components/TitleEditor.svelte";

    let count = $state(5)
    let doubled = count * 2;

</script>

<h1> {website.title} </h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<TitleEditor/>

<ClicksCounter bind:initialCount={count}/> 
{#if count > 10 && count < 20}
    <p>count from parent is {count}</p>
{:else if count > 30}
    <p>that's a lot of clicks!</p>
{:else}
    <p>count is not in range</p>
{/if}

<CanvasSquare/>
<ToDoList/>

<style>
    h1 {
        color: #B40123;
    }
</style>