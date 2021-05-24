<template>
  <div id="app">
    <div class="container text-center mt-5">
      <div class="row">

        <Card
          v-for="card in cards"
          :key="card.title"
          :card="card"
        />

      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card';

export default {
  name: 'App',
  components: {
    Card
  },
  data(){
    return{
      axios,
      cards:[],
    }
  },
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then(res => {
        /* ERRORE?(DEVO PRENDERE I RESPONSE, NON IL SUCCESS) */
        this.cards.response = res.data
      })
      .catch(err => {
        console.log(err);
      })
  },
  
}
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';

  @import '@/style/general.scss';
</style>
