<template>
  <div class="impactory">
    <div class="impactory__container container">
      <div
        class="video"
        v-bind:style="{ backgroundImage: 'url(' + videoArea + ')' }"
      >
        <div class="video-img" v-on:click="modalVideo = !modalVideo">
          <img
            src="../assets/images/playcircle.png"
            alt="../assets/images/playcircle.png"
          />
        </div>
      </div>

      <!-- modal video -->
      <div class="modal" v-bind:class="{ 'is-active': modalVideo }">
        <div class="modal-background"></div>
        <div class="modal-content">
          <iframe
            width="420"
            height="315"
            src="https://www.youtube.com/embed/tgbNymZ7vqY"
          >
          </iframe>
        </div>
        <button
          class="modal-close is-large"
          aria-label="close"
          v-on:click="modalVideo = false"
        ></button>
      </div>

      <div class="box-containe">
        <div class="module" style="padding: 38px 60px">
          <div class="top">
            <!-- left -->
            <div class="left">
              <div class="left__top">
                <p>1페이지 기준</p>
                <h3>5분</h3>
              </div>
              <div class="left__bottom">MS Word</div>
            </div>
            <!-- rignht -->
            <div class="right">
              <div class="percent">
                <h1>60%</h1>
                <h2>빠르게!</h2>
              </div>
              <div class="minutes">
                <div class="minutes__top">
                  <p>1페이지 기준</p>
                  <h2>2분</h2>
                </div>
                <div class="minutes__bottom">IPEDIT</div>
              </div>
            </div>
          </div>
          <div
            class="bottom"
            v-bind:style="{ backgroundImage: 'url(' + highlight + ')' }"
          >
            작업 시간
          </div>
        </div>

        <div class="module" style="padding: 38px 30px">
          <div class="top top-module_2">
            <h1>NO</h1>
            <h2>청구항 인용 오류</h2>
          </div>
          <div
            class="bottom"
            v-bind:style="{ backgroundImage: 'url(' + highlight + ')' }"
          >
            품질
          </div>
        </div>

        <div class="module" style="padding: 38px 30px">
          <div class="top top-module_3">
            <div class="top-img">
              <img
                src="../assets/images/Korea.png"
                alt="../assets/images/Korea.png"
              />
            </div>
            <div class="top-img">
              <img
                src="../assets/images/USA.png"
                alt="../assets/images/USA.png"
              />
            </div>
            <div class="top-img">
              <img
                src="../assets/images/frame.png"
                alt="../assets/images/frame.png"
              />
            </div>
            <div class="top-img">
              <img
                src="../assets/images/Japan.png"
                alt="../assets/images/Japan.png"
              />
            </div>
          </div>
          <div
            class="bottom"
            v-bind:style="{ backgroundImage: 'url(' + highlight + ')' }"
          >
            사용 국가
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/impactory.scss";
</style>

<script>
import VideoArea from "../assets/images/VideoArea.png";
import Rectangle3 from "../assets/images/Rectangle 3.png";
import Rectangle6 from "../assets/images/Rectangle 6.png";
import Highlight from "../assets/images/img_highlight_1.png";
export default {
  data() {
    return {
      videoArea: VideoArea,
      rectangle3: Rectangle3,
      rectangle6: Rectangle6,
      highlight: Highlight,
      modalVideo: false,
    };
  },
  components: {},
};
</script>
