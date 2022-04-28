<template>
  <button :class="buttonClass">
    <div v-if="icon" class="icon">
      <img-element :src="icon" :maxWidth="'100%'" />
    </div>
    <slot></slot>
  </button>
</template>

<script>
import ImgElement from "./ImgElement.vue";
export default {
  name: "ButtonElement",
  components: {
    ImgElement,
  },
  props: {
    size: {
      type: String,
      default: "lg",
    },
    variant: {
      type: String,
      default: "primary",
    },
    caps: {
      type: Boolean,
      default: false,
    },
    boxShadow: {
      type: Boolean,
      default: false,
    },
    icon: {
      type: String,
      default: "",
    },
    outlined: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    buttonClass() {
      if (this.icon) {
        return {
          btn: true,
          [`btn-${this.size}-inner`]: true,
          [`btn-${this.variant}`]: true,
          "btn-caps": this.caps,
          "btn-shadow": this.boxShadow,
          "btn-outlined": this.outlined,
        };
      }

      return {
        btn: true,
        [`btn-${this.size}`]: true,
        [`btn-${this.variant}`]: true,
        "btn-caps": this.caps,
        "btn-shadow": this.boxShadow,
        "btn-outlined": this.outlined,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.btn {
  padding: 1.3rem 3rem;
  border: none;
  border-radius: 500px;
  font-size: 0.9rem;
  font-weight: 700;
  line-height: 1.5;
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  outline: none;
  margin: 1px;
}

// styles for button variants
.btn-primary {
  background-color: $mt-btn-primary-bg;
  color: $mt-btn-primary-color;
  &:hover {
    background-color: $mt-btn-primary-bg-hover;
    color: $mt-btn-primary-color-hover;
  }
}
.btn-secondary {
  background-color: $mt-btn-secondary-bg;
  color: $mt-btn-secondary-color;
  &:hover {
    background-color: $mt-btn-secondary-bg-hover;
    color: $mt-btn-secondary-color-hover;
  }
}
.btn-tertiary {
  background-color: $mt-btn-tertiary-bg;
  color: $mt-btn-tertiary-color;
  &:hover {
    background-color: $mt-btn-tertiary-bg-hover;
    color: $mt-btn-tertiary-color-hover;
  }
}
.btn-fourth {
  background-color: $mt-btn-fourth-bg;
  color: $mt-btn-fourth-color;
  &:hover {
    background-color: $mt-btn-fourth-bg-hover;
    color: $mt-btn-fourth-color-hover;
  }
}

// styles for button sizes
.btn-lg {
  padding: $mt-btn-lg;
}
.btn-md {
  padding: $mt-btn-md;
}
.btn-sm {
  padding: $mt-btn-sm;
}
.btn-xs {
  padding: $mt-btn-xs;
}
.btn-icon {
  padding: $mt-btn-icon;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: $mt-border-radius-round;
}
.btn-icon-inner {
  border-radius: $mt-border-radius-round;
  padding: 0;
  display: block;
  width: 50px;
  height: 50px;
  // display: flex;
  // justify-content: center;
  // align-items: center;
  position: relative;

  & > .icon {
    position: absolute;
    top: 55%;
    left: 50%;
    transform: translate(-50%, -50%);
    margin: auto;
  }
}

.btn-outlined {
  background-color: transparent;
  color: $mt-btn-secondary-color;
  border: 1px solid $mt-bg-tertiary;
  &:hover {
    background-color: $mt-bg-tertiary;
    color: $mt-btn-primary-bg;
  }
}

// text styling
.btn-caps {
  text-transform: uppercase;
}

.btn-shadow {
  box-shadow: $mt-shadow-default;
}
</style>
