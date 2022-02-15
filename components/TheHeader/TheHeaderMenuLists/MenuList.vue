<template>
<div>
  <div class="columns is-justify-content-center mt-4 mb-5 is-size-6 has-text-weight-normal">
    <div v-for="(menuListItem, menuListItemKey) in menuList" :key="`menu-list-item-${menuListItemKey}`" class="column is-3 is-flex is-flex-direction-column">
      <div class="menu-list-title is-size-4 has-text-weight-bold">{{ menuListItem.title }}</div>

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
              subtitle: "Bộ sưu tập",
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
              subtitle: "Style",
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
              subtitle: "Phụ kiện",
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
