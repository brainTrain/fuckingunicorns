<template>
  <div class="container">
    <div>
      <FuckingUnicorn />   
      <h2>🦄🦄🦄🦄🦄</h2>
      <RainDown />
    </div>
  </div>
</template>

<script>
import FuckingUnicorn from '~/components/fucking-unicorn.vue'
import RainDown from '~/components/rain-down.vue'

export default {
  components: {
    FuckingUnicorn,
    RainDown,
  }
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-image: url('/okcomputer-bg.jpg');
  background-size: contain;
}
</style>
