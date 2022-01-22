<template>
  <div>
    <TopHeading />
    <MiddleHeading />
    <BottomHeading />
  </div>
</template>

<script>
import TopHeading from "~/components/TheHeading/TopHeading";
import MiddleHeading from "~/components/TheHeading/MiddleHeading";
import BottomHeading from "~/components/TheHeading/BottomHeading";

export default {
  name: "TheHeading",
  components: { TopHeading, MiddleHeading, BottomHeading }
};
</script>
