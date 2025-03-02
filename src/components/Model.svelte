<script>
    import PublicationCard from "./profilecards/PublicationCard.svelte";

    let modelsDatas = [
        {
            link: "#stackbraf",
            title: "StackBRAF: A Large-Scale Stacking Ensemble Learning for BRAF Affinity Prediction.",
            year: 2023,
            journal: "",
            authors: "",
        },
        {
            link: "#spheroiddeath",
            title: "Classification of Spheroid Cell Death Using Propidium Iodide And Convolutional Neural Networks",
            year: 2023,
            journal: "",
            authors: "",
        },
        // {
        //     link: "#vitaminc",
        //     title: "Prediction of drug stability using stacked ensemble convolutional neural network and smartphone: a case study of ascorbic acid tablets",
        //     year: 2023,
        //     journal: "",
        //     authors: "",
        // },
        {
            link: "#stackhacat",
            title: "Stacked Ensemble Learning on HaCaT Cytotoxicity for Skin Irritation Prediction",
            year: 2023,
            journal: "",
            authors: "",
        },
        {
            link: "https://github.com/taraponglab/enraqsar-skinirritation",
            title: "Ensemble Read-Across Quantitative Structure-Activity Relationship Algorithm for Predicting Skin Irritation Toxicity",
            year: 2023,
            journal: "",
            authors: "",
        },
        {
            link: "#braf",
            title: "Exploring Quantitative Structure Activity Relationship of Pyrimidine-Sulfonamide Analogues for BRAF V600E Targeting",
            year: 2023,
            journal: "",
            authors: "",
        }
    ];
</script>

<section id="models">
    <h1>Models</h1>
    <div class="wrapper">
        {#each modelsDatas as data}
            <a href={data.link}>
                <PublicationCard
                    title={data.title}
                    year={data.year}
                    journal={data.journal}
                    author={data.authors}
                />
            </a>
        {/each}
    </div>
</section>

<style>
    section {
        background: radial-gradient(
                    at 50% 40%,
                    rgb(255, 255, 255),
                    transparent 80%
                )
                repeat scroll 0% 0%,
            radial-gradient(at 50% -47%, #bbdef9, transparent 80%) repeat scroll
                0% 0%,
            radial-gradient(at 100% 0%, #bbdef9 0px, transparent 32%) repeat
                scroll 0% 0%,
            radial-gradient(at 100% 98%, rgb(255, 241, 235), transparent) repeat
                scroll 0% 0%,
            rgba(0, 0, 0, 0)
                radial-gradient(at 0px 97%, rgb(181, 233, 247), white) repeat
                scroll 0% 0%;
        text-align: center;
        font-size: 30px;
        padding: 30px;
        padding-bottom: 100px;
    }
</style>
