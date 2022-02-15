<template>
  <a
    class="menu-item"
    :href="menuItem.link"
    @mouseenter="onMouseEnterHandler"
    @mouseleave="onMouseLeaveHandler"
  >
    <b-dropdown
      v-if="menuItem.type === 'menu'"
      ref="dropdown"
      aria-role="list"
      :triggers="['hover']"
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
          <div v-if="menuFooter" class="menu-footer has-text-centered is-size-6 is-italic my-4">
            <a :href="menuFooter.link">
              <span v-html="menuFooter.text" />
            </a>
          </div>
        </div>
      </b-dropdown-item>
    </b-dropdown>

    <span v-else-if="menuItem.type === 'text'" :href="menuItem.link">
      {{ menuItem.text }}
    </span>

    <figure v-else class="image">
      <img :src="require(`~/assets/img/${menuItem.imageSrc}`)" />
    </figure>
  </a>
</template>

<script>
import MenuThumbnail from '~/components/TheHeader/TheHeaderMenuLists/MenuThumbnail'
import MenuList from '~/components/TheHeader/TheHeaderMenuLists/MenuList'

export default {
  name: 'MiddleHeaderMenuItem',
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
    onMouseEnterHandler() {
      this.menuDropdownIcon = 'chevron-up'
      this.calcDropdownMenuStyles()
    },
    onMouseLeaveHandler() {
      this.menuDropdownIcon = 'chevron-down'
    },
    calcDropdownMenuStyles() {
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

<style lang="scss" scoped>
.menu-item {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  margin-left: 0.75rem !important;
  margin-right: 0.75rem !important;
}

a {
  color: black !important;

  &:hover {
    color: $primary !important;
  }
}
</style>

<style lang="scss">
.menu-item {
  .dropdown-content {
    width: 100%;
    background: $dark;
    cursor: default;
  }
}

.menu-footer {
  a {
    color: #808080 !important;
  }

  &-highlight {
    color: white;
  }
}
</style>
