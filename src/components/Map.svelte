<script>
	import {onMount} from 'svelte';

	onMount(() => {
		console.log('mounting');
		const map = new Mazemap.Map({
			container: 'map',
			campuses: 225,
			campuses: '225',
			center: {lng: 8.576892, lat: 58.334367},
			zoom: 15,
			zLevel: 3,
		});

		map.addControl(new Mazemap.mapboxgl.NavigationControl());
	});
</script>

<style>
	#map {
		height: 520px;
	}
</style>

<div id="map" class="mazemap" />
