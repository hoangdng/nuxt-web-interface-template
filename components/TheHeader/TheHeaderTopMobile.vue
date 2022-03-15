<template>
  <div>
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
          <span class="header-mobile-item-note">({{ goodsInCart }})</span>
        </a>
      </div>
      <div
        class="header-mobile-burger navbar-burger"
        :class="isNavbarBurgerActive ? 'is-open' : ''"
        aria-label="menu"
        aria-expanded="false"
        @click="onNavbarBurgerClickHandler"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </div>
    </nav>
    <div v-show="isNavbarBurgerActive" class="header-mobile-dropdown">
      <div class="header-mobile-dropdown-item header-mobile-dropdown-list">
        <MultilevelMenuItem v-for="(productMenuItem, key) in productMenuList" :key="key" :item="productMenuItem" />
      </div>
      <ul class="header-mobile-dropdown-item header-mobile-dropdown-functions">
        <li v-for="(functionMenu, key) in functionalMenuList" :key="key">
          <span class="icon mr-1">
            <img :src="functionMenu.icon" :alt="functionMenu.key" />
          </span>
          <span>{{ functionMenu.title }}</span>
        </li>
      </ul>
      <div class="header-mobile-dropdown-item menu-footer">
        <a :href="menuFooter.link">
          <span v-html="menuFooter.text" />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import MultilevelMenuItem from "~/components/TheHeader/MultilevelMenuItem";
export default {
  name: 'TheHeaderTopMobile',
  components: { MultilevelMenuItem },
  props: {
    productMenuList: {
      required: true,
      type: Array
    },
    functionalMenuList: {
      required: true,
      type: Array
    },
    menuFooter: {
      required: true,
      type: Object
    }
  },
  data() {
    return {
      isNavbarBurgerActive: false,
      goodsInCart: 0,
      isOpenSubmenu: false
    }
  },
  methods: {
    onNavbarBurgerClickHandler() {
      this.isNavbarBurgerActive = !this.isNavbarBurgerActive
    },
    openSubmenu() {
      this.isOpenSubmenu = !this.isOpenSubmenu;
    }
  },
}
</script>

<style lang="scss">
$navbar-min-height: 72px;
$navbar-max-height: 110px;
$navbar-height: 15vw;
$header-mobile-item-padding: 8px;

.header-mobile {
  @include desktop {
    display: none !important;
  }

  display: flex;
  flex-direction: row;
  justify-content: stretch;
  height: $navbar-height;
  max-height: $navbar-max-height;
  min-height: $navbar-min-height;

  &-item {
    display: flex;
    align-self: center;
    box-sizing: border-box;
    max-height: $navbar-max-height !important;
    padding: $header-mobile-item-padding !important;

    img {
      max-width: 47px !important;
    }

    &-note {
      align-self: end;
      font-size: 1.5rem;
      color: #4c4c4c;
    }
  }

  &-center &-item {
    margin-right: 2%;
  }

  &-burger {
    background: #4c4c4c !important;
    color: white !important;
    width: $navbar-height;
    height: $navbar-height;
    max-height: $navbar-max-height;
    min-height: $navbar-min-height;
    max-width: $navbar-max-height;
    border-bottom: #666666 1px solid;

    span {
      height: 2px;
      width: 40%;
      left: 30%;

      &:nth-child(1) {
        top: 40%;
      }

      &:nth-child(2),
      &:nth-child(3) {
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
  }

  &-brand &-item {
    img {
      max-height: 100% !important;
    }
  }

  img {
    width: 7vw !important;
    align-self: center;
  }

  &-center {
    flex-grow: 7;
    display: flex;
    justify-content: flex-end;
    align-content: center;
  }

  &-dropdown {
    z-index: 5;
    position: absolute;
    background: #4c4c4c;
    width: 100%;
    color: white;

    @include desktop {
      display: none !important;
    }

    &-functions {
      border-top: white 3px solid;
      border-bottom: white 3px solid;
    }

    &-item {
      font-size: 5vw;

      li {
        padding: 20px 30px;
        margin: 0;
      }
    }

    &-sublist {
      display: none;
      background-color: #4c4c4c;
      height: 100%;
      width: 100%;
      position: absolute;
      left: 0;
      top: 0;

      &.is-open {
        display: block;
      }
    }
  }
}
</style>
