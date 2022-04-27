<template>
  <div class="wave">
    <img
      v-if="isWaveTop()"
      class="wave-top"
      src="https://github.com/sargon17/proj-html-vuejs/blob/83382a4886ae39aba9fd476109e29ff8e1c1aa3f/src/assets/svg-0.svg?raw=true"
      alt=""
    />
    <img
      v-if="!isWaveTop()"
      class="wave-bottom"
      src="https://raw.githubusercontent.com/sargon17/proj-html-vuejs/2dc345b55cfe1d7a37067cffb32da8e663b74ee0/src/assets/svg-1.svg?raw=true"
      alt=""
    />
  </div>
</template>

<script>
export default {
  name: "WaveElement",
  props: {
    variant: {
      type: String,
      default: "top",
    },
  },
  methods: {
    isWaveTop() {
      return this.variant === "top";
    },
  },
};
</script>

<style lang="scss" scoped>
.wave {
  max-width: 100vw;
  overflow: hidden;
}
.wave-top {
  margin-bottom: -3px;
}
.wave-bottom {
  margin-top: -3px;
}
</style>
