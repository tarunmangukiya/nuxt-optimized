<template>
  <div>
    <nuxt />

    <modal-login />
  </div>
</template>

<script>
import ModalLogin from '@/modals/Login.vue'

export default {
  components: {
    ModalLogin
  }  
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Roboto:100,300,400,500,700,900');

body {
  font-family: "Roboto",
}
</style>