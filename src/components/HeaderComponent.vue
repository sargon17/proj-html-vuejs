<template>
  <div class="header">
    <div class="header__container">
      <div class="header__logo">
        <img :src="logo" alt="" />
      </div>
      <div class="header__nav">
        <div class="header__nav-links">
          <NavigationDropdown :data="navLinks" />
        </div>
        <div class="header__nav-main-btn">
          <ButtonElement variant="primary" dimensions="lg" caps>
            view courses
          </ButtonElement>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import logo from "../assets/theme_eduprime_logo.png";
import ButtonElement from "./components_library/ButtonElement.vue";
import NavigationDropdown from "./components_library/NavigationDropdown.vue";
import headerNavigationData from "../data/headerNavigationData";

export default {
  name: "HeaderComponent",
  data() {
    return {
      logo,
      navLinks: headerNavigationData,
    };
  },
  components: {
    ButtonElement,
    NavigationDropdown,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.header {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 75px;
  z-index: 5;
  padding: 20px 36px;

  &__container {
    max-width: $mt-screen-xl;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    height: 100%;
    width: 250px;
    max-width: 100%;
    overflow: hidden;
    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }
  &__nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
    gap: 20px;
  }
}
</style>
