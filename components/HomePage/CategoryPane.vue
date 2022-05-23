<template>
  <div class="column is-relative">
    <img :src="bgImageUrl" alt="product category">
    <div class="middle-text has-text-centered has-text-white has-text-weight-bold">
      <p class="is-uppercase is-underlined is-size-5 mb-4">
        <a href="#">{{ categoryName }}</a>
      </p>
      <p
        v-for="(item, index) in subCategories" :key="index"
        class="is-size-6 my-2"
      >
        <a href="#">{{ item }}</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "CategoryPane",
  props: {
    bgImageUrl: {
      type: String,
      required: true
    },
    categoryName: {
      type: String,
      required: true
    },
    subCategories: {
      type: Array,
      default() {
        return [];
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.middle-text {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  top: 17%;
  left: 0;
  right: 0;
}

img {
  filter: brightness(76%);
  display: block;
  margin-left: auto;
  margin-right: auto;
}

a {
  color: inherit;

  &:hover {
    color: $primary;
  }
}
</style>
