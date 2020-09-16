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
	<title>Stillingsannonser - Beta</title>
	<meta name="description" content="Side med datarelaterte jobbannonser" />
</svelte:head>

<main>
	{#if show}
		<div class="card" in:fly={{y: 20}}>
			<h2>Stillingsannonser</h2>
			<p>
				Her vil vi legge ut annonser for diverse datarelaterte jobber.
				Ta kontakt med <a href="mailto:bedkom@betauia.net">bedkom</a> for
				å få deres annonse listet her.
			</p>
		</div>
	{/if}
</main>
