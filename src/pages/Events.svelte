<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;
</script>

<svelte:head>
	<title>Arrangementer - Beta</title>
	<meta
		name="description"
		content="Her vil vi legge ut arrangementer som skjer i regi av BETA. Dette kan være alt fra bedriftspresentasjoner til møter med interessegruppene." />
</svelte:head>

<main>
	{#if show}
		<div class="card" in:fly={{y: 20}}>
			<h2>Arrangementer</h2>
			<p>
				Her vil vi legge ut arrangementer som skjer i regi av BETA.
				Dette kan være alt fra bedriftspresentasjoner til møter med
				interessegruppene.
			</p>
		</div>
	{/if}
</main>
