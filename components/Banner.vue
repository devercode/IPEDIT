<template>
  <div class="hompage-baner">
    <div
      class="radio-btns__btn"
      v-for="(item, index) in arrData"
      :key="index"
      v-bind:style="{ backgroundImage: 'url(' + item.background + ')' }"
      :class="item.class"
    >
      <div class="containe">
        <div class="containe__img">
          <img :src="item.img" :alt="item.img" />
        </div>
        <div class="containe__text">
          <p>{{ item.title }}</p>
          <p>{{ item.description }}</p>
        </div>
        <a class="button btn btn-banner" :style="item.color">
          {{ item.btn }}
        </a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/banner.scss";
</style>

<script>
import Banner1 from "../assets/images/baner1.png";
import Banner2 from "../assets/images/baner2.png";
import Draft from "../assets/images/draft.png";
import Translate from "../assets/images/translate.png";
export default {
  data() {
    return {
      banner1: Banner1,
      banner2: Banner2,
      arrData: [
        {
          background: Banner1,
          img: Draft,
          title: "더 쉽고 빠르게, 더 높은 품질로!",
          description: "특허 명세서 작성 전용 에디터",
          btn: "특허 명세서 작성하러 가기",
          color: "color: #5c6bc0",
          class: "hompage-baner__left",
        },
        {
          background: Banner2,
          img: Translate,
          title: "번역에 필요한 모든 고민은 IPEDIT가 대신 해드리겠습니다.",
          description: "특허 명세서 번역 전용 에디터",
          btn: "특허 명세서 번역하러 가기",
          color: "color: #8d6e63",
          class: "hompage-baner__right",
        },
      ],
    };
  },
  components: {},
};
</script>
