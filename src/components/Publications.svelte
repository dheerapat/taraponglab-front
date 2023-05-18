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
        background: radial-gradient(at 50% 40%, rgb(255, 255, 255), transparent 80%) repeat scroll 0% 0%, radial-gradient(at 50% -47%, #bbdef9, transparent 80%) repeat scroll 0% 0%, radial-gradient(at 100% 0%, #bbdef9 0px, transparent 32%) repeat scroll 0% 0%, radial-gradient(at 100% 98%, rgb(255, 241, 235), transparent) repeat scroll 0% 0%, rgba(0, 0, 0, 0) radial-gradient(at 0px 97%, rgb(181, 233, 247), white) repeat scroll 0% 0%;
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