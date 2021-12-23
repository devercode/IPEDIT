<template>
  <div
    class="modal contact-us"
    id="modal"
    v-bind:class="{ 'is-active': isContact }"
  >
    <div class="modal-background"></div>
    <div class="modal-content modal-contact">
      <button
        class="modal-close is-large"
        aria-label="close"
        v-on:click="closeContact"
      ></button>
      <h1 class="contact__text">Contact us</h1>
      <!-- Input username -->
      <Input
        fatherClass="control"
        className="input"
        type="text"
        name="nameContact"
        placeHolder="이름*"
      />

      <Input
        fatherClass="control"
        className="input"
        type="text"
        name="company"
        placeHolder="회사명"
      />

      <Input
        fatherClass="control"
        className="input"
        type="text"
        name="emailContact"
        placeHolder="이메일 주소*"
      />

      <Input
        fatherClass="control"
        className="input"
        type="text"
        name="phoneContact"
        placeHolder="휴대폰 번호"
      />

      <!-- Select country -->

      <div class="select-country">
        <div
          class="navbar-item has-dropdown field select-country__mobile"
          style="width: 100%; margin-bottom: 10px"
          v-on:click="activeCountry = !activeCountry"
          v-bind:class="{ 'is-active': activeCountry }"
        >
          <a
            class="navbar-link select__cout"
            v-bind:class="{ selected__cout: countryText !== '' }"
            style="border-color: #5c6bc0 !important"
            :style="[
              countryText === ''
                ? { color: '#7C7F90', paddingLeft: '10px' }
                : { color: '#212037', paddingLeft: '10px' },
            ]"
          >
            <img
              v-bind:style="[
                countryText === ''
                  ? { display: 'none', marginRight: '10px' }
                  : { display: 'block', marginRight: '10px' },
              ]"
              :src="countryText.img"
            />
            {{ countryText === "" ? "국가 선택" : countryText.name }}
          </a>
          <div
            class="navbar-dropdown"
            style="background: #fff; width: 280px"
            :style="[!activeCountry && { display: 'none' }]"
          >
            <a
              class="navbar-item item__country"
              v-for="item in countries"
              :key="item"
              v-on:click="selectCountry(item)"
            >
              <img :src="item.img" />
              <span class="nameCountry">{{ item.name }}</span>
            </a>
          </div>
        </div>
      </div>

      <div class="omrs-input-group">
        <label class="omrs-input-filled">
          <textarea
            class="input"
            required
            name="note"
            placeHolder="내용*"
            style="height: 160px; color: #000; font-size: 14px"
            v-on:change="handleChange"
          />
        </label>
      </div>

      <!-- login with Email -->
      <Button text="보내기" :disabled="true" class="btn-contact" />
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
      countryText: "",
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
    selectCountry: function (item) {
      this.countryText = item;
    },
  },
  created() {
    if (typeof window !== "undefined") {
      window.addEventListener("keydown", (evt) => {
        evt = evt || window.event;
        if (evt.keyCode == 27) {
          this.$emit("closeContact");
        }
      });
    }
  },
};
</script>
