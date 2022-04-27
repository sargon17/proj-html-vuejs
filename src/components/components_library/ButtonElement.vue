<template>
  <button :class="buttonClass">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "ButtonElement",
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
  },
  computed: {
    buttonClass() {
      return {
        btn: true,
        [`btn-${this.size}`]: true,
        [`btn-${this.variant}`]: true,
        "btn-caps": this.caps,
        "btn-shadow": this.boxShadow,
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

// text styling
.btn-caps {
  text-transform: uppercase;
}

.btn-shadow {
  box-shadow: $mt-shadow-default;
}
</style>
