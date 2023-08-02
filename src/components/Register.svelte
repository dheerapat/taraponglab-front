<script>
    import PocketBase from "pocketbase";
    const pb = new PocketBase("http://127.0.0.1:8090");

    let data = {
        username: "",
        email: "",
        emailVisibility: false,
        password: "",
        passwordConfirm: "",
        name: "",
    };

    async function register() {
        try {
            const record = await pb.collection('users').create(data);
            console.log(record);
        } catch (error) {
            console.log(error);
        }
    }
</script>

<section>
    <div>
        <form on:submit|preventDefault={register}>
            <input type="text" placeholder="Username" bind:value={data.username} />
            <input type="text" placeholder="Fullname" bind:value={data.name} />
            <input type="email" placeholder="E-mail" bind:value={data.email} />
            <input type="password" placeholder="Password" bind:value={data.password} />
            <input type="password" placeholder="Confirmed Password" bind:value={data.passwordConfirm} />
            <input type="submit" value="Login" />
        </form>
    </div>
</section>