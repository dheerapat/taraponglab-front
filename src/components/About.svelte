<section class="wrapper" id="about">
    <div>
        <h1>About Us</h1>
        <p>We are university researchers from Faculty of Pharmaceutical Sciences, Khon Kaen, Thailand</p>
        <p>Ours area of expertises:</p>
        <ul>
            <li>Machine Learning in Drug design</li>
            <li>3D Cell Culture</li>
            <li>Cell-based assay</li>
        </ul>
    </div>
    <div>
        <img src="/img/about_lab.jpg" alt="3 people working in the laboratory" width="100%">
    </div>
</section>

<style>
    section {
        background: radial-gradient(at 50% 40%, rgb(255, 255, 255), transparent 80%) repeat scroll 0% 0%, radial-gradient(at 50% -47%, #bbdef9, transparent 80%) repeat scroll 0% 0%, radial-gradient(at 100% 0%, #bbdef9 0px, transparent 32%) repeat scroll 0% 0%, radial-gradient(at 100% 98%, rgb(255, 241, 235), transparent) repeat scroll 0% 0%, rgba(0, 0, 0, 0) radial-gradient(at 0px 97%, rgb(181, 233, 247), white) repeat scroll 0% 0%;
    }

    .wrapper {
        display: flex;
        padding: 50px;
        justify-content: center;
        align-items: center;
    }

    .wrapper div {
        font-size: 30px;
        padding: 10px;
        width: 50%;
    }
    img {
        border-radius: 20px;
    }

    @media (max-width: 1200px) {
        .wrapper {
            flex-wrap: wrap;
        }

        .wrapper div {
            width: 90%;
        }
    }

    @media (max-width: 810px) {
        .wrapper div {
            font-size: 20px;
        }
    }

    @media (max-width: 360px) {
        .wrapper div {
            font-size: 15px;
        }
    }
</style>