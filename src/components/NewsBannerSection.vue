<template>
  <div>
    <GridElement :grids="'2'" :align="'between'">
      <template #element-1>
        <ContainerElement :contentPosition="'left centre'">
          <HeadingText :type="'white'" :textAlign="'left'">
            <template #title>Subscribe Now to Our Newsletter!</template>
          </HeadingText>
        </ContainerElement>
      </template>
      <template #element-2>
        <ContainerElement :contentPosition="'right centre'">
          <InputElement
            :btnVariant="'primary'"
            :placeholder="'Email adress...'"
          />
        </ContainerElement>
      </template>
    </GridElement>
  </div>
</template>

<script>
import GridElement from "./components_library/GridElement.vue";
import HeadingText from "./components_library/HeadingText.vue";
import ContainerElement from "./components_library/ContainerElement.vue";
import InputElement from "./components_library/InputElement.vue";
export default {
  name: "NewsBannerSection",
  components: {
    GridElement,
    HeadingText,
    ContainerElement,
    InputElement,
  },
};
</script>

<style lang="scss" scoped></style>
