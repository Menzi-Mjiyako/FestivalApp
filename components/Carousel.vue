<template>
  <div class="container">
    <b-carousel
      class="v-carousel"
      id="carousel-fade"
      fade
      indicators
      img-width="320"
      img-height="90"
    >
      <b-carousel-slide
        v-for="card in cards"
        :key="card.id"
        :caption="`${card.title}`"
        :img-src="require(`~/assets/images/${card.image}`)"
      ></b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
export default {
  props: ["cards"],
};
</script>

<style scoped>
.v-carousel {
  margin-top: 2.5rem;
  text-shadow: 0px 0px 2px #000;
};
.container {
 width: 10rem;
 height: 10rem;
}
</style>