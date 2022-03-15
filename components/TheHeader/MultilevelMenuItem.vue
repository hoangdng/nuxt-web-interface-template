<template>
  <div>
    <li v-if="!hasChildren">
      <a :href="menuLink">{{ item.text }}</a>
    </li>
    <template v-else>
      <li class="level is-mobile my-0" @click="openSubmenu">
        <div class="level-left">
          <div class="level-item">
            {{ item.text }}
          </div>
        </div>
        <div class="level-right">
          <b-icon icon="menu-right" size="is-medium" />
        </div>
      </li>
      <div
        class="header-mobile-dropdown-sublist"
        :class="isOpenSubmenu ? 'is-open' : ''"
      >
        <li class="level is-mobile my-0" @click="openSubmenu">
          <div class="level-left">
            <div class="level-item">
              <b-icon icon="menu-left" size="is-medium" />
            </div>
          </div>
          <div class="level-item">
            <span v-if="hasParentTitle">
              {{  parentTitle }} |
            </span>
            {{ item.text }}
          </div>
        </li>
        <MultilevelMenuItem
          v-for="(menuItem, key) in item.contents"
          :key="key"
          :item="menuItem"
          :parent-title="item.text"
        />
      </div>
    </template>
  </div>
</template>

<script>
export default {
  name: 'MultilevelMenuItem',
  props: {
    item: {
      required: true,
      type: Object,
    },
    parentTitle: {
      required: false,
      type: String,
      default: ""
    }
  },
  data() {
    return {
      isOpenSubmenu: false,
    }
  },
  computed: {
    menuLink() {
      return this.item.link ?? '#';
    },
    hasChildren() {
      return this.item.contents && this.item.contents.length > 0;
    },
    hasParentTitle() {
      return this.parentTitle && this.parentTitle.length > 0;
    }
  },
  methods: {
    openSubmenu() {
      this.isOpenSubmenu = !this.isOpenSubmenu;
    },
  },
}
</script>

<style scoped></style>
