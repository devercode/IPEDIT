<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img src="../assets/images/ipedit.png" width="112" height="28" />
      </a>

      <a
        role="button"
        class="navbar-burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="navbarBasicExample"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link"> Products </a>
          <div class="navbar-dropdown dropdown-products">
            <a class="navbar-item">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
            <a class="navbar-item">
              <p>IPEDIT draft</p>
              <p>
                더 쉽고 빠르게, 더 높은 품질로!<br />
                특허 명세서 작성 전용 에디터
              </p>
            </a>
          </div>
        </div>

        <a class="navbar-item"> Impact </a>
        <a class="navbar-item"> Stats </a>
        <a class="navbar-item"> Why IPEDIT? </a>
        <a class="navbar-item"> Contact us </a>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <div class="navbar-item has-dropdown is-hoverable">
              <a class="navbar-link"> 한국어 </a>
              <div class="navbar-dropdown">
                <a class="navbar-item">
                  <p>English</p>
                </a>
                <a class="navbar-item">
                  <p>日本語</p>
                </a>
              </div>
            </div>
            <a class="navbar-item"> 로그인 </a>
            <a class="button btn"> 시작하기 </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/header.scss";
</style>

<script>
export default {
  data() {
    return {};
  },
  components: {},
};
</script>
