<template>
  <div>
    <Header />
    <Banner />
    <Impactory />
    <Competitor />
    <CompExamples />
    <UseFree />
    <Footer />
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/main.sass";
@import "../assets/stylesheets/global.scss";
</style>;

<script>
import Header from "../container/Header.vue";
import Footer from "../container/Footer.vue";

export default {
  data() {
    return {};
  },
  components: {
    Header,

    Footer,
  },
};
</script>
