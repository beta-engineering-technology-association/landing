<script>
	import {onMount} from 'svelte';

	import {fly} from 'svelte/transition';

	onMount(() => {
		show = true;
	});

	let show = false;

	const logo = '/logo.png';
	const sopraLogo = '/sopra-logo.png';
</script>

<style>
	main {
		max-width: 1100px;
		margin: 0 auto;
	}
	.container {
		display: grid;
		grid-template-columns: 1.3fr 1fr;
		grid-gap: 30px;
	}
	.card {
		box-shadow: 0 1px 4px rgba(0, 0, 0, 0.04);
		padding: 30px;
		border-radius: 5px;
		background: white;
	}
	a:hover {
		color: #057cea;
	}

	h2 {
		margin-top: 0;
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
	input {
		width: 100%;
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
			<div class="card">
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

			<div class="card">
				<h2>Logg inn</h2>
				<label for="username">Brukernavn</label>
				<input id="username" />
				<label for="password">Passord</label>
				<input id="password" type="password" />
				<input type="submit" value="Logg inn" />
			</div>

			<div class="card">
				<div class="cont">
					<div class="half">
						<h2>Bedriftspresentasjon</h2>
						<ul class="nox">
							<li><span>CGI</span> <span>21.09</span></li>
							<li><span>Mnemonic</span> <span>15.10</span></li>
						</ul>
					</div>
					<div class="half">
						<h2>Møter</h2>
						<ul class="nox">
							<li><span>BetaSec</span> <span>17.09</span></li>
							<li><span>BetaDev</span> <span>24.10</span></li>
						</ul>
					</div>
				</div>
			</div>

			<div class="card">
				<h2>Hovedsponsor</h2>
				<a href="https://www.soprasteria.no/"><img
						alt="sponsor-logo"
						src={sopraLogo}
						width="100%" /></a>
			</div>

			<div class="card">
				<div>
					<h2>Siste nytt</h2>
					<div class="news">
						<h3 class="dist">BetaLAN Pog!</h3>
						<p class="dist">
							Da er det straks klart for en ny runde med BetaLAN!
							BetaLAN vil foregå på bluebox som vanlig, og finner
							i år sted den 25.10. Husk å meld dere på
							arrangementet på forhånd slik at dere kan bestille
							bordplass
						</p>
						<div class="gray">28.08.2020</div>
					</div>
					<div class="news">
						<h3 class="dist">CGI</h3>
						<p class="dist">
							21.09.2020 Kommer CGI for å holde
							bedriftspresentasjon med beta! Her er det gode
							muligheter for å bli kjent med en vikitg aktør fra
							næringslivet! Det blir servert Wraps og brus!
							Påmelding via docs skjema! Åpent for alle årstrinn!
						</p>
						<div class="gray">28.08.2020</div>
					</div>
				</div>
			</div>

			<div class="card">
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
		</div>
	{/if}
</main>
