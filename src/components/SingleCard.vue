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
        <p class="fs-5 p-3 fw-bold text-white text-center"> {{ cardName }}</p>
        <div class="text-center">
            <p class="fs-5"> {{ cardCategory }} </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.my-card-col {
    margin: 20px;
    width: calc(100% / 5 - 40px);    
}

img{
    width: 100%;
}

</style>