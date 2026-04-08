<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()} 

<footer>
	<p>©polimi 2026</p>
</footer>

<style> /*dice di trattare questo style css globalmente quindi applicato a tutti i p paragrafi*/
	:global(p){
        color: rgb(255, 164, 104);
    }
</style>