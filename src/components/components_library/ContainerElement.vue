<template>
  <div class="container" :class="containerClasses" :style="containerStyles">
    <slot />
  </div>
</template>

<script>
export default {
  name: "ContainerElement",
  props: {
    contentPosition: {
      type: String,
      default: "center center",
    },
    height: {
      type: String,
      default: "auto",
    },
    width: {
      type: String,
      default: "auto",
    },
  },
  computed: {
    containerClasses() {
      let position = this.contentPosition.split(" ");
      return {
        "container-center": position[0] === "center",
        "container-left": position[0] === "left",
        "container-right": position[0] === "right",
        "container-top": position[1] === "top",
        "container-vCentre": position[1] === "center",
        "container-bottom": position[1] === "bottom",
      };
    },
    containerStyles() {
      return {
        height: this.height,
        width: this.width,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.container {
  padding: 20px;
  width: 100%;
  max-width: $mt-screen-lg;
  margin: 0 auto;
  display: flex;
  align-items: center;
}

// content position
.container-center {
  justify-content: center;
}
.container-left {
  justify-content: flex-start;
}
.container-right {
  justify-content: flex-end;
}
.container-top {
  align-items: flex-start;
}
.container-vCentre {
  align-items: center;
}
.container-bottom {
  align-items: flex-end;
}
</style>
