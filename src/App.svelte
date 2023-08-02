<script>
	import Nav from "./components/Nav.svelte";
	import Footer from "./components/Footer.svelte";
	import Hero from "./components/Hero.svelte";
	import About from "./components/About.svelte";
	import Researcher from "./components/Researcher.svelte";
	import Funding from "./components/Funding.svelte";
	import Publications from "./components/Publications.svelte";
	import Contact from "./components/Contact.svelte";
	import StackBRAF from "./components/StackBRAF.svelte";
	import StackHacat from "./components/StackHacat.svelte";
	import UploadImage from "./components/UploadImage.svelte";
	import Model from "./components/Model.svelte";
	import ResultStackBraf from "./components/ResultStackBRAF.svelte";
	import ResultStackHacat from "./components/ResultStackHacat.svelte";
	import PocketBase from 'pocketbase';
    import Login from "./components/Login.Svelte";
    import Register from "./components/Register.svelte";

	function getDataFromHash() {
		const hash = window.location.hash.slice(1);
		const [route, data, name] = hash.split("#");
		return { route, data: data || null };
	}

	let { route, data } = getDataFromHash();

	function handlehash() {
		const { route: newRoute, data: newData } = getDataFromHash();
		route = newRoute;
		data = newData;
	}

	handlehash();
</script>

<svelte:window on:hashchange={handlehash} />

{#if route == "stackbraf"}
	<Nav />
	<StackBRAF />
	<Footer />
{:else if route == "successStackBRAF"}
	<Nav />
	<ResultStackBraf process_id={data} />
	<Footer />
{:else if route == "stackhacat"}
	<Nav />
	<StackHacat />
	<Footer />
{:else if route == "successStackHacat"}
	<Nav />
	<ResultStackHacat process_id={data} />
	<Footer />
{:else if route == "spheroiddeath"}
	<Nav />
	<UploadImage />
	<Footer />
{:else if route == "model"}
	<Nav />
	<Model />
	<Footer />
{:else if route == "login"}
	<Nav />
	<Login />
	<Footer />
{:else if route == "register"}
	<Nav />
	<Register />
	<Footer />
{:else}
	<Nav />
	<Hero />
	<About />
	<Researcher />
	<Funding />
	<Publications />
	<Contact />
	<Footer bg="white" />
{/if}
