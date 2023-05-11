<script>
	import Nav from "./components/Nav.svelte"
	import Footer from "./components/Footer.svelte"
	import Hero from "./components/Hero.svelte"
	import About from "./components/About.svelte"
	import Researcher from "./components/Researcher.svelte";
    import Publications from "./components/Publications.svelte";
    import Form from "./components/Form.svelte"
    import Result from "./components/Result.svelte";

	function getDataFromHash() {
		const hash = window.location.hash.slice(1)
		const [route, data, name] = hash.split('#')
		return { route, data: data || null }
	}

	let { route, data } = getDataFromHash()

	function handlehash() {
		const { route: newRoute, data: newData } = getDataFromHash()
    	route = newRoute
    	data = newData
	}

	handlehash()
</script>

<svelte:window on:hashchange={handlehash} />

{#if route == "model"}
	<Nav />
	<Form />
	<Footer />
{:else if route =="success"}
	<Nav />
	<Result process_id = {data} />
	<Footer />
{:else}
	<Nav />
	<Hero />
	<About />
	<Researcher />
	<Publications />
	<Footer bg="white" />
{/if}