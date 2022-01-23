<template>
  <section class="cart-fixed p-2">
    <div @click="changeCartCollapseState">
      <p class="has-text-centered has-text-weight-bold">
        {{ totalItemsInCart }}
      </p>
      <b-icon class="pb-1" icon="shopping"/>
    </div>
    <div v-if="isCollapsedCartOpen" class="cart-collapse p-3">
      <div class="has-text-left has-text-weight-bold is-size-5">
        <p>Giỏ hàng ({{ totalItemsInCart }})</p>
      </div>
      <hr class="my-2"/>
      <div class="cart-items-box">
        <ItemInCartCollapse
          v-for="(item, index) in itemsInCart"
          :key="index"
          :item-image="item.itemImage"
          :item-name="item.itemName"
          :item-price="item.itemPrice"
          :item-size="item.itemSize"
          :item-quantity="item.itemQuantity"/>
      </div>
      <hr class="my-2"/>
      <div class="is-flex is-justify-content-space-between has-text-weight-bold is-size-6 my-4">
        <p>Tổng cộng:</p>
        <p class="has-text-primary">
          <!--
          TODO: Calculate the total price of items  in cart and put it here
          (We will need a separated plugin/mixin for this function)
          -->
          720.000 VNĐ
        </p>
      </div>
      <nuxt-link to="/cart">
        <b-button type="is-primary" expanded @click="isCollapsedCartOpen=false;">
          <p class="has-text-white has-text-weight-bold is-size-5">Thanh toán</p>
        </b-button>
      </nuxt-link>
    </div>
  </section>
</template>

<script>
import ItemInCartCollapse from "~/components/RightSideBar/ItemInCartCollapse";

export default {
  name: "CartFixed",
  components: {
    ItemInCartCollapse
  },
  data() {
    return {
      isCollapsedCartOpen: false,
      // itemsInCart is just a mock data array
      itemsInCart: [
        {
          itemImage: "https://ananas.vn/wp-content/uploads/pro_basas_A61078_1.jpg",
          itemPrice: "500.000 VNĐ",
          itemName: "VINTAS THE NEW MILITARY - HIGH TOP - CAPULET OLIVE",
          itemSize: 36,
          itemQuantity: 1
        },
        {
          itemImage: "https://ananas.vn/wp-content/uploads/pro_A6T004_1_1.jpg",
          itemName: "TRACK 6 SUEDE MEADOW - LOW TOP - MEADOW",
          itemPrice: "1500.000 VNĐ",
          itemSize: 41,
          itemQuantity: 2
        },
        {
          itemImage: "https://ananas.vn/wp-content/uploads/Pro_AV00020_1.jpg",
          itemName: "BASAS BUMPER GUM NE - HIGH TOP - OFFWHITE/GUM",
          itemPrice: "750.000 VNĐ",
          itemSize: 39,
          itemQuantity: 1
        }
      ]
    }
  },
  computed:
    {
      totalItemsInCart() {
        return this.itemsInCart.reduce((sum, item) => {
          return sum + item.itemQuantity
        }, 0);
      }
    },
  methods: {
    changeCartCollapseState() {
      this.isCollapsedCartOpen = !this.isCollapsedCartOpen;
    }
  }
}
</script>

<style lang="scss" scoped>
@import "assets/customized-buefy.scss";

hr {
  background-color: $black;
  height: 3px;
}

button:hover {
  transform: scale(1.02);
  transition: all 0.5s;
}

.cart-fixed {
  height: 60px;
  width: 40px;
  background-color: $primary;
  color: $white;
  position: fixed;
  right: 0;
  top: 30%;
  z-index: 9999;

  &:hover {
    cursor: pointer;
    color: $primary-light;
  }
}

.cart-collapse {
  position: relative;
  right: 310px;
  top: -56px;
  width: 300px;
  height: auto;
  background-color: $info;
  color: $black;
  z-index: 9999;
}

.cart-items-box {
  height: 80px;
  overflow-y: scroll;
  overflow-x: hidden;
}

</style>
