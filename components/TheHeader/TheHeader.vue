<template>
  <div>
    <TopHeader />
    <MiddleHeader />
    <BottomHeader />
  </div>
</template>

<script>
import TopHeader from "~/components/TheHeader/TheHeaderTop";
import MiddleHeader from "~/components/TheHeader/TheHeaderMiddle";
import BottomHeader from "~/components/TheHeader/TheHeaderBottom";

export default {
  name: "TheHeader",
  components: { TopHeader, MiddleHeader, BottomHeader }
};
</script>
