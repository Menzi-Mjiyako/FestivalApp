<template>
  <div class="container">
    <h3 class="name-tag">{{selectedArtist.name}}</h3>
    <div class="container" style="display: flex">   
         <img :src="`${selectedArtist.image_url}`" alt="" style="flex: 1">
         <div style="flex:2; ">
             <SocialMedia :links="selectedArtist.links"/>
         </div>
    </div>
  </div>
</template>

<script>
import { mapState } from "vuex";

export default {
  computed: {
    ...mapState(["selectedArtist"]),
  },
};
</script>

<style scoped>
img {
    width: 25rem
}
</style>