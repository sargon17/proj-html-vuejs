<template>
  <div class="tag">
    <p>
      <font-awesome-icon :icon="content.icon" />
      {{ content.title }}
      <span :class="infoClasses">
        {{ content.info }}
      </span>
    </p>
  </div>
</template>

<script>
export default {
  name: "InfoTagElement",
  props: {
    content: {
      type: Object,
      required: true,
    },
  },
  computed: {
    infoClasses() {
      return {
        "info-bold": this.content.isInfoBold,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";

.tag {
  margin-bottom: 10px;
}

.info-bold {
  font-weight: $mt-font-weight-bold;
}
</style>
