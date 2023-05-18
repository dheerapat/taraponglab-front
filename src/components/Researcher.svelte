<script>
    import Card from "./profilecards/ResearcherCard.svelte"
</script>

<section id="researchers">
    <h1>Researchers</h1>
    <div class="wrapper">
        <Card
        profileurl="/img/01.jpg"
        profilealt="Tarapong Srisonkram"
        name="Tarapong Srisongkram"
        detail="Principal Investigator"
        study="Ph.D."
        />
    
        <Card
        profileurl="/img/02.jpg"
        profilealt="Dheerapat Tookkane"
        name="Dheerapat Tookkane"
        detail="Developer"
        study="Pharm.D."
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
        /*grid-template-columns:  1fr 1fr 1fr 1fr;*/
        padding: 50px;
        justify-content: center;
        align-items: center;
    }
</style>