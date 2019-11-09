<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ film.title }}</h5>
      <p>{{ releaseDate }}</p>
      <p class="card-text">{{ film.opening_crawl }}</p>
      <nuxt-link :to="{ name: 'film-id', params: { id } }" class="btn btn-primary">Go somewhere</nuxt-link>
    </div>
  </div>
</template>

<script>
import moment from "moment";
import format from 'date-fns/format';

export default {
  props: {
    film: {
      type: Object,
      default: () => {}
    }
  },

  computed: {
    id() {
      return this.film.url
        .replace("https://swapi.co/api/films/", "")
        .replace("/", "");
    },




    releaseDate() {
      // Remove moment
      // return moment(this.film.release_date)
      //   .format("MMM Do, YYYY");

      // Replace it with date-fns
      return format(
        new Date(this.film.release_date),
        'MMM dd, yyyy'
      );
    }



  }
};
</script>