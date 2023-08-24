<script>
export default {
    props: {
        card: {
            type: Object,
            required: true,
        }
    }
}
</script>

<template>
    <div class="card">
        <div class="img-container">
            <img :src="card.card_images[0].image_url" alt="">
        </div>
        <div class="card-info">
            <h5>{{ card.name.toUpperCase() }}</h5>

            <p>{{ card.archetype }}</p>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.card {
    height: 400px;
    width: 180px;
    background-color: #d48f38;
    text-align: center;
    
}
h5{
    color: white;
}
.img-container {
    width: 100%;
}

img {
    width: 100%;
}
.card-info{
    width: 90%;
    margin: 0 auto;
    margin-top:20px;
}
</style>