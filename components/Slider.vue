<template>
  <div>
    <carousel :per-page="1" autoplay navigation-enabled>
      <slide v-for="i in 10" :key="i">
        <img :src="`https://picsum.photos/1440/500/?random=${i}`" class="img-fluid" />
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

<style>
.example-slide {
  align-items: center;
  background-color: #666;
  color: #999;
  display: flex;
  font-size: 1.5rem;
  justify-content: center;
  min-height: 10rem;
}
</style>