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
	import VitaminC from "./components/VitaminC.svelte";
	import Model from "./components/Model.svelte";
	import ResultStackBraf from "./components/ResultStackBRAF.svelte";
	import ResultStackHacat from "./components/ResultStackHacat.svelte";
	// import PocketBase from "pocketbase";
	import Login from "./components/Login.svelte";
	import Register from "./components/Register.svelte";
	import { onMount } from "svelte";
	import Braf from "./components/Braf.svelte";
    import ResultBraf from "./components/ResultBraf.svelte";

	// const pb = new PocketBase("https://pb.qsarlabs.com");

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

	let isAuthValid = true;

	// const checkAuthValidity = () => {
	// 	if (pb.authStore.isValid) {
	// 		isAuthValid = true;
	// 	}
	// 	// console.log(isAuthValid);
	// };

	const handlehashChange = () => {
		handlehash();
		// checkAuthValidity();
	};

	onMount(() => {
		handlehashChange();
		// console.log(isAuthValid);
	});
</script>

<svelte:window on:hashchange={handlehashChange} />

{#if route == "stackbraf"}
	<Nav />
	<StackBRAF auth={isAuthValid} />
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
{:else if route == "vitaminc"}
	<Nav />
	<VitaminC />
	<Footer />
{:else if route == "braf"}
	<Nav />
	<Braf />
	<Footer />
{:else if route == "successBRAF"}
	<Nav />
	<ResultBraf process_id={data} />
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
