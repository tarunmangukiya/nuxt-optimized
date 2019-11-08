<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ film.title }}</h5>
      <p>{{ releaseDate }}</p>
      <p class="card-text">{{ film.opening_crawl }}</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  props: {
    film: {
      type: Object,
      default: () => {}
    }
  },

  computed: {
    releaseDate() {
      return moment(this.film.release_date).format("MMM Do, YYYY");
    }
  }
};
</script>