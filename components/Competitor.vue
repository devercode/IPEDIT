<template>
  <div class="competitor">
    <div class="competitor__container container">
      <h3>
        아직도 사용 전이신가요?<br />
        당신의 경쟁자는 이미 IPEDIT으로 앞서가고 있습니다.
      </h3>
      <div class="markets">
        <p>사용자 수</p>
        <h1 class="count" id="count"><span>명</span></h1>
      </div>
      <div class="markets">
        <p>처리 사건 수</p>
        <h1 class="count2"><span>건</span></h1>
      </div>
      <div class="markets">
        <p>작성 시간</p>
        <h1 class="count3"><span>시간</span></h1>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/competitor.scss";
</style>

<script type='text/javascript'>
export default {
  data() {
    return {
      text: "",
    };
  },
  methods: {
    myFunction: function () {
      setTimeout(function () {
        this.text = "60,000";
      }, 5000);
      console.log(this.text);
      // return text;
    },
  },

  components: {},

  mounted() {
    this.myFunction();
  },
};
</script>
