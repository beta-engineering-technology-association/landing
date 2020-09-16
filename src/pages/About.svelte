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
		margin: 20px 0;
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
				<p>
					Beta Engineering & Technology Association er linjeforeningen
					for studenter som studere Dataingeniørfag ved Universitetet
					i Agder. I alt er det omlag 350 studenter som er medlem av
					Beta.
				</p>
				<p>
					Beta ble grunnlagt i 2006 mens det fortsatt het Høyskolen i
					Agder, deretter, under flyttingen i 2010 så fulgte Beta med
					inn på Universitetet i Agder.
				</p>
				<p>
					Beta har hatt en lang tradisjon med å forbedre det
					studentsosiale mulighet rundt studiet for studenter. Beta
					har blant annet arrangert BetaLAN og Retrokveld som er helt
					åpent for alle studenter, og arrangert bedriftpresentasjoner
					som har hjulpet studenter ut i arbeidslivet.
				</p>
				<p>
					Siden oppstarten har Beta vært underlagt STA
					(STudentorganisasjonen i Agder), men det var først i 2014 at
					Beta for første gang ble registrert i Brønnøysund Registeret
					som en frivillig organisasjon under STA..
				</p>
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
