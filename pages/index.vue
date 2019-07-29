<template>
  <div class="container" role="main">
    <input
      class="fly-range"
      type="range"
      min="-5"
      max="5"
      v-model="rainDirection"
    />
    <div class="fucking-grid">
      <AnimatedCell
        v-for="index in totalUnicorns"
        :key="index + rainDirection"
        :delay-max="delayMax"
        :delay-min="delayMin"
        :duration-max="durationMax"
        :duration-min="durationMin"
        :horizontal-max="horizontalMax"
        :horizontal-min="horizontalMin"
        :rain-direction="rainDirection"
        :size-max="sizeMax"
        :size-min="sizeMin"
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
      delayMax: -10,
      delayMin: 1,
      durationMax: 4,
      durationMin: 8,
      horizontalMax: 100,
      horizontalMin: -100,
      rainDirection: 0,
      sizeMax: 5,
      sizeMin: 0.1,
      totalUnicorns: 50,
      verticalMax: 100,
      verticalMin: -100,
    }
  },
}
</script>

<style>
html {
  background-image: url('/unplez.gif');
}
</style>

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
  background-position: center;
  background-repeat: no-repeat;
}

.fucking-grid {
  position: absolute;
  display: flex;
  flex-wrap: wrap;
  height: 100%;
  width: 100%;
  overflow: hidden;
}

.fly-control {
  cursor: pointer;
  background-color: #FFF;
  padding: 0.5rem;
  border-radius: 50%;
  overflow: hidden;
  position: absolute;
  top: 0;
  user-select: none;
}

.fly-image {
}

.fly-range {
  z-index: 1;
  width: 100%;
  -webkit-appearance: none;
  top: 0;
  position: absolute;
}

.fly-range:focus {
  outline: none;
}
.fly-range::-webkit-slider-runnable-track {
  width: 100%;
  height: 25.6px;
  cursor: pointer;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
  background: #484d4d;
  border-radius: 0px;
  border: 0px solid #010101;
}
.fly-range::-webkit-slider-thumb {
  height: 8rem;
  width: 8rem;
  border-radius: 50%;
  cursor: pointer;
  background-color: #FFF;
  background-image: url('/fly-gai.png');
  background-repeat: no-repeat;
  background-position: center;

  -webkit-appearance: none;
}

.fly-range:focus::-webkit-slider-runnable-track {
  background: #545a5a;
}

.fly-range::-moz-range-track {
  width: 100%;
  height: 25.6px;
  cursor: pointer;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
  background: #484d4d;
  border-radius: 0px;
  border: 0px solid #010101;
}

.fly-range::-moz-range-thumb {
  height: 8rem;
  width: 8rem;
  border-radius: 50%;
  cursor: pointer;
  background-color: #FFF;
  background-image: url('/fly-gai.png');
  background-repeat: no-repeat;
  background-position: center;
}

.fly-range::-ms-track {
  width: 100%;
  height: 25.6px;
  cursor: pointer;
  background: transparent;
  border-color: transparent;
  color: transparent;
}
.fly-range::-ms-fill-lower {
  background: #3c4040;
  border: 0px solid #010101;
  border-radius: 0px;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
}
.fly-range::-ms-fill-upper {
  background: #484d4d;
  border: 0px solid #010101;
  border-radius: 0px;
  box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
}
.fly-range::-ms-thumb {
  height: 8rem;
  width: 8rem;
  border-radius: 50%;
  cursor: pointer;
  background-color: #FFF;
  background-image: url('/fly-gai.png');
  background-repeat: no-repeat;
  background-position: center;
}
.fly-range:focus::-ms-fill-lower {
  background: #484d4d;
}
.fly-range:focus::-ms-fill-upper {
  background: #545a5a;
}
</style>
