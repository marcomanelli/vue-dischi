<template>
  <div>
    <img :src="card.poster" alt="">
    <h3>{{ card.title }}</h3>
    <h4>{{ card.author }}</h4>
    <h6>{{ card.year }}</h6>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props:{
    card: Object
  }

}
</script>

<style>

</style>