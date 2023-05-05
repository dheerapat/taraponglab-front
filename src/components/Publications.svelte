<script>
    import publicationDatas from "../data/publications.json"
    import PublicationCard from "./profilecards/PublicationCard.svelte"
</script>

<section>
    <h1>Publications</h1>
    {#each publicationDatas as data }
    <PublicationCard
    title = {data.title}
    year = {data.year}
    journal = {data.journal}
    author = {data.authors}
    />
    {/each}
</section>