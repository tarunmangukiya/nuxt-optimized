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