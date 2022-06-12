<template>
  <section class="section">
    <ProductCategories />
    <ListBestSeller />
    <SocialAndNews />
  </section>
</template>

<script>
import ListBestSeller from "~/components/HomePage/ListBestSeller";
import ProductCategories from "~/components/HomePage/ProductCategories";
import SocialAndNews from "~/components/HomePage/SocialAndNews";

export default {
  name: "IndexPage",
  components: {
    ListBestSeller,
    ProductCategories,
    SocialAndNews
  },
}
</script>
