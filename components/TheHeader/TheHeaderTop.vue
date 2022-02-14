<template>
  <nav class="level has-background-dark has-text-white is-size-7 px-6 py-1 m-0">
    <div class="level-left" />
    <div class="level-right">
      <TopHeaderMenuItem
        v-for="menuItem in menuList"
        :key="menuItem.key"
        class="level-item ml-3"
        :icon="menuItem.icon"
        :alt-text="menuItem.key"
        :title="menuItem.title"
        :link="menuItem.href"
        :is-show-number-badge="menuItem.isShowNumberBadge"
      />
    </div>
  </nav>
</template>

<script>
import TopHeaderMenuItem from '~/components/TheHeader/TheHeaderTopMenuItem'
export default {
  name: 'TopHeader',
  components: { TopHeaderMenuItem },
  data() {
    return {
      menuList: [
        {
          key: 'order-tracking',
          icon: require('~/assets/img/order-tracking.svg'),
          title: 'Tra cứu đơn hàng',
          href: '#',
          isShowNumberBadge: false
        },
        {
          key: 'store-location',
          icon: require('~/assets/img/store-location.svg'),
          title: 'Tìm cửa hàng',
          href: '#',
          isShowNumberBadge: false
        },
        {
          key: 'favourite-heart',
          icon: require('~/assets/img/favourite-heart.svg'),
          title: 'Yêu thích',
          href: '#',
          isShowNumberBadge: false
        },
        {
          key: 'log-in',
          icon: require('~/assets/img/log-in.svg'),
          title: 'Đăng nhập',
          href: '#',
          isShowNumberBadge: false
        },
        {
          key: 'cart',
          icon: require('~/assets/img/cart.svg'),
          title: 'Giỏ hàng',
          href: '#',
          isShowNumberBadge: true
        },
      ],
    }
  },
}
</script>
