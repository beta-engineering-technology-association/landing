<script>
	import {Route} from 'tinro';

	import Head from './components/Head.svelte';
	import Home from './pages/Home.svelte';
	import Events from './pages/Events.svelte';
	import Jobs from './pages/Jobs.svelte';
	import Bedrift from './pages/Bedrift.svelte';
	import About from './pages/About.svelte';
	import Footer from './components/Footer.svelte';
	import Event from './pages/Event.svelte';
	import Event2 from './pages/Event2.svelte';
	import Event3 from './pages/Event3.svelte';
</script>

<Head />
<Route path="/">
	<Home />
</Route>
<Route path="/events">
	<Events />
</Route>
<Route path="/jobs">
	<Jobs />
</Route>
<Route path="/bedrift">
	<Bedrift />
</Route>
<Route path="/about">
	<About />
</Route>
<Route path="/event">
	<Event />
</Route>
<Route path="/event2">
	<Event2 />
</Route>
<Route path="/event3">
	<Event3 />
</Route>
<Footer />
