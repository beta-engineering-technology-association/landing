<script>
	import {onMount} from 'svelte';
	import {fly} from 'svelte/transition';
	import {router} from 'tinro';

	$: console.log();

	onMount(() => {
		show = true;
	});

	let show = false;

	const about = `		
		<h2>Om Beta</h2>
			<p>
				Beta er linjeforeningen for datastudenter ved Universitetet
				i Agder. Beta er en non-profit organisasjon. Det betyr Beta
				ikke driver for å tjene penger, men heller bruker
				fortjenesten på våre medlemmer. Alle studenter ved
				datarelaterte fag ved UiA er automatisk medlem av Beta
				dersom en ikke aktivt melder seg ut. Det betyr at vi idag
				har omlag 500 medlemmer.
			</p>`;

	const verv = `		
		<h2>Verv</h2>
			<p>
				Beta har 8 forskjellige verv i hovedstyret
				<ul style="list-style:none; padding:0">
					<li>Leder</li>
					<li>Nestleder</li>
					<li>Økonomiansvarlig</li>
					<li>BetaLAN leder</li>
					<li>Bedkom leder</li>
					<li>Eventkom leder</li>
					<li>BetaDEV leder</li>
					<li>BetaSEC leder</li>
				</ul>
			</p>
		<h3>Leder</h3>
		<p>
			Lederen har den øverste ansvaret i organisasjonen. De skal sørge for
			 den daglige driften av organisasjonen.
		</p>

		<br>

		<h3>Nestleder</h3>
		<p>
			Nestlederens ansvar er å være lederens høyre hånd.
		</p>

		<br>

		<h3>Økonomiansvarlig</h3>
		<p>
			Økonomiansvarlig har ansvaret for organisasjonens økonomi.
		</p>

		<br>

		<h3>BetaLAN leder</h3>
		<p>
			BetaLAN leder har ansvar for å planlegge, og organisere BetaLan,
			som er et LAN-party som blir avholdt en gang per semester.
		</p>

		<br>

		<h3>Bedkom leder</h3>
		<p>
			Bedkom leder har ansvar for å ha kontakt med bedrifter, og planlegge
			framtidige bedrifstpresentasjoner, og andre arrangementer.
		</p>
		<div>

		<br>

		<h3>Eventkom leder</h3>
		<p>
			Eventkom leder har ansvar for å planlegge og organisere andre 
			arrangementer som skal skje i løpet av semesteret.
		</p>
		<div>

		<br>

		<h3>BetaDEV leder</h3>
		<p>
			BetaDEV leder har ansvar for interessegruppen BetaDEV. Ansvaret her
			ligger i å planlegge og oragnisere et møte annenhver uke, samt
			eventuelt andre arrangementer.
		</p>
		</div>

		<br>

		<h3>BetaSEC leder</h3>
		<p>
			BetaSEC leder har ansvar for interessegruppen BetaSEC. Ansvaret her
			ligger i å planlegge og oragnisere et møte annenhver uke, samt
			eventuelt andre arrangementer.
		</p>
		`;

	const interestGroups = `
				<h2>Interessegrupper</h2>
				<div class="cont">
					<div class="half">
						<img alt="betasec" src="/betadev.png" />
						<p>
							BetaSec er en gruppe studenter med interresse for
							sikkerhet. Her går vi gjennom alt fra CTF'er til
							andre sikkerhetsrelaterte utfordringer.
						</p>
					</div>
					<br/>
					<br/>
					<div class="half">
						<img alt="betadev" src="/betasec.png" />
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
	
			`;

	const history = `
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
		`;

	const getPage = page => {
		switch (page) {
			case 'interest':
				return interestGroups;
			case 'verv':
				return verv;
			case 'about':
				return about;
			case 'history':
				return history;
		}
	};

	$: content = getPage($router.path.split('/').pop());
</script>

<style>
	.container {
		display: grid;
		grid-gap: 20px;
		grid-template-areas: 'sidebar content';
		grid-template-columns: 1fr 3fr;
	}
	.sidebar {
		grid-area: sidebar;
		padding: 15px;
	}
	.content {
		grid-area: content;
	}
	ul {
		list-style: none;
		padding-left: 0;
		margin-top: 0;
	}
	li {
		padding: 10px;
	}
	li.selected {
		background-color: #eee;
	}
	.card {
		min-height: 600px;
	}
</style>

<svelte:head>
	<title>Om oss - Beta</title>
	<meta name="description" content="Informasjon om Beta" />
</svelte:head>

<main>
	{#if show}
		<div class="container" in:fly={{y: 20}}>
			<div class="card sidebar">
				<ul>
					<a href="/about">
						<li
							class={$router.path
								.split('/')
								.pop() === 'about' && 'selected'}>
							Om BETA
						</li></a>
					<a href="/about/interest">
						<li
							class={$router.path
								.split('/')
								.pop() === 'interest' && 'selected'}>
							Interessegrupper
						</li></a>
					<a href="/about/verv">
						<li
							class={$router.path
								.split('/')
								.pop() === 'verv' && 'selected'}>
							Verv
						</li></a>
					<a href="/about/history"><li
							class={$router.path
								.split('/')
								.pop() === 'history' && 'selected'}>
							Historie
						</li></a>
				</ul>
			</div>

			<div class="card content">
				{@html content}
			</div>
		</div>
	{/if}
</main>
