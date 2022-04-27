<template>
  <div class="paper" :class="styleVariantClass">
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
  },
  computed: {
    styleVariantClass() {
      return `paper-${this.styleVariant}`;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.paper {
  width: 100%;
  height: 100%;
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
