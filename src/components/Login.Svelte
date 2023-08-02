<script>
    import PocketBase from "pocketbase";
    const pb = new PocketBase("http://127.0.0.1:8090");

    let email = "";
    let pass = "";

    async function login() {
        try {
            const authData = await pb
                .collection("users")
                .authWithPassword(email, pass);
            console.log(authData);
        } catch (error) {
            console.log(error);
        }
    }
</script>

<section>
    <div>
        <form on:submit|preventDefault={login}>
            <input type="email" placeholder="E-mail" bind:value={email} />
            <input type="password" placeholder="Password" bind:value={pass} />
            <input type="submit" value="Login" />
        </form>
    </div>
</section>