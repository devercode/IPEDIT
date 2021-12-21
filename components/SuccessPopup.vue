<template>
  <div class="modal" v-bind:class="{ 'is-active': successPopup }">
    <!-- <div class="modal-background is-clipped"></div> -->
    <div class="modal-content" style="width: 400px; height: 152px">
      <p class="">이메일로 비밀번호 재설정 링크를 보내드렸습니다.</p>
      <!-- Reset -->
      <Button text="확인" v-on:click="closePopUp"> </Button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/login.scss";
@import "../assets/stylesheets/resetPassword.scss";
</style>

<script>
export default {
  data() {
    return {};
  },
  props: { successPopup: Boolean },
  components: {},
  methods: {
    closePopUp: function () {
      this.$emit("changeModalLogin");
      this.$emit("closeModalSuccess");
    },
  },
  mounted() {},
  created() {
    if (typeof window !== "undefined") {
      window.addEventListener("keydown", (evt) => {
        evt = evt || window.event;
        if (evt.keyCode == 27) {
          this.$emit("closeModalResetPassword");
        }
      });
    }
  },
};
</script>
