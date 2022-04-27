<template>
  <div class="selection-bar">
    <div class="selection_btn_wrapper">
      <div
        v-for="item in sections"
        :key="item.id"
        class="selection_btn-element"
        :class="{ active: isSelected(item.id) }"
        @click="select(item.id)"
      >
        <div class="selection_btn-element__content">
          <ImgElement
            :src="item.icon.path"
            :width="'50%'"
            :maxWidth="'250px'"
            :custom="
              isSelected(item.id) ? { filter: 'brightness(0) invert(1)' } : {}
            "
          />
          <h3>{{ item.title }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ImgElement from "./ImgElement.vue";
export default {
  name: "MultiSelectionElement",
  components: {
    ImgElement,
  },
  props: {
    sections: {
      type: Array,
      required: true,
    },
    selected: {
      type: String,
      required: true,
    },
  },
  methods: {
    isSelected(id) {
      console.log(this.selected);
      return this.selected === id;
    },
    select(id) {
      this.$emit("select", id);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.selection-bar {
  height: 20vh;
  width: 100%;
  background-color: $mt-white;
  box-shadow: $mt-shadow-default;
}
.selection_btn_wrapper {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  max-width: $mt-screen-lg;
  margin: 0 auto;
}
.selection_btn-element {
  position: relative;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: $mt-screen-lg;
  margin: 0 auto;
  transition: $mt-transition;
  cursor: pointer;
  border: 1px solid $mt-white-gray;

  &__content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;

    & h3 {
      font-size: $mt-font-size-xs;
      font-weight: $mt-font-weight-bold;
      font-family: $mt-font-family-accent;
      color: $mt-text-color-red;
    }
  }
  &::after {
    content: "";
    position: absolute;
    bottom: 20px;
    left: 47%;
    width: 0px;
    aspect-ratio: 1;
    transform: rotate(45deg) translate(10%, 50%);
    background: $mt-red;
    opacity: 0;
    transition: $mt-transition, opacity 0s;
    border-radius: 3px;
  }
}
.active {
  background: $mt-red;
  color: $mt-white;
  border: none;

  .selection_btn-element__content {
    & h3 {
      color: $mt-white;
    }
  }

  &::after {
    width: 30px;
    bottom: 0;
    opacity: 1;
    transition-delay: 200ms;
  }
}
</style>
