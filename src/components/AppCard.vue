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
      <h4>{{ }}</h4>
      <p>{{  }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>