<template>
  <div class="hide-in-tablet-screen">
    <RightSidebarCart/>
    <RightSidebarSocials/>
  </div>
</template>

<script>
import RightSidebarCart from "~/components/TheRightSidebar/RightSidebarCart.vue";
import RightSidebarSocials from "~/components/TheRightSidebar/RightSidebarSocials.vue";

export default {
  name: "TheRightSidebar",
  components: {RightSidebarCart, RightSidebarSocials},
}
</script>

<style scoped>
@media only screen and (max-width: 768px) {
  .hide-in-tablet-screen {
    display: none;
  }
}
</style>
