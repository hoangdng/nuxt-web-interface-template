<template>
<div>
  <div class="columns is-justify-content-center mt-4 mb-5 is-size-6 has-text-weight-normal">
    <div v-for="(menuListItem, menuListItemKey) in menuList" :key="`menu-list-item-${menuListItemKey}`" class="column is-3 is-flex is-flex-direction-column">
      <div class="menu-list-title is-size-4 has-text-weight-bold">{{ menuListItem.text }}</div>

      <template v-for="(group, groupKey) in menuListItem.contents">
        <a :key="`group-key-${menuListItemKey}-${groupKey}`" class="menu-list-subtitle menu-list-item has-text-weight-bold mt-5" href="#">{{ group.text }}</a>
        <a v-for="(elem, elemKey) in group.contents" :key="`group-item-${menuListItemKey}-${groupKey}-${elemKey}`" class="menu-list-item" href="#">{{ elem.text }}</a>
      </template>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "MenuList",
  props: {
    menuList: {
      required: true,
      type: Array
    }
  },
  methods: {
    getLink(gender, category, attribute) {
      return `/product-list?gender=${gender}&amp;category=${category}&amp;attribute=${attribute}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.menu-list {
  &-column {
    width: 260px;
  }

  &-item {
    color : #CCCCCC !important;

    &:hover {
      color: $primary !important;
    }
  }

  &-title {
    color: white !important;
  }
}
</style>
