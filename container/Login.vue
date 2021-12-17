<template>
  <div class="modal" id="modal" v-bind:class="{ 'is-active': modalLogin }">
    <SignUp
      v-if="!modalSigin && modalSignup"
      v-bind:modalSignup="modalSignup"
      v-on:changeModalLogin="changeModalLogin"
      v-on:changeModalSignUp="changeModalSignUp"
    />
    <div class="modal-background"></div>
    <div
      class="modal-content"
      v-bind:style="[modalSignup ? { display: 'none' } : { display: 'block' }]"
    >
      <button
        class="modal-close is-large"
        aria-label="close"
        v-on:click="changeModalLogin"
      ></button>
      <div class="logo">
        <img :src="logo" alt="../assets/images/ipedit.svg" />
      </div>

      <p class="signup-title">로그인</p>
      <!-- Input username -->
      <div class="omrs-input-group">
        <label class="omrs-input-filled omrs-input-danger">
          <input
            class="input"
            required
            name="username"
            type="text"
            v-on:change="handleValue"
          />
          <span class="omrs-input-label">이메일</span>
          <!-- <span class="omrs-input-helper">Helper Text</span> -->
        </label>
      </div>

      <div class="omrs-input-group">
        <label class="omrs-input-filled omrs-input-danger">
          <input
            class="input"
            required
            name="password"
            type="password"
            v-on:change="handleValue"
          />
          <span class="omrs-input-label">비밀번호</span>
          <!-- <span class="omrs-input-helper">Helper Text</span> -->
        </label>
      </div>

      <!-- Remember password -->
      <div class="checkbox-control">
        <label class="container__checbox"
          >이메일 저장하기
          <input type="checkbox" checked="checked" />
          <span class="checkmark"></span>
        </label>
        <a class="forget-pass">비밀번호 찾기</a>
      </div>

      <!-- login with Email -->

      <Button
        style="width: 100%"
        :style="[
          data.userName !== '' &&
            data.password !== '' && {
              background: '#5C6BC0',
              color: '#fff',
            },
        ]"
        text="로그인"
      >
        로그인
      </Button>

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
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/login.scss";
</style>

<script>
import SignUp from "./SignUp.vue";
import Logo from "../assets/images/ipedit.svg";
import Google from "../assets/images/google.svg";
import Apple from "../assets/images/apple.svg";
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
    // document.onkeydown = (evt) => {
    //   evt = evt || window.event;
    //   if (evt.keyCode == 27) {
    //     this.$emit("changeModalLogin");
    //   }
    // };
    window.addEventListener("keydown", (evt) => {
      evt = evt || window.event;
      if (evt.keyCode == 27) {
        this.$emit("changeModalLogin");
      }
    });
  },
};
</script>
