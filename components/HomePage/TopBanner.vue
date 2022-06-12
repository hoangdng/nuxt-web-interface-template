<template>
  <section class="hero">
    <b-carousel
      :arrow="false"
      indicator-style="is-lines"
      :interval="3333"
      :repeat="true"
    >
      <b-carousel-item v-for="(carousel, i) in carousels" :key="i">
        <b-image class="image" :src="carousel.link" />
      </b-carousel-item>
    </b-carousel>
  </section>
</template>

<script>
export default {
  name: "TopBanner",
  data() {
    return {
      carousels: [
        {
          link: 'https://ananas.vn/wp-content/uploads/Flannel_1920x1050_desktop.jpeg',
        },
        {
          link: 'https://ananas.vn/wp-content/uploads/Hi-im-Mule_1920x1050-Desktop.jpg',
        },
        {
          link: 'https://ananas.vn/wp-content/uploads/Track-6_Suede_Moonphase_1920x1050.jpg',
        },
        {
          link: 'https://ananas.vn/wp-content/uploads/Vintas-Temperate_desktop.jpg',
        },
      ],
    }
  }
}
</script>
