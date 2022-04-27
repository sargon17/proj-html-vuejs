<template>
  <div class="grid">
    <div
      v-for="element in gridElements"
      class="grid-element"
      :key="element"
      :class="gridElementClasses"
    >
      <slot :name="`element-${element}`" />
    </div>
  </div>
</template>

<script>
export default {
  name: "GridElement",
  data() {
    return {
      gridElements: [],
    };
  },
  props: {
    subdivision: {
      type: String,
      default: "auto",
    },
    grids: {
      type: String,
      default: "2",
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
  },
  watch: {
    grids() {
      this.setGridElements();
    },
  },
  mounted() {
    this.setGridElements();
  },
  methods: {
    setGridElements() {
      this.gridElements = [];
      for (let i = 1; i <= parseInt(this.grdis); i++) {
        console.log(i);
        this.gridElements.push(i);
      }
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
.grid-element {
  width: 100%;
  max-width: $mt-screen-xl;
  margin: 0 auto;
  display: flex;
  align-items: center;
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
