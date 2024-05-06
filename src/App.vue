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
    };
  },
  created() {
    axios
      .get("https://rickandmortyapi.com/api/character", {
  
      })
      .then((resp) => {
        this.cardsArray = resp.data.results;
        console.log(resp);
      });
  },
};
</script>

<template>
  <CardsList :cardsArray="cardsArray" />
</template>

<style lang="scss">

</style>