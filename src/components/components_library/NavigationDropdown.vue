<template>
  <div class="nav-dropdown">
    <ul class="nav-dropdown__list">
      <NavDropdownItem
        v-for="item in data"
        :key="item.title"
        :value="item"
        :isSelected="checkCurrentSelectedMenu(item.id)"
        @setSelectedMenu="setSelectedMenu"
      />
    </ul>
  </div>
</template>

<script>
import NavDropdownItem from "./NavDropdownItem.vue";

export default {
  name: "NavigationDropdown",
  data() {
    return {
      currentSelectedMenu: "about",
    };
  },
  components: {
    NavDropdownItem,
  },
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
  methods: {
    checkCurrentSelectedMenu(id) {
      return this.currentSelectedMenu === id;
    },
    setSelectedMenu(id) {
      this.currentSelectedMenu = id;
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
    gap: $mt-spacing-xs;
  }
}
</style>
