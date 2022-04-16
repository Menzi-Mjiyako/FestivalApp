<template>
  <div class="container">
    <Carousel :cards="topCards"/>
    <div style="position: relative;top: 5rem;">
      <LargeCardDisplay
        v-for="cardInfo in LargeCardInfo"
        :key="cardInfo.id"
        :cardSection="cardInfo"
      />
      <SmallCardDisplay v-for="smallCard in smallCards"
      :key="smallCard.id"
      :cards="smallCard"/>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import LargeCardDisplay from "~/components/LargeCardDisplay.vue";
import { largeCardSections, smallCardSections } from "~/assets/data";
import { mapState } from "vuex"

export default Vue.extend({
  components: { LargeCardDisplay },
  name: "IndexPage",

  data() {
    return {
      LargeCardInfo: largeCardSections,
      smallCards: smallCardSections
    };
  },

  computed: {
    ...mapState([
      'topCards'
    ])
  }
});
</script>
