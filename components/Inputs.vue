<template>
  <div class="omrs-input-group">
    <label class="omrs-input-filled">
      <input
        class="input"
        required
        :name="name"
        :style="[!checkConditional() && { borderColor: '#d2416d' }]"
        :type="type"
        v-model="vModel"
        v-on:change="handleChange"
      />

      <span class="omrs-input-label">{{ placeHolder }}</span>
      <!-- <span class="omrs-input-helper">에러메세지는 여기에</span> -->
    </label>
    <div
      class="control control-button"
      :style="[!buttonRequire ? { display: 'none' } : { display: 'block' }]"
    >
      <button
        :style="[
          vModel !== '' && {
            background: '#5C6BC0',
            color: '#fff',
          },
        ]"
        class="button"
      >
        {{ buttonRequire }}
      </button>
    </div>
  </div>
  <!-- Input username -->
  <!-- <div class="field"> -->
  <!-- <div :class="fatherClass">
    <input
      :class="className"
      :type="type"
      :placeholder="placeHolder"
      :name="name"
      :style="[!checkConditional() && { borderColor: '#d2416d' }]"
      v-model="vModel"
      v-on:change="handleChange"
    />
    <p
      style="color: #d2416d; font-size: 10px; padding-top: 5px"
      v-if="!checkConditional()"
    >
      {{ errorText }}
    </p>

    <div
      class="control control-button"
      :style="[!buttonRequire ? { display: 'none' } : { display: 'block' }]"
    >
      <button
        class="button is-link is-light"
        :style="[
          vModel !== '' && {
            background: '#5C6BC0',
            color: '#fff',
          },
        ]"
      >
        {{ buttonRequire }}
      </button>
    </div>
  </div> -->

  <!-- </div> -->
</template>

<style lang="scss" scoped>
// @import "../assets/stylesheets/login.scss";
@import "../assets/stylesheets/signUp.scss";
</style>

<script>
export default {
  data() {
    return {
      tempPassword: "",
    };
  },
  props: {
    fatherClass: String,
    className: String,
    type: String,
    placeHolder: String,
    name: String,
    vModel: String,
    Style: String,
    errorText: String,
    buttonRequire: String,
    oldPass: String,
  },
  components: {},
  methods: {
    handleChange: function (e) {
      this.$emit("handleChange", e);
    },
    checkConditional: function () {
      if (this.name === "password") {
        if (this.vModel.split("").length >= 8) {
          return true;
        }
      } else if (this.name === "confirmPassword") {
        if (this.vModel === this.oldPass) {
          console.log(this.oldPass);
          return true;
        }
      } else {
        if (this.vModel !== "") {
          return true;
        }
      }
    },
  },
};
</script>
