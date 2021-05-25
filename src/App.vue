<template>
  <div id="app">
    <header>
      <img src="@/assets/img/logo.jpg" alt="">
    </header>

    <main>
      <div class="mm-wrapper text-center">
        <div>
          <Card class="card-box"
          v-for="card in cards" 
          :key="card" 
          :card="card" />
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import axios from "axios";
import Card from "@/components/Card";

export default {
  name: "App",
  components: {
    Card,
  },
  data() {
    return {
      axios,
      cards: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.cards = res.data.response;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

@import "@/assets/style/general.scss";

header {
  height: 50px;
  background-color: #2E3A46;
  img {
    width: 50px;
    height: 50px;
  }
}

main {
  background-color: #1E2D3B;
  height: calc(100vh - 50px);
  .mm-wrapper {
    width: 70%;
    margin: auto;
    padding: 50px;
    div {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      max-width: 1100px;
    }
  }
  .card-box {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 180px;
    padding: 10px;
    background-color: #2E3A46;
    margin: 10px;
  }
  img {
    width: 150px;
    height: 150px;
  }
  h3 {
    color: white;
  }
  h4, h6 {
    color: gray;
  }
}

</style>
