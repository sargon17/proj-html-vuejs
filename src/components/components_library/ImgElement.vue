<template>
  <img :src="src" alt="" :style="imgStyles" />
</template>

<script>
export default {
  name: "ImgElement",
  props: {
    src: {
      type: String,
      default: "",
    },
    width: {
      type: String,
      default: "auto",
    },
    maxWidth: {
      type: String,
      default: "",
    },
    custom: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    imgStyles() {
      if (this.width === "auto") {
        return "";
      }
      let customStyle = this.custom;
      return {
        width: this.width,
        "max-width": this.maxWidth,
        ...customStyle,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  max-width: 100%;
  max-height: 100% !important;
  transition: $mt-transition;
}
</style>
