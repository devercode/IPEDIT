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

<script>
import Header from "../container/Header.vue";
import Banner from "./Banner.vue";
import Impactory from "./Impactory.vue";
import Competitor from "./Competitor.vue";
import CompExamples from "./CompExamples.vue";
import UseFree from "./UseFree.vue";
import Footer from "../container/Footer.vue";

export default {
  data() {
    return {};
  },
  components: {
    Header,
    Banner,
    Impactory,
    Competitor,
    CompExamples,
    UseFree,
    Footer,
  },
};
</script>
