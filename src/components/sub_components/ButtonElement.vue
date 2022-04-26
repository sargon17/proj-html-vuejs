<template>
  <button :class="buttonClass">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "ButtonElement",
  props: {
    dimensions: {
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
  },
  computed: {
    buttonClass() {
      return `btn btn-${this.variant} btn-${this.dimensions} ${
        this.caps ? "btn-caps" : ""
      }`;
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

// styles for button sizes
.btn-lg {
  padding: 1.3rem 3rem;
}
.btn-md {
  padding: 1.3rem 2rem;
}
.btn-sm {
  padding: 0.8rem 1.5rem;
}

// text styling
.btn-caps {
  text-transform: uppercase;
}
</style>
