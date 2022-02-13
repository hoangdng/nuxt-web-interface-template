<template>
  <nav class="level mx-6 my-0 py-4">
    <div class="level-left">
      <figure class="image ml-6 pl-6">
        <img src="~/assets/img/brand-logo.svg" />
      </figure>
    </div>
    <div class="level-item has-text-weight-bold is-size-5 has-text-black">
      <MiddleHeadingMenuItem
        v-for="(menuItem, key) in menuList"
        :key="key"
        :menu-item="menuItem"
        :menu-footer="menuFooter"
      />
    </div>
    <div class="level-right">
      <b-field>
        <b-input
          placeholder="Tìm kiếm"
          type="search"
          icon="magnify"
          icon-clickable
        >
        </b-input>
      </b-field>
    </div>
  </nav>
</template>

<script>
import MiddleHeadingMenuItem from '~/components/TheHeading/MiddleHeadingMenuItem';

export default {
  name: 'MiddleHeading',
  components: { MiddleHeadingMenuItem },
  data() {
    return {
      menuList: [
        {
          type: 'menu',
          menuType: 'thumbnail',
          text: 'SẢN PHẨM',
          link: '#',
          contents: [
            {
              imageSrc: "menu-nam.jpg",
              imageAlt: "menu nam",
              text: "CHO NAM"
            },
            {
              imageSrc: "menu-nu.jpg",
              imageAlt: "menu-nu",
              text: "CHO NỮ"
            },
            {
              imageSrc: "menu-sale-off.jpg",
              imageAlt: "menu-sale-off",
              text: "OUTLET SALE"
            },
            {
              imageSrc: "menu-phu-kien.jpg",
              imageAlt: "menu-phu-kien",
              text: "THỜI TRANG & PHỤ KIỆN"
            }
          ]
        },
        {
          type: 'menu',
          menuType: 'list',
          text: 'NAM',
          link: '#'
        },
        {
          type: 'menu',
          menuType: 'list',
          text: 'NỮ',
          link: '#',
        },
        {
          type: 'text',
          text: 'SALE OFF',
          link: '#',
        },
        {
          type: 'image',
          imageSrc: 'discover-you.svg',
          link: '#',
        },
      ],
      menuFooter: {
        link: "#",
        text: "MỌI NGƯỜI THƯỜNG GỌI CHÚNG TÔI LÀ DỨA!"
      }
    }
  },
}
</script>

<style scoped lang="scss">
.has-text-black {
  color: #000000;
}
</style>
