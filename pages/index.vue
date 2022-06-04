<template>
  <section>
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

    <div class="container">
      <div class="columns is-variable is-5 m-6">
        <div class="column">
          <div class="card">
            <div class="card-image">
              <b-image
                class="image"
                src="https://ananas.vn/wp-content/uploads/banner-phụ_2m-600x320.jpg"
              />
            </div>
            <div class="card-content">
              <div class="media">
                <div class="media-content">
                  <p class="title is-4">ALL BLACK IN BLACK</p>
                </div>
              </div>

              <div class="content">
                <p>Mặc dù được ứng dụng rất nhiều, nhưng sắc đen lúc nào cũng toát lên một vẻ huyền bí không nhàm chán</p>
              </div>
            </div>
          </div>
        </div>
        <div class="column">
          <div class="card">
            <div class="card-image">
              <b-image
                class="image"
                src="https://ananas.vn/wp-content/uploads/Banner_Sale-off-1.jpg"
              />
            </div>
            <div class="card-content">
              <div class="media">
                <div class="media-content">
                  <p class="title is-4">OUTLET SALE</p>
                </div>
              </div>

              <div class="content">
                Danh mục những sản phẩm bán tại "giá tốt hơn" chỉ được bán kênh online - Online Only, chúng đã từng làm mưa làm gió một thời gian và hiện đang rơi vào tình trạng bể size, bể số.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'IndexPage',
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
  },
}
</script>
