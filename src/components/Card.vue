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
            <h3>{{ card.name }}</h3>

            <p>{{ card.archetype }}</p>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.card {
    height: 400px;
    width: 180px;
    background-color: #d48f38;
}

.img-container {
    width: 100%;
}

img {
    width: 100%;
}
</style>