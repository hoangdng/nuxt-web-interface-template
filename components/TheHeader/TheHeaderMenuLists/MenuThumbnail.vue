<template>
  <div class="columns">
    <div v-for="(content, key) in contents" :key="key" class="column mt-5">
      <div class="menu-thumbnail">
        <figure class="image is-260x260">
          <img :src="require(`~/assets/img/${content.imageSrc}`)" :alt="content.imageAlt" />
        </figure>
        <div class="has-text-semibold is-size-5 mt-4 menu-thumbnail-text">
          {{ content.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuThumbnail",
  props: {
    contents: {
      required: true,
      type: Array
    }
  }
};
</script>

<style lang="scss" scoped>
.menu-thumbnail {
  display: flex;
  flex-direction: column;
  align-items: center;
  opacity: 0.5;
  cursor: pointer;
  transition: 0.2s ease-in-out;

  &:hover {
    opacity: 1;
  }

  &-text {
    color: $info;

    &:hover {
    color: $primary;
    }
  }
}
</style>
