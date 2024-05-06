<script>
export default {
  props: {
    cardObj: Object,
  },
  computed: {
    image() {
      return this.cardObj.image;
    },

  },
};
</script>

<template>
  <div class="card">
    <img :src="image" alt="" />
    <div class="card-body">
      <h4>{{ cardObj.name}}</h4>
      <p>{{ cardObj.status }}</p>
      <p>{{ cardObj.species }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
img{
    border-radius: 50%;
}
.card{
    border: none;
}
</style>