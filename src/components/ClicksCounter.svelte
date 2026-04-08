<script> //scrivo il javascript qui dentro
    let {initialCount = $bindable()} = $props(); //props è un oggetto che contiene tutte le proprietà che vengono passate al componente, se ne passo una nuova, il componente si aggiorna
    let count = $state(initialCount); //è lo stato del comonente, se cambia in qualche modo, il componente si aggiorna, in questo caso inizia da initialCount
    let doubled = $derived(count * 2); 
</script>

<h1>Clicks Counter</h1>

<button onclick={() => count++}>
    clicks: {count} <!--stampo il valore di count, ogni volta che clicco sul bottone, count aumenta di 1 e quindi il componente si aggiorna e mostra il nuovo valore di count-->
</button>

<span>doubled is {doubled}</span>