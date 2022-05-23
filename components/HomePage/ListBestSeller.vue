<template>
  <div class="is-hidden-mobile px-5">
    <h1
      class="
        has-text-weight-bold
        has-text-black
        is-uppercase
        is-size-4
        has-text-centered
        mb-4
    ">
      Best seller
    </h1>
    <b-carousel-list
      v-model="test"
      :data="items"
      :items-to-show="4"
      repeat
      icon-size="is-large"
    >
      <template #item="list">
        <nuxt-link :to="`products/${list.name}`">
          <div class="card">
            <div class="card-image">
              <figure class="image is-1by1">
                <a @click="info(list.index)"><img :src="list.image" alt="product image"></a>
              </figure>
            </div>
            <div class="card-content">
              <div class="content has-text-centered">
                <p class="title has-text-weight-bold is-size-6">
                  {{ list.name }}
                </p>
                <p class="is-size-6">
                  {{ list.characteristic }}
                </p>
                <p class="is-size-6 has-text-weight-bold">
                  {{ list.currentPrice }}
                  <span class="has-text-weight-normal has-text-grey ml-3">{{ list.basePrice }}</span>
                </p>
              </div>
            </div>
          </div>
        </nuxt-link>
      </template>
    </b-carousel-list>
  </div>
</template>

<script>
export default {
  name: "ListBestSeller",
  data() {
    return {
      test: 0,
      items: [
        {
          name: 'Basas Mono Black - Slip On',
          characteristic: 'All Black',
          image: 'https://ananas.vn/wp-content/uploads/stu_basas_A61022_1-500x500.jpg',
          currentPrice: '320.000 VND',
          basePrice: '420.000 VND'
        },
        {
          name: 'Basas New Familiar - Low Top',
          characteristic: 'Light Grey',
          image: 'https://ananas.vn/wp-content/uploads/stu_basas_A61015_11-500x500.jpg',
          currentPrice: '420.000 VND',
        },
        {
          name: 'Basas Mono Black - Low Top',
          characteristic: 'All Black',
          image: 'https://ananas.vn/wp-content/uploads/stu_basas_A61013_1-500x500.jpg',
          currentPrice: '420.000 VND',
        },
        {
          name: 'Basas New Simple Life - Low Top',
          characteristic: 'Life Grey',
          image: 'https://ananas.vn/wp-content/uploads/stu_basas_A61003_1-500x500.jpg',
          currentPrice: '320.000 VND',
          basePrice: '420.000 VND'
        },
        {
          name: 'Baseball Cap - Be Positive',
          characteristic: 'Pink',
          image: 'https://ananas.vn/wp-content/uploads/pro_ABC100_1-500x500.jpg',
          currentPrice: '275.000 VND'
        }
      ]
    }
  }
}
</script>

<style scoped>
.card {
  height: 100%;
  box-shadow: none;
}

span {
  text-decoration: line-through;
}
</style>
