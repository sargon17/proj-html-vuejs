<template>
  <div class="hero">
    <div class="hero__content">
      <h1 class="title">Some title</h1>
      <p class="subtitle">Some subtitle</p>
    </div>
    <div class="hero__bg">
      <div class="hero__bg-waves">
        <img :src="wave" alt="" />
      </div>
      <div class="hero__bg-color"></div>
      <div class="hero__bg-img">
        <img :src="bgImg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
import bgImg from "../assets/theme_slider1_bg-1.jpg";
import wave from "../assets/Wave-1.png";
export default {
  name: "HeroComponent",
  data() {
    return {
      bgImg,
      wave,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.hero {
  position: relative;
  height: 90vh;
  width: 100%;
  overflow: hidden;
  &__bg {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    &-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      top: 0;
      left: 0;
      z-index: -1;
    }
    &-color {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: $mt-bg-red-transparent;
      z-index: 0;
    }
    &-waves {
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 100%;
      height: fit-content;
      z-index: 1;
      &-img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
