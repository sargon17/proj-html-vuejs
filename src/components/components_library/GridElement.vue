<template>
  <div class="grid" :class="gridClasses">
    <div
      v-for="n in parseInt(grids)"
      class="grid-element"
      :key="n"
      :class="gridElementClasses"
      :style="gridElementStyles"
    >
      <slot
        :name="`element-${order === 'normal' ? n : parseInt(grids) + 1 - n}`"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "GridElement",
  props: {
    subdivision: {
      type: String,
      default: "auto",
    },
    grids: {
      type: String,
      default: "2",
    },
    spacing: {
      type: String,
      default: "0",
    },
    align: {
      type: String,
      default: "center",
    },
    order: {
      type: String,
      default: "normal",
    },
  },

  computed: {
    gridElementClasses() {
      return {
        "grid-element-2": this.grids === "2",
        "grid-element-3": this.grids === "3",
        "grid-element-4": this.grids === "4",
        "grid-element-5": this.grids === "5",
        "grid-element-6": this.grids === "6",
        "grid-element-7": this.grids === "7",
        "grid-element-8": this.grids === "8",
        "grid-element-9": this.grids === "9",
        "grid-element-10": this.grids === "10",
        "grid-element-11": this.grids === "11",
        "grid-element-12": this.grids === "12",
      };
    },
    gridClasses() {
      return {
        "grid-center": this.align === "center",
        "grid-left": this.align === "left",
        "grid-right": this.align === "right",
        "grid-space-between": this.spacing === "between",
        "grid-space-around": this.spacing === "around",
        "grid-space-evenly": this.spacing === "evenly",
      };
    },
    gridElementStyles() {
      return {
        padding: `0 ${this.spacing / 2}px`,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  width: 100%;
}
.grid-center {
  justify-content: center;
}
.grid-left {
  justify-content: flex-start;
}
.grid-right {
  justify-content: flex-end;
}
.grid-space-between {
  justify-content: space-between;
}
.grid-space-around {
  justify-content: space-around;
}
.grid-space-evenly {
  justify-content: space-evenly;
}

.grid-element {
  width: 100%;
  max-width: $mt-screen-xl;
  margin: 0 auto;
  display: flex;
  align-items: stretch;
  justify-content: center;
  align-content: stretch;
}
.grid-element-2 {
  width: calc(100% / 2);
}
.grid-element-3 {
  width: calc(100% / 3);
}
.grid-element-4 {
  width: calc(100% / 4);
}
.grid-element-5 {
  width: calc(100% / 5);
}
.grid-element-6 {
  width: calc(100% / 6);
}
.grid-element-7 {
  width: calc(100% / 7);
}
.grid-element-8 {
  width: calc(100% / 8);
}
.grid-element-9 {
  width: calc(100% / 9);
}
.grid-element-10 {
  width: calc(100% / 10);
}
.grid-element-11 {
  width: calc(100% / 11);
}
.grid-element-12 {
  width: calc(100% / 12);
}
</style>
