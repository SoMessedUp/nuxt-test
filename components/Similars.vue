<template>
    <div class="similars">
        <div class="wrapper">
            <div class="similars__text">
                Похожие товары
            </div>
            <div class="similars__cards-row">
                <Card
                    imageSrc="img/card__img1.jpg"
                    title="ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ"
                    priceActual="14 900"
                    priceBefore="8 000"
                />
                <Card
                    imageSrc="img/card__img2.jpg"
                    title="ЖАКЕТ ДВУБОРТНЫЙ, СЕРО-ГОЛУБОЙ"
                    priceActual="8 900"
                />
                <Card
                    imageSrc="img/card__img3.jpg"
                    title="ПЛАТЬЕ МАКСИ С ЯРУСАМИ, БЕЛЫЙ"
                    priceActual="10 500"
                />
                <Card
                    imageSrc="img/card__img4.jpg"
                    title="КОМБИНЕЗОН СО СТОЙКОЙ, ЧёРНЫЙ<"
                    priceActual="9 500"
                /> 
            </div>
        </div>
    </div>
</template>

<style scoped>

.similars {
    margin-top: 45px;
    margin-bottom: 50px;
}
.similars__text {
    font-weight: 400;
    font-size: 12px;
    line-height: 133%;
    text-transform: uppercase;
    color: #333;
    margin-bottom: 30px;
}
.similars__cards-row {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    justify-content: space-between;
}

@media (max-width: 760px){
    .similars__cards-row .card:nth-last-child(1){
        display: none;
    }
    .similars__cards-row {
        gap: 8px;
    }
}
@media (max-width: 555px){
    .similars__cards-row .card:nth-last-child(2){
        display: none;
    }
    .similars__cards-row {
        gap: 8px;
    }
}

@media (max-width: 1350px) {
    .similars__cards-row {
        justify-content: space-between;
    }
}


</style>