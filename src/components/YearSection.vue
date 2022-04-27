<template>
  <div>
    <HeadingText :type="'white'" :icon="clockIcon">
      <template #title>University Year</template>
    </HeadingText>
    <div class="timeline">
      <div class="timeline__row timeline__row-top">
        <div class="timeline-content">
          <h3>Demo Classes</h3>
          <p>
            In the first week, students try to accomodate with the teaching
            style and choose their optional courses.
          </p>
        </div>
        <div class="timeline-content">
          <h3>Graduation Day</h3>
          <p>
            On the day of graduation, all students gather for the ceremony and
            then network and perty among others.
          </p>
        </div>
      </div>
      <div class="timeline__row timeline__row-bottom">
        <div class="timeline-content">
          <h3>Orientation</h3>
          <p>
            First day of the university year, all students gather for the
            opening ceremony and then network with others
          </p>
        </div>
        <div class="timeline-content">
          <h3>Evalutation</h3>
          <p>
            At the end of semester, students take a general evalutation test for
            every subject they're learning
          </p>
        </div>
      </div>
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
  margin: 150px auto 150px auto;
  padding: 0;
  border-radius: 10px;

  &__row {
    position: absolute;
    width: 81%;
    height: 50%;
    overflow: hidden;
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
  }

  &__row-top {
    transform: translateY(-100%);
    top: 0;
    right: -10px;
  }
  &__row-bottom {
    transform: translateY(125%);
    bottom: 0;
    left: -10px;
    align-items: flex-end;
  }
  &-content {
    width: 50%;
    height: 100%;
    padding: 0;
    margin: 0;
    text-align: center;

    h3 {
      font-size: $mt-font-size-xs;
      font-weight: $mt-font-weight-bold;
      font-family: $mt-font-family-accent;
      color: $mt-text-color-white;
      margin: 0 0 10px 0;
    }
    p {
      color: $mt-text-color-white;
      font-size: $mt-font-size-xxs;
      max-width: 70%;
      line-height: 1.2;
      margin: 0 auto;
    }
  }
}
</style>
