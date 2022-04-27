<template>
  <div>
    <ContainerElement :contentPosition="'center center'" :height="'70vh'">
      <AsideDescElement :content="coursesIntro" />
    </ContainerElement>
    <MultiDescriptionComponent :content="facultiesIntro" />
    <ContainerElement
      :contentPosition="'center center'"
      v-for="feature in schoolDescription"
      :key="feature.id"
      :height="'60vh'"
    >
      <AsideDescElement :content="feature" :textSide="feature.textSide" />
    </ContainerElement>
  </div>
</template>

<script>
import ContainerElement from "./components_library/ContainerElement.vue";
import AsideDescElement from "./components_library/AsideDescElement.vue";
import coursesIntro from "./../data/coursesIntro.json";
import schoolDescription from "./../data/schoolDescription.json";
import MultiDescriptionComponent from "./components_library/MultiDescriptionComponent.vue";
import facultiesIntro from "./../data/facultiesIntro.json";
export default {
  name: "MainComponent",
  data() {
    return {
      coursesIntro,
      schoolDescription,
      facultiesIntro,
    };
  },
  components: {
    ContainerElement,
    AsideDescElement,
    MultiDescriptionComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";
</style>
