<script>
    import PocketBase from "pocketbase";
    const pb = new PocketBase("https://pb.qsarlabs.com");

    let data = {
        username: "",
        email: "",
        emailVisibility: false,
        password: "",
        passwordConfirm: "",
        name: "",
        surname: "",
        institute: "",
    };

    async function register() {
        try {
            const record = await pb.collection("users").create(data);
            console.log(record);
            window.location.hash = "login";
        } catch (error) {
            console.log(error);
        }
    }
</script>

<section>
    <h1>Register</h1>
    <div>
        <form on:submit|preventDefault={register}>
            <label for="username">Username</label>
            <input
                id="username"
                placeholder="Username"
                bind:value={data.username}
            /><br />
            <label for="name">Name</label>
            <input id="name" placeholder="Name" bind:value={data.name} /><br />
            <label for="surname">Surname</label>
            <input
                id="surname"
                placeholder="Surname"
                bind:value={data.surname}
            /><br />
            <label for="institute">Institute</label>
            <input
                id="institute"
                placeholder="Institute"
                bind:value={data.institute}
            /><br />
            <label for="email">E-mail</label>
            <input id="email" placeholder="E-mail" bind:value={data.email} /><br
            />
            <label for="password">Password</label>
            <input
                id="password"
                placeholder="Password"
                type="password"
                bind:value={data.password}
            /><br />
            <label for="confirmpassword">Confirm Password</label>
            <input
                id="confirmpassword"
                placeholder="Confirmed Password"
                type="password"
                bind:value={data.passwordConfirm}
            /><br />
            <input type="submit" value="Register" />
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
