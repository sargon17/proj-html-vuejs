<template>
  <ContainerElement :contentPosition="'center center'" :height="'100%'">
    <GridElement :grids="'2'" :spacing="'60'" :order="setOrder">
      <template #element-1>
        <ContainerElement :contentPosition="'center center'">
          <div>
            <ImgElement
              v-if="content.hasInitialImg"
              :src="content.initialImg.path"
              :width="'60px'"
            />
            <HeadingText :textAlign="'left'">
              <template #title>
                {{ content.title }}
              </template>
              <template #rich>
                {{ content.rich }}
              </template>
            </HeadingText>
            <ButtonElement
              v-if="content.hasButton"
              :variant="content.button.variant"
              :size="content.button.size"
            >
              <font-awesome-icon
                v-if="content.button.hasIcon"
                :icon="content.button.icon"
              />
              {{ content.button.text }}
            </ButtonElement>
          </div>
        </ContainerElement>
      </template>
      <template #element-2>
        <ContainerElement :contentPosition="'center center'">
          <ImgElement :src="content.image.path" />
        </ContainerElement>
      </template>
    </GridElement>
  </ContainerElement>
</template>

<script>
import GridElement from "./GridElement.vue";
import HeadingText from "./HeadingText.vue";
import ButtonElement from "./ButtonElement.vue";
import ImgElement from "./ImgElement.vue";

export default {
  name: "AsideDescElement",
  components: {
    GridElement,
    HeadingText,
    ButtonElement,
    ImgElement,
  },
  props: {
    content: {
      type: Object,
      default: () => ({}),
      required: true,
    },
    textSide: {
      type: String,
      default: "left",
    },
  },
  computed: {
    setOrder() {
      return this.textSide === "left" ? "normal" : "inverse";
    },
  },
};
</script>

<style lang="scss" scoped></style>
