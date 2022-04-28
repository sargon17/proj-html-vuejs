<template>
  <div class="input">
    <input type="text" :placeholder="placeholder" />
    <ButtonElement :size="'icon'" :variant="btnVariant">
      <font-awesome-icon :icon="btnIcon" />
    </ButtonElement>
  </div>
</template>

<script>
import ButtonElement from "./ButtonElement.vue";
export default {
  name: "InputElement",
  components: {
    ButtonElement,
  },
  props: {
    btnVariant: {
      type: String,
      default: "primary",
    },
    placeholder: {
      type: String,
      default: "Input here...",
    },
    btnIcon: {
      type: String,
      default: "fa-solid fa-paper-plane",
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";
.input {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  border: none;
  border-radius: 500px;
  transition: all 0.3s ease;
  outline: none;
  margin: 1px 10px;
  background: $mt-bg-input;
  overflow: hidden;
}
input {
  width: calc(100% - 2rem);
  height: 100%;
  border: none;
  padding: 0 2rem;
  font-size: 0.9rem;
  font-weight: 700;
  line-height: 1.5;
  cursor: pointer;
  transition: all 0.3s ease;
  outline: none;
  margin: 1px;
  background: $mt-bg-input;
  color: $mt-text-color;

  &::placeholder {
    color: $mt-text-color-light;
    font-weight: $mt-font-weight-regular;
  }
}
</style>
