<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;
</script>

<style>
	main {
		max-width: 1100px;
		margin: 0 auto;
	}
	.card {
		box-shadow: 0 1px 4px rgba(0, 0, 0, 0.04);
		padding: 30px;
		border-radius: 5px;
		background: white;
	}
	h2 {
		margin-top: 0;
	}
</style>

<svelte:head>
	<title>For Bedrifter - Beta</title>
	<meta
		name="description"
		content="Info til bedrifter som ønsker å komme i kontakt med Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="card" in:fly={{y: 20}}>
			<h2>For bedrifter</h2>
			<p>Her er det mye nyttig info gitt.</p>
		</div>
	{/if}
</main>
