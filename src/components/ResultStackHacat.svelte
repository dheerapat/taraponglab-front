<script>
    import { onMount } from "svelte";

    export let process_id

    let jsonData
    let key
    let pred
    let outlier
    let sim_train
    let sim_test

    async function get_result() {
        const res = await fetch(`/stackhacat/${process_id}`)
        const data = await res.json()

        if (data.status == "complete") {
            jsonData = JSON.parse(data.result)
            console.log(jsonData)
            key = Object.keys(jsonData)[0]

            let Key = jsonData[key]

            pred = Key["Skin Irritation Prediction"]
            outlier = Key["Compound Outlier"]
            sim_train = Key["Similarity to training set"] * 100
            sim_test = Key["Similarity to test set"] * 100
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
        <h3>Skin Irritation Prediction: {pred}</h3>
        <h3>Outlier: {outlier}</h3>
        <h3>Similarity to training set: {sim_train.toFixed(1)} %</h3>
        <h3>Similarity to test set: {sim_test.toFixed(1)} %</h3>
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