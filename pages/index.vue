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
