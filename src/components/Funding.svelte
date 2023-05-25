<script>
    import Card from "./profilecards/FundingCard.svelte"
    
</script>

<section id="funding">
    <h1>Funding</h1>
    <div class="wrapper">
        <Card
        profileurl="/img/NRCT.png"
        profilealt="National Research Council of Thailand"
        name="National Research Council of Thailand"
        />
        <Card
        profileurl="/img/MHESRI.png"
        profilealt="Ministry of Higher Education, Science, Research and Innovation"
        name="Ministry of Higher Education, Science, Research and Innovation"
        />
        <Card
        profileurl="/img/kku.png"
        profilealt="Khon Kaen University"
        name="Khon Kaen University"
        />
    </div>
</section>

<style>
    section {
        text-align: center;
        font-size: 30px;
        
    }

    .wrapper {
        display: grid;
        grid-template-columns:  1fr 1fr 1fr;
        padding: 50px;
        justify-content: center;
        align-items: center;
    }

    @media (max-width: 1200px) {
        .wrapper {
            grid-template-columns: 1fr;
        }
    }
</style>