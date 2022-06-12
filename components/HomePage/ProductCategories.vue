<template>
  <div>
    <h1
      class="has-text-centered
      has-text-black
      has-text-weight-bold
      is-uppercase
      is-size-4
      mb-5">
      Danh mục mua hàng
    </h1>
    <div class="columns is-variable is-2">
      <CategoryPane
        v-for="(category, index) in productCategories"
        :key="index"
        :bg-image-url="category.bgImageUrl"
        :category-name="category.categoryName"
        :sub-categories="category.subCategories"
      />
    </div>
  </div>
</template>

<script>
import CategoryPane from "~/components/HomePage/CategoryPane";

export default {
  name: "ProductCategories",
  components: {CategoryPane},
  data() {
    return {
      productCategories: [
        {
          bgImageUrl: "https://ananas.vn/wp-content/uploads/catalogy-1.jpg",
          categoryName: "Giày nam",
          subCategories: ["New arrivals", "Best sellers", "Sale off"]
        },
        {
          bgImageUrl: "https://ananas.vn/wp-content/uploads/catalogy-2.jpg",
          categoryName: "Giày nữ",
          subCategories: ["New arrivals", "Best sellers", "Sale off"]
        },
        {
          bgImageUrl: "https://ananas.vn/wp-content/uploads/catalogy-3.jpg",
          categoryName: "Dòng sản phẩm",
          subCategories: ["Basas", "Vintas", "Urbas", "Pattas"]
        }
      ]
    }
  }
}
</script>
