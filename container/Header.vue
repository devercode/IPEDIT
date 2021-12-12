<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <Login
      v-if="modalLogin"
      v-bind:modalLogin="modalLogin"
      v-on:changeModalLogin="changeModalLogin"
    />
    <div class="navbar-brand">
      <a class="navbar-item logo" href="/">
        <img src="../assets/images/ipedit.png" width="112" height="28" />
      </a>
      <!-- responsive-edd -->
      <div class="responsive-edd">
        <div class="navbar-end endd">
          <div class="navbar-item">
            <div class="buttons">
              <div class="navbar-item has-dropdown is-hoverable">
                <a class="navbar-link" v-on:click="activeEdd = !activeEdd">
                  한국어
                </a>
                <div
                  class="navbar-dropdown"
                  v-bind:class="{ showDropEdd: !activeEdd }"
                >
                  <a class="navbar-item">
                    <p>English</p>
                  </a>
                  <a class="navbar-item">
                    <p>日本語</p>
                  </a>
                </div>
              </div>
              <a class="navbar-item item-log"> 로그인 </a>
              <a class="button btn" v-on:click="modalLogin = !modalLogin">
                시작하기
              </a>
            </div>
          </div>
        </div>
        <a
          role="button"
          class="navbar-burger isActive"
          v-bind:class="{ 'is-active': activeMenu }"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
          v-on:click="activeMenu = !activeMenu"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
    </div>

    <div
      id="navbarBasicExample"
      class="navbar-menu"
      v-bind:class="{ 'is-active': activeMenu }"
    >
      <div class="navbar-start">
        <div class="navbar-item has-dropdown is-hoverable">
          <a
            class="navbar-link"
            style="width: max-content"
            v-on:click="activeDropdown = !activeDropdown"
          >
            Products
          </a>
          <div
            class="navbar-dropdown dropdown-products"
            v-bind:class="{ showDropRespon: !activeDropdown }"
          >
            <a class="navbar-item">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
            <a class="navbar-item">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
          </div>
        </div>

        <a class="navbar-item"> Impact </a>
        <a class="navbar-item"> Stats </a>
        <a class="navbar-item"> Why IPEDIT? </a>
        <a class="navbar-item"> Contact us </a>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <div class="navbar-item has-dropdown is-hoverable">
              <a class="navbar-link"> 한국어 </a>
              <div class="navbar-dropdown">
                <a class="navbar-item">
                  <p>English</p>
                </a>
                <a class="navbar-item">
                  <p>日本語</p>
                </a>
              </div>
            </div>
            <a class="navbar-item"> 로그인 </a>
            <a class="button btn" v-on:click="modalLogin = !modalLogin">
              시작하기
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/header.scss";
</style>

<script>
import Login from "../components/Login.vue";
export default {
  data() {
    return {
      activeMenu: false,
      activeEdd: false,
      activeDropdown: false,
      modalLogin: false,
    };
  },
  components: { Login },
  methods: {
    changeModalLogin: function () {
      this.modalLogin = false;
    },
  },
  // created() {
  //   console.log(
  //     "propertyComputed sẽ update vì this.property đã thay đổi",
  //     this.modalLogin
  //   );
  // },
};
</script>
