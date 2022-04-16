<template>
  <a :href="`${link.url}`" target="_blank" class="card">
    <div v-if="link.type.includes('facebook')" class="facebook card-item"></div>
    <div v-if="link.type.includes('twitter')" class="twitter card-item"></div>
    <div
      v-if="link.type.includes('instagram')"
      class="instagram card-item"
    ></div>
    <div v-if="link.type.includes('youtube')" class="youtube card-item"></div>
    <div
      v-if="link.type.includes('soundcloud')"
      class="soundcloud card-item"
    ></div>
    <div v-if="link.type.includes('itunes')" class="itunes card-item"></div>
    <div
      v-else-if="link.type.includes('spotify')"
      class="spotify card-item"
    ></div>
    <div
      v-else-if="link.type.includes('wikipedia')"
      class="wikipedia card-item"
    ></div>
    <div
      v-else-if="link.type.includes('website')"
      class="website card-item"
    ></div>
    <p class="snippet card-item">{{ link.type }}</p>
  </a>
</template>

<script>
export default {
  props: ["link"],
};
</script>

<style scoped>
.card {
  /* border: none; */
  display: flex;
  flex-direction: column;
  overflow: hidden;
  cursor: pointer;
  box-shadow: 5px 10px #888888;
  flex-basis: 30%;
  margin: 0.5rem;
}
.card:hover {
  box-shadow: rgba(50, 50, 93, 0.25) 0px 30px 60px -12px inset,
    rgba(0, 0, 0, 0.3) 0px 18px 36px -18px inset;
}

.snippet {
  flex: 1;
  text-align: center;
}
.facebook {
  flex: 4;
  background-image: url("~/assets/images/social-media/facebook-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.twitter {
  flex: 4;
  background-image: url("~/assets/images/social-media/twitter-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.instagram {
  flex: 4;
  background-image: url("~/assets/images/social-media/instagram-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.youtube {
  flex: 4;
  background-image: url("~/assets/images/social-media/youtube-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.itunes {
  flex: 4;
  background-image: url("~/assets/images/social-media/itunes-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.spotify {
  flex: 4;
  background-image: url("~/assets/images/social-media/spotify-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.soundcloud {
  flex: 4;
  background-image: url("~/assets/images/social-media/soundcloud-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.wikipedia {
  flex: 4;
  background-image: url("~/assets/images/social-media/wiki-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
.website {
  flex: 4;
  background-image: url("~/assets/images/social-media/website-logo.png");
  background-size: cover;
  width: fit-content;
  justify-content: center;
  padding: 5%;
}
</style>