<template>
  <div class="row">
    <div v-for="(film, index) in films" :key="index" class="col-md-4">
      <div class="card">
        <div class="card-body">
          <h5 class="card-title">{{ film.title }}</h5>
          <p class="card-text">{{ film.opening_crawl }}</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    films: {
      type: Array,
      default: () => []
    }
  }
}
</script>