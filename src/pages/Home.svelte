<script>
	import {onMount} from 'svelte';

	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;

	const sopraLogo = '/sopra-logo.png';
</script>

<style>
	.container {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 20px;
		grid-template-areas:
			'header header'
			'bedpres partner'
			'nytt facebook ';
	}
	.header {
		grid-area: header;
	}
	.bedpres {
		grid-area: bedpres;
	}
	.partner {
		grid-area: partner;
	}
	.facebook {
		grid-area: facebook;
	}
	.nytt {
		grid-area: nytt;
	}
	ul {
		list-style: none;
		padding: 0px;
	}
	li {
		display: flex;
		justify-content: space-between;
	}
	.dist {
		margin: 5px;
		padding: 0;
	}
	.full {
		width: 100%;
	}
	.gray {
		color: #555;
		padding-left: 5px;
	}
	.news {
		margin-bottom: 30px;
	}
	.cont {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-gap: 40px;
	}
	img {
		width: 100%;
	}
</style>

<svelte:head>
	<title>Hjem - Beta</title>
	<meta
		name="description"
		content="BETA er linjeforeningen for datastudenter ved UiA, og drives av studenter ved disse studiene." />
</svelte:head>

<main>
	{#if show}
		<div class="container" in:fly={{y: 20}}>
			<div class="card header">
				<h2>Velkommen til BETA!</h2>
				<p>
					BETA er linjeforeningen for datastudentene ved UiA, og
					drives av studenter ved disse studiene.
				</p>
				<p>
					BETA's formål er å gi disse studentene veiledning i
					studiesituasjonen, arrangere kurs som utfyller fagtilbudet
					ved UiA, fremme kontakten med næringslivet og bidra med
					sosiale aktiviteter.
				</p>
			</div>

			<div class="card partner">
				<h2>Hovedsamarbeidspartner</h2>
				<a href="https://www.soprasteria.no/"><img
						alt="soprasteria"
						src={sopraLogo} /></a>
			</div>

			<div class="card bedpres">
				<div class="cont">
					<div class="half">
						<h2>Bedpres / Kurs</h2>
						<ul class="nox">
							<li>
								<a href="/event2">Mnemonic</a>
								<span>15.10</span>
							</li>
							<li>
								<a href="/event">Sopra Steria</a>
								<span>05.11</span>
							</li>
						</ul>
					</div>
					<div class="half">
						<h2>Møter</h2>
						<ul class="nox">
							<li>
								<a href="/event3">BetaLAN</a>
								<span>17.09</span>
							</li>
							<li><a href="/">BetaSec</a> <span>17.09</span></li>
							<li><a href="/">BetaDev</a> <span>24.10</span></li>
						</ul>
					</div>
				</div>
			</div>

			<div class="card facebook">
				<div class="full" in:fly>
					<h2>Facebook</h2>
					<div
						class="fb-page"
						data-href="https://www.facebook.com/beta.linjeforening/"
						data-tabs="timeline"
						data-width=""
						data-height=""
						data-small-header="true"
						data-adapt-container-width="true"
						data-hide-cover="false"
						data-show-facepile="false">
						<blockquote
							cite="https://www.facebook.com/beta.linjeforening/"
							class="fb-xfbml-parse-ignore">
							<a
								href="https://www.facebook.com/beta.linjeforening/">BETA
								- Linjeforeningen for datastudenter</a>
						</blockquote>
					</div>
				</div>
			</div>

			<div class="card nytt">
				<div>
					<h2>Siste nytt</h2>
					<div class="news">
						<a href="/"><h3 class="dist">BetaLAN Pog!</h3>
							<p class="dist">
								Da er det straks klart for en ny runde med
								BetaLAN! BetaLAN vil foregå på bluebox som
								vanlig, og finner i år sted den 25.10. Husk å
								meld dere på arrangementet på forhånd slik at
								dere bare kan...
							</p>
						</a>
						<div class="gray">28.08.2020</div>
					</div>
					<div class="news">
						<a href="/"><h3 class="dist">CGI</h3>
							<p class="dist">
								21.09.2020 Kommer CGI for å holde
								bedriftspresentasjon med beta! Her er det gode
								muligheter for å bli kjent med en vikitg aktør
								fra næringslivet! Det blir servert Wraps og
								brus! Påmelding via docs...
							</p>
						</a>
						<div class="gray">28.08.2020</div>
					</div>
				</div>
			</div>
		</div>
	{/if}
</main>
