<script>
	import {onMount} from 'svelte';

	import {fly} from 'svelte/transition';

	import Map from '../components/Map.svelte';

	onMount(() => {
		show = true;
	});

	let show = false;

	const handleDateChange = e => {
		console.log(e);
	};
</script>

<style>
	input,
	textarea {
		width: 100%;
		max-width: 100%;
	}
	textarea {
		height: 100px;
		resize: vertical;
	}
	.third {
		width: 49%;
		display: inline-table;
	}
	input[type='submit'] {
		width: 50%;
	}

	.tab-bar {
		margin: 30px auto;
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		list-style-type: none;
		-webkit-padding-start: 0;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
	}

	.tab {
		width: 150px;
		padding: 20px 0;
		background: white;
		color: #607d8b;
		overflow: hidden;
		text-align: center;
		flex-grow: 1;
		cursor: pointer;
		position: relative;
	}

	.indicator {
		width: 500px;
		height: 3px;
		background: #2196f3;
		position: absolute;
		margin-top: 58px;
		margin-left: 0;
		transition: margin 0.5s ease;
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
				<h2>Rediger arrangement</h2>
				<ul class="tab-bar">
					<li data-num="1" class="tab wave dark">INFO</li>
					<li data-num="2" class="tab wave dark">ØKONOMI</li>
					<div class="indicator" />
				</ul>

				<!--
				<div class="third">
					<label for="name">Navn på arrangement</label><br />
					<input id="name" /><br />

					<label for="description">Beskrivelse</label><br />
					<textarea id="description" /><br />

					<div class="third">
						<label for="date1">Fra Dato</label><br />
						<input
							id="date1"
							type="date"
							on:change={handleDateChange} /><br />
						<label for="date1">Fra Klokka</label><br />
						<input id="date1" type="time" /><br />
					</div>

					<div class="third">
						<label for="date2">Til Dato</label><br />
						<input id="date2" type="date" /><br />
						<label for="date2">Til Klokka</label><br />
						<input id="date2" type="time" /><br />
					</div>
					<br />

					<label for="room">Rom</label><br />
					<input id="room" autocomplete="off" /><br />

					<label for="price">Pris</label><br />
					<input id="price" /><br />

					<label for="responsible">Ansvarlig for arrangementet</label><br />
					<input id="responsible" /><br />

					<input type="submit" value="Forhåndsvis" />
					<input type="submit" value="Lagre" /><br /><br />
				</div>
				<div class="third">
					<br />

					<Map />
				</div>
-->

				<div class="third">
					<label for="firm">Firmanavn</label><br />
					<input id="firm" /><br />

					<label for="address">Faktureringsaddresse</label><br />
					<input id="address" /><br />

					<label for="reference">Referanseperson</label><br />
					<input id="reference" /><br />

					<label for="email">Epost</label><br />
					<input id="email" /><br />

					<label for="mark">Merk faktura med</label><br />
					<input id="mark" /><br />

					<label for="notes">Notater</label><br />
					<textarea id="notes" /><br />

					<label for="room">Vedlegg</label><br />
					<input type="button" value="Legg til" />
				</div>
			</div>
		</div>
	{/if}
</main>
