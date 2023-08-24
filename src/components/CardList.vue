<script>
import axios from "axios"
import Card from "./Card.vue"
export default {
    components: {
        Card,
    },
    data() {
        return {
            cardList: []
        }
    },
    methods: {
        fetchCharacters() {
            const url = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
            axios.get(url).then((response) => {
                this.cardList = response.data.data;
            })
        }
    },
    mounted() {
        this.fetchCharacters()
    }

}
</script>

<template>
    <div class="wrapper">
        <div class="cards-container">

            <div class="col" v-for="card in cardList" key="card.id">
                <Card :card="card"></Card>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
.wrapper {
    width: 80%;
    padding: 80px 0;
    margin: 0 auto;
    display: flex;
    justify-content: center;
   
}

.cards-container {
    display: flex;
    flex-wrap: wrap;
    padding-top: 40px;
    padding-left: 40px;
    background-color: white;
}


.col {
    width: calc(100% / 5);
    padding: 20px 0;
}
</style>