<script>
import axios from "axios"
import Card from "./Card.vue"
export default {
    components:{
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
    <div class="cards-container">
        <div class="col" v-for="card in cardList">
           <Card :card="card"></Card>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.cards-container {
    width: 80%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
   
}

.col {
    width: 200px;
    width: calc(100% / 5);
}


</style>