<template>
  <div>
    <TopHeader />
    <MiddleHeader />
    <BottomHeader />
  </div>
</template>

<script>
import TopHeader from "~/components/TheHeader/TopHeader";
import MiddleHeader from "~/components/TheHeader/MiddleHeader";
import BottomHeader from "~/components/TheHeader/BottomHeader";

export default {
  name: "TheHeader",
  components: { TopHeader, MiddleHeader, BottomHeader }
};
</script>
