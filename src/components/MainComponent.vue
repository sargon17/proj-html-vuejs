<template>
  <div>
    <ContainerElement :contentPosition="'center center'" :height="'70vh'">
      <AsideDescElement :content="coursesIntro" />
    </ContainerElement>
    <MultiDescriptionComponent :content="facultiesIntro" />
    <WaveElement :variant="'top'" />
    <PaperElement :styleVariant="'secondary'">
      <ContainerElement :contentPosition="'center center'" :height="'80vh'">
        <YearSection />
      </ContainerElement>
    </PaperElement>
    <PaperElement :styleVariant="'secondary'">
      <ContainerElement :contentPosition="'center center'" :height="'80vh'">
        <EventsSection />
      </ContainerElement>
    </PaperElement>
    <WaveElement :variant="'bottom'" />
    <PaperElement :styleVariant="'primary'">
      <ContainerElement :contentPosition="'center center'" :height="'60vh'">
        <LatestCoursesSection />
      </ContainerElement>
    </PaperElement>
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
import WaveElement from "./components_library/WaveElement.vue";
import PaperElement from "./components_library/PaperElement.vue";
import YearSection from "./YearSection.vue";
import EventsSection from "./EventsSection.vue";
import LatestCoursesSection from "./LatestCoursesSection.vue";

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
    WaveElement,
    PaperElement,
    YearSection,
    EventsSection,
    LatestCoursesSection,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";
</style>
