<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;
	const sopraLogo = '/sopra-logo.png';
	const hey = '/hey.png';
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
	<title>Bedpres Sopra Steria - Beta</title>
	<meta
		name="description"
		content="Info til bedrifter som ønsker å komme i kontakt med Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="container">
			<div class="card head" in:fly={{y: 20}}>
				<img width="100%" alt="soprasteria" src={sopraLogo} />
			</div>
			<div class="card content" in:fly={{y: 20}}>
				<h2>Bedriftspresentasjon med Sopra Steria</h2>
				<p>
					Vil du vite mer om hvilke spennende prosjekter og
					teknologier Norges største IT-konsulentselskap jobber med?
					Ønsker du å høre mer om hvordan det er å være nyutdannet
					(graduate) hos oss eller hvordan en sommerjobb kan se ut? Da
					håper vi å se deg på vår digitale bedriftspresentasjon 6.
					oktober!
				</p>
				<p>
					Det blir bingo med premie til vinnerne! Arrangementet vil
					foregå over Zoom eller Teams, og lenke til arrangementet vil
					bli sent på mail.
				</p>
				<p>
					Det blir selvfølgelig også servering! Hver deltaker kan
					bruke 200 kroner på mat og drikke, med unntak av sprit, som
					dere får refundert i etterkant av arrangementet. Maten må
					dere fikse selv, og helst ha klart til arrangementet
					begynner. For eksempel kan man benytte tjenester som
					Foodora. For tilbakebetaling må man vise til kvittering! Mer
					informasjon om dette kommer på mail til alle påmeldte i
					etterkant av arrangementet.
				</p>
			</div>
			<div class="card info" in:fly={{y: 20}}>
				<h2>Info</h2>
				<ul class="nox">
					<li>
						<span>Tid</span>
						<strong>Onsdag 30. september</strong>
					</li>
					<li><span>Pris</span> <strong>Gratis</strong></li>
					<li>
						<span>Sted</span>
						<span><a href="https://bit.ly/39Hoib0">Digitalt</a></span>
					</li>
					<li><span>Påmeldte</span> <strong>10/40</strong></li>
				</ul>
				<button>Meld meg på</button>
			</div>
		</div>
	{/if}
</main>
