<script>
    import publicationDatas from "../data/publications.json"
    import PublicationCard from "./profilecards/PublicationCard.svelte"
</script>

<section id="publications">
    <h1>Publications</h1>
    <div class="pub">
        <a href="https://scholar.google.com/citations?user=1-XwteMAAAAJ&hl=en&fbclid=IwAR0RY1TGIqzMglcu_b7VUJlpr9uTEJ3I-Mcp0jnzazFlbsrGbCjmp0x0qXg">Google Scholar</a>
        <a href="https://orcid.org/0000-0001-8512-5379?fbclid=IwAR0SFf85_RdmRWTPC5whUmw-5S4aKQ5pFIIBCtPn2PgKOw214KZhtGDtIV4">ORCID</a>
        <a href="https://www.scopus.com/authid/detail.uri?origin=resultslist&authorId=57211125114&zone=&fbclid=IwAR2HLYhTJZKG3sFUA7iZ3BlsVK__tC8OFfESXZOmtZfxM5T89GQTwIYbO-o">Scopus</a>
    </div>
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

    .pub {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }

    /* p {
        display: inline;
    } */

    .wrapper {
        display: grid;
        grid-template-columns:  1fr 1fr;
        padding: 50px;
        justify-content: center;
    }

    @media (max-width: 1366px) {
        .wrapper {
            grid-template-columns: 1fr;
        }
    }

    @media (max-width: 810px) {
        .pub {
            grid-template-columns: 1fr;
        }

        .wrapper {
            padding: 50px 0;
        }
    }
</style>