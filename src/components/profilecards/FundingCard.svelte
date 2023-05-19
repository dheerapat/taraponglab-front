<script>
    export let profileurl
    export let profilealt
    export let name
    export let detail
</script>
<div class="card">
    <img src="{profileurl}" alt="{profilealt}" width="75%">
    <h3>{name}</h3>

</div>

<style>
    .card {
        /* border-style: dashed;
        border-color: black;
        border-width: 2px; */
        margin: 20px;
        text-align: center;
        padding: 15px 20px;
        /* border-radius: 20px; */
        font-size: 20px;
    }

    img {
        height: 250px;
        object-fit: contain;
    }
</style>