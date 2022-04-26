<template>
  <div class="heading" :class="{ white: isWhite, black: !isWhite }">
    <h2>
      <slot name="title"></slot>
    </h2>
    <p>
      <slot name="rich"></slot>
    </p>
  </div>
</template>

<script>
export default {
  name: "HeadingText",
  data() {
    return {
      //   isWhite: false,
    };
  },
  props: {
    type: {
      type: String,
      default: "black",
    },
  },
  computed: {
    isWhite() {
      return this.type === "white";
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.heading {
  & > h2 {
    font-size: 3rem;
    font-weight: 900;
    line-height: 1.2;
    margin-bottom: 2rem;
    font-family: $mt-font-family-accent;
  }
  & > p {
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.7;
    margin-bottom: 2rem;
    font-family: $mt-font-family;
  }
}

.white {
  color: #fff;
  & * {
    color: #fff;
  }
}
.black {
  color: #000;
  & * {
    color: #000;
  }
}
</style>
