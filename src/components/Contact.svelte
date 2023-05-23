<section class="wrapper" id="contact">
    <div>
        <h3>Contact Us</h3>
        <p>Dr. Tarapong Srisongkram</p>
        <p>Division of Pharmaceutical Chemistry, Faculty of Pharmaceutical Sciences, Khon Kaen, Thailand</p>
        <a  href = "tarasri@kku.ac.th"><p>tarasri@kku.ac.th</p>
    </div>
    <div>
        <img src="/ps-building.png" alt="Faculty of Pharmaceutical Sciences, Khon Kaen University, Thailand" width="100%">
    </div>
</section>

<style>
    section {
        background-color: white;
    }

    .wrapper {
        display: flex;
        padding: 50px;
        justify-content: center;
        align-items: center;
    }

    .wrapper div {
        font-size: 20px;
        padding: 50px;
        width: 50%;
    }

    img {
        border-radius: 20px;
    }

    @media (max-width: 1366px) {
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