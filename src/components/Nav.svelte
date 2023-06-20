<script>
    let visible = false

    function toggle() {
        visible = !visible
        console.log(visible)
    }

    function noVisibility() {
        visible = false
    }
</script>

<svelte:window on:resize={noVisibility}/>

<nav>
    <a href="/"> <img src="/Banner-2.png" alt="QSARLabs logo" id="logo" /></a>
    <a class="hidable" href="#about">About Us</a>
    <a class="hidable" href="#researchers">Researchers</a>
    <a class="hidable" href="#funding">Funding</a>
    <a class="hidable" href="#publications">Publications</a>
    <a class="hidable" href="#contact">Contact</a>
    <a class="box hidable" href="/">Models</a>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="can_toggle" on:click={toggle}>
        <div class="toggle" />
        <div class="toggle" />
        <div class="toggle" />
    </div>
</nav>
<div id="myLinks" style="display: {visible ? "initial" : "none"};">
    <a href="#about">About Us</a>
    <a href="#researchers">Researchers</a>
    <a href="#funding">Funding</a>
    <a href="#publications">Publications</a>
    <a href="#contact">Contact</a>
    <a href="/">Models</a>
</div>

<style>
    nav {
        display: flex;
        justify-content: space-evenly;

        background: linear-gradient(
                    45deg,
                    rgb(26, 1, 117) 0%,
                    rgba(225, 5, 34, 0) 70%
                )
                repeat scroll 0% 0%,
            linear-gradient(
                    135deg,
                    rgb(225, 5, 152) 10%,
                    rgba(49, 5, 209, 0) 80%
                )
                repeat scroll 0% 0%,
            linear-gradient(
                    225deg,
                    hsla(179, 81%, 45%, 1) 10%,
                    rgba(10, 219, 216, 0) 80%
                )
                repeat scroll 0% 0%,
            rgba(0, 0, 0, 0)
                linear-gradient(
                    315deg,
                    rgb(189, 5, 245) 100%,
                    rgba(9, 245, 5, 0) 70%
                )
                repeat scroll 0% 0%;
        padding: 5px 20px;
        align-items: center;
        /* position: fixed;
        top: 0;
        width: 100%; */
    }

    nav a {
        font-size: 30px;
        text-decoration: none;
        color: white;
        font-weight: 600;
    }

    #myLinks a {
        padding: 14px 16px;
        text-decoration: none;
        font-size: 17px;
        display: block;
        text-align: center;
    }

    #logo {
        width: 200px;
        height: 70px;
    }
    .box {
        background-color: white;
        padding: 5px 15px;
        border-radius: 10px;
        color: #143f6b;
    }

    .toggle {
        width: 35px;
        height: 5px;
        background-color: white;
        margin: 6px 0;
    }

    @media (max-width: 1200px) {
        .hidable {
            display: none;
        }
        nav {
            justify-content: space-between;
        }
    }

    @media (min-width: 1200px) {
        .toggle {
            display: none;
        }
    }
</style>
