<template >
  <div class="modal is-active">
    <div class="modal-background"></div>
    <div class="modal-content">
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
          <button class="button">이메일로 가입하기</button>
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

      <p class="signup">이미 회원이신가요?<span>로그인</span></p>
    </div>
    <button class="modal-close is-large" aria-label="close"></button>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/signUp.scss";
</style>

<script>
export default {
  data() {
    return {};
  },
  props: {
    modalLogin: Boolean,
  },
  components: {},
  methods: {
    // changeModalLogin: function () {
    //   this.$emit("changeModalLogin");
    // },
  },
};
</script>
