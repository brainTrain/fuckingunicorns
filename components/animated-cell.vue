<template>
  <div>
    <div
      class="container"
      v-bind:style="styleObject"
    >
      <slot></slot>
    </div>
  </div>
</template>

<script>
const randomNumber = (min, max) => (Math.random() * (max - min) + min);

export default {
  props: {
    delayMax: Number,
    delayMin: Number,
    durationMax: Number,
    durationMin: Number,
    sizeMax: Number,
    sizeMin: Number,
    horizontalMax: Number,
    horizontalMin: Number,
    verticalMax: Number,
    verticalMin: Number,
  },
  data: function () {
    const {
      delayMax,
      delayMin,
      durationMax,
      durationMin,
      sizeMax,
      sizeMin,
      horizontalMax,
      horizontalMin,
      verticalMax,
      verticalMin,
    } = this;

    return {
      styleObject: {
        top: `${randomNumber(verticalMin, verticalMax)}%`,
        left: `${randomNumber(horizontalMin, horizontalMax)}%`,
        height: `${randomNumber(sizeMin, sizeMax)}rem`,
        width: `${randomNumber(sizeMin, sizeMax)}rem`,
        animationDuration: `${randomNumber(durationMin, durationMax)}s`,
        animationDelay: `${randomNumber(delayMin, delayMax)}s`
      }
    };
  }
}
</script>

<style scoped>
.container {
  position: absolute;
  animation: fly linear infinite;

  /* keyframe style initialization */
  opacity: 0;
  transform: translate(0, 0) scale(0.2) rotate(0deg);
}

@keyframes fly {
  25% {
    opacity: 1;
  }

  80% {
    opacity: 1;
  }

  100% {
    transform: translate(110vh, 110vh) scale(1) rotate(47deg);
    opacity: 0;
  }
}
</style>
