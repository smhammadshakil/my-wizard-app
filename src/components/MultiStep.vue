<template>
  <div class="hello">
    <WelcomePage :next="next" v-if="page === 1" />
    <StepOne :next="next" :saveInfo="saveInfo" v-if="page === 2" />
    <StepTwo :next="next" :info="info" v-if="page === 3" />
    <ErrorPage :next="next" v-if="page === 4" />
  </div>
</template>

<script>
import WelcomePage from "./WelcomePage.vue";
import StepOne from "./StepOne.vue";
import StepTwo from "./StepTwo.vue";
import ErrorPage from "./ErrorPage.vue";

export default {
  name: "MultiStep",
  components: {
    WelcomePage,
    StepOne,
    StepTwo,
    ErrorPage,
  },
  data() {
    return {
      page: 1,
      info: {},
    };
  },
  methods: {
    next(count) {
      let self = this;
      self.page = self.page + count;
    },
    saveInfo(info) {
      let self = this;
      self.info = info;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  width: 500px;
  margin: 0 auto;
}
</style>
