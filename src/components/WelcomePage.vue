<template>
  <div class="wizard-box">
    <h1>Hello There!</h1>
    <h4>
      Let's buy some insurance. <br />It is going to take only a few steps
    </h4>
    <button class="action-button" @click="next(1)">Start</button>
  </div>
</template>

<script>
export default {
  name: "WelcomePage",
  props: {
    next: Function,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
