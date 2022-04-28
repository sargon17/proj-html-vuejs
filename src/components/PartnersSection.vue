<template>
  <div>
    <div class="partners-decoration">
      <div class="color-box"></div>
      <div class="img-box">
        <img-element :src="partnersBackground" :width="'120%'" />
      </div>
    </div>
    <div class="partner-container">
      <ContainerElement :contentPosition="'center center'" :width="'30vw'">
        <HeadingText :type="'black'" :textAlign="'center'">
          <template #title>Partners</template>
          <template #rich
            >Leverage agile frameworks to provide a robust synopsis for high
            level overviews. Iterative approaches to corporate
            strategy.</template
          >
        </HeadingText>
      </ContainerElement>
    </div>
    <div class="partner-container">
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
  </div>
</template>

<script>
import HeadingText from "./components_library/HeadingText.vue";
import ContainerElement from "./components_library/ContainerElement.vue";
import GridElement from "./components_library/GridElement.vue";
import partnersLogos from "./../data/partnersLogos.json";
import ImgElement from "./components_library/ImgElement.vue";
import partnersBackground from "./../assets/background-wave3.png";

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
      partnersBackground,
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
.partner-container {
  z-index: 2;
}

.partner {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
}

.partners-decoration {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  z-index: -1;
  overflow: hidden;

  & > .color-box {
    width: 100%;
    height: 30vh;
    background-color: rgb(255, 255, 255);
  }
  & > .img-box {
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
}
</style>
