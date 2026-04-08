<script>
    import { onMount} from "svelte"; //sono delle dunzioni che avvengono in momenti specifici ovvero in questo caso quando il componente viene montato
    let size = $state(50); //sono i due state che associeremo ai 2 input
    let color = $state("aff3e00");

    let canvas 

    onMount(() => {
        const context = canvas.getContext("2d");
        context.clearRect(0, 0, canvas.width, canvas.height) //pulisco il canvas, altrimenti ogni volta che cambio la size o il colore, disegno un nuovo quadrato sopra quello vecchio e non si vede più niente

        context.fillStyle = color; //imposto il colore di riempimento del quadrato
        context.fillRect(0, 0, size, size); 
    })
    
</script>
    

<h3>Canvas Square</h3>

<!--il bind serve per collegare gli elementi, lo collego a ciò che sta dentro le graffe {}-->
<article>
    <canvas bind:this={canvas} width="100" height="100"></canvas> <!--è uno spazio vuoto che ci permete di disegnare ogni singolo pixel, usato per fare disegni 2d, mettere disegni 3d, fare grafici, ...-->
    <nav> <!--ci metto dei controlli per gestire il disegno ()il quadrato creato sopra-->
        <label> <!--serve per poter selezionare l'input anche senza che io schiaccio sull'input stesso-->
            Size: <input type="range" bind:value={size}>
        </label>
        <label>
            Color: <input type="color" bind:value={color}> <!--grazie al bind collego il colore alla variabile color che ho scritto nello script-->
        </label>
    </nav>
</article>

<!--sto modificando lo stile dell'article e del canvas-->
<style> 
    article { 
        display: flex;
        gap: 1em;
        align-items: end;
    }

    Canvas {
        border: 1px solid black;
    }

    nav {
        display: flex;
        gap: 1em;
        flex-direction: column;
    }
</style>