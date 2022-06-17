<template>
  <div>
    <TopBanner />
    <section class="section">
      <SpecialCollections />
      <ProductCategories />
      <ListBestSeller />
    </section>
    <div class="hero">
      <b-image class="image" src="https://ananas.vn/wp-content/uploads/Banner_Clothing.jpg" alt="ananas banner" />
    </div>
    <section class="section">
      <SocialAndNews />
    </section>
  </div>
</template>

<script>
import ListBestSeller from "~/components/HomePage/ListBestSeller";
import ProductCategories from "~/components/HomePage/ProductCategories";
import SocialAndNews from "~/components/HomePage/SocialAndNews";
import SpecialCollections from "~/components/HomePage/SpecialCollections";
import TopBanner from "~/components/HomePage/TopBanner";

export default {
  name: "IndexPage",
  components: {
    ListBestSeller,
    ProductCategories,
    SocialAndNews,
    SpecialCollections,
    TopBanner
  },
}
</script>
