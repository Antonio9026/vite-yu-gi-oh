<script >
import TheHeader from './components/TheHeader.vue';
import CardList from './components/CardList.vue';
import Card from './components/Card.vue';

export default{
  components:{
    TheHeader,
    CardList,
    Card,
  }
}
</script>

<template>
<TheHeader></TheHeader>
<main>
  <CardList>
    <Card></Card>
  </CardList>
  </main>

</template>

<style lang="scss" >

</style>
