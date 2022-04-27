<template>
  <div>
    <HeadingText :type="'white'" :icon="upcomingIcon">
      <template #title>Upcoming Events</template>
    </HeadingText>
    <GridElement :grids="upcomingCard.length.toString()">
      <template v-for="card in upcomingCard" v-slot:[card.position]>
        <ContainerElement :contentPosition="'center center'" :key="card.id">
          <CardElement :content="card" />
        </ContainerElement>
      </template>
    </GridElement>
    <ContainerElement :contentPosition="'center center'">
      <ButtonElement :variant="'primary'" :size="'lg'">
        View All Events
      </ButtonElement>
    </ContainerElement>
  </div>
</template>

<script>
import HeadingText from "./components_library/HeadingText.vue";
import upcomingIcon from "../assets/upcoming-events-calendar-icon.png";
import GridElement from "./components_library/GridElement.vue";
import ContainerElement from "./components_library/ContainerElement.vue";
import CardElement from "./components_library/CardElement.vue";
import ButtonElement from "./components_library/ButtonElement.vue";
import upcomingCard from "../data/upcomingCard";

export default {
  name: "EventsSection",
  data() {
    return {
      upcomingIcon,
      upcomingCard,
    };
  },
  components: {
    HeadingText,
    GridElement,
    ContainerElement,
    CardElement,
    ButtonElement,
  },
};
</script>

<style></style>
