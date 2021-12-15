<template>
  <!-- v-bind:class="{ 'is-active': modalSignup }" -->
  <div class="modal is-active">
    <div class="modal-background"></div>
    <SignUpEmail
      v-if="signupEmail"
      v-on:changeModalSignUp="changeModalSignUp"
    />
    <div class="modal-content" v-if="!signupEmail">
      <div class="logo">
        <img
          src="../assets/images/ipedit.png"
          alt="../assets/images/ipedit.png"
        />
      </div>

      <p class="signup-title">회원가입</p>

      <!-- login with Email -->
      <div class="field">
        <p class="control">
          <button class="button" v-on:click="signupEmail = !signupEmail">
            이메일로 가입하기
          </button>
        </p>
      </div>

      <p class="or">또는</p>

      <!-- login with Goolge -->
      <div class="field">
        <img src="../assets/images/google.png" alt="" />
        <p class="control">
          <button class="button google">Google로 시작하기</button>
        </p>
      </div>

      <!-- login with apple -->
      <div class="field">
        <img src="../assets/images/apple.png" alt="" />
        <p class="control">
          <button class="button apple">Apple로 시작하기</button>
        </p>
      </div>

      <p class="signup">
        이미 회원이신가요?<span v-on:click="openModalLogin">로그인</span>
      </p>
    </div>
    <button
      class="modal-close is-large"
      aria-label="close"
      v-on:click="changeModalSignUp"
    ></button>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/signUp.scss";
</style>

<script>
import SignUpEmail from "./SignupEmail.vue";
export default {
  data() {
    return {
      signupEmail: false,
    };
  },
  props: {
    modalSignup: Boolean,
  },
  components: { SignUpEmail },
  methods: {
    changeModalSignUp: function () {
      this.$emit("changeModalLogin");
      this.$emit("changeModalSignUp");
    },
    openModalLogin: function () {
      this.$emit("changeModalSignUp");
      this.$emit("openModalLogin");
    },
  },
  created() {
    document.onkeydown = (evt) => {
      evt = evt || window.event;
      if (evt.keyCode == 27) {
        this.$emit("changeModalLogin");
        this.$emit("changeModalSignUp");
      }
    };
  },
};
</script>
