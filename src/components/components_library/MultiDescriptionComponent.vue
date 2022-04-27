<template>
  <div>
    <HeadingText :align="'center'">
      <template #title>{{ content.title }}</template>
      <template #rich>
        {{ content.rich }}
      </template>
    </HeadingText>
    <MultiSelectionElement
      :sections="content.sections"
      :selected="selected"
      @select="updateSelection"
    />
    <ContainerElement :contentPosition="'center center'" :height="'60vh'">
      <AsideDescElement :content="selectedSection" :textSide="'right'" />
    </ContainerElement>
  </div>
</template>

<script>
import MultiSelectionElement from "./MultiSelectionElement.vue";
import HeadingText from "./HeadingText.vue";
import AsideDescElement from "./AsideDescElement.vue";
import ContainerElement from "./ContainerElement.vue";
export default {
  name: "MultiDescriptionComponent",
  data() {
    return {
      selected: "",
    };
  },
  components: {
    MultiSelectionElement,
    HeadingText,
    AsideDescElement,
    ContainerElement,
  },
  props: {
    content: {
      type: Object,
      required: true,
    },
  },
  mounted() {
    this.selected = this.content.sections[0].id;
  },
  computed: {
    selectedSection() {
      return this.content.sections.find(
        (section) => section.id === this.selected
      );
    },
  },
  methods: {
    updateSelection(id) {
      this.selected = id;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";
</style>
