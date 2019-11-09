<template>
  <div>
    <master-header />
    <slider />
    <div class="container my-5">
      <films :films="films" />
    </div>

    <div class="container">
      <div class="row no-gutters">
        <div v-for="i in 40" :key="i" class="image col-4">
          <img :src="`https://picsum.photos/360/250/?random=${i}`" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MasterHeader from "@/components/Header.vue";
import Slider from "@/components/Slider.vue";
import Films from "@/components/Films.vue";

export default {
  components: {
    MasterHeader,
    Slider,
    Films
  },

  async asyncData({ $axios }) {
    const films = await $axios.$get("https://swapi.co/api/films/");

    return {
      films: films.results
    };
  }
};
</script>

<style lang="scss">
.image {
  > img {
    height: 250px;
    width: 100%;
  }
}
</style>