<template>
  <div class="px-6 py-4 has-background-info">
    <b-carousel
      class="carousel-custom"
      animated="slide"
      :autoplay="true"
      icon-size="is-medium"
      :indicator="false"
      :interval="3000"
      :repeat="true"
      :pause-hover="false"
    >
      <b-carousel-item v-for="(content, key) in flashContents" :key="key">
        <section class="level">
          <div
            class="level-item is-size-6 is-uppercase is-italic has-text-weight-semibold has-text-centered my-1"
          >
            <span>{{ content.text }}</span>
          </div>
        </section>
      </b-carousel-item>
    </b-carousel>
  </div>
</template>

<script>
export default {
  name: 'TheHeaderBottom',
  props: {
    flashContents: {
      required: true,
      type: Array
    }
  }
}
</script>

<style lang="scss" scoped>
.carousel-custom {
  $padding: 3rem;
  min-height: auto !important;
  padding-left: $padding;
  padding-right: $padding;
}
</style>
