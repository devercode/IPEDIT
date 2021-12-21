<template>
  <NuxtPage id="__layout" style="background: #f6f7f9" />
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/main.sass";
@import "../assets/stylesheets/global.scss";
html {
  overflow-y: hidden !important;
}
</style>;

<script>
// import "./main";
import Main from "./pages";
import { useI18n } from "vue-i18n";

export default {
  data() {
    return {};
  },
  components: {
    Main,
  },
};
</script>
