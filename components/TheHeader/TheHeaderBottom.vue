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
      <b-carousel-item v-for="(carousel, i) in carousels" :key="i">
        <section class="level">
          <div
            class="level-item is-size-6 is-uppercase is-italic has-text-weight-semibold has-text-centered my-1"
          >
            <span>{{ carousel.title }}</span>
          </div>
        </section>
      </b-carousel-item>
    </b-carousel>
  </div>
</template>

<script>
export default {
  name: 'BottomHeader',
  data() {
    return {
      carousels: [
        { title: 'BUY 2 GET 10% OFF - ÁP DỤNG VỚI TẤT CẢ BASIC TEE' },
        { title: 'FREE SHIPPING VỚI HOÁ ĐƠN TỪ 800K !' },
        { title: 'BUY MORE PAY LESS - ÁP DỤNG KHI MUA PHỤ KIỆN' },
      ],
    }
  },
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
