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
		grid-gap: 20px;
	}
	p {
		margin: 20px 0;
	}
	.cont {
		margin: 10px;
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
	}
</style>

<svelte:head>
	<title>Om oss - Beta</title>
	<meta name="description" content="Informasjon om Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="container" in:fly={{y: 20}}>
			<div class="card">
				<h2>Om Beta</h2>
				<p>
					Beta er linjeforeningen for datastudenter ved Universitetet
					i Agder. Beta er en non-profit organisasjon. Det betyr Beta
					ikke driver for å tjene penger, men heller bruker
					fortjenesten på våre medlemmer. Alle studenter ved
					datarelaterte fag ved UiA er automatisk medlem av Beta
					dersom en ikke aktivt melder seg ut. Det betyr at vi idag
					har omlag 500 medlemmer.
				</p>
			</div>

			<div class="card">
				<h2>Historie</h2>
				<p>
					Beta ble grunnlagt i 2006 mens det fortsatt het Høyskolen i
					Agder, deretter, under flyttingen i 2010 fulgte Beta med inn
					på Universitetet i Agder.
				</p>
				<p>
					Beta har hatt en lang tradisjon med å forbedre det
					studentsosiale mulighet rundt studiet for studenter. Vi
					arrangerer blant annet BetaLAN og Retrokveld som er helt
					åpent for alle studenter, samt bedriftpresentasjoner som har
					hjulpet studenter ut i arbeidslivet.
				</p>
				<p>
					Siden oppstarten har Beta vært underlagt STA
					(STudentorganisasjonen i Agder), men det var først i 2014 at
					Beta for første gang ble registrert i Brønnøysund Registeret
					som en frivillig organisasjon under STA.
				</p>
			</div>
			<div class="card">
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
