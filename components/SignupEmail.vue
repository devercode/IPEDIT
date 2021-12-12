<template>
  <div class="modal is-active">
    <div class="modal-background"></div>
    <div class="modal-content">
      <div class="logo">
        <img
          src="../assets/images/ipedit.png"
          alt="../assets/images/ipedit.png"
        />
      </div>

      <p class="signup-title">회원가입</p>

      <div class="services">
        <h3>서비스 및 유형 <span>*</span></h3>
        <p>
          어머니 이름을 까닭이요, 계집애들의 봅니다. 별 피어나듯이 그리워
          이름과.
        </p>
      </div>

      <!-- tabs -->
      <div class="tabs-containe">
        <ul>
          <li class="" v-on:click="ShowTabContent(1)">
            <img
              src="../assets/images/draft-black.png"
              alt="../assets/images/draft.png"
            />
          </li>
          <li class="img-child2" v-on:click="ShowTabContent(2)">
            <img
              src="../assets/images/translate.png"
              alt="../assets/images/translate.png"
            />
          </li>
        </ul>
      </div>
      <!-- tabs content -->
      <div class="px-2" id="tab-content">
        <!-- content 1 -->
        <div id="product-details" class="content-data" v-if="idTabs === 1">
          <!-- Type of application -->
          <div class="field">
            <div class="control">
              <div class="select">
                <select>
                  <option>명세서 유형</option>
                  <option>With options</option>
                </select>
              </div>
            </div>
          </div>

          <div class="services">
            <h3>서비스 및 유형 <span>*</span></h3>
          </div>
          <!-- name -->
          <div class="field">
            <div class="control">
              <input class="input" type="text" placeholder="이름" />
            </div>
          </div>

          <!-- email -->
          <div class="field field-doubles">
            <div class="control has-icons-left has-icons-right">
              <input
                class="input is-success"
                type="text"
                placeholder="이메일 주소"
                value="이메일 주소"
              />
            </div>
            <div class="control control-button">
              <button class="button is-link is-light">인증코드 발송</button>
            </div>
          </div>

          <!--verify email -->
          <div class="field field-doubles">
            <div class="control has-icons-left has-icons-right">
              <input
                class="input is-success"
                type="text"
                placeholder="이메일 인증코드"
                value="이메일 인증코드"
              />
            </div>
            <div class="control control-button">
              <button class="button is-link is-light">인증하기</button>
            </div>
          </div>

          <!-- password -->
          <div class="field">
            <div class="control">
              <input class="input" type="text" placeholder="비밀번호" />
            </div>
          </div>

          <!-- password confirm-->
          <div class="field">
            <div class="control">
              <input class="input" type="text" placeholder="비밀번호 재입력" />
            </div>
          </div>

          <!-- COUNTRY -->
          <div class="services">
            <h3>휴대폰 인증 <span>*</span></h3>
          </div>
          <!-- Select country -->
          <div class="select-country">
            <div class="field">
              <div class="control">
                <div class="select">
                  <select>
                    <option v-for="item in countries" :key="item">
                      <span>{{ item.name }}</span>
                      <span>{{ item.dial_code }}</span>
                    </option>
                    <option>With options</option>
                  </select>
                </div>
              </div>
            </div>
            <!-- Phone -->
            <div class="field field-doubles">
              <div class="control">
                <input class="input" type="text" placeholder="휴대폰 번호" />
              </div>
              <div class="control control-button">
                <button class="button is-link is-light">인증코드 발송</button>
              </div>
            </div>
          </div>

          <!-- Phone Code-->
          <div class="field field-doubles">
            <div class="control">
              <input class="input" type="text" placeholder="휴대폰 인증코드" />
            </div>
            <div class="control control-button">
              <button class="button is-link is-light">인증하기</button>
            </div>
          </div>

          <!-- Promotion code -->
          <div class="services">
            <h3>프로모션 코드</h3>
          </div>

          <!-- apply Code-->
          <div class="field field-doubles">
            <div class="control">
              <input class="input" type="text" placeholder="프로모션 코드" />
            </div>
            <div class="control control-button">
              <button class="button is-link is-light">적용하기</button>
            </div>
          </div>

          <div class="services">
            <p>
              회원가입 시 IPEDIT의 이용약관과 개인정보처리방침에 동의하게
              됩니다.
            </p>
          </div>

          <!-- button submit -->
          <div class="field is-grouped">
            <div class="control btn-submit">
              <button class="button is-link">가입하기</button>
            </div>
          </div>
        </div>

        <!-- content 2 -->
        <div
          id="delivery-informations"
          class="content-data"
          v-if="idTabs === 2"
        >
          <h3 class="is-size-5 title">Delivery informations</h3>
          <p>delivery</p>
        </div>
      </div>
    </div>
    <button
      class="modal-close is-large"
      aria-label="close"
      v-on:click="changeModalSignUp"
    ></button>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/signUp.scss";
</style>

<script>
import { Country } from "../assets/javascripts/data";
export default {
  data() {
    return {
      idTabs: 1,
      countries: Country,
    };
  },
  props: {
    modalLogin: Boolean,
  },
  components: {},
  methods: {
    ShowTabContent: function (data) {
      this.idTabs = data;
    },
    changeModalSignUp: function () {
      this.$emit("changeModalSignUp");
    },
  },
  beforeUpdate() {
    const tabs = document.querySelectorAll(".tab li");
    const tableContentBoxs = document.querySelectorAll("#tab-content > div");

    tabs.forEach((tab) => {
      tab.addEventListener("click", () => {
        tabs.forEach((item) => item.classList.remove("is-active"));
        tab.classList.add("is-active");

        const target = tab.dataset.target;
      });
    });
  },
};
</script>
