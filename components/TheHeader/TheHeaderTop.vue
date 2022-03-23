<template>
  <nav class="header-top level has-background-dark has-text-white is-size-7 px-6 py-1 m-0">
    <div class="level-left" />
    <div class="level-right">
      <TheHeaderTopMenuItem
        v-for="menuItem in functionalMenuList"
        :key="menuItem.key"
        class="level-item ml-3"
        :icon="menuItem.icon"
        :alt-text="menuItem.key"
        :title="menuItem.title"
        :link="menuItem.href"
        :is-show-number-badge="menuItem.isShowNumberBadge"
      />
    </div>
  </nav>
</template>

<script>
import TheHeaderTopMenuItem from '~/components/TheHeader/TheHeaderTopMenuItem'
export default {
  name: 'TheHeaderTop',
  components: { TheHeaderTopMenuItem },
  props: {
    functionalMenuList: {
      required: true,
      type: Array
    }
  }
}
</script>

<style lang="scss">
.header-top {
  @include touch {
    display: none !important;
  }
}
</style>
