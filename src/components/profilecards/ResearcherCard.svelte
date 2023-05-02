<script>
    export let profileurl
    export let profilealt
    export let name
    export let detail
    export let study
    export let email
</script>

<div class="card">
    <img src="{profileurl}" alt="{profilealt}" width="75%">
    <h3>{name}</h3>
    <p>{detail}</p>
    <p>{study}</p>
    <a href="mailto:{email}">{email}</a>
</div>

<style>
    .card {
        border-style: dashed;
        border-color: black;
        border-width: 2px;
        margin: 20px;
        text-align: center;
        padding: 15px 20px;
        border-radius: 20px;
        font-size: 20px;
    }

    img {
        border-radius: 20px;
        width: 300px;
        height: 400px;
        object-fit: cover;
        object-position: top;
    }
</style>