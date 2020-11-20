<template>
    <h2>&#8601; Official Covid-19 Related Websites &#8600;</h2>
    <nav>
        <a alt="nhs_uk" href="https://www.nhs.uk/conditions/coronavirus-covid-19/" id="nhs-box"></a>
        <a alt="gov_uk" href="https://www.gov.uk/coronavirus" id="gov-uk-box"></a>
        <a alt="scot_uk" href="https://www.gov.scot/coronavirus-covid-19/" id="gov-scot"></a>
    </nav>
</template>

<script>

</script>

<style scoped>
h2{
    margin-top: 50px;
    margin-bottom: 30px;
}
#nhs-box, #gov-uk-box, #gov-scot{
    float: left;
    margin-left: 15%;
    height: 26vh;
    width: 12.5vw;
    border-radius: 30px/30px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}

#nhs-box{
    background-color: #1c5daf;
    background-image: url('../assets/nhs-logo.png');
}

#gov-uk-box{
    background-color: #0a0b0b;
    background-image: url('../assets/gov-uk.png');
}

#gov-scot{
    background-image: url('../assets/gov-scot.png');
    background-color: white;
}

#nhs-box:hover, #gov-uk-box:hover, #gov-scot:hover{
    border: solid 5px lightskyblue;
    transition: 320ms;
}
</style>
