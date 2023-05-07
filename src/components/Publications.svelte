<script>
    import publicationDatas from "../data/publications.json"
    import PublicationCard from "./profilecards/PublicationCard.svelte"
</script>

<section id="publications">
    <h1>Publications</h1>
    <div class="wrapper">
        {#each publicationDatas as data }
        <PublicationCard
        title = {data.title}
        year = {data.year}
        journal = {data.journal}
        author = {data.authors}
        />
        {/each}
    </div>
</section>

<style>
    section {
        background-color: #f5f5f5;
        text-align: center;
        font-size: 30px;
        padding: 30px;
    }

    .wrapper {
        display: grid;
        grid-template-columns:  1fr 1fr;
        padding: 50px;
        justify-content: center;
    }
</style>