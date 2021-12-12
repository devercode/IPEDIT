<template>
  <div class="useFree">
    <div class="useFree__container container">
      <h1>지금 바로 무료 체험판 이용을 시작하세요!</h1>
      <a class="button btn btn-useFree" v-on:click="openModalSignUp">
        IPEDIT 시작하기
      </a>
    </div>
    <SignUp
      v-if="modalSignup"
      v-bind:modalSignup="modalSignup"
      v-on:changeModalSignUp="changeModalSignUp"
    />
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/useFree.scss";
</style>

<script>
import SignUp from "./SignUp.vue";
export default {
  data() {
    return { modalSignup: false };
  },
  components: { SignUp },
  methods: {
    changeModalSignUp: function () {
      this.modalSignup = false;
    },
    openModalSignUp: function () {
      this.modalSignup = true;
    },
  },
};
</script>
