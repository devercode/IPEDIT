<template>
  <div class="competitor" id="Stats" v-on:scroll="scrollFunction">
    <div class="competitor__container container">
      <h3>
        아직도 사용 전이신가요?<br />
        당신의 경쟁자는 이미 IPEDIT으로 앞서가고 있습니다.
      </h3>

      <div class="markets">
        <p>사용자 수</p>
        <h1 class="" id="count"><span>명</span></h1>
      </div>
      <div class="markets">
        <p>처리 사건 수</p>
        <h1 class="" id="count2"><span>건</span></h1>
      </div>
      <div class="markets">
        <p>작성 시간</p>
        <h1 class="" id="count3"><span>시간</span></h1>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/competitor.scss";
</style>

<script  type="text/babel">
import ICountUp from "vue-countup-v2";
export default {
  data() {
    return {
      text: "",
      delay: 1000,
      endVal: 120500,
      options: {
        useEasing: true,
        useGrouping: true,
        separator: ",",
        decimal: ".",
        prefix: "",
        suffix: "",
      },
    };
  },
  methods: {
    onReady: function (instance, CountUp) {
      const that = this;
      instance.update(that.endVal + 100);
    },
    scrollFunction: function () {
      if (
        window.scrollY >= 2000
        // ||
        // document.documentElement.scrollTop > 2000
      ) {
        document.getElementById("count").className = "count";
        document.getElementById("count2").className = "count2";
        document.getElementById("count3").className = "count3";
      }
    },
  },

  components: { ICountUp },

  created() {
    window.addEventListener("scroll", this.scrollFunction);
  },
};
</script>
