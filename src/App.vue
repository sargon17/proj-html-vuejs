<template>
  <div id="app">
    <HeaderComponent />
    <HeroComponent />
    <MainComponent />
    <FooterComponent />
    <FloatingElements />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import HeroComponent from "./components/HeroComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
import FloatingElements from "./components/FloatingElements.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    HeroComponent,
    MainComponent,
    FooterComponent,
    FloatingElements,
  },
};
</script>

<style lang="scss">
@import "./styles/general.scss";
.app {
  position: relative;
}
</style>
