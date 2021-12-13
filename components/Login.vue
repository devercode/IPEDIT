<template>
  <div class="modal" id="modal" v-bind:class="{ 'is-active': modalLogin }">
    <div class="modal-background"></div>
    <div class="modal-content">
      <div class="logo">
        <img
          src="../assets/images/ipedit.png"
          alt="../assets/images/ipedit.png"
        />
      </div>
      <!-- Input username -->
      <div class="field">
        <div class="control">
          <input class="input" type="text" placeholder="이메일" />
        </div>
      </div>

      <div class="field">
        <div class="control">
          <input class="input" type="email" placeholder="비밀번호 " />
        </div>
      </div>

      <!-- Remember password -->
      <div class="checkbox-control">
        <label class="checkbox">
          <input type="checkbox" />
          이메일 저장하기
        </label>
        <p>비밀번호 찾기</p>
      </div>
      <!-- login with Email -->
      <div class="field">
        <p class="control">
          <button class="button">로그인</button>
        </p>
      </div>

      <p class="or">또는</p>

      <!-- login with Goolge -->
      <div class="field">
        <img src="../assets/images/google.png" alt="" />
        <p class="control">
          <button class="button google">Google로 로그인하기</button>
        </p>
      </div>

      <!-- login with apple -->
      <div class="field">
        <img src="../assets/images/apple.png" alt="" />
        <p class="control">
          <button class="button apple">Apple로 로그인하기</button>
        </p>
      </div>

      <p class="signup">
        IPEDIT이 처음이신가요?<span v-on:click="openModalSignUp">회원가입</span>
      </p>
    </div>
    <SignUp
      v-if="modalSignup"
      v-bind:modalSignup="modalSignup"
      v-on:changeModalSignUp="changeModalSignUp"
    />

    <button
      class="modal-close is-large"
      aria-label="close"
      v-on:click="changeModalLogin"
    ></button>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/login.scss";
</style>

<script>
import SignUp from "./SignUp.vue";
export default {
  data() {
    return {
      modalSignup: false,
    };
  },
  props: {
    modalLogin: Boolean,
  },
  components: { SignUp },
  methods: {
    changeModalLogin: function () {
      this.$emit("changeModalLogin");
    },
    changeModalSignUp: function () {
      this.modalSignup = false;
    },
    openModalSignUp: function () {
      this.modalSignup = true;
      // modalLogin = false;
    },
  },
};
</script>
