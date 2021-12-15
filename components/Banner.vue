<template>
  <div class="hompage-baner">
    <div
      class="radio-btns__btn hompage-baner__left"
      v-bind:style="{ backgroundImage: 'url(' + banner1 + ')' }"
    >
      <div class="containe">
        <div class="containe__img">
          <img
            src="../assets/images/draft.png"
            alt="../assets/images/draft.png"
          />
        </div>
        <div class="containe__text">
          <p>더 쉽고 빠르게, 더 높은 품질로!</p>
          <p>특허 명세서 작성 전용 에디터</p>
        </div>
        <a class="button btn btn-banner" style="color: #5c6bc0">
          특허 명세서 작성하러 가기
        </a>
      </div>
    </div>

    <div
      class="radio-btns__btn hompage-baner__right"
      v-bind:style="{ backgroundImage: 'url(' + banner2 + ')' }"
    >
      <div class="containe">
        <div class="containe__img">
          <img
            src="../assets/images/translate.png"
            alt="../assets/images/translate.png"
          />
        </div>
        <div class="containe__text">
          <p>번역에 필요한 모든 고민은 IPEDIT가 대신 해드리겠습니다.</p>
          <p>특허 명세서 번역 전용 에디터</p>
        </div>
        <a class="button btn btn-banner" style="color: #8d6e63">
          특허 명세서 번역하러 가기
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
export default {
  data() {
    return {
      banner1: Banner1,
      banner2: Banner2,
    };
  },
  components: {},
};
</script>
