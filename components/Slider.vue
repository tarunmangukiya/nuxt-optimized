<template>
  <div>
    <carousel :per-page="1" autoplay navigation-enabled>
      <slide v-for="i in 10" :key="i">
        <img :src="`https://picsum.photos/1440/350/?random=${i}`" class="img-fluid" />
      </slide>
    </carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [
        '<div class="example-slide">Slide 1</div>',
        '<div class="example-slide">Slide 2</div>',
        '<div class="example-slide">Slide 3</div>'
      ]
    };
  }
};
</script>

<style scoped>
img {
  height: 350px;
}
</style>