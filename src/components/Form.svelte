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

        const resData = await res.json()
        const processID = resData.process_id
        
        if (res.ok) {
            console.log(processID)
            window.location.hash = `success#${processID}#${name}`
        } else {
            alert("API Call Failed: Please report to admin")
        }
    }
</script>

<section>
    <h1>StackBRAF Model</h1>
    <div>
        <form on:submit|preventDefault={prediction}>
            <label for="name">Name</label>
            <input id="name" name="name" type="text" bind:value={name}><br>
            <label for="smiles">SMILES</label>
            <input id="smiles" name="smiles" type="text" bind:value={smiles}><br>
            <button type="submit" width="20%">Predict</button>
        </form>
    </div>
</section>

<style>
    section {
        background-color: white;
        font-size: 30px;
        padding: 50px;
        margin-top: 50px;
        margin-bottom: 30px;
    }
    h1, form {
        text-align: center;
    }
    
</style>