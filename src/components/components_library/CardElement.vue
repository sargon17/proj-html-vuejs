<template>
  <div class="card-container">
    <div class="card" :style="cardStyles">
      <PaperElement :styleVariant="'primary'">
        <ContainerElement :contentPosition="'center center'">
          <div>
            <ImgElement :src="content.image" :width="'100px'" />
            <h3 class="card-title">{{ content.title }}</h3>
            <div class="card-data">
              <InfoTagElement
                :content="tag"
                v-for="tag in content.infoTags"
                :key="tag.id + tag.title"
              />
            </div>
            <p class="card-description">
              {{ content.description }}
            </p>
          </div>
        </ContainerElement>
      </PaperElement>
    </div>
    <div class="card-button" v-if="content.hasButton">
      <ContainerElement :contentPosition="'center center'">
        <ButtonElement :variant="'fourth'" :size="'xs'" :boxShadow="true">
          <font-awesome-icon :icon="content.button.icon" />
          {{ content.button.text }}
        </ButtonElement>
      </ContainerElement>
    </div>
  </div>
</template>

<script>
import PaperElement from "./PaperElement.vue";
import ContainerElement from "./ContainerElement.vue";
import ButtonElement from "./ButtonElement.vue";
import ImgElement from "./ImgElement.vue";
import InfoTagElement from "./InfoTagElement.vue";

export default {
  name: "CardElement",
  components: {
    PaperElement,
    ContainerElement,
    ButtonElement,
    ImgElement,
    InfoTagElement,
  },
  props: {
    content: {
      type: Object,
      required: true,
    },
    height: {
      type: String,
      default: "auto",
    },
  },
  computed: {
    cardStyles() {
      return {
        height: this.height,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";
.card-container {
  &:hover .card {
    box-shadow: $mt-shadow-hover;
    transform: scale(0.995);
  }

  &:hover .card-button {
    transform: scale(0.99) translateY(-50%);
  }
}

.card {
  width: 100%;
  border-radius: $mt-border-radius-xl;
  overflow: hidden;
  text-align: center;
  box-shadow: $mt-shadow-default;
  transition: $mt-transition-press;

  &-title {
    font-size: $mt-font-size-sm;
    font-weight: $mt-font-weight-black;
    color: $mt-text-color;
    font-family: $mt-font-family-accent;
    padding: $mt-spacing-sm $mt-spacing-sm;
    margin-top: 20px;
  }
  &-data {
    font-size: $mt-font-size-xxs;
    font-weight: $mt-font-weight-regular;
    color: $mt-text-color-light;
    font-family: $mt-font-family;
    padding: $mt-spacing-sm $mt-spacing-sm;
  }
  &-description {
    font-size: $mt-font-size-xs;
    font-weight: $mt-font-weight-regular;
    line-height: 1.4rem;
    color: $mt-text-color-light;
    font-family: $mt-font-family;
    padding: $mt-spacing-sm $mt-spacing-sm;
    margin-bottom: 20px;
  }
  &-button {
    transform: translateY(-50%);
  }
}
</style>
