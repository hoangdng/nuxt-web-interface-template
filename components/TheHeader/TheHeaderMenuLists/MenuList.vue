<template>
<div>
  <div class="columns is-justify-content-center mt-4 mb-5 is-size-6 has-text-weight-normal">
    <div v-for="(menuListItem, menuListItemKey) in menuList" :key="`menu-list-item-${menuListItemKey}`" class="column is-3 is-flex is-flex-direction-column">
      <a class="menu-list-title is-size-4 has-text-weight-bold" href="#">{{ menuListItem.title }}</a>

      <template v-for="(group, groupKey) in menuListItem.groups">
        <a :key="`group-key-${menuListItemKey}-${groupKey}`" class="menu-list-subtitle menu-list-item has-text-weight-bold mt-5" href="#">{{ group.subtitle }}</a>
        <a v-for="(elem, elemKey) in group.contents" :key="`group-item-${menuListItemKey}-${groupKey}-${elemKey}`" class="menu-list-item" href="#">{{ elem.text }}</a>
      </template>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "MenuList",
  data() {
    return {
      menuList: [
        {
          title: "NỔI BẬT",
          groups: [
            {
              subtitle: "",
              contents: [
                {
                  text: "Best seller"
                },
                {
                  text: "New Arrival"
                },
                {
                  text: "Sale off"
                }
              ]
            },
            {
              subtitle: "Bộ sưu tập",
              contents: [
                {
                  text: "Urbas Ruler"
                },
                {
                  text: "Track 6 Class E"
                },
                {
                  text: "Vintas Flannel"
                }
              ]
            },
            {
              subtitle: "Collaboration",
              contents: []
            }
          ]
        },
        {
          title: "GIÀY",
          groups: [
            {
              subtitle: "Dòng sản phẩm",
              contents: [
                {
                  text: "Basas"
                },
                {
                  text: "Vintas"
                },
                {
                  text: "Urbas"
                },
                {
                  text: "Pattas"
                },
                {
                  text: "Creas"
                },
                {
                  text: "Track 6"
                }
              ]
            },
            {
              subtitle: "Style",
              contents: [
                {
                  text: "High Top"
                },
                {
                  text: "Low Top"
                },
                {
                  text: "Slip-on"
                }
              ]
            },
            {
              subtitle: "Tất cả giày",
              contents: []
            }
          ]
        },
        {
          title: "THỜI TRANG & PHỤ KIỆN",
          groups: [
            {
              subtitle: "Nửa trên",
              contents: [
                {
                  text: "Basic Tee"
                },
                {
                  text: "Graphic tee"
                },
                {
                  text: "Sweatshirt"
                },
                {
                  text: "Hoodie"
                }
              ]
            },
            {
              subtitle: "Phụ kiện",
              contents: [
                {
                  text: "Nón"
                },
                {
                  text: "Dây giày"
                },
                {
                  text: "Vớ"
                },
                {
                  text: "Ba lô & Túi"
                }
              ]
            },
            {
              subtitle: "Xem tất cả",
              contents: []
            }
          ]
        },
      ]
    }
  },
  methods: {
    getLink(gender, category, attribute) {
      return `/product-list?gender=${gender}&amp;category=${category}&amp;attribute=${attribute}`;
    }
  }
};
</script>

<style lang="scss" scoped>
.menu-list {
  &-column {
    width: 260px;
  }

  &-item {
    color : #CCCCCC !important;

    &:hover {
      color: $primary !important;
    }
  }

  &-title {
    color: white !important;
  }
}
</style>
