<template>
  <div class="nav-dropdown">
    <ul class="nav-dropdown__list">
      <li
        class="nav-dropdown__list-item"
        v-for="item in data"
        :key="item.title"
      >
        <a :href="item.url">
          {{ item.title }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "NavigationDropdown",
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped.>
@import "../../styles/general.scss";
.nav-dropdown {
  &__list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;

    &-item {
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0.5rem 1rem;
      font-size: 1.2rem;
      color: #fff;
      text-decoration: none;
      transition: all 0.2s ease-in-out;

      &:hover {
        background-color: #fff;
        color: #000;
      }
      a {
        color: $mt-white;
      }
    }
  }
}
</style>
