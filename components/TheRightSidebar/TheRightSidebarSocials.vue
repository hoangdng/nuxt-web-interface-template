<template>
  <section class="socials-fixed p-2">
    <div class="my-1">
      <a :href="`https://www.facebook.com/${facebookProfileUrl}`" target="_blank">
        <b-icon icon="facebook"/>
      </a>
    </div>
    <div>
      <a :href="`https://www.instagram.com/${instagramProfileUrl}`" target="_blank">
        <b-icon icon="instagram"/>
      </a>
    </div>
    <div>
      <a :href="`https://www.youtube.com/${youtubeChannelUrl}`" target="_blank">
        <b-icon icon="youtube"/>
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: "TheRightSidebarSocials",
  data() {
    return {
      facebookProfileUrl: "",
      instagramProfileUrl: "",
      youtubeChannelUrl: ""
    }
  }
}
</script>

<style lang="scss" scoped>
@import "assets/customized-buefy.scss";

a {
  color: $grey-light;
}

.socials-fixed {
  height: auto;
  width: auto;
  background-color: $grey;
  color: $grey-light;
  position: fixed;
  right: 0;
  top: 45%;
  z-index: 9999;
}
</style>
