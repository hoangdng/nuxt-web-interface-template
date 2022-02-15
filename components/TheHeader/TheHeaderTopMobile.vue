<template>
  <nav class="header-mobile" role="navigation" aria-label="navigation">
    <div class="header-mobile-brand">
      <a class="header-mobile-item" href="#">
        <img src="~/assets/img/brand-logo.svg" alt="brand logo" />
      </a>
    </div>
    <div class="header-mobile-center">
      <a class="header-mobile-item" href="#">
        <img src="~/assets/img/mb-search.png" alt="order-tracking" />
      </a>
      <a class="header-mobile-item" href="#">
        <img src="~/assets/img/mb-location.png" alt="order-tracking" />
      </a>
      <a class="header-mobile-item" href="#">
        <img src="~/assets/img/mb-cart.png" alt="order-tracking" />
      </a>
    </div>
    <div class="header-mobile-burger navbar-burger" :class="isNavbarBurgerActive? 'is-open' : ''" aria-label="menu" aria-expanded="false" @click="onNavbarBurgerClickHandler">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </div>
  </nav>
</template>

<script>
export default {
  name: "TheHeaderTopMobile",
  data() {
    return {
      isNavbarBurgerActive: false
    };
  },
  methods: {
    onNavbarBurgerClickHandler() {
      this.isNavbarBurgerActive = !this.isNavbarBurgerActive;
    }
  }
};
</script>

<style lang="scss">
$navbar-max-height: 110px;
$navbar-height: 15vw;
$header-mobile-item-padding: 8px;

.header-mobile {
  display: flex;
  flex-direction: row;
  justify-content: stretch;
  height: $navbar-height;
  max-height: $navbar-max-height;

  &-item {
    box-sizing: border-box;
    max-height: $navbar-max-height !important;
    padding: $header-mobile-item-padding !important;
  }

  &-burger {
    background: #4C4C4C !important;
    color: white !important;
    width: $navbar-height;
    height: $navbar-height;
    max-height: $navbar-max-height;
    max-width: $navbar-max-height;

    span {
      height: 2px;
      width: 40%;
      left: 30%;

      &:nth-child(1) {
        top: 40%;
      }

      &:nth-child(2), &:nth-child(3) {
        top: 50%;
      }

      &:nth-child(4) {
        top: 60%;
      }
    }

    &.is-open span {
      &:nth-child(1) {
        opacity: 0;
      }

      &:nth-child(2) {
        transform: rotate(45deg);
      }

      &:nth-child(3) {
        transform: rotate(-45deg);
      }

      &:nth-child(4) {
        opacity: 0;
      }
    }
  }

  &-brand {
    flex-grow: 3;
    display: inline-flex;
    justify-content: center;
    border-right: #f1f1f1 1px solid;

    img {
      width: 7vw !important;
      max-height: 100% !important;
    }
  }

  &-center {
    flex-grow: 7;
  }
}
</style>
