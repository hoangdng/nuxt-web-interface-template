<template>
  <!-- TODO: Give this component a valid URL to point to the product details page -->
  <nuxt-link :to="`/${itemName}`">
    <div class="columns has-text-black">
      <div class="column is-4">
        <b-image ratio="1by1" :src="itemImage" :placeholder="`Image of ${itemName}`"/>
      </div>
      <div class="column is-8">
        <div class="has-text-weight-bold is-size-7">
          <p class="mb-1">{{ itemName }}</p>
          <p>{{ itemPrice }}</p>
        </div>
        <div class="is-flex is-justify-content-space-between is-size-7">
          <p>Size:</p>
          <p>{{ itemSize }}</p>
        </div>
        <div class="is-flex is-justify-content-space-between is-size-7">
          <p>Số lượng:</p>
          <p>{{ itemQuantity }}</p>
        </div>
      </div>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "RightSidebarCartItem",
  props: {
    itemImage: {
      type: String,
      required: true,
      default: "https://via.placeholder.com/150"
    },
    itemName: {
      type: String,
      required: true,
      default: ""
    },
    itemPrice: {
      type: String,
      required: true,
      default: ""
    },
    itemSize: {
      type: Number,
      required: true,
      default: 0
    },
    itemQuantity: {
      type: Number,
      required: true,
      default: 0
    }
  }
}
</script>

