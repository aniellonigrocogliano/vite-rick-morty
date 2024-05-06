<script>
import axios from "axios";
import CardsList from "./components/CardsList.vue";

export default {
  components: {
    CardsList,
  },
  data() {
    return {
      cardsArray: [],
      flag: false,
    };
  },
  created() {
    axios
      .get("https://rickandmortyapi.com/api/character", {
  
      })
      .then((resp) => {
        this.cardsArray = resp.data.results;
        console.log(resp);
        this.flag=true;
      });
  },
};
</script>

<template>
  <div class="container">
    <h1>Rick and Morty App</h1>
  </div>
  <div v-if="flag" >
     <CardsList :cardsArray="cardsArray" />
</div>
  <div v-else class="container">
    <h1>Caricamento in corso</h1>
  </div>
</template>

<style lang="scss">
h1{
  text-align: center;
}
</style>