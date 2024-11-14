<template>
    <div class="card">
        <img :src="imageSrc" :alt="title" class="card__img">
        <div class="card__title">{{ title }}</div>
        <div class="card__price">
            <div class="card__price-actual">
                {{ priceActual }} RUB
            </div>
            <div class="card__price-before  " :class="{price_true: priceBefore}">
                {{ priceBefore }} RUB
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        imageSrc: {
            type: String,
            required: true
        },
        title: {
            type: String,
            required: true
        },
        priceActual: {
            type: String,
            required: true
        },
        priceBefore: {
            type: String,
            required: false
        },
    }
}
</script>

<style scoped>
.card {
    width: calc(25% - 16px);
    box-sizing: border-box;
    min-width: 130px;
}

.card__img {
    width: 100%;
    height: auto;
    object-fit: cover;
}

.card__title {
    font-weight: 400;
    font-size: 10px;
    line-height: 140%;
    text-transform: lowercase;
    color: #333;
    margin: 14px 0 0 14px;
}

.card__price {
    margin: 11px 0 0 14px;
    display: flex;
}

.card__price-actual {
    font-weight: 400;
    font-size: 10px;
    line-height: 140%;
    text-transform: uppercase;
    color: #333;
    margin-right: 10px;
}

.card__price-before {
    font-weight: 400;
    font-size: 10px;
    line-height: 140%;
    text-transform: uppercase;
    text-decoration: line-through;
    color: #828282;
    display: none;
}

.price_true {
    display: block;
}

@media (max-width: 760px){
    .card {
        width: calc(33% - 8px);
        box-sizing: border-box;
    }
}

@media (max-width: 555px){
    .card {
        width: calc(50% - 8px);
        box-sizing: border-box;
    }
    .card__title {
        margin: 10px 0 0 5px;
        max-width: calc(100% - 20px);
    }
    .card__price {
        margin: 5px 0 0 5px;
        max-width: calc(100% - 20px);
    }
}

</style>