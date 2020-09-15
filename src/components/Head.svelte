<script>
	import {active} from 'tinro';

	const logo = '/logo.png';
</script>

<style>
	.head {
		display: flex;
		margin: 50px auto 30px auto;
		max-width: 1100px;
	}
	.logo {
		flex-grow: 1;
	}
	a {
		font-size: 24px;
		margin: 0 10px;
		color: #333;
		text-decoration: none;
	}
	a:hover {
		color: #057cea;
	}
	.active {
		color: #000;
	}
</style>

<nav class="head">
	<e class="active" />
	<a class="logo" href="/"><img height="32" alt="logo" src={logo} /></a>
	<a use:active active-class="active" href="/events">ARRANGEMENTER</a>
	<a use:active active-class="active" href="/bedrift">FOR BEDRIFTER</a>
	<a use:active active-class="active" href="/about">OM BETA</a>
</nav>
