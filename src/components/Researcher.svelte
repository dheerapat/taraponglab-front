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

        <Card
        profileurl="/img/06.jpg"
        profilealt="Natthida Weerapreeyakul"
        name="Natthida Weerapreeyakul"
        detail="Mentor"
        study="Ph.D."
        />

        <Card
        profileurl="/img/05.jpg"
        profilealt="Nur Fadhilah Syahid"
        name="Nur Fadhilah Syahid"
        detail="Researcher"
        study="Master student"
        />

        <Card
        profileurl="/img/03.jpg"
        profilealt="Nathida Sawasnopparat"
        name="Nathida Sawasnopparat"
        detail="Intern"
        study="Pharm.D. student"
        />
    
        <Card
        profileurl="/img/04.jpg"
        profilealt="Patcharapa Khamtang"
        name="Patcharapa Khamtang"
        detail="Intern"
        study="Pharm.D. student"
        />

        <Card
        profileurl="/img/07.jpg"
        profilealt="Thanawat Piyasawetkul"
        name="Thanawat Piyasawetkul"
        detail="Intern"
        study="Pharm.D. student"
        />

        <Card
        profileurl="/img/08.jpg"
        profilealt="Pannaphat Thirawatthanasak"
        name="Pannaphat Thirawatthanasak"
        detail="Intern"
        study="Pharm.D. student"
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
        flex-wrap: wrap;
        /* grid-template-columns:  1fr 1fr 1fr 1fr 1fr; */
        padding: 20px;
        justify-content: center;
        /* align-items: center; */
    }
    /* @media (max-width: 1366px) {
        .wrapper {
            grid-template-columns: 1fr 1fr 1fr;
        }
    } */
</style>