<template>
  <div class="columns has-text-centered">
    <div v-for="(content, key) in contents" :key="key" class="column">
      <figure class="image is-1by1">
        <img :src="require(`~/assets/img/${content.imageSrc}`)" :alt="content.imageAlt" />
      </figure>
      <div>
        {{ content.text }}
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
