<template>
  <div class="footer">
    <div class="columns">
      <div class="column is-3">
        <b-image src="https://ananas.vn/wp-content/themes/ananas/fe-assets/images/svg/Store.svg" ratio="4by3"/>
        <b-button type="is-primary" expanded class="mt-4">
          <nuxt-link to="/stores">
            <p class="is-uppercase has-text-weight-bold has-text-white is-size-5">Tìm cửa hàng</p>
          </nuxt-link>
        </b-button>
      </div>
      <div class="column is-9">
        <div class="columns">
          <div class="column">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Sản phẩm</h1>
            <br>
            <p>
              <nuxt-link to="/">Giày nam</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Giày nữ</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Thời trang và phụ kiện</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Sale-off</nuxt-link>
            </p>
          </div>
          <div class="column">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Về công ty</h1>
            <br>
            <p>
              <nuxt-link to="/">Dứa tuyển dụng</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Liên hệ nhượng quyền</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Về Ananas</nuxt-link>
            </p>
          </div>
          <div class="column">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Hỗ trợ</h1>
            <br>
            <p>
              <nuxt-link to="/">FAQs</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Bảo mật thông tin</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Chính sách chung</nuxt-link>
            </p>
          </div>
          <div class="column">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Liên hệ</h1>
            <br>
            <p>
              <nuxt-link to="/">Email góp ý</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">Hot line</nuxt-link>
            </p>
            <p>
              <nuxt-link to="/">0963 429 749</nuxt-link>
            </p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-3">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Ananas Social</h1>
            <br>
            <a :href="`https://www.facebook.com/${facebookProfileUrl}`" target="_blank">
              <b-icon icon="facebook" size="is-large"/>
            </a>
            <a :href="`https://www.instagram.com/${instagramProfileUrl}`" target="_blank">
              <b-icon icon="instagram" size="is-large"/>
            </a>
            <a :href="`https://www.youtube.com/${youtubeChannelUrl}`" target="_blank">
              <b-icon icon="youtube" size="is-large"/>
            </a>
          </div>
          <div class="column is-3">
            <h1 class="is-uppercase has-text-white has-text-weight-bold">Đăng ký nhận mail</h1>
            <br>
            <b-input
              v-model="emailToBeRegistered"
              icon-right="close-circle"
              icon-right-clickable
              @icon-right-click="clearEmail"/>
            <b-button type="is-black" size="is-medium" @click="registerEmail">
              <b-icon
                icon="arrow-right"
                size="is-medium"
              />
            </b-button>
          </div>
          <div class="column is-6">
            <b-image src="https://ananas.vn/wp-content/themes/ananas/fe-assets/images/svg/Logo_Ananas_Footer.svg"/>
          </div>
        </div>
      </div>
    </div>
    <div class="is-flex is-justify-content-center is-align-items-center reverse-flex-direction">
      <a href="http://online.gov.vn/Home/WebDetails/61921" target="_blank">
        <b-image
          src="https://ananas.vn/wp-content/themes/ananas/fe-assets/images/icon_bocongthuong.png"
          placeholder="Đã thông báo Bộ Công Thương"
          class="mx-5"/>
      </a>
      <p class="has-text-grey is-size-5 mx-5">Copyright © 2021 Ananas. All rights reserved.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheFooter",
  data() {
    return {
      facebookProfileUrl: "",
      instagramProfileUrl: "",
      youtubeChannelUrl: "",
      emailToBeRegistered: ""
    }
  },
  methods: {
    clearEmail() {
      this.emailToBeRegistered = ""
    },
    // TODO: Complete the real functionality of this method
    registerEmail() {
      this.emailToBeRegistered = this.emailToBeRegistered.trim();
      if (this.emailToBeRegistered !== "") {
        if (/^\S+@\S+\.\S+$/.test(this.emailToBeRegistered)) {
          alert(`Email ${this.emailToBeRegistered} is registered`);
        } else {
          alert(`${this.emailToBeRegistered} is not a VALID email!!!`)
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@media only screen and (max-width: 768px) {
  .reverse-flex-direction{
    flex-direction: column;
  }
}

a {
  color: $grey-light;

  i {
    color: red;
  }

  &:hover {
    color: $primary-light;
  }
}

.footer {
  height: auto;
  width: 100%;
  background-color: $dark;
}
</style>
