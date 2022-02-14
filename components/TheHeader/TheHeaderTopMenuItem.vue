<template>
  <a :href="link">
    <span class="icon mr-1">
      <img :src="icon" :alt="altText" />
    </span>
    {{ title }}
    <span v-if="isShowNumberBadge" class="ml-1">({{ getNumberBadge }})</span>
  </a>
</template>

<script>
export default {
  name: 'TopHeaderMenuItem',
  props: {
    altText: {
      type: String,
      required: true,
      default: ""
    },
    icon: {
      type: String,
      required: true,
      default: ""
    },
    link: {
      type: String,
      required: true,
      default: ""
    },
    title: {
      type: String,
      required: true,
      default: ""
    },
    isShowNumberBadge: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      alo: 123
    };
  },
  computed: {
    getNumberBadge(){
      // get number from vuex store and return
      return 0;
    }
  }
}
</script>

<style lang="scss" scoped>
a {
  color: $info;

  &:hover {
    color: $primary;
  }
}
</style>
