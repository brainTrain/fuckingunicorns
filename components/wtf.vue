<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<script>
const randomNumber = (min, max) => (Math.random() * (max - min) + min)

export default {
  data: function () {
    console.log('wutttt')
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
      }
    }
  }
}
</script>

<style scoped>
.container {
  background-color: #B4D455;
}
</style>
