<script>
    let name
    let smiles

    async function prediction() {
        const data = {name, smiles}

        const res = await fetch("http://localhost:8000/stackbraf",
        {
            method: "POST",
            headers: {
                "Content-type": "application/json"
            },
            body: JSON.stringify(data)
        })

        if (res.ok) {
            alert(res)
        } else {
            alert("API call failed")
        }
    }
</script>

<section>
    <h1>StackBRAF Model</h1>
    <div>
        <form on:submit|preventDefault={prediction}>
            <input type="text" bind:value={name}>
            <input type="text" bind:value={smiles}>
            <button type="submit">Submit</button>
        </form>
    </div>
</section>