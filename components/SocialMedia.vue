<template>
  <div class="container">
    <div class="card-container">
      <SocialMediaItem v-for="link in links" :key="link.type" :link="link" />
    </div>
    <button @click="toEvents()">Events</button>
  </div>
</template>

<script>
export default {
  props: ["links"],
  methods: {
      toEvents(){
          this.$router
      }
  }
};
</script>

<style scoped>
.container {
  padding: 1rem;
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  align-content: flex-start;
  justify-content:space-around;
}
button{
    background-color: #343a40;
    margin-top: 1rem;
    border: 0.15em solid #28a745;
    color: #28a745;
    width: 20rem;
    height: 5rem;
    position: relative;
    top: 4rem;
    left: 12rem;

}
button:hover{
    background-color:#28a745;
    color: #fff;
}
</style>