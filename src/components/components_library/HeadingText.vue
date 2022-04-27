<template>
  <div class="heading" :class="headingClasses">
    <ImgElement :src="icon" :width="'100px'" />
    <h2>
      <slot name="title"></slot>
    </h2>
    <p>
      <slot name="rich"></slot>
    </p>
  </div>
</template>

<script>
import ImgElement from "./ImgElement.vue";
export default {
  name: "HeadingText",
  data() {
    return {
      //   isWhite: false,
    };
  },
  components: {
    ImgElement,
  },
  props: {
    type: {
      type: String,
      default: "black",
    },
    icon: {
      type: String,
      default: "",
    },
    textAlign: {
      type: String,
      default: "center",
    },
  },
  computed: {
    isWhite() {
      return this.type === "white";
    },
    headingClasses() {
      return {
        "text-center": this.textAlign === "center",
        "text-right": this.textAlign === "right",
        "text-left": this.textAlign === "left",
        "text-white": this.isWhite,
        "text-black": !this.isWhite,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.heading {
  & > h2 {
    font-size: $mt-font-size-lg;
    font-weight: $mt-font-weight-black;
    line-height: 1.2;
    margin-bottom: 2rem;
    font-family: $mt-font-family-accent;
  }
  & > p {
    font-size: $mt-font-size-xs;
    font-weight: $mt-font-weight-regular;
    line-height: 1.7;
    margin-bottom: 2rem;
    font-family: $mt-font-family;
  }
}

.text-white {
  color: #fff;
  & * {
    color: #fff;
  }
}
.text-black {
  color: $mt-text-color;
  & * {
    color: $mt-text-color;
  }
}
.text-center {
  text-align: center;
}
.text-right {
  text-align: right;
}
.text-left {
  text-align: left;
}
</style>
