<script>
    export let title
    export let journal
    export let year
    export let author
</script>

<div>
    <h1>{title}</h1>
    <h5>{journal}</h5>
    <p>{year}</p>
    <h3>{author}</h3>
</div>

<style>
    div {
        text-align: left;
        font-size: medium;
        margin: 15px;
        background-color: white;
        padding: 15px;
        border-radius: 15px;
        border-style: dashed;
        border-color: black;
        border-width: 2px;
    }
    div > * {
        margin: 10px;
    }
</style>