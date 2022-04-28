<template>
  <div
    :style="containerStyle"
    @mouseover="hooverEffectToggle"
    @mouseleave="hooverEffectToggle"
  >
    <img :src="src" alt="" :style="imgStyles" :height="height" />
  </div>
</template>

<script>
export default {
  name: "ImgElement",
  data() {
    return {
      isHoovered: false,
    };
  },
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
    height: {
      type: String,
      default: "",
    },
    maxHeight: {
      type: String,
      default: "",
    },
    imgFit: {
      type: String,
      default: "cover",
    },
    onHoover: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    imgStyles() {
      let customStyle = this.custom;
      if (this.isHoovered) {
        customStyle = this.onHoover;
      }
      return {
        "object-fit": this.imgFit,
        ...customStyle,
      };
    },
    containerStyle() {
      return {
        height: this.height,
        width: this.width,
        "max-width": this.maxWidth,
        "max-height": this.maxHeight,
      };
    },
  },
  methods: {
    hooverEffectToggle() {
      this.isHoovered = !this.isHoovered;
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
