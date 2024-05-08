<script>
import { store } from "./store";
import axios from "axios";
import CardsList from "./components/CardsList.vue";
import AppSearchTab from "./components/AppSearchTab.vue";

export default {
  components: {
    CardsList,
    AppSearchTab,
  },
  data() {
    return {
      flag: true,
      store,
      
    };
  },
  created() {
    this.getCards();
  },
  methods: {
    getCards() {
      this.flag=false
      const paramsObj = {
        num: 20,
        offset: 0,
      };
      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }
      axios
        .get("https://rickandmortyapi.com/api/character", {
          params: paramsObj,
        })
        .then((resp) => {
        this.store.cardsArray = resp.data.results;
        this.flag=true;
        });
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>Rick and Morty App</h1>
    <AppSearchTab @filter="getCards" />
  </div>
  <div v-if="flag" >
     <CardsList :store.cardsList="store.cardsList" />
</div>
  <div v-else class="container">
    <h1>Caricamento in corso</h1>
  </div>
</template>

<style lang="scss">
h1{
  text-align: center;
}

body {
    background-image: 
            repeating-linear-gradient(90deg, rgba(238, 238, 238,0.5) 0px, rgba(238, 238, 238,0.5) 20px,transparent 20px, transparent 40px),repeating-linear-gradient(0deg, rgba(238, 238, 238,0.5) 0px, rgba(238, 238, 238,0.5) 20px,transparent 20px, transparent 40px),
            linear-gradient(90deg, rgb(255, 255, 255),rgb(255,255,255));
            }
</style>