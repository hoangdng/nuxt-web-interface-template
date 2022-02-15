<template>
  <div>
    <template v-if="isMobileOrTablet">
      <TheHeaderTopMobile />
    </template>
    <template v-else>
      <TheHeaderTop />
      <TheHeaderMiddle />
    </template>
    <TheHeaderBottom />
  </div>
</template>

<script>
import TheHeaderTop from "~/components/TheHeader/TheHeaderTop";
import TheHeaderMiddle from "~/components/TheHeader/TheHeaderMiddle";
import TheHeaderBottom from "~/components/TheHeader/TheHeaderBottom";
import TheHeaderTopMobile from "~/components/TheHeader/TheHeaderTopMobile";

export default {
  name: "TheHeader",
  components: { TheHeaderTopMobile, TheHeaderTop, TheHeaderMiddle, TheHeaderBottom },
  data() {
    return {
      isMobileOrTablet: false
    };
  },
  mounted() {
    this.onResizeHandler();
    window.addEventListener("resize", this.onResizeHandler);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResizeHandler);
  },
  methods: {
    onResizeHandler() {
      if (window.innerWidth < 1024) {
        this.isMobileOrTablet = true;
      } else {
        this.isMobileOrTablet = false;
      }
    }
  }
};
</script>
