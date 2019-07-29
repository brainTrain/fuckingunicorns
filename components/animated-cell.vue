<template>
  <div
    class="cell"
    v-bind:style="styleObject"
  >
    <slot></slot>
  </div>
</template>

<script>
const randomNumber = (min, max) => (Math.random() * (max - min) + min);
const calculateDirection = (value) => (`${parseInt(value) * 100}vh`);

export default {
  props: {
    delayMax: Number,
    delayMin: Number,
    durationMax: Number,
    durationMin: Number,
    horizontalMax: Number,
    horizontalMin: Number,
    rainDirection: [Number, String],
    sizeMax: Number,
    sizeMin: Number,
    verticalMax: Number,
    verticalMin: Number,
  },
  data: function () {
    const {
      delayMax,
      delayMin,
      durationMax,
      durationMin,
      horizontalMax,
      horizontalMin,
      rainDirection,
      sizeMax,
      sizeMin,
      verticalMax,
      verticalMin,
    } = this;

    return {
      styleObject: {
        '--direction': calculateDirection(rainDirection),
        top: `${randomNumber(verticalMin, verticalMax)}%`,
        left: `${randomNumber(horizontalMin, horizontalMax)}%`,
        height: `${randomNumber(sizeMin, sizeMax)}rem`,
        width: `${randomNumber(sizeMin, sizeMax)}rem`,
        animationDuration: `${randomNumber(durationMin, durationMax)}s`,
        animationDelay: `${randomNumber(delayMin, delayMax)}s`
      }
    };
  },
  watch: {
    rainDirection: function (newValue, oldValue) {
      const newDirection = calculateDirection(newValue);
      const newStyle = {
        ...this.styleObject,
        '--direction': newDirection,
      };

      this.styleObject = newStyle;
    },
  },
}
</script>

<style>
:root {
  --direction: 200vh;
}
</style>

<style>
.cell {
  position: absolute;
  animation: fly linear infinite;

  /* keyframe style initialization */
  opacity: 0;
  transform: translate(0, 0) scale(1) rotate(0deg);
}

@keyframes fly {
  5% {
    opacity: 1;
  }

  90% {
    opacity: 1;
  }

  100% {
    transform: translate(var(--direction), 200vh) scale(0.2) rotate(10deg);
    opacity: 0;
  }
}
</style>
