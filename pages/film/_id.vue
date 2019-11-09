<template>
  <div>
    <master-header />

    <div class="container my-4">
      <h1>{{ film.title }}</h1>
      <p>
        <strong>Episode:</strong>
        {{ film.episode_id }}
      </p>
      <p>
        <strong>Director:</strong>
        {{ film.director }}
      </p>
      <p>
        <strong>Producer:</strong>
        {{ film.producer }}
      </p>
      <p>{{ film.opening_crawl }}</p>
    </div>
  </div>
</template>

<script>
import MasterHeader from "@/components/Header.vue";

export default {
  components: {
    MasterHeader
  },

  async asyncData({ $axios, params }) {
    const film = await $axios.$get(`https://swapi.co/api/films/${params.id}`);

    return {
      film
    };
  }
};
</script>
