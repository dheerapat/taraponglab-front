<script>
    import { onMount } from "svelte";

    // export let auth
    let selectedImage;
    let uploadStatus = "";
    let result;
    let imageURL;

    async function predict_spheroid() {
        const image = selectedImage[0];
        const formData = new FormData();
        formData.append("file", image);

        try {
            const res = await fetch("/spheroiddeath/", {
                method: "POST",
                body: formData,
            });

            const resData = await res.json();

            if (resData.status == "complete") {
                result = resData.result;
                imageURL = URL.createObjectURL(image);
                console.log(result);
            } else {
                alert("API Call Failed: Please report to admin");
            }
        } catch (error) {
            uploadStatus = "An error occur while attempting upload image.";
        }
    }

    // onMount(() => {
    //     if (auth == false) {
    //         window.location.hash = 'login'
    //     }
    // });
</script>

<section>
    <h1>
        Prediction of Spheroid Cell Death Using Fluorescence Staining and Convolutional Neural Networks
    </h1>
    <h3>
        You can upload spheroid images that have been stained with propidium
        iodide and calcein AM into this system.
    </h3>
    <h3>
        Our model will analyze the images and provide predictions for the live
        and dead cells within your spheroid.
    </h3>
    <form
        on:submit|preventDefault={predict_spheroid}
        enctype="multipart/form-data"
        method="post"
    >
        <input type="file" accept="image/*" bind:files={selectedImage} />
        <button type="submit">Upload Image</button>
    </form>
    {#if result}
        <br />
        <h1>Result</h1>
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src={imageURL} alt="Uploaded Image" />
        <h4>Class: {result.class}</h4>
        <h4>Probability: {result.prob.toPrecision(3)}%</h4>
        <br>
        <h3>If you think this service is helpful please cite: </h3>
        <a href="https://pubs.acs.org/doi/10.1021/acs.chemrestox.3c00257?fbclid=IwAR2wcnI-fbeEg9MhbYxgO1BHSlat_y-NLKxTe3CDsJyB9DzO5ET__OGJMwo">
            <p>Srisongkram T., Syahid, N. F., Piyasawetkul T., Thirawatthanasak P., Khamtang P., Sawasnopparat N., Tookkane D., Weerapreeyakul N., and Puthongking P. <b>Prediction of Spheroid Cell Death Using Fluorescence Staining and Convolutional Neural Networks,</b> Chemical Research in Toxicology, 2023</p>
        </a>
    {/if}
</section>

<style>
    section {
        background-color: white;
        font-size: 30px;
        padding: 50px;
        margin-top: 100px;
        margin-bottom: 100px;
    }
    h1,
    h3,
    h4,
    form {
        text-align: center;
    }

    h3 {
        margin: 0;
    }

    img {
        display: block;
        margin-left: auto;
        margin-right: auto;
        width: 50%;
    }

    form {
        margin-top: 100px;
    }

    @media (max-width: 1200px) {
        section {
            font-size: medium;
            margin-top: 25px;
        }
    }
</style>
