<script>
    import imgUrl from "../svg/RunningDollar_app.png";
</script>

<div class="title">
    <h1>WHAT'S A DOLLAR COST?</h1>
    <h2>
        EXPLORING THE PRICE OF INCARCERATION WITHIN THE UNITED STATES PRISON
        SYSTEM
    </h2>
    <h4>
        by <a href="https://www.carolinecullinan.com/" target="_blank"
            >CAROLINE CULLINAN</a
        >
    </h4>
    <br />
    <img
        src={imgUrl}
        alt="Visualization related to what a dollar costs for folks incarcerated in the US"
        width="75%"
    />
</div>

<div class="introParagraph">
    <p>
        While the December 18, 1865 proclamation of the Thirteenth Amendment
        protected most United States (US) residents from enslavement, it failed
        to defend people convicted of crimes. Today, more than 150 years later,
        incarcerated people across US prisons are still being subjected to
        slavery. According to a June 2022 <a
            href="https://www.aclu.org/report/captive-labor-exploitation-incarcerated-workers?redirect=captivelabor"
            target="blank">report</a
        > made by the American Civil Liberties Union (ACLU), roughly 800,000 incarcerated
        people are subjected to working conditions characterized by imbalanced power
        dynamics and inadequately compensated labor.
    </p>
    <p class="centerParagraph">So, what’s a dollar cost to these folks?</p>
    <p>
        While this value varies across types of detention centers throughout
        different US states, one thing is consistent: the dollar of an
        incarcerated person is far harder earned than the dollar of someone not
        subjected to the US prison system.
    </p>
    <p class="centerParagraph">How so?</p>
    <p class="centerParagraph">Scroll below to find out.</p>
</div>
<span class="material-symbols-outlined"> arrow_drop_down </span>

<style>
    a {
        font-weight: 500;
        color:  #213547;
        text-decoration: underline;
    }
    a:hover {
        color: rgb(88, 8, 88);
    }
    .title {
        height: 60vh;
        display: flex;
        place-items: center;
        flex-direction: column;
        justify-content: center;
        text-align: center;
        margin-bottom: 60px;
        max-width: 650px;
        margin: auto;
        color: #213547;
    }

    h2 {
        font-weight: 400;
    }

    h4 {
        font-weight: 400;
        font-size: smaller;
    }
    .introParagraph {
        text-align: justify;
        max-width: 500px;
        margin: auto;
    }

    .centerParagraph {
        text-align: center;
    }

    .material-symbols-outlined {
        font-variation-settings: "FILL" 0, "wght" 700, "GRAD" 0, "opsz" 48;
        font-size: 48px;
    }

    h1 {
        font-size: 56px;
    }
</style>
