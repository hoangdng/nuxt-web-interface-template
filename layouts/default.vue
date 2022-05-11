<template>
  <div>
    <TheHeader />
    <TheRightSidebar />
    <Nuxt />
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader/TheHeader'
import TheRightSidebar from '~/components/TheRightSidebar/TheRightSidebar'
import TheFooter from '~/components/TheFooter'

export default {
  name: 'DefaultLayout',
  components: { TheHeader, TheRightSidebar, TheFooter }
}
</script>