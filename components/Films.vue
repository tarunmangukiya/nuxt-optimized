<template>
  <div>
    <div class="d-flex justify-content-between align-items-center mb-3">
      <h1>Star Wars Films</h1>
      <select v-model="currentFilter">
        <option v-for="(item, index) in filters" :key="index" :value="item">{{item.text}}</option>
      </select>
    </div>

    <div class="row">
      <div v-for="(film, index) in filteredMovies" :key="index" class="col-md-4 mb-4">
        <film :film="film" />
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
import _ from "lodash";

import Film from "./Film";

export default {
  props: {
    films: {
      type: Array,
      default: () => []
    }
  },

  components: {
    Film
  },

  data() {
    return {
      filters: [
        {
          text: "Before 1980s",
          filter: item => moment(item.release_date).isBefore("01-01-1981")
        },
        {
          text: "1981 - 1990",
          filter: item =>
            moment(item.release_date).isBetween("01-01-1981", "01-01-1990")
        },
        {
          text: "1990 - 2000",
          filter: item =>
            moment(item.release_date).isBetween("01-01-1991", "01-01-2000")
        },
        {
          text: "2001 - 2010",
          filter: item =>
            moment(item.release_date).isBetween("01-01-2001", "01-01-2010")
        },
        {
          text: "After 2010",
          filter: item => moment(item.release_date).isAfter("01-01-2010")
        }
      ],
      currentFilter: null
    };
  },

  computed: {
    filteredMovies() {
      if (this.currentFilter) {
        return _.filter(this.films, this.currentFilter.filter);
      }
      return this.films;
    }
  },

  created() {
    this.currentFilter = this.filters[0];
  }
};
</script>