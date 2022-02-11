<template>
  <nav class="level mx-6 my-0 py-4">
    <div class="level-left">
      <figure class="image ml-6 pl-6">
        <img src="~/assets/img/brand-logo.svg" />
      </figure>
    </div>
    <div class="level-item has-text-weight-bold is-size-5 has-text-black">
      <b-dropdown
        :append-to-body="true"
        aria-role="menu"
        scrollable
        max-height="200"
        trap-focus
        @mouseenter="onMouseOverHandler"
        @mouseleave="onMouseOverHandler"
      >
        <template #trigger>
          <div aria-haspopup="true" aria-controls="dropdown-menu">
            SẢN PHẨM
            <b-icon custom-size="mdi-20px" :icon="menuDropdownIcon"></b-icon>
          </div>
        </template>

        <b-dropdown-item aria-role="listitem" expanded>Action</b-dropdown-item>
        <b-dropdown-item aria-role="listitem">Another action</b-dropdown-item>
        <b-dropdown-item aria-role="listitem">Something else</b-dropdown-item>
      </b-dropdown>
      <div
        class="dropdown is-active"
        @mouseenter="onMouseOverHandler"
        @mouseleave="onMouseOverHandler"
      >
        <div class="dropdown-trigger">
          <div aria-haspopup="true" aria-controls="dropdown-menu">
            SẢN PHẨM
            <b-icon custom-size="mdi-20px" :icon="menuDropdownIcon"></b-icon>
          </div>
        </div>
        <div id="dropdown-menu" class="dropdown-menu" role="menu">
          <div class="dropdown-content" style="width: 98vw;">
            <div class="container is-fluid">
              <div class="columns">
                <div class="column">
                  <h1 class="title is-6 is-mega-menu-title">Sub Menu Title</h1>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                </div>
                <div class="column">
                  <h1 class="title is-6 is-mega-menu-title">Sub Menu Title</h1>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                  <a href="/documentation/overview/start/">
                    Overview
                  </a>
                  <a href="http://bulma.io/documentation/modifiers/syntax/">
                    Modifiers
                  </a>
                  <a href="http://bulma.io/documentation/columns/basics/">
                    Columns
                  </a>
                </div>
                <div class="column">
                  <h1 class="title is-6 is-mega-menu-title">Sub Menu Title</h1>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>
                  <a href="/2017/08/03/list-of-tags/">
                    <p>
                      <small class="has-text-info">03 Aug 2017</small>
                    </p>
                    <p>New feature: list of tags</p>
                  </a>

                </div>
                <div class="column">
                  <h1 class="title is-6 is-mega-menu-title">Sub Menu Title</h1>
                  <a href="/documentation/overview/start/">
                    Overview
                  </a>
                  <a href="http://bulma.io/documentation/modifiers/syntax/">
                    Modifiers
                  </a>
                  <a href="http://bulma.io/documentation/columns/basics/">
                    Columns
                  </a>
                  <a href="http://bulma.io/documentation/layout/container/">
                    Layout
                  </a>
                </div>
              </div>
            </div>

            <hr class="navbar-divider">
            <div class="container is-fluid">
              <div class="level is-mobile">
                <div class="level-left">
                  <div class="level-item">
                    <strong>Stay up to date!</strong>
                  </div>
                </div>
                <div class="level-right">
                  <div class="level-item">
                    <a class="button bd-is-rss is-small" href="http://bulma.io/atom.xml">
                      <span class="icon is-small">
                        <i class="fa fa-rss"></i>
                      </span>
                      <span>Subscribe</span>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="navbar-item">
        <div>
          NAM
          <b-icon custom-size="mdi-20px" icon="chevron-down"></b-icon>
        </div>
      </div>
      <div class="navbar-item">
        <div>
          NỮ
          <b-icon custom-size="mdi-20px" icon="chevron-down"></b-icon>
        </div>
      </div>
      <div class="navbar-item">SALE OFF</div>
      <div class="navbar-item">
        <figure class="image">
          <img src="~/assets/img/discover-you.svg" />
        </figure>
      </div>
    </div>
    <div class="level-right">
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
export default {
  name: 'MiddleHeading',
  data() {
    return {
      menuDropdownIcon: 'chevron-down',
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
  },
}
</script>

<style scoped lang="scss">
.navbar-item {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  margin-left: 0.75rem !important;
  margin-right: 0.75rem !important;
}

.has-text-black {
  color: #000000;
}

.is-mega {
  position: relative;

  &-menu-title {
    margin-bottom: 0;
    padding: 0.375rem 1rem;
  }
}
</style>
