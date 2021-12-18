<template>
  <div class="footer">
    <div class="footer__container container">
      <div class="content">
        <div class="logo-footer">
          <img :src="logo" />
        </div>
        <ul>
          <li><a> IPEDIT draft</a></li>
          <li><a>IPEDIT translate</a></li>
          <li><a href="https://ipactory.com">회사소개</a></li>
          <li><a href="/term">이용약관</a></li>
          <li><a href="/privacy">개인정보이용방침</a></li>
        </ul>
      </div>
      <div class="information">
        (주)아이팩토리 | 대표자: 유장현 | 사업자번호: 123-12-12345 |
        통신판매업번호: 123123123 | 서울특별시 서초구 논현로 175 신한빌딩 6층 |
        대표번호: 02-6954-7657 | 이메일 admin@ipactory.com | 개인정보책임자: 000
      </div>
      <div class="years">© 2019 — 2020 IPACTORY. All Rights Reserved</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/footer.scss";
</style>

<script>
import Logo from "../assets/images/iconFooter.svg";
export default {
  data() {
    return {
      logo: Logo,
    };
  },
  components: {},
};
</script>
