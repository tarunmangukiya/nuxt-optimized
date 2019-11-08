<template>
  <div>
    <master-header />
    <slider />
    <div class="container my-5">
      <h1>Star Wars Films</h1>
      <films :films="films" />
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
