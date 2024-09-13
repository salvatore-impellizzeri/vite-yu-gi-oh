<script>
export default {
    props:{
        cardImg: String,
        cardName: String,
        cardCategory: String
    }
}
</script>

<template>
    <div class="my-card-col mt-4">
        <img :src="cardImg" :alt="cardName">
        <div class="bg-text-orange">
            <p class="fs-5 pb-2 fw-bold text-white text-center w-100"> {{ cardName }}</p>
            <div class="text-center">
                <p class="fs-5"> {{ cardCategory }} </p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.bg-text-orange{
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    justify-content: center;
    min-height: 200px;
    padding: 20px 0;
    background-color: orange;
    text-transform: uppercase;
}

.my-card-col {
    margin: 20px;
    width: calc(100% / 5 - 40px);    
}

img{
    width: 100%;
}

</style>