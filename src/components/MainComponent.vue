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
    <PaperElement :styleVariant="'secondary'">
      <ContainerElement :contentPosition="'center center'" :height="'30vh'">
        <NewsBannerSection />
      </ContainerElement>
    </PaperElement>
    <PaperElement :styleVariant="'quaternary'">
      <div class="partners-decoration">
        <img-element :src="partnersBackground" />
      </div>
      <ContainerElement :contentPosition="'center top'" :height="'70vh'">
        <PartnersSection />
      </ContainerElement>
    </PaperElement>
    <div class="decorative-bg-elements">
      <div class="courses-decoration">
        <img-element :src="homeBackground" />
      </div>
    </div>
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
import NewsBannerSection from "./NewsBannerSection.vue";
import PartnersSection from "./PartnersSection.vue";
import ImgElement from "./components_library/ImgElement.vue";
import homeBackground from "./../assets/home-background.png";
import partnersBackground from "./../assets/background-wave3.png";

export default {
  name: "MainComponent",
  data() {
    return {
      coursesIntro,
      schoolDescription,
      facultiesIntro,
      homeBackground,
      partnersBackground,
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
    NewsBannerSection,
    PartnersSection,
    ImgElement,
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.courses-decoration {
  position: absolute;
  top: 90vh;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
.partners-decoration {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
</style>
