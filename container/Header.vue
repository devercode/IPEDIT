<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <Login
      v-if="modalLogin"
      v-bind:modalLogin="modalLogin"
      v-on:changeModalLogin="changeModalLogin"
    />
    <SignUp
      v-if="modalSignup"
      v-bind:modalSignup="modalSignup"
      v-on:changeModalSignUp="changeModalSignUp"
      v-on:openModalLogin="openModalLogin"
      v-on:changeModalLogin="changeModalLogin"
    />
    <ContactUs v-bind:isContact="isContact" v-on:closeContact="closeContact" />

    <div class="navbar-brand">
      <a class="navbar-item logo" href="/">
        <img src="../assets/images/ipedit.svg" width="112" height="28" />
      </a>

      <!-- responsive-edd -->
      <div class="responsive-edd">
        <div class="navbar-end endd">
          <div class="navbar-item" style="margin-right: 0">
            <div class="buttons">
              <div class="navbar-item has-dropdown is-hoverable">
                <a class="navbar-link" v-on:click="activeEdd = !activeEdd">
                  {{ language }}
                </a>
                <div
                  class="navbar-dropdown"
                  v-bind:class="{ showDropEdd: !activeEdd }"
                  style="z-index: 111111"
                >
                  <a
                    v-for="(item, index) in arrLanguage"
                    :key="index"
                    class="navbar-item"
                    style="margin-right: 0; width: 100%; white-space: nowrap"
                    v-on:click="handleLanguage(item)"
                  >
                    <p>{{ item }}</p>
                  </a>
                </div>
              </div>
              <a class="navbar-item item-log" v-on:click="openModalLogin">
                로그인
              </a>
              <a class="button btn" v-on:click="openModalSignUp"> 시작하기 </a>
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
            style="width: max-content; background: none"
            v-on:click="activeDropdown = !activeDropdown"
          >
            Products
          </a>
          <div
            class="navbar-dropdown dropdown-products"
            v-bind:class="{ showDropRespon: !activeDropdown }"
          >
            <a class="navbar-item hover_products" @click="activeMenu = false">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
            <a class="navbar-item hover_products" @click="activeMenu = false">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
          </div>
        </div>

        <a class="navbar-item" v-on:click="scrollToHeader('Impact')">
          Impact
          <!-- {{ t("title", {}, { locale: lang }) }} -->
        </a>
        <a class="navbar-item" v-on:click="scrollToHeader('Stats')"> Stats </a>
        <a class="navbar-item" v-on:click="scrollToHeader('IPEDIT')">
          Why IPEDIT?
        </a>
        <a class="navbar-item" v-on:click="openContact"> Contact us </a>
        <a
          class="
            navbar-item navbar-item-modal
            item-login-header
            respon-text-signup
          "
          v-on:click="openModalLogin"
        >
          로그인
        </a>
        <a class="button btn btn-respon" v-on:click="openModalSignUp">
          시작하기
        </a>
      </div>

      <div class="navbar-end">
        <div
          class="navbar-item"
          style="padding-right: 0; margin-right: 0; padding-top: 8px !important"
        >
          <div class="buttons">
            <div
              class="navbar-item"
              v-bind:class="{ 'has-dropdown is-hoverable': !upHere }"
            >
              <a
                class="navbar-link"
                v-bind:class="{ 'dropdown-option': !upHere }"
                style="width: max-content; background: none; height: 50px"
                v-on:mouseleave="upHere = false"
              >
                {{ language }}
              </a>
              <div class="navbar-dropdown" style="margin-top: -4px">
                <a
                  v-for="(item, index) in arrLanguage"
                  :key="index"
                  class="navbar-item"
                  style="margin-right: 0; width: 100%; white-space: nowrap"
                  v-on:click="handleLanguage(item)"
                  v-on:mouseleave="upHere = false"
                >
                  <p>{{ item }}</p>
                </a>
              </div>
            </div>
            <a
              class="navbar-item navbar-item-modal item-login-header"
              v-on:click="openModalLogin"
            >
              로그인
            </a>
            <Button v-on:click="openModalSignUp" text="시작하기"> </Button>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/header.scss";
@import "../assets/stylesheets/main.sass";
</style>

<script>
import Login from "./Login.vue";
import SignUp from "./SignUp.vue";
import ContactUs from "./ContactUs.vue";
export default {
  data() {
    return {
      activeMenu: false,
      activeEdd: false,
      activeDropdown: false,
      modalLogin: false,
      modalSignup: false,
      isContact: false,
      upHere: false,
      language: "한국어",
      arrLanguage: ["English", "日本語"],
    };
  },
  components: { Login, SignUp, ContactUs },
  methods: {
    // login
    openModalLogin: function () {
      document.querySelector("html").classList.add("is-clipped");
      this.modalLogin = true;
      this.activeMenu = false;
    },
    changeModalLogin: function () {
      document.querySelector("html").classList.remove("is-clipped");
      this.modalLogin = false;
    },
    // Register
    openModalSignUp: function () {
      document.querySelector("html").classList.add("is-clipped");
      this.modalSignup = true;
      this.activeMenu = false;
    },
    changeModalSignUp: function () {
      document.querySelector("html").classList.remove("is-clipped");
      this.modalSignup = false;
    },
    // Contact
    openContact: function () {
      document.querySelector("html").classList.add("is-clipped");
      this.isContact = true;
      this.activeMenu = false;
    },
    closeContact: function () {
      document.querySelector("html").classList.remove("is-clipped");
      this.isContact = false;
    },
    handleLanguage: function (lang) {
      this.language = lang;
      this.upHere = true;
      this.activeEdd = false;
      if (lang === "English") {
        this.arrLanguage = ["한국어", "日本語"];
      } else if (lang === "한국어") {
        this.arrLanguage = ["English", "日本語"];
      } else {
        this.arrLanguage = ["한국어", "English"];
      }
    },
    scrollToHeader: function (type) {
      this.activeMenu = false;
      let offset = document.getElementById(type)?.offsetTop;
      if (typeof window !== "undefined") {
        switch (type) {
          case "Impact":
            window.scrollTo(0, offset);
            break;
          case "Stats":
            window.scrollTo(0, offset);
            break;
          case "IPEDIT":
            window.scrollTo(0, offset - 200);
            break;
        }
      }
    },
  },
};
</script>
