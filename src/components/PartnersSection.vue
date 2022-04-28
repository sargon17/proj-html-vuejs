<template>
  <div>
    <ContainerElement :contentPosition="'center center'" :width="'30vw'">
      <HeadingText :type="'black'" :icon="upcomingIcon" :textAlign="'center'">
        <template #title>Partners</template>
        <template #rich
          >Leverage agile frameworks to provide a robust synopsis for high level
          overviews. Iterative approaches to corporate strategy.</template
        >
      </HeadingText>
    </ContainerElement>
    <ContainerElement :contentPosition="'center center'">
      <GridElement :grids="partnersLogos.length.toString()">
        <template v-for="partner in partnersLogos" v-slot:[partner.position]>
          <div class="partner" :key="partner.id">
            <ImgElement
              :src="partner.img"
              :alt="partner.name"
              :maxHeight="'50px'"
              :height="'50px'"
              :width="'10vw'"
              :maxWidth="'110px'"
              :custom="{ 'margin-right': '10px', opacity: '0.4' }"
              :imgFit="'contain'"
              :onHoover="{ 'margin-right': '10px', opacity: '1' }"
            />
          </div>
        </template>
      </GridElement>
    </ContainerElement>
  </div>
</template>

<script>
import HeadingText from "./components_library/HeadingText.vue";
import ContainerElement from "./components_library/ContainerElement.vue";
import GridElement from "./components_library/GridElement.vue";
import partnersLogos from "./../data/partnersLogos.json";
import ImgElement from "./components_library/ImgElement.vue";

export default {
  name: "PartnersSection",
  components: {
    HeadingText,
    ContainerElement,
    GridElement,
    ImgElement,
  },
  data() {
    return {
      partnersLogos,
      isLookout: false,
    };
  },
  computed: {
    customStyles() {
      if (this.isLookout) {
        return {
          "margin-top": "20px",
          opacity: "1",
        };
      }
      return {
        "margin-top": "20px",
        opacity: "0.4",
      };
    },
  },
  methods: {
    hooverEffect() {
      this.isLookout = !this.isLookout;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.partner {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
}
</style>
