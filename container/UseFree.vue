<template>
  <div class="useFree">
    <div class="useFree__container container">
      <h1>지금 바로 무료 체험판 이용을 시작하세요!</h1>
      <!-- <a class="button btn btn-useFree"> </a> -->
      <div class="div_btn">
        <Button
          class="btn-useFree"
          v-on:click="openModalSignUp"
          text="IPEDIT 시작하기"
        >
        </Button>
      </div>
    </div>
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
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/useFree.scss";
</style>

<script>
import SignUp from "./SignUp.vue";
import Login from "./Login.vue";
export default {
  data() {
    return {
      modalLogin: false,
      modalSignup: false,
      modalSigin: false,
      loginFree: false,
    };
  },
  components: { SignUp, Login },
  methods: {
    changeModalSignUp: function () {
      document.querySelector("html").classList.remove("is-clipped");
      this.modalSignup = false;
    },
    openModalSignUp: function () {
      document.querySelector("html").classList.add("is-clipped");
      this.modalSignup = true;
    },
    openModalLogin: function () {
      this.modalLogin = true;
    },
    changeModalLogin: function () {
      this.modalLogin = false;
    },
  },
};
</script>
