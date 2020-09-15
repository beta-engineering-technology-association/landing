<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;

	const betaSec = '/betasec.png';
	const betaDev = '/betadev.png';
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
	.container {
		display: grid;
		grid-gap: 30px;
	}
	p {
		margin: 0;
	}
	.cont {
		margin: 10px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 30px;
	}
	img {
		margin-bottom: 10px;
	}
</style>

<svelte:head>
	<title>Om oss - Beta</title>
	<meta name="description" content="Informasjon om Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="container">
			<div class="card" in:fly={{y: 20}}>
				<h2>Om Beta</h2>
				<p>Beta ble stiftet i xxxx....</p>
			</div>
			<div class="card" in:fly={{y: 20}}>
				<h2>Interessegrupper</h2>
				<div class="cont">
					<div class="half">
						<img alt="betasec" src={betaSec} />
						<p>
							BetaSec er en gruppe studenter med interresse for
							sikkerhet. Her går vi gjennom alt fra CTF'er til
							andre sikkerhetsrelaterte utfordringer.
						</p>
					</div>

					<div class="half">
						<img alt="betadev" src={betaDev} />
						<p>
							BetaDev er en gjeng som er interresert i alt av
							utvikling. De har blant annet vært med på å designe
							og utvikle nettsiden du sitter å ser på akkurat nå.
							Annet enn det holder de på med å utvikle en Discord
							bot, og diverse python scripts og andre godbiter.
							Stikk en tur innom hvis dette høres kult ut.
						</p>
					</div>
				</div>
			</div>
		</div>
	{/if}
</main>
