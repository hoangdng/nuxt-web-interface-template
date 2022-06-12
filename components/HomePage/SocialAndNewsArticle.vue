<template>
  <div class="column is-half">
    <div>
      <nuxt-link :to="`/articles/${title}`">
        <b-image :src="thumbnailUrl" ratio="16by9"/>
        <h2 class="is-uppercase is-size-5 is-size-6-touch has-text-weight-bold my-2">
          {{ title }}
        </h2>
      </nuxt-link>
      <p>{{ content }}</p>
      <nuxt-link :to="`/articles/${title}`">
        <h4 class="has-text-primary is-italic has-text-weight-semibold has-text-right mx-4">
          Đọc thêm
        </h4>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "SocialAndNewsArticle",
  props: {
    thumbnailUrl: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
p {
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

a {
  color: black;
}

figure:hover {
  transform: scale(1.02);
  transition: all 0.3s;
}

h2:hover {
  color: $primary;
}
</style>
