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
  },
  computed: {
    imgStyles() {
      if (this.width === "auto") {
        return "";
      }
      return {
        width: this.width,
        "max-width": this.width,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  max-width: 100%;
}
</style>
