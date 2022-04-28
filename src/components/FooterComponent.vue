<template>
  <paper-element :style-variant="'secondary'">
    <container-element :content-position="'center center'" :height="'60vh'">
      <div>
        <grid-element :grids="'3'">
          <template #element-1>
            <div>
              <img-element :src="logo" :maxWidth="'70%'" />
              <heading-text :textAlign="'left'" :type="'white'">
                <template #rich>
                  EduPrime is the most versatile WordPress theme for educational
                  purposes, showcasing universities, courses, secondary schools
                  etc.
                </template>
              </heading-text>
              <div class="social-buttons">
                <button-element
                  :size="'icon'"
                  :icon="facebook"
                  :outlined="true"
                >
                </button-element>
                <button-element :size="'icon'" :icon="twitter" :outlined="true">
                </button-element>
                <button-element
                  :size="'icon'"
                  :icon="instagram"
                  :outlined="true"
                >
                </button-element>
              </div>
            </div>
          </template>
          <template #element-2>
            <div>
              <grid-element :grids="'2'">
                <template #element-1>
                  <container-element :contentPosition="'center top'">
                    <div class="footer-nav">
                      <h4>Get EduPrime</h4>
                      <ul>
                        <li>
                          <a href="#">Request a website</a>
                        </li>
                        <li>
                          <a href="#">Browse Theme</a>
                        </li>
                        <li>
                          <a href="#">Payment options</a>
                        </li>
                        <li>
                          <a href="#">Support System</a>
                        </li>
                        <li>
                          <a href="#">Checkout</a>
                        </li>
                        <li>
                          <a href="#">Purchase Theme</a>
                        </li>
                      </ul>
                    </div>
                  </container-element>
                </template>
                <template #element-2>
                  <container-element :contentPosition="'center top'">
                    <div class="footer-nav">
                      <h4>Networking</h4>
                      <ul>
                        <li>
                          <a href="#">Request a website</a>
                        </li>
                        <li>
                          <a href="#">Browse Theme</a>
                        </li>
                        <li>
                          <a href="#">Payment options</a>
                        </li>
                        <li>
                          <a href="#">Support System</a>
                        </li>
                        <li>
                          <a href="#">Checkout</a>
                        </li>
                        <li>
                          <a href="#">Purchase Theme</a>
                        </li>
                      </ul>
                    </div>
                  </container-element>
                </template>
              </grid-element>
            </div>
          </template>
          <template #element-3>
            <div>
              <input-element
                :type="'text'"
                :placeholder="'Search...'"
                :btnIcon="'fa-solid fa-magnifying-glass'"
              />
              <div class="search-categories">
                <h3>Search categories</h3>
                <div class="search-categories-box">
                  <p class="search-categories-element">economy</p>
                  <p class="search-categories-element">design</p>
                  <p class="search-categories-element">coaching</p>
                  <p class="search-categories-element">business</p>
                  <p class="search-categories-element">medicine</p>
                  <p class="search-categories-element">law</p>
                  <p class="search-categories-element">fitnes</p>
                </div>
              </div>
              <h4 class="rights">ModelTheme. All rights reserved.</h4>
            </div>
          </template>
        </grid-element>
      </div>
    </container-element>
  </paper-element>
</template>

<script>
import ContainerElement from "./components_library/ContainerElement.vue";
import GridElement from "./components_library/GridElement.vue";
import ImgElement from "./components_library/ImgElement.vue";
import PaperElement from "./components_library/PaperElement.vue";
import HeadingText from "./components_library/HeadingText.vue";
import logo from "../assets/theme_eduprime_logo.png";
import ButtonElement from "./components_library/ButtonElement.vue";
import facebook from "../assets/facebook.svg";
import twitter from "../assets/twitter.svg";
import instagram from "../assets/instagram.svg";
import InputElement from "./components_library/InputElement.vue";

export default {
  name: "FooterComponent",
  components: {
    PaperElement,
    ContainerElement,
    GridElement,
    ImgElement,
    HeadingText,
    ButtonElement,
    InputElement,
  },
  data() {
    return {
      logo,
      facebook,
      twitter,
      instagram,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.social-buttons {
  display: flex;
  justify-content: flex-start;
  margin-top: 2rem;
  gap: 1rem;
}

.footer-nav {
  & * {
    margin-bottom: 1rem;
    color: $mt-white;
    text-decoration: none;
  }
  & h4 {
    margin-bottom: 2rem;
    font-family: $mt-font-family-accent;
    font-size: $mt-font-size-sm;
    font-weight: $mt-font-weight-black;
  }
}
.search-categories {
  margin-top: 2rem;

  & * {
    color: $mt-white;
  }

  & h3 {
    font-family: $mt-font-family-accent;
    font-size: $mt-font-size-sm;
    font-weight: $mt-font-weight-black;
    text-align: end;
    margin-bottom: 1rem;
  }

  &-box {
    display: flex;
    flex-direction: row-reverse;
    flex-wrap: wrap;
    gap: 0.6rem;
  }
  &-element {
    font-family: $mt-font-family;
    font-size: $mt-font-size-xxs;
    font-weight: $mt-font-weight-regular;
    padding: 0.4rem 1rem;
    border-radius: $mt-border-radius-xxl;
    border: 1px solid $mt-white;
    text-transform: uppercase;
  }
}
.rights {
  font-family: $mt-font-family;
  font-size: $mt-font-size-xs;
  font-weight: $mt-font-weight-regular;
  text-align: end;
  margin-top: 2rem;
  color: $mt-yellow;
}
</style>
