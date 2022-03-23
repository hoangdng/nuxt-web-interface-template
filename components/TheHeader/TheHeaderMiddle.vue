<template>
  <nav class="header-middle columns mx-6 my-0 py-4">
    <div class="column is-1 is-flex is-flex-direction-column is-justify-content-center">
      <img src="~/assets/img/brand-logo.svg" width="50px" />
    </div>
    <div class="column is-flex is-flex-direction-column is-justify-content-center">
      <div class="is-flex is-flex-direction-row is-justify-content-center has-text-weight-bold is-size-5 has-text-black is-align-items-baseline">
        <template v-for="(menuItem, key) in menuList">
          <TheHeaderMiddleMenuItem
            :key="key"
            :menu-item="menuItem"
            :menu-footer="menuFooter"
          />
          <div v-if="key != menuList.length - 1" :key="`divider-${key}`" class="menu-item-divider" />
        </template>
      </div>
    </div>
    <div class="column is-3-desktop is-2-widescreen p-0 is-flex is-flex-direction-column is-justify-content-center">
      <b-field>
        <b-input
          placeholder="Tìm kiếm"
          type="search"
          icon="magnify"
          icon-clickable
        >
        </b-input>
      </b-field>
    </div>
  </nav>
</template>

<script>
import TheHeaderMiddleMenuItem from '~/components/TheHeader/TheHeaderMiddleMenuItem';

export default {
  name: 'TheHeaderMiddle',
  components: { TheHeaderMiddleMenuItem },
  props: {
    menuList: {
      required: true,
      type: Array
    },
    menuFooter: {
      required: true,
      type: Object
    }
  }
}
</script>

<style scoped lang="scss">
.has-text-black {
  color: #000000;
}
</style>

<style lang="scss">
.menu-item-divider {
  border-right: #e3e2e2 2px solid;
  height: 23px;
}

.header-middle {
  @include touch {
    display: none !important;
  }
}
</style>
