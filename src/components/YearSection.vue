<template>
  <div>
    <HeadingText :type="'white'" :icon="clockIcon">
      <template #title>University Year</template>
    </HeadingText>
    <div class="timeline">
      <div class="timeline__row timeline__row-top">
        <div class="timeline-content">
          <h3>hello</h3>
        </div>
        <div class="timeline-content">
          <h3>hello</h3>
        </div>
      </div>
      <div class="timeline__row timeline__row-top"></div>
      <div class="timeline__bg">
        <ImgElement :src="TimelineItem" />
      </div>
    </div>
  </div>
</template>

<script>
import clockIcon from "../assets/Clock-and-Bell.png";
import HeadingText from "./components_library/HeadingText.vue";
import ImgElement from "./components_library/ImgElement.vue";
import TimelineItem from "../assets/Timeline-Item.png";
export default {
  name: "YearSection",
  components: {
    HeadingText,
    ImgElement,
  },
  data() {
    return {
      clockIcon,
      TimelineItem,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../styles/general.scss";

.timeline {
  position: relative;
  width: 100%;
  height: 100%;
  margin: 0 auto;
  padding: 0;
  overflow: hidden;
  border-radius: 10px;

  &__row {
    transform: translateY(-50%);
    position: absolute;
    width: 75%;
    height: 50%;
    top: 0;
    right: 0;
    padding: 0;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>
