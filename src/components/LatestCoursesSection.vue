<template>
  <div>
    <HeadingText :type="'black'" :textAlign="'left'">
      <template #title>Latest Courses</template>
    </HeadingText>
    <GridElement :grids="latestCoursesCards.length.toString()">
      <template v-for="card in latestCoursesCards" v-slot:[card.position]>
        <ContainerElement :contentPosition="'center center'" :key="card.id">
          <CardElement :content="card" :height="'300px'" />
        </ContainerElement>
      </template>
    </GridElement>
  </div>
</template>

<script>
import GridElement from "./components_library/GridElement.vue";
import ContainerElement from "./components_library/ContainerElement.vue";
import HeadingText from "./components_library/HeadingText.vue";
import CardElement from "./components_library/CardElement.vue";
import latestCoursesCards from "../data/latestCoursesCards";

export default {
  name: "LastestCoursesSection",
  components: {
    GridElement,
    ContainerElement,
    HeadingText,
    CardElement,
  },
  data() {
    return {
      latestCoursesCards,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/variables";
</style>
