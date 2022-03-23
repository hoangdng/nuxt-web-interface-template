<template>
  <nav>
    <TheHeaderTopMobile :product-menu-list="menuList" :functional-menu-list="functionalMenuList" :menu-footer="menuFooter" />
    <TheHeaderTop :functional-menu-list="functionalMenuList" />
    <TheHeaderMiddle :menu-list="menuList" :menu-footer="menuFooter" />
    <TheHeaderBottom :flash-contents="flashContents" />
  </nav>
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
          link: '#',
          contents: [
            {
              text: "NỔI BẬT",
              menuType: "list-title",
              contents: [
                {
                  text: "",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Best seller"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "New Arrival"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Sale off"
                    }
                  ]
                },
                {
                  text: "Bộ sưu tập",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Urbas Ruler"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Track 6 Class E"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vintas Flannel"
                    }
                  ]
                },
                {
                  text: "Collaboration",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
            {
              text: "GIÀY",
              menuType: "list-title",
              contents: [
                {
                  text: "Dòng sản phẩm",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Basas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vintas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Urbas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Pattas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Creas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Track 6"
                    }
                  ]
                },
                {
                  text: "Style",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "High Top"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Low Top"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Slip-on"
                    }
                  ]
                },
                {
                  text: "Tất cả giày",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
            {
              text: "THỜI TRANG & PHỤ KIỆN",
              menuType: "list-title",
              contents: [
                {
                  text: "Nửa trên",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Basic Tee"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Graphic tee"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Sweatshirt"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Hoodie"
                    }
                  ]
                },
                {
                  text: "Phụ kiện",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Nón"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Dây giày"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vớ"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Ba lô & Túi"
                    }
                  ]
                },
                {
                  text: "Xem tất cả",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
          ]
        },
        {
          type: 'menu',
          menuType: 'list',
          text: 'NỮ',
          link: '#',
          contents: [
            {
              text: "NỔI BẬT",
              menuType: "list-title",
              contents: [
                {
                  text: "",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Best seller"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "New Arrival"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Sale off"
                    }
                  ]
                },
                {
                  text: "Bộ sưu tập",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Urbas Ruler"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Track 6 Class E"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vintas Flannel"
                    }
                  ]
                },
                {
                  text: "Collaboration",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
            {
              text: "GIÀY",
              menuType: "list-title",
              contents: [
                {
                  text: "Dòng sản phẩm",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Basas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vintas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Urbas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Pattas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Creas"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Track 6"
                    }
                  ]
                },
                {
                  text: "Style",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "High Top"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Low Top"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Slip-on"
                    }
                  ]
                },
                {
                  text: "Tất cả giày",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
            {
              text: "THỜI TRANG & PHỤ KIỆN",
              menuType: "list-title",
              contents: [
                {
                  text: "Nửa trên",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Basic Tee"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Graphic tee"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Sweatshirt"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Hoodie"
                    }
                  ]
                },
                {
                  text: "Phụ kiện",
                  menuType: "list-subtitle",
                  contents: [
                    {
                      category: "",
                      attribute: "",
                      text: "Nón"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Dây giày"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Vớ"
                    },
                    {
                      category: "",
                      attribute: "",
                      text: "Ba lô & Túi"
                    }
                  ]
                },
                {
                  text: "Xem tất cả",
                  menuType: "list-subtitle",
                  contents: []
                }
              ]
            },
          ]
        },
        {
          type: 'text',
          text: 'SALE OFF',
          link: '#',
        },
        {
          type: 'image',
          imageSrc: 'discover-you.svg',
          text: 'DiscoverYOU',
          link: '#',
        },
      ],
      menuFooter: {
        link: "#",
        text: "MỌI NGƯỜI THƯỜNG GỌI CHÚNG TÔI LÀ <span class=\"menu-footer-highlight\">DỨA</span> !"
      },
      functionalMenuList: [
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
      flashContents: [
        { text: 'BUY 2 GET 10% OFF - ÁP DỤNG VỚI TẤT CẢ BASIC TEE' },
        { text: 'FREE SHIPPING VỚI HOÁ ĐƠN TỪ 800K !' },
        { text: 'BUY MORE PAY LESS - ÁP DỤNG KHI MUA PHỤ KIỆN' },
      ],
    }
  }
};
</script>
