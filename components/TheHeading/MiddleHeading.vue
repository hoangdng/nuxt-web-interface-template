<template>
  <nav class="level mx-6 my-0 py-4">
    <div class="level-left">
      <figure class="image ml-6 pl-6">
        <img src="~/assets/img/brand-logo.svg" />
      </figure>
    </div>
    <div class="level-item has-text-weight-bold is-size-4">
      <div class="mx-3 is-flex is-flex-direction-row is-justify-content-center is-align-content-center">
        <div>
          SẢN PHẨM
        </div>
        <b-icon size="is-medium" icon="chevron-down"></b-icon>
      </div>
      <div class="mx-3 is-flex is-flex-direction-row is-justify-content-center is-align-content-center">
        <div>
          NAM
        </div>
        <b-icon size="is-medium" icon="chevron-down"></b-icon>
      </div>
      <div class="mx-3 is-flex is-flex-direction-row is-justify-content-center is-align-content-center">
        <div>
          NỮ
        </div>
        <b-icon size="is-medium" icon="chevron-down"></b-icon>
      </div>
      <div class="mx-3">SALE OFF</div>
      <div class="mx-3">DISCOVER YOU</div>
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
export default {
  name: 'MiddleHeading',
}
</script>

<style scoped></style>
