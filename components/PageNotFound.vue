<template>
  <div class="container">
    <h2 class="header">Page Not Found</h2>
    <img
      :src="require(`~/assets/images/plug-g63c6f1658_640.jpg`)"
      alt="not found"
      class="image"
    />
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
div {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50rem;
}
h2 {
  font-size: 7.5rem;
}
img {
  width: 15rem;
  margin: 0 auto;
}
</style>