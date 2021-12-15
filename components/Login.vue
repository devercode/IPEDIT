<template>
  <div class="modal" id="modal" v-bind:class="{ 'is-active': modalLogin }">
    <SignUp
      v-if="!modalSigin && modalSignup"
      v-bind:modalSignup="modalSignup"
      v-on:changeModalLogin="changeModalLogin"
      v-on:changeModalSignUp="changeModalSignUp"
    />
    <div class="modal-background" v-on:click="changeModalLogin"></div>
    <div
      class="modal-content"
      v-bind:style="[modalSignup ? { display: 'none' } : { display: 'block' }]"
    >
      <div class="logo">
        <img :src="logo" alt="../assets/images/ipedit.png" />
      </div>
      <!-- Input username -->
      <div class="field">
        <div class="control">
          <input
            class="input"
            type="text"
            placeholder="이메일"
            name="username"
            v-on:change="handleValue"
          />
        </div>
      </div>

      <div class="field">
        <div class="control">
          <input
            class="input"
            type="email"
            placeholder="비밀번호 "
            name="password"
          />
        </div>
      </div>

      <!-- Remember password -->
      <div class="checkbox-control">
        <label class="container__checbox"
          >이메일 저장하기
          <input type="checkbox" checked="checked" />
          <span class="checkmark"></span>
        </label>
        <p>비밀번호 찾기</p>
      </div>

      <!-- login with Email -->
      <div class="field">
        <p class="control">
          <button
            class="button"
            :style="[
              data.userName !== '' &&
                data.password !== '' && {
                  background: '#5C6BC0',
                  color: '#fff',
                },
            ]"
          >
            로그인
          </button>
        </p>
      </div>

      <p class="or">또는</p>

      <!-- login with Goolge -->
      <div class="field">
        <img :src="google" alt="" style="position: absolute" />
        <p class="control">
          <button class="button google">Google로 로그인하기</button>
        </p>
      </div>

      <!-- login with apple -->
      <div class="field">
        <img :src="apple" alt="" style="position: absolute" />
        <p class="control">
          <button class="button apple">Apple로 로그인하기</button>
        </p>
      </div>

      <p class="signup">
        IPEDIT이 처음이신가요?<span v-on:click="openModalSignUp">회원가입</span>
      </p>
    </div>

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
import Logo from "../assets/images/ipedit.png";
import Google from "../assets/images/google.png";
import Apple from "../assets/images/apple.png";
export default {
  data() {
    return {
      modalSignup: false,
      modalSigin: false,
      logo: Logo,
      google: Google,
      apple: Apple,
      data: { userName: "", password: "" },
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
    },
    handleValue: function (e) {
      this.data = { [e.target.name]: e.target.value };
    },
  },

  created() {
    document.onkeydown = (evt) => {
      evt = evt || window.event;
      if (evt.keyCode == 27) {
        this.$emit("changeModalLogin");
      }
    };
  },
};
</script>
