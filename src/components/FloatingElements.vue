<template>
  <div>
    <div class="theme-purchase">
      <div class="purchase-tag">
        <p>Purchase Eduprime on Evanto Market</p>
      </div>
      <div class="theme-purchaes__card">
        <img-element :src="leafIcon" :width="'10px'" />
        <p>Purchase Theme</p>
      </div>
      <div class="theme-purchaes__card">
        <img-element :src="releated" :width="'10px'" />
        <p>Related Themes</p>
      </div>
    </div>
    <div class="return-top-btn" @click="returnToTop">
      <button-element :size="'icon'" :variant="'primary'" :boxShadow="true">
        <font-awesome-icon icon="fa-solid fa-chevron-up" />
      </button-element>
    </div>
  </div>
</template>

<script>
import ImgElement from "./components_library/ImgElement.vue";
import leafIcon from "./../assets/svg-3.svg";
import releated from "./../assets/svg-2.svg";
import ButtonElement from "./components_library/ButtonElement.vue";

export default {
  name: "FloatingElements",
  components: {
    ImgElement,
    ButtonElement,
  },
  data() {
    return {
      leafIcon,
      releated,
    };
  },
  methods: {
    returnToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
  },
};
ImgElement;
</script>
<style lang="scss" scoped>
.theme-purchase {
  position: fixed;
  bottom: 20px;
  left: 20px;
  z-index: 9999;
}

.purchase-tag {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #161616;
  padding: 2px 10px;
  border-radius: 3px;
  font-size: 10px;
  font-weight: 400;
  max-width: 150px;
  margin: 0 auto;
  text-align: center;
  color: #fff;
  position: relative;

  &::after {
    content: "";
    display: block;
    width: 10px;
    height: 10px;
    background-color: #161616;
    position: absolute;
    bottom: -5px;
    right: 50%;
    transform: rotate(45deg);
    z-index: -1;
  }
}

.theme-purchaes__card {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  background-color: rgb(68, 68, 68);
  color: rgb(182, 182, 182);
  border-radius: 5px;
  padding: 0.5rem 1rem;
  min-width: 180px;
  margin-top: 0.5rem;
  box-shadow: 0px 12px 8px -5px rgba(0, 0, 0, 0.4);
  cursor: pointer;
  transition: all 300ms ease-in-out;

  p {
    margin-left: 0.5rem;
    font-size: 0.7rem;
  }

  &:hover {
    background-color: rgb(55, 55, 55);
    transform: scale(0.99);
    box-shadow: 0px 8px 8px -5px rgba(0, 0, 0, 0.4);
  }
}
.return-top-btn {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 9999;
}
</style>
