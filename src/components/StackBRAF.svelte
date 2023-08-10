<script>
    import { onMount } from "svelte";

    export let auth;
    let name;
    let smiles;

    async function prediction() {
        const data = { name, smiles };

        const res = await fetch("/stackbraf/", {
            method: "POST",
            mode: "same-origin",
            credentials: "same-origin",
            headers: {
                "Content-type": "application/json",
            },
            body: JSON.stringify(data),
        });

        const resData = await res.json();
        const processID = resData.process_id;

        if (res.ok) {
            console.log(processID);
            window.location.hash = `successStackBRAF#${processID}#${name}`;
        } else {
            alert("API Call Failed: Please report to admin");
        }
    }

    onMount(() => {
        if (auth == false) {
            window.location.hash = "login";
        }
    });
</script>

<section>
    <h1>
        StackBRAF: a large-scale stacking ensemble learning for BRAF affinity
        prediction
    </h1>
    <h4>
        You can enter your compound name and SMILES to predict BRAF affinity
        concentration (pIC50)
    </h4>
    <div>
        <form on:submit|preventDefault={prediction}>
            <label for="name">Name</label>
            <input id="name" name="name" type="text" bind:value={name} /><br />
            <label for="smiles">SMILES</label>
            <input
                id="smiles"
                name="smiles"
                type="text"
                bind:value={smiles}
            /><br />
            <button type="submit" width="20%">Predict</button>
        </form>
    </div>
</section>

<style>
    section {
        background-color: white;
        font-size: 30px;
        padding: 50px;
        margin-top: 100px;
        margin-bottom: 100px;
    }
    h1,
    h4,
    form {
        text-align: center;
    }
    form {
        margin-top: 100px;
    }

    @media (max-width: 1200px) {
        section {
            font-size: medium;
            margin-top: 25px;
        }
    }
</style>
