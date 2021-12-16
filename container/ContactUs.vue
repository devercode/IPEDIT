<template>
  <div
    class="modal contact-us"
    id="modal"
    v-bind:class="{ 'is-active': isContact }"
  >
    <!-- <div class="modal-background" v-on:click="closeContact"></div> -->
    <div class="modal-content" style="padding: 30px">
      <button
        class="modal-close is-large"
        aria-label="close"
        v-on:click="closeContact"
      ></button>
      <h1 class="contact__text">Contact us</h1>
      <!-- Input username -->
      <div class="field">
        <Input
          fatherClass="control"
          className="input"
          type="text"
          name="nameContact"
          placeHolder="이름*"
        />
      </div>

      <div class="field">
        <Input
          fatherClass="control"
          className="input"
          type="text"
          name="company"
          placeHolder="회사명"
        />
      </div>

      <div class="field">
        <Input
          fatherClass="control"
          className="input"
          type="text"
          name="emailContact"
          placeHolder="이메일 주소*"
        />
      </div>

      <div class="field">
        <Input
          fatherClass="control"
          className="input"
          type="text"
          name="phoneContact"
          placeHolder="휴대폰 번호"
        />
      </div>

      <!-- Select country -->
      <div class="select-country">
        <div
          class="navbar-item has-dropdown field"
          style="width: 100%; margin-bottom: 10px"
          v-on:click="activeCountry = !activeCountry"
          v-bind:class="{ 'is-active': activeCountry }"
        >
          <a class="navbar-link">
            <img
              v-bind:style="[
                country === '' ? { display: 'none' } : { display: 'block' },
              ]"
              src="../assets/images/Korea.svg"
            />
            {{ country.dial_code }}
          </a>
          <div
            class="navbar-dropdown"
            style="background: #fff"
            :style="[!activeCountry && { display: 'none' }]"
          >
            <a
              class="navbar-item item__country"
              v-for="item in countries"
              :key="item"
              v-on:click="selectCountry(item)"
            >
              <img src="../assets/images/Korea.svg" />
              <span class="nameCountry">{{ item.name }}</span>
              <span class="dial_code">{{ item.dial_code }}</span>
            </a>
          </div>
        </div>
      </div>

      <div class="field">
        <Input
          fatherClass="control"
          className="input"
          type="text"
          name="phoneContact"
          placeHolder="내용*"
          style="height: 160px"
        />
      </div>

      <!-- login with Email -->
      <Button
        text="보내기"
        :disabled="true"
        style="width: 69px; height: 36px; float: right"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/signUp.scss";
</style>

<script>
import { Country } from "../assets/javascripts/data";
import Input from "../components/Inputs.vue";

export default {
  data() {
    return {
      countries: Country,
      country: "",
      activeCountry: false,
    };
  },
  props: {
    isContact: Boolean,
  },
  components: { Input },
  methods: {
    closeContact: function () {
      this.$emit("closeContact");
    },
  },
  selectCountry: function (item) {
    this.country = item;
  },
  created() {
    document.onkeydown = (evt) => {
      evt = evt || window.event;
      if (evt.keyCode == 27) {
        this.$emit("closeContact");
      }
    };
  },
};
</script>
