<script>
    import { onMount } from "svelte";

    export let process_id

    let jsonData
    let key
    let pIC50
    let IC50
    let AD_status

    async function get_result() {
        const res = await fetch(`/braf/${process_id}`)
        const data = await res.json()

        if (data.status == "complete") {
            jsonData = JSON.parse(data.result)
            key = Object.keys(jsonData)[0]

            let Key = jsonData[key]

            pIC50 = Key.pIC50.toPrecision(3)
            IC50 = Key.IC50.toPrecision(3)
            AD_status = Key.AD_status
        } else if (data.status == "processing") {
            setTimeout(get_result,2000)
        }
    }

    onMount(() => {
        get_result()
    })
</script>

<section class="wrapper">
    {#if jsonData}
    <div>
        <h1>Result</h1>
        <h3>Ligand: {key}</h3>
        <h3>pIC50: {pIC50}</h3>
        <h3>IC50: {IC50}</h3>
        <h3>Activity Domain: {AD_status}</h3>
        <br>
    </div>
    {:else}
    <div>
        <h1>Your request is being process.</h1>
        <h2>Please wait a moment.</h2>
    </div>
    {/if}
</section>

<style>
    .wrapper {
        padding-top: 80px;
    }

    .wrapper div {
        margin: 0 auto;
        font-size: 30px;
        padding: 50px;
        width: 50%;
    }

    .wrapper div h1,h2 {
        text-align: center;
    }

    @media (max-width: 1200px) {
        .wrapper div {
            font-size: medium;
            margin-top: 25px;
            padding: 0;
        }
    }
</style>