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
import ButtonElement from "./sub_components/ButtonElement.vue";
import NavigationDropdown from "./sub_components/NavigationDropdown.vue";

export default {
  name: "HeaderComponent",
  data() {
    return {
      logo,
      navLinks: [
        {
          title: "Home",
          url: "#",
          hasDropdown: true,
          dropDownData: [
            {
              title: "Home",
              url: "#",
            },
            {
              title: "Home",
              url: "#",
            },
            {
              title: "Home",
              url: "#",
            },
          ],
        },
        {
          title: "About",
          url: "#",
          hasDropdown: false,
        },
        {
          title: "Courses",
          url: "#",
          hasDropdown: false,
        },
        {
          title: "Contact",
          url: "#",
          hasDropdown: false,
        },
      ],
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
  padding: 20px 0;

  &__container {
    max-width: $mt-screen-lg;
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
    overflow: hidden;
    gap: 20px;
  }
}
</style>
