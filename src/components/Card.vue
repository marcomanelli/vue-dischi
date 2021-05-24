<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <h3>{{ card.title }}</h3>
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