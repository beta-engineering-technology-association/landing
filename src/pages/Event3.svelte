<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;
	const mnemonicLogo = '/betalan.jpg';
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
	<title>BetaLAN - Beta</title>
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
				<h2>BetaLAN</h2>
				<p>
					Det er tid for årets BetaLAN! Dato for dette semesteret er
					9. - 11. oktober
				</p>
				<p>
					Vi kommer til å ha en redusert kapasitet på deltagere i år,
					men det kommer til å være mulighet til å delta på noen av
					turneringene vår ONLINE. I år har vi samlet en helt vill
					sponsorlineup, og vi har mange heftige premier som trenger
					vinnere!
				</p>

				<strong>Compoer</strong>
				<ul>
					<li>CSGO 3v3 *</li>
					<li>League of Legends *</li>
					<li>Minecraft *</li>
					<li>Super Smash Bros.</li>
					<li>Super Smash Bros. Ultimate</li>
					<li>Mario Kart</li>
					<li>CTF *</li>
					<li>+++</li>
					<li>(* Kan delta online)</li>
				</ul>
				<p>
					Dersom det skal være noen spørsmål så er det bare å spørre
					noen i crew på Discord, sende en e-post til
					betalan@betauia.net, eller spørre her i Messenger
					Billettpris: 100kr Åpent for alle.
				</p>
			</div>
			<div class="card info" in:fly={{y: 20}}>
				<h2>Info</h2>
				<ul class="nox">
					<li>
						<span>Start</span>
						<strong>9. oktober kl 16:00</strong>
					</li>
					<li>
						<span>Slutt</span>
						<strong>11. oktober kl 20:00</strong>
					</li>
					<li><span>Pris</span> <strong>100,-</strong></li>
					<li>
						<span>Sted</span>
						<strong><a href="https://bit.ly/39Hoib0">Bluebox </a>/
							Digitalt</strong>
					</li>
					<li><span>Påmeldte</span> <strong>4 / 20</strong></li>
				</ul>
				<button>Meld meg på</button>
			</div>
		</div>
	{/if}
</main>
