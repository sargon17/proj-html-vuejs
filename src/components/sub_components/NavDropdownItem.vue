<template>
  <li
    class="list-item"
    :class="{
      'list-item-active': this.isSelected,
    }"
    :key="value.title"
    @click="setSelectedMenu(value.id)"
    @mouseover="displayDropdown = true"
    @mouseleave="displayDropdown = false"
  >
    <a :href="value.url">
      {{ value.title }}
      <font-awesome-icon
        icon="fa-solid fa-chevron-down"
        v-if="value.hasDropdown"
      />
    </a>
    <div
      v-if="value.hasDropdown"
      class="list-item__dropdown"
      :class="{ 'list-item__dropdown-show': this.displayDropdown }"
    >
      <ul class="list-item__dropdown__list">
        <li
          class="list-item__dropdown__list-item"
          v-for="item in value.dropDownData"
          :key="item.title"
        >
          <a :href="item.url">
            {{ item.title }}
          </a>
        </li>
      </ul>
    </div>
  </li>
</template>

<script>
export default {
  name: "NavDropdownItem",
  data() {
    return {
      displayDropdown: false,
    };
  },
  props: {
    value: {
      type: Object,
      required: true,
    },
    isSelected: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    setSelectedMenu(id) {
      this.$emit("setSelectedMenu", id);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.list-item {
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.2s ease-in-out;
  position: relative;

  a {
    padding: 0.4rem 0.8rem;
    color: $mt-white;
    text-decoration: none;
    font-weight: $mt-font-weight-black;
    font-size: $mt-font-size-xs;
    transition: $mt-transition;
    border-radius: $mt-border-radius-xl;
    font-family: $mt-font-family-accent;

    &:hover {
      color: $mt-red;
      background-color: $mt-white;
    }
    &:hover .list-item__dropdown {
      opacity: 1;
    }
  }

  &-active {
    a {
      color: $mt-yellow;
    }
  }

  &__dropdown {
    position: absolute;
    top: 100%;
    left: 50%;
    margin-top: 2px;
    transform: translateX(-50%) translateY(100%);
    background-color: $mt-white;
    border-radius: $mt-border-radius-xl;
    box-shadow: $mt-shadow-default;
    z-index: 10;
    transition: transform 0.2s ease-in-out, opacity 0.2s ease-in-out;
    opacity: 0;
    overflow: hidden;
    height: 0;
    min-width: 200px;

    &-show {
      opacity: 1;
      height: auto;
      transform: translateX(-50%) translateY(0);
    }
    &__list {
      list-style: none;
      margin: 0;
      &-item {
        transition: $mt-transition;
        border-bottom: 1px solid $mt-white-gray;
        transition: all 0.2s ease-in-out;
        padding: 0.5rem;

        &:hover {
          background-color: $mt-white-gray;
        }

        a {
          color: $mt-gray;
          padding: 0.5rem 4rem 0.5rem 0.5rem;
          margin: 10px;
          width: 100%;
          min-width: 200px;
          height: 100%;

          &:hover {
            background: none;
          }
        }
      }
    }
  }
}
</style>
