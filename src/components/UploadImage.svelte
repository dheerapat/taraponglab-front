<script>
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
</script>

<section>
    <h1>
        PCAS-CNN : Spheroid cell death prediction using propidium iodide and
        calcein AM straining and convolutional neural network
    </h1>
    <h4>
        You can upload spheroid images that have been stained with propidium
        iodide and calcein AM into this system. Our model will analyze the
        images and provide predictions for the live and dead cells within your
        spheroid.
    </h4>
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
    h4,
    form {
        text-align: center;
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
