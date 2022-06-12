<template>
  <section class="section">
    <ProductCategories />
    <ListBestSeller />
  </section>
</template>

<script>
import ListBestSeller from "~/components/HomePage/ListBestSeller";
import ProductCategories from "~/components/HomePage/ProductCategories";

export default {
  name: "IndexPage",
  components: {
    ListBestSeller,
    ProductCategories
  },
}
</script>
