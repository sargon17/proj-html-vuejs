<template>
  <div>
    <HeadingText :type="'white'" :icon="upcomingIcon">
      <template #title>University Year</template>
    </HeadingText>
  </div>
</template>

<script>
import HeadingText from "./components_library/HeadingText.vue";
import upcomingIcon from "../assets/upcoming-events-calendar-icon.png";
export default {
  name: "EventsSection",
  data() {
    return {
      upcomingIcon,
    };
  },
  components: {
    HeadingText,
  },
};
</script>

<style></style>
