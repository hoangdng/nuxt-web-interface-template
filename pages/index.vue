<template>
  <div>
    <TopBanner />
    <section class="section">
      <SpecialCollections />
      <ProductCategories />
      <ListBestSeller />
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
