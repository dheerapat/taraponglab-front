<script>
    import PocketBase from "pocketbase";
    const pb = new PocketBase("https://pb.qsarlabs.com");

    let email = "";
    let pass = "";

    async function login() {
        try {
            const authData = await pb
                .collection("users")
                .authWithPassword(email, pass);
            // console.log(authData);
            window.location.hash = '';
        } catch (error) {
            console.log(error);
        }
    }
</script>

<section>
    <h1>Please login before using our model.</h1>
    <div>
        <form on:submit|preventDefault={login}>
            <label for="email">E-mail</label>
            <input id="email" name="email" placeholder="E-mail" bind:value={email} /><br>
            <label for="password">Password</label>
            <input id="password" name="password" placeholder="Password" type="password" bind:value={pass} /><br>
            <input type="submit" value="Login" />
        </form>
    </div>
    <h4>Not a member? Click <a href="#register">here</a> to register.</h4>
    
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