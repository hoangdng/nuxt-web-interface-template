<template>
  <div>
    <TheHeader />

    <section class="main-content columns">
      <TheRightSidebar/>
      <aside class="column is-2 section">
        <p class="menu-label is-hidden-touch">General</p>
        <ul class="menu-list">
          <li v-for="(item, key) of items" :key="key">
            <NuxtLink :to="item.to" exact-active-class="is-active">
              <b-icon :icon="item.icon" /> {{ item.title }}
            </NuxtLink>
          </li>
        </ul>
      </aside>

      <div class="container column is-10 test">
        <Nuxt />
      </div>
    </section>
  </div>
</template>

<script>
import TheHeader from "~/components/TheHeader/TheHeader";
export default {
  name: 'DefaultLayout',
  components: { TheHeader },
  data() {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' },
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' },
        },
      ],
    }
  },
}
</script>

<style>
.test{
  height: 1000px;
}
</style>
