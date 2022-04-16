<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark padding">
      <NuxtLink class="navbar-brand" to="/">
        <img
          :src="require(`~/assets/images/musical-note-3d-gc3d48681a_640.jpg`)"
          alt=""
          class="icon"
        />
        <span>Music Festivals</span>
      </NuxtLink>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <form class="form-inline my-2 my-lg-0 nav-search">
        <input
          class="form-control mr-sm-2 long-input"
          type="search"
          v-model="searchTerm"
          placeholder="Search"
          aria-label="Search"
          @keypress.enter="searchArtist"
        />
        <button
          class="btn btn-outline-success my-2 my-sm-0"
          type="button"
          v-b-modal="'prevModal'"
          artist="'artist'"
          @click="() => searchArtist()"
        >
          Search
        </button>
      </form>

    </nav>

    <b-modal ref="prevModal" id="pre-modal" hide-footer title="Artist Preview" :artist="artist">
      <div class="calendar-container" v-if="artist && searching">
        <div class="text-container" >
          <span><label>Name</label>:</span> <label>{{ artist.name }}</label>
          <div class="avatar">
            <img :src="`${artist.image_url}`" alt="" />
          </div>
        </div>
        <b-button
          class="artist-btn"
          block
          @click="
            () => {
              goToArtist()
            }
          "
          >Go To Artist</b-button
        >
      </div>
      <div v-else>
          ARTIST NOT FOUND
                 <b-button
          class="mt-3"
          variant="outline-danger"
          block
          @click="
            () => {
              goHome()
            }
          "
          >Go Home</b-button
        > 
          </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  methods: {
    searchArtist() {
      try {
        if (this.searchTerm) {
          this.searching = true;
          this.artist = this.$store.state.artists.find(
            (artist) => artist.name.toLowerCase() == this.searchTerm.toLowerCase()
          );
          this.showModal();
        }
      } catch (e) {
        console.log(e);
      }
    },

    showModal() {
      this.$refs["prevModal"].show();
    },
    hideModal() {
      this.$refs["prevModal"].hide();
    },
    // toggleModal() {
    //   this.$refs["prevModal"].toggle("#toggle-btn");
    // },
    goHome(){
        this.$router.push("/")
        this.hideModal()
    },

    goToArtist(){
        this.$store.commit("setSelectedArtist",this.artist)
        this.$router.push({ path: '/artist', query: { name: `${this.artist.name}` } })
        this.hideModal()
    }
  },

  //   fetch() {
  //     debugger;
  //     this.reviewers = fetch(
  //       `https://rest.bandsintown.com/artists/${this.searchTerm}?app_id=8`
  //     ).then((response) => {
  //       console.log(response);
  //       if (response.ok) {
  //         console.log(response.json()); //first consume it in console.log
  //         return response.json(); //then consume it again, the error happens
  //       }
  //     });
  //   },

  data() {
    return {
      searchTerm: "",
      searching: false,
      artist: null,
    };
  },
};
</script>

<style scoped>
img {
    width: 75%;
}
nav {
  display: flex;
  flex-direction: row;
  width: 100%;
}
.artist-btn{
    background-color: #343a40;
    margin-top: 1rem;
    border: 0.15em solid #28a745;
    color: #28a745;

}
.artist-btn:hover{
    background-color:#28a745;
    color: #fff;
}
.nav-search {
  position: relative;
  left: 12rem;
}
.long-input {
  width: 35rem;
}
.icon {
  height: 2.5rem;
  width: 4rem;
}
.padding {
  padding: 1.5rem;
  background-color: black;
}
.nav-left {
  margin-left: auto;
}
</style>