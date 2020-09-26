<script>
	import {active} from 'tinro';

	const logo = '/logo.png';
</script>

<style>
	.head {
		display: flex;
		margin: 50px auto 30px auto;
		max-width: 1100px;
		align-items: center;
	}
	.logo {
		flex-grow: 1;
	}
	a {
		font-size: 20px;
		margin: 0 15px;

		font-weight: normal;
	}
	a:not(:hover) {
		color: white;
	}
	.active {
		color: white;
		font-weight: bold;
	}
</style>

<nav class="head">
	<e class="active" />
	<a class="logo" href="/"><img height="48" alt="logo" src={logo} /></a>
	<a class="link" use:active href="/events">ARRANGEMENTER</a>
	<a class="link" use:active href="/jobs">STILLINGSANNONSER</a>
	<a class="link" use:active href="/bedrift">FOR BEDRIFTER</a>
	<a class="link" use:active href="/about">OM BETA</a>
</nav>
