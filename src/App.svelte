<script>
	import {Route} from 'tinro';

	import Head from './components/Head.svelte';
	import Home from './pages/Home.svelte';
	import Events from './pages/Events.svelte';
	import Bedrift from './pages/Bedrift.svelte';
	import About from './pages/About.svelte';
	import Footer from './components/Footer.svelte';
</script>

<Head />
<Route path="/">
	<Home />
</Route>
<Route path="/events">
	<Events />
</Route>
<Route path="/bedrift">
	<Bedrift />
</Route>
<Route path="/about">
	<About />
</Route>
<Footer />
