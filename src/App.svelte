<script>
	import Nav from "./components/Nav.svelte"
	import Footer from "./components/Footer.svelte"
	import Hero from "./components/Hero.svelte"
	import About from "./components/About.svelte"
	import Researcher from "./components/Researcher.svelte";
    import Publications from "./components/Publications.svelte";
    import Form from "./components/Form.svelte"
    // import { onMount } from "svelte"

	let route = window.location.hash.slice(1)

	function handlehash() {
		route = window.location.hash.slice(1)
		console.log(route)
	}

	// onMount(handlehash)
</script>

<svelte:window on:hashchange={handlehash} />

{#if route == "model"}
	<Nav />
	<Form />
	<Footer />
{:else}
	<Nav />
	<Hero />
	<About />
	<Researcher />
	<Publications />
	<Footer bg="white" />
{/if}