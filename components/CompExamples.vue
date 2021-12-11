<template>
  <div class="examples">
    <div class="examples__container container">
      <div
        v-for="(item, index) in data"
        :key="index"
        class="exmodule"
        v-bind:style="{ backgroundImage: 'url(' + item.background + ')' }"
      >
        <div class="module-text">
          <div class="img-icon">
            <img v-bind:src="item.img" v-bind:alt="item.img" />
          </div>
          <div class="text">
            <p>{{ item.text_1 }}</p>
            <p>{{ item.text_2 }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/compExamples.scss";
</style>

<script>
import Banner1 from "../assets/images/exameple1.png";
import Banner2 from "../assets/images/exameple2.png";
import Banner3 from "../assets/images/exameple3.png";
import Banner4 from "../assets/images/exameple4.png";
import Banner5 from "../assets/images/exameple5.png";
import Banner6 from "../assets/images/exameple6.png";
import icon1 from "../assets/images/iconExample1.png";
import icon2 from "../assets/images/iconExample2.png";
import icon3 from "../assets/images/iconExample3.png";
import icon4 from "../assets/images/iconExample4.png";
import icon5 from "../assets/images/iconExample5.png";
import icon6 from "../assets/images/iconExample6.png";
export default {
  data() {
    return {
      data: [
        {
          background: Banner1,
          img: icon1,
          text_1: "최적화된",
          text_2: "UI/UX",
        },
        {
          background: Banner2,
          img: icon2,
          text_1: "안전한",
          text_2: "데이터 저장",
        },
        {
          background: Banner3,
          img: icon3,
          text_1: "자동완성",
          text_2: "기능",
        },
        {
          background: Banner4,
          img: icon4,
          text_1: "AI",
          text_2: "어시스턴트",
        },
        {
          background: Banner5,
          img: icon5,
          text_1: "빅데이터",
          text_2: "데이터베이스",
        },
        {
          background: Banner6,
          img: icon6,
          text_1: "읽기 편한",
          text_2: "결과물",
        },
      ],
    };
  },
  components: {},
};
</script>
