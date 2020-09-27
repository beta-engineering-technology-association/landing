<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;
	const mnemonicLogo = '/mnemonic.png';
</script>

<style>
	.container {
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-gap: 20px;
		grid-template-areas:
			'head head'
			'content info';
	}
	.head {
		grid-area: head;
	}
	.content {
		grid-area: content;
	}
	.info {
		grid-area: info;
	}
	ul {
		list-style: none;
		padding: 0px;
	}
	li {
		display: flex;
		justify-content: space-between;
	}
	button {
		width: 100%;
	}
</style>

<svelte:head>
	<title>Bedpres Mnemonic - Beta</title>
	<meta
		name="description"
		content="Info til bedrifter som ønsker å komme i kontakt med Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="container">
			<div class="card head" in:fly={{y: 20}}>
				<img width="100%" alt="soprasteria" src={mnemonicLogo} />
			</div>
			<div class="card content" in:fly={{y: 20}}>
				<h2>Bedriftspresentasjon med Mnemonic</h2>
				<p>
					mnemonic er Nordens største fagmiljø innen cybersikkerhet,
					og samarbeider med de største virksomhetene i regionen. Vi
					jobber daglig på frontlinjen med å håndtere dataangrep,
					overvåke kritisk infrastruktur, gjennomføre penetrasjons- og
					sikkerhetstester, bygge sikrere IT-systemer, og hjelpe våre
					kunder med å kartlegge og håndtere sin sikkerhetsrisiko.
				</p>
				<p>
					Vi teller i dag over 200 ansatte fordelt på seks kontorer,
					og har en solid økonomi. mnemonic er et firma i vekst, og
					jobber aktivt for å videreutvikle våre tjenester og styrke
					vår posisjon som det ledende sikkerhetsselskapet i Norden. I
					tillegg til et spennende fagmiljø og gode muligheter for
					faglig utvikling, har mnemonic et unikt sosialt miljø med
					mange felles aktiviteter og tilbud. mnemonic har flere
					ganger blitt kåret til en av Norges og Europas beste
					arbeidsplasser av Great Place to Work.
				</p>
			</div>
			<div class="card info" in:fly={{y: 20}}>
				<h2>Info</h2>
				<ul class="nox">
					<li>
						<span>Dato</span>
						<strong>15. oktober kl 16:15</strong>
					</li>
					<li><span>Klokka</span> <strong>16:30</strong></li>
					<li><span>Pris</span> <strong>Gratis</strong></li>
					<li>
						<span>Sted</span>
						<span><a href="https://bit.ly/39Hoib0">C2 036</a></span>
					</li>
					<li><span>Påmeldte</span> <strong>10/40</strong></li>
				</ul>
				<button>Meld meg på</button>
			</div>
		</div>
	{/if}
</main>
