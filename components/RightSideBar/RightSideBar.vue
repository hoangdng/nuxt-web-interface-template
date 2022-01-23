<template>
  <div class="hide-in-tablet-screen">
    <CartFixed/>
    <SocialsFixed/>
  </div>
</template>

<script>
import CartFixed from "@/components/RightSideBar/CartFixed.vue";
import SocialsFixed from "@/components/RightSideBar/SocialsFixed.vue";

export default {
  name: "RightSideBar",
  components: {CartFixed, SocialsFixed},
}
</script>

<style scoped>
@media only screen and (max-width: 768px) {
  .hide-in-tablet-screen {
    display: none;
  }
}
</style>
