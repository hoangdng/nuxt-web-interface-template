<template>
  <a class="menu-item" :href="menuItem.link">
    <b-dropdown
      v-if="menuItem.type === 'menu'"
      ref="dropdown"
      aria-role="list"
      @mouseenter="onMouseOverHandler"
      @mouseleave="onMouseOverHandler"
      @active-change="onActiveChangeHandler"
    >
      <template #trigger>
        <div aria-haspopup="true" aria-controls="dropdown-menu">
          {{ menuItem.text }}
          <b-icon custom-size="mdi-20px" :icon="menuDropdownIcon"></b-icon>
        </div>
      </template>

      <b-dropdown-item aria-role="listitem" custom>
        <div class="container">
          <MenuThumbnail
            v-if="menuItem.menuType === 'thumbnail'"
            :contents="menuItem.contents"
          />
          <MenuList v-else />
          <div v-if="menuFooter" class="menu-footer has-text-centered">
            <a :href="menuFooter.link">{{ menuFooter.text }}</a>
          </div>
        </div>
      </b-dropdown-item>
    </b-dropdown>

    <span v-else-if="menuItem.type === 'text'" :href="menuItem.link">{{
      menuItem.text
    }}</span>

    <figure v-else class="image">
      <img :src="require(`~/assets/img/${menuItem.imageSrc}`)" />
    </figure>
  </a>
</template>

<script>
import MenuThumbnail from '~/components/TheHeading/TheHeadingMenuLists/MenuThumbnail'
import MenuList from '~/components/TheHeading/TheHeadingMenuLists/MenuList'

export default {
  name: 'MiddleHeadingMenuItem',
  components: { MenuThumbnail, MenuList },
  props: {
    menuItem: {
      required: true,
      type: Object,
    },
    menuFooter: {
      required: false,
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      menuDropdownIcon: 'chevron-down',
      dropdownMenuWidth: 0.999,
    }
  },
  methods: {
    onMouseOverHandler() {
      if (this.menuDropdownIcon === 'chevron-down') {
        this.menuDropdownIcon = 'chevron-up'
      } else {
        this.menuDropdownIcon = 'chevron-down'
      }
    },
    onActiveChangeHandler(value) {
      if (!value) return
      const dropdown = this.$refs.dropdown
      const dropdownMenu = this.$refs.dropdown?.$refs.dropdownMenu

      if (dropdown && dropdownMenu) {
        const bodyWidth = document.body.clientWidth

        const dropdownRect = dropdown.$el.getBoundingClientRect()
        dropdownMenu.style.width = `calc(${bodyWidth}px * ${this.dropdownMenuWidth})`
        dropdownMenu.style.left = `calc(${-dropdownRect.left}px + ${bodyWidth}px * ${
          (1 - this.dropdownMenuWidth) / 2
        })`
      }
    },
  },
}
</script>

<style scoped>
.menu-item {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  margin-left: 0.75rem !important;
  margin-right: 0.75rem !important;
}
</style>
