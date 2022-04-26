<template>
  <div class="hero">
    <div class="hero__content">
      <HeadingText :type="'white'" :align="'center'">
        <template #title> Key to your success </template>
        <template #rich>
          EduPrime is the most versatile WordPress theme for educational
          purposes, showcasing universities, courses, secondary shools etc.
        </template>
      </HeadingText>
      <div class="hero__content__buttons-container">
        <ButtonElement :variant="'primary'" :dimensions="xl">
          <font-awesome-icon icon="fa-solid fa-magnifying-glass" /> Search
          courses
        </ButtonElement>
        <ButtonElement :variant="'tertiary'" :dimensions="xl">
          <font-awesome-icon icon="fa-solid fa-user-plus" />
          Apply for university
        </ButtonElement>
      </div>
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
import HeadingText from "./sub_components/HeadingText.vue";
import ButtonElement from "./sub_components/ButtonElement.vue";

export default {
  name: "HeroComponent",
  data() {
    return {
      bgImg,
      wave,
      headerText: {
        title: "This title",
        rich: "Some subtitle",
      },
    };
  },
  components: {
    HeadingText,
    ButtonElement,
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

  &__content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    z-index: 3;
    max-width: 30%;

    &__buttons-container {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      margin-top: 2rem;
    }
  }

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
      background-color: $mt-red-transparent;
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
