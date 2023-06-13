<script>
    let selectedImage;
    let uploadStatus = "";

    async function predict_spheroid() {
        const image = selectedImage[0]
        console.log(image)
        const formData = new FormData();
        formData.append("file", image);
        console.log(formData);

        try {
            const res = await fetch("/spheroiddeath/", {
                method: "POST",
                body: formData
            });
            console.log(res);
        } catch (error) {
            uploadStatus = "An error occur while attempting upload image.";
        }
    }
</script>

<section>
    <form on:submit|preventDefault={predict_spheroid} enctype="multipart/form-data" method="post">
        <input type="file" accept="image/*" bind:files={selectedImage} />
        <button type="submit">Upload Image</button>
    </form>
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
