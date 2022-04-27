<template>
  <div>
    <ContainerElement :contentPosition="'center center'" :height="'100vh'">
      <GridElement :grids="'3'">
        <template #element-1>
          <ContainerElement :contentPosition="'center bottom'">
            <h1>First block</h1>
          </ContainerElement>
        </template>
        <template #element-2>
          <ContainerElement :contentPosition="'left center'">
            <h1>Second Block</h1>
          </ContainerElement>
        </template>
        <template #element-3>
          <ContainerElement :contentPosition="'left center'">
            <h1>Third Block</h1>
          </ContainerElement>
        </template>
      </GridElement>
    </ContainerElement>
  </div>
</template>

<script>
import ContainerElement from "./components_library/ContainerElement.vue";
import GridElement from "./components_library/GridElement.vue";
export default {
  name: "MainComponent",
  components: {
    ContainerElement,
    GridElement,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";
</style>
