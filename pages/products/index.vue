<template>
    <div class="container">
      <LargeCardDisplay
        v-for="largeCard in largeCardSections.slice(0,1)"
        :key="largeCard.id"
        :cardSection="largeCard"
      />

      <SmallCardDisplay
        v-for="smallCard in smallCardSections"
        :key="smallCard.id"
        :cards="smallCard"
      />
    </div>
</template>

<script>
import { largeCardSections, smallCardSections } from "~/assets/data";
export default {
  data() {
      console.log("Hello")
      console.log(largeCardSections)
      console.log(smallCardSections)
    return {
      largeCardSections,
      smallCardSections,
    };
  },
};
</script>

<style scoped>
</style>