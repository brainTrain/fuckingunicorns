<template>
  <div class="container">
    <div class="fucking-grid">
      <AnimatedCell
        v-for="index in totalUnicorns"
        :key="index"
        :delay-max="delayMax"
        :delay-min="delayMin"
        :duration-max="durationMax"
        :duration-min="durationMin"
        :size-max="sizeMax"
        :size-min="sizeMin"
        :horizontal-max="horizontalMax"
        :horizontal-min="horizontalMin"
        :vertical-max="verticalMax"
        :vertical-min="verticalMin"
      >
        <FuckingUnicorn />
      </AnimatedCell>
    </div>
    <RainDown />
  </div>
</template>

<script>
import AnimatedCell from '~/components/animated-cell.vue';
import FuckingUnicorn from '~/components/fucking-unicorn.vue';
import RainDown from '~/components/rain-down.vue';

export default {
  components: {
    AnimatedCell,
    FuckingUnicorn,
    RainDown,
  },
  data: function () {
    return {
      totalUnicorns: 50,
      delayMax: -10,
      delayMin: 1,
      durationMax: 2,
      durationMin: 5,
      sizeMax: 5,
      sizeMin: 0.1,
      horizontalMax: 100,
      horizontalMin: -100,
      verticalMax: 100,
      verticalMin: -100,
    }
  },
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-image: url('/okcomputer-bg.jpg');
  background-size: contain;
}

.fucking-grid {
  position: absolute;
  display: flex;
  flex-wrap: wrap;
  height: 100%;
  width: 100%;
  overflow: hidden;
}
</style>
