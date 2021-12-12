<template>
  <div class="term">
    <div class="term__container container">
      <h1>{{ title }}</h1>
      <!-- select -->
      <div class="field">
        <div class="control">
          <div class="select">
            <select>
              <option v-for="item in arrSelect" :key="item">{{ item }}</option>
            </select>
          </div>
        </div>
      </div>

      <!-- cotaine 1 -->
      <div class="rule-containe">
        <h3>{{ rule1 }}</h3>
        <p>
          {{ content1 }}
        </p>
      </div>

      <!-- cotaine 2 -->
      <div class="rule-containe">
        <h3>{{ rule2 }}</h3>
        <p>
          {{ content2 }}
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/stylesheets/term.scss";
</style>

<script>
export default {
  data() {
    return {};
  },
  props: {
    title: String,
    arrSelect: Array,
    rule1: String,
    content1: String,
    rule2: String,
    content2: String,
  },
  components: {},
};
</script>
