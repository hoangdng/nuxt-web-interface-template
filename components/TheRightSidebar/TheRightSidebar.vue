<template>
  <div class="hide-in-tablet-screen">
    <TheRightSidebarCart/>
    <TheRightSidebarSocials/>
  </div>
</template>

<script>
export default {
  name: "TheRightSidebar"
}
</script>

<style scoped>
@media only screen and (max-width: 768px) {
  .hide-in-tablet-screen {
    display: none;
  }
}
</style>
