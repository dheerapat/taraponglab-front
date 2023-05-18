<script>
    import Card from "./profilecards/FundingCard.svelte"
    
</script>

<section id="funding">
    <h1>Funding</h1>
    <div class="wrapper">
        <Card
        profileurl="/img/NRCT.png"
        profilealt="National Research Council of Thailand"
        name="Fundamental Fund"
        detail="National Research Council of Thailand"
        />
        <Card
        profileurl="/img/MHESRI.png"
        profilealt="Ministry of Higher Education, Science, Research and Innovation"
        name="Research Grant for New Scholar"
        detail="Ministry of Higher Education, Science, Research and Innovation"
        />
        <Card
        profileurl="/img/kku.png"
        profilealt="Khon Kaen University"
        name="New Researcher Grant"
        detail="Khon Kaen University"
        />
    </div>
</section>

<style>
    section {
        text-align: center;
        font-size: 30px;
        
    }

    .wrapper {
        display: flex;
        grid-template-columns:  1fr 1fr 1fr 1fr;
        padding: 50px;
        justify-content: center;
        align-items: center;
    }
</style>