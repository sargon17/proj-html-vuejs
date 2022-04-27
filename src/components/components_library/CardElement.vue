<template>
  <div>
    <div class="card">
      <PaperElement :styleVariant="'primary'">
        <ContainerElement :contentPosition="'center center'">
          <div>
            <h3 class="card-title">Coaching Sessions</h3>
            <p class="card-data">
              <font-awesome-icon icon="fa-solid fa-calendar-days" />
              24 Mar 18:00 PM
            </p>
            <p class="card-description">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit.
              Vestibulum eget nunc eget nunc tincidunt euismod.
            </p>
          </div>
        </ContainerElement>
      </PaperElement>
    </div>
    <div class="card-button">
      <ContainerElement :contentPosition="'center center'">
        <ButtonElement :variant="'fourth'" :size="'xs'" :boxShadow="true">
          <font-awesome-icon icon="fa-solid fa-plus" />
          Find More
        </ButtonElement>
      </ContainerElement>
    </div>
  </div>
</template>

<script>
import PaperElement from "./PaperElement.vue";
import ContainerElement from "./ContainerElement.vue";
import ButtonElement from "./ButtonElement.vue";

export default {
  name: "CardElement",
  components: {
    PaperElement,
    ContainerElement,
    ButtonElement,
  },
};
</script>

<style lang="scss" scoped>
@import "../../styles/general.scss";
.card {
  width: 100%;
  border-radius: $mt-border-radius-xl;
  overflow: hidden;
  text-align: center;

  &-title {
    font-size: $mt-font-size-sm;
    font-weight: $mt-font-weight-black;
    color: $mt-text-color;
    font-family: $mt-font-family-accent;
    padding: $mt-spacing-sm $mt-spacing-sm;
    margin-top: 20px;
  }
  &-data {
    font-size: $mt-font-size-xxs;
    font-weight: $mt-font-weight-regular;
    color: $mt-text-color-light;
    font-family: $mt-font-family;
    padding: $mt-spacing-sm $mt-spacing-sm;
  }
  &-description {
    font-size: $mt-font-size-xs;
    font-weight: $mt-font-weight-regular;
    line-height: 1.4rem;
    color: $mt-text-color-light;
    font-family: $mt-font-family;
    padding: $mt-spacing-sm $mt-spacing-sm;
    margin-bottom: 20px;
  }
  &-button {
    transform: translateY(-50%);
  }
}
</style>
