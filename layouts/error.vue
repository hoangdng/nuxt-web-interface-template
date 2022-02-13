<template>
  <div class="is-flex is-flex-direction-column is-align-items-center my-6 py-6">
    <div class="p-4">
      <img
        src="https://ananas.vn/wp-content/themes/ananas/fe-assets/images/page_not_found.png"
        alt="Error!!! Page not found!"
      />
    </div>
    <div class="p-4">
      <b-button
        tag="nuxt-link"
        to="/"
        type="is-primary"
        size="is-large"
      >
        <p class="is-uppercase has-text-weight-bold">
          Quay lại trang chủ
        </p>
      </b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ErrorPage"
}
</script>

<style lang="scss" scoped>
img {
  max-height: 200px;
  width: auto;
}
</style>
