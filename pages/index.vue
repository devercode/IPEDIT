<template>
  <div>
    <Header />
    <Banner />
    <Impactory />
    <Competitor />
    <CompExamples />
    <UseFree />
    <Footer />
    <Reset />
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/main.sass";
@import "../assets/stylesheets/global.scss";
</style>;

<script>
import Header from "../container/Header.vue";
import Footer from "../container/Footer.vue";
import Banner from "../container/Banner.vue";
import Impactory from "../container/Impactory.vue";
import Competitor from "../container/Competitor.vue";
import CompExamples from "../container/CompExamples.vue";
import UseFree from "../container/UseFree.vue";
import Reset from "../container/ResetPassword.vue";

export default {
  data() {
    return {};
  },
  components: {
    Reset,
    Header,
    Banner,
    Competitor,
    UseFree,
    Impactory,
    CompExamples,
    Footer,
  },
};
</script>
