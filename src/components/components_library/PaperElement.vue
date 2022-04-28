<template>
  <div class="paper" :class="styleVariantClass" :style="paperStyle">
    <slot />
  </div>
</template>

<script>
export default {
  name: "PaperElement",
  props: {
    styleVariant: {
      type: String,
      default: "primary",
    },
    zIndex: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    styleVariantClass() {
      return `paper-${this.styleVariant}`;
    },
    paperStyle() {
      return {
        "z-index": this.zIndex,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.paper {
  width: 100%;
  height: 100%;
  position: relative;
}
.paper-primary {
  background-color: $mt-bg-primary;
}
.paper-secondary {
  background-color: $mt-bg-secondary;
}
.paper-tertiary {
  background-color: $mt-bg-tertiary;
}
.paper-quaternary {
  background-color: $mt-bg-quaternary;
}
.paper-quinary {
  background-color: $mt-bg-quinary;
}
.paper-senary {
  background-color: $mt-bg-senary;
}
</style>
