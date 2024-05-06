<script>
import axios from "axios";

export default {
  components: {
   
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
        console.log(resp);
        this.cardsArray = resp.results;
        console.log(this.cardsArray);
      });
  },
};
</script>

<template>
</template>

<style lang="scss">

</style>